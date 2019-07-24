---
title: Liczba dni z ujemnym stanem i dynamiczna liczba dni z ujemnym stanem.
description: Ten temat zawiera informacje o ujemnych dniach i dynamicznych dniach ujemnych oraz sposobach ich używania aby pomoc twojej firmie.
author: t-benebo
manager: AnnBe
ms.date: 06/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: ''
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff907a624d62b00d2aaf21c185175e8717b6c624
ms.sourcegitcommit: b3d099eb1f9a8a582c02ea6c5ee30c830d53a411
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2019
ms.locfileid: "1628795"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Liczba dni z ujemnym stanem i dynamiczna liczba dni z ujemnym stanem.

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o ujemnych dniach i dynamicznych dniach ujemnych oraz sposobach ich używania aby pomoc twojej firmie. *Horyzont czasowy w dniach ujemnych* reprezentuje liczbę dni, po upływie których użytkownik chce zamówić nowe uzupełnienie zapasów w przypadku ujemnego stanu zapasów.

W tym temacie poznasz następujące informacje:

- Jak są tworzone planowane zamówienia.
- Korelacja między horyzontem czasowym w dniach ujemnych a czasem realizacji towaru
- Sposób obliczania dynamicznego okresu czasu ujemnego i sposobu w jaki czas realizacji towaru jest uwzględniany w obliczeniach
- Sposób interpretacji [sugestii dotyczących poprawiania czasu działania na potrzeby planowania zapotrzebowania materiałowego (MRP) (planowanie główne)](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx), które są związane z dniami ujemnymi

W tym temacie są używane trzy hipotetyczne scenariusze ułatwiające zrozumienie tych informacji. Różnica między scenariuszami to punkt, w którym użytkownik uzyskuje zapotrzebowanie: przed, w trakcie lub po okresie realizacji danego towaru.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Scenariusz 1: przed upływem czasu realizacji towaru uzyskasz zapotrzebowanie

Popyt można uzyskać stosunkowo wcześnie w czasie realizacji danego towaru lub tuż przed rozpoczęciem okresu realizacji. Oto przykład tego scenariusza:

- Towar DemoProduct ma sześciodniowy czas realizacji zakupu.
- W dniu zero (1 stycznia) poziom zapasów dla towaru DemoProduct wynosi 0 (zero).
- W dniu zero (1 stycznia) jest uzyskane zamówienie sprzedaży na ilość 10 sztuk towaru DemoProduct.
- W dniu 7 (7 stycznia) istnieje istniejące zamówienie zakupu na ilość 10 sztuk DemoProduct.

Poniższa ilustracja pokazuje graficzny widok tego scenariusza.

![Widok graficzny scenariusza 1](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Przypadek A: liczba dni ujemnych jest mniejsza niż czas realizacji towaru

Jeśli liczba dni z ujemnym poziomem zapasów jest mniejsza niż czas realizacji towaru, MRP będzie szukać paragonów dla pozycji DemoProduct w ujemnym terminie dni. Ponieważ nie odnaleziono żadnych przyjęć, MRP tworzy nowe planowane zamówienie zakupu. To planowane zamówienie jest natychmiast opóźniane o sześć dni (czas realizacji). Z tego względu przyjdzie 7 stycznia. Istniejące zamówienie zakupu uzyskuje komunikat **Anuluj**, ponieważ utworzenie nowego planowanego zamówienia zakupu sprawiło, że stało się zbędne.

Poniższa ilustracja pokazuje zrzut ekranu tego przypadku.

![Zrzut ekranu dotyczący przypadku A dla scenariusza 1](./media/negative-days-2.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku A dla scenariusza 1](./media/negative-days-3.png)

Jeśli rozważasz wydajność MRP i planujesz nerwowość, ten przypadek nie działa dobrze. MRP musi utworzyć nowe zamówienie planowane i musi być obliczyć opóźnienia i akcje. Zadania te są czasochłonne. W takim przypadku do planu dodawane są dwie kolejne transakcje. Z drugiej strony zamówienie sprzedaży jest opóźnione o zaledwie sześć dni, a nie siedem dni.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Przypadek B: liczba dni ujemnych jest większa niż czas realizacji towaru

Aby zwiększyć wydajność MRP, można określić liczbę dni ujemnych na liczbę większą niż czas realizacji towaru. Ponieważ w tym scenariuszu nie można uzyskać dostawy w czasie realizacji, można szukać przyjęć, dopóki to wyszukiwanie ma sens. Chociaż czas realizacji dla MRP będzie krótszy, należy uważać na dodatkowe opóźnienia w realizacji zamówień.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Przypadek C: Automatyczna korelacja między horyzontem czasowym w dniach ujemnych a czasem realizacji towaru

Aby automatycznie skorelować czas realizacji towaru z horyzontem czasowym w dniach ujemnych, użyj dynamicznych dni ujemnych. Aby skorzystać z dynamicznych dni ujemnych, przejdź do **Planowanie główne \> Parametry \> Główne parametry planowania**, a następnie na karcie **Ogólne**, w sekcji **Zapotrzebowanie**, ustaw opcję **Użyj dynamicznych dni ujemnych** na **Tak**. Następnie program MRP wyszukuje przychody w ramach dynamicznego okresu ujemnego. To granica czasowa jest obliczana przy użyciu następującej formuły:

Dynamiczny okres z ujemnymi dniami = czas realizacji zakupu + horyzont czasowy dni ujemnych + (data bieżąca — data zapotrzebowania)

(Jeśli domyślnym typem zamówienia towaru DemoProduct jest **Produkcja** lub **Przeniesienie**, czas realizacji jest czasem realizacji **zapasów**.)

Gdy używane są dynamiczne dni ujemne, horyzont czasowy, w którym MRP szuka odbiorów, wynosi teraz 6 + 2 + 0 = 8 dni. MRP znajduje istniejące zamówienie zakupu i przypisuje do niego zamówienie sprzedaży. Nie są tworzone żadne nowe zamówienia planowane. Dlatego czas pracy MRP jest krótszy. Na poniższej ilustracji przedstawiono wymagania netto dla towaru DemoProduct.

![Wymagania netto przypadku C dla scenariusza 1](./media/negative-days-4.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku C dla scenariusza 1](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Przypadek D: użyj tylko dynamicznych dni ujemnych

Jeśli wartość dni ujemnych jest ustawiona na **0** (zero) i zostanie użyty tylko dynamiczny horyzont czasowy w liczbie dni ujemnych, to dynamiczny horyzont czasowy w dniach ujemnych wynosi 6 + 0 + 0 = 6 dni. W tym przypadku wynik jest taki sam, jak wynik w przypadku A dla tego scenariusza. MRP musi utworzyć nowe zamówienie planowane i musi być obliczyć opóźnienia i akcje. Zadania te są czasochłonne i mogą być także frustrujące. Istnieją także dwie dalsze transakcje do przetworzenia. Ponieważ popyt nie może być zrealizowany na czas na dostarczenie towaru, ten przypadek dodaje niepotrzebne komplikacje do planu.

Poniższa ilustracja przedstawia zrzut ekranu dla tego przypadku.

![Zrzut ekranu dotyczący przypadku D dla scenariusza 1](./media/negative-days-6.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku D dla scenariusza 1](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Przypadek E: należy stosować obydwa dni ujemne, które są większe niż czas realizacji towaru oraz dynamiczny horyzont czasowy w dniach ujemnych

Jeśli liczba dni ujemnych zostanie ustawiona na liczbę większą niż czas realizacji towaru, a także ten przypadek korzysta z dynamicznego horyzontu czasowego dni ujemnych, to dynamiczny horyzont czasowy w dniach ujemnych wynosi 6 + 6 + 0 = 12 dni. Takie podejście może wytworzyć bardzo długi horyzont czasowy, w którym MRP musi wyszukiwać wyników w programie. Aby uzyskać informacje o tym, jak przypadek E jest związany z sytuacją, w której negatywne dni ustawia się na długi horyzont czasowy, zapoznaj się z [Podsumowanie](#conclusion) sekcją tego tematu.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Scenariusz 2: podczas czasu realizacji towaru uzyskasz zapotrzebowanie

Istnieje możliwość uzyskania popytu w czasie realizacji danego towaru. Oto przykład tego scenariusza:

- Towar DemoProduct ma sześciodniowy czas realizacji zakupu. 
- W dniu zero (1 stycznia) poziom zapasów dla towaru DemoProduct wynosi 0 (zero).
- W dniu 4 (5 stycznia), który znajduje się w czasie realizacji towaru, zamówienie sprzedaży zostanie zrealizowane na ilość 10 sztuk towaru DemoProduct.
- W dniu 7 (8 stycznia) istnieje zamówienie zakupu na ilość 10 sztuk DemoProduct.

Poniższa ilustracja pokazuje graficzny widok tego scenariusza.

![Widok graficzny scenariusza 1](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Przypadek A: liczba dni ujemnych jest mniejsza niż czas realizacji towaru

Jeśli liczba dni z ujemnym poziomem zapasów jest mniejsza niż czas realizacji towaru, MRP będzie szukać paragonów dla pozycji DemoProduct w ujemnym terminie dni. Ponieważ nie znaleziono żadnych przychodów, MRP tworzy nowe planowane zamówienie zakupu, które wykorzystuje bieżącą datę jako datę zamówienia. To planowane zamówienie jest natychmiast opóźniane o sześć dni (czas realizacji). Z tego względu przyjdzie 7 stycznia. Istniejące zamówienie zakupu uzyskuje komunikat **Anuluj**, ponieważ utworzenie nowego planowanego zamówienia zakupu sprawiło, że stało się zbędne.

Poniższa ilustracja przedstawia zrzut ekranu dla tego przypadku.

![Zrzut ekranu dotyczący przypadku A dla scenariusza 2](./media/negative-days-9.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku A dla scenariusza 2](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Przypadek B: liczba dni ujemnych jest większa niż czas realizacji towaru

Przypadek ten przypomina przypadek B dla scenariusza 1. Jeśli ustawiono ujemne dni na liczbę większą niż czas realizacji towaru, nie otrzymamy nowego zamówienia planowanego. Zamówienie sprzedaży jest dołączone do istniejącego zamówienia zakupu.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Przypadek C: Automatyczna korelacja między horyzontem czasowym w dniach ujemnych a czasem realizacji towaru

Ten przypadek przypomina przypadek C dla scenariusza 1, ponieważ dynamiczne dni ujemne działają równie dobrze jak w tym przypadku. Dynamiczny horyzont czasowy w dniach ujemnych wynosi teraz 6 + 2 — 4 = 4 dni. W przypadku zastosowania tego podejścia MRP wyszukuje istniejące zamówienie zakupu i dołącza do niego zamówienie sprzedaży. Ponieważ nie są tworzone żadne nowe zamówienia planowane, czas pracy MRP jest krótszy.

Poniższa ilustracja pokazuje zrzut ekranu tego przypadku.

![Zrzut ekranu dotyczący przypadku C dla scenariusza 2](./media/negative-days-11.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku C dla scenariusza 2](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Przypadek D: użyj tylko dynamicznych dni ujemnych

Jeśli wartość dni ujemnych jest ustawiona na **0** (zero) i zostanie użyty tylko dynamiczny horyzont czasowy w liczbie dni ujemnych, to dynamiczny horyzont czasowy w dniach ujemnych wynosi teraz 6 + 0 - 4 = 2 dni. W tym przypadku wynik jest taki sam, jak wynik w przypadku A dla tego scenariusza. Aby zapoznać się z graficznym widokiem tego zdarzenia, zobacz przypadek A w tym scenariuszu.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Przypadek E: należy stosować obydwa dni ujemne, które są większe niż czas realizacji towaru oraz dynamiczny horyzont czasowy w dniach ujemnych

Jeśli liczba dni ujemnych zostanie ustawiona na liczbę większą niż czas realizacji towaru, a także ten przypadek korzysta z dynamicznego horyzontu czasowego dni ujemnych, to dynamiczny horyzont czasowy w dniach ujemnych wynosi 6 + 6 - 4 = 8 dni. Takie podejście może wytworzyć bardzo długi horyzont czasowy, w którym MRP musi wyszukiwać wyników w programie. Aby uzyskać informacje o tym, jak przypadek E jest związany z sytuacją, w której negatywne dni ustawia się na długi horyzont czasowy, zapoznaj się z [Podsumowanie](#conclusion) sekcją tego tematu.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Scenariusz 3: po czasie realizacji towaru uzyskasz zapotrzebowanie

Scenariusz 3: po czasie realizacji towaru uzyskasz zapotrzebowanie Oto przykład tego scenariusza:

- Towar DemoProduct ma sześciodniowy czas realizacji zakupu.
- W dniu zero (1 stycznia) zapas dla towaru DemoProduct wynosi 0 (zero).
- W dniu 7 (8 stycznia), który znajduje się w poza czasem realizacji towaru, zamówienie sprzedaży zostanie otrzymane na ilość 10 sztuk towaru DemoProduct.
- W dniu 10 (11 stycznia) istnieje zamówienie zakupu na ilość 10 sztuk DemoProduct.

Poniższa ilustracja pokazuje graficzny widok tego scenariusza.

![Widok graficzny scenariusza 3](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Przypadek A: liczba dni ujemnych jest mniejsza niż czas realizacji towaru

Jeśli liczba dni ujemnych jest ustawiona tak, że jest mniejsza niż czas realizacji towaru, MRP będzie wyglądało dwa dni przed datą zapotrzebowania na zamówienie sprzedaży. Ponieważ nie odnaleziono żadnych przyjęć, MRP tworzy nowe planowane zamówienie zakupu 2 stycznia. Ta planowane zamówienie zakupu zostanie wysłane w czasie, aby zrealizować zapotrzebowanie zamówienia sprzedaży. Istniejące zamówienie zakupu otrzymuje komunikat **Anuluj**, ponieważ nie jest on wymagany.

Poniższa ilustracja pokazuje zrzut ekranu tego przypadku.

![Zrzut ekranu dotyczący przypadku A dla scenariusza 3](./media/negative-days-14.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku A dla scenariusza 3](./media/negative-days-15.png)

> [!NOTE]
> W poprzednim zrzucie ekranu data zapotrzebowania zamówienia zakupu wynosi 12 stycznia. Ponieważ ten zrzut został pobrany w 2015, kiedy 11 stycznia była niedziela, MRP przeniosło datę zapotrzebowania na następny dzień roboczy, który był w poniedziałek, 12 stycznia. Niemniej jednak zamówienie zakupu ma datę dostawy 11 stycznia.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Przypadek B: liczba dni ujemnych jest większa niż czas realizacji towaru

Jeśli ustawiono ujemne dni na liczbę większą niż czas realizacji towaru, nie otrzymamy nowego zamówienia planowanego. Zamówienie sprzedaży jest powiązane z istniejącym zamówieniem zakupu. Dlatego zamówienie sprzedaży jest opóźnione. W przypadku utworzenia zamówienia planowanego można wysłać zamówienie sprzedaży na czas.

Poniższa ilustracja pokazuje zrzut ekranu tego przypadku.

![Zrzut ekranu dotyczący przypadku B dla scenariusza 3](./media/negative-days-16.png)

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku B dla scenariusza 3](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Przypadek C: Automatyczna korelacja między horyzontem czasowym w dniach ujemnych a czasem realizacji towaru

Ten przypadek przypomina przypadek C dla scenariusza 1, ponieważ dynamiczne dni ujemne działają równie dobrze, jeśli nie lepiej niż w przypadku B dla tego scenariusza.

Dynamiczny horyzont czasowy w dniach ujemnych wynosi teraz 6 + 2 — 7 = 1 dzień. Jednak w tym przypadku system nadal bierze pod uwagę ujemne dni realizacji (2), ponieważ MRP uwzględnia maksymalną wartość z przedziału czasowego dni ujemnych i dynamicznych ujemnych dni realizacji. Dlatego wynik w tym przypadku jest taki sam jak wynik w przypadku A dla tego scenariusza.

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się w tym przypadku.

![Graficzny widok przypadku C dla scenariusza 3](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Przypadek D: użyj tylko dynamicznych dni ujemnych

Jeśli wartość dni ujemnych jest ustawiona na **0** (zero) i zostanie użyty tylko dynamiczny horyzont czasowy w liczbie dni ujemnych, to dynamiczny horyzont czasowy w dniach ujemnych wynosi teraz 6 + 0 - 7 = -1 dzień. W takim przypadku system nadal uwzględnia dni ujemne realizacji (2). Dlatego wynik w tym przypadku jest taki sam jak wynik w przypadku A dla tego scenariusza i ma wszystkie te same wady. Aby zapoznać się z graficznym widokiem tego zdarzenia, zobacz przypadek A w scenariuszu 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Przypadek E: należy stosować obydwa dni ujemne, które są większe niż czas realizacji towaru oraz dynamiczny horyzont czasowy w dniach ujemnych

Ten przypadek jest taki sam jak przypadek E dla scenariuszy 1 i 2. Ma zasadniczo takie same zalety i wady.

## <a name="conclusion"></a>Wniosek

Jak pokazują trzy scenariusze w tym temacie, dobrze jest określić liczbę dni ujemnych do liczby, która jest większa niż czas realizacji towarów w grupie zapotrzebowania. Warto również stosować tylko dynamiczne dni ujemne, a także ustawiać liczbę dni ujemnych na liczbę dni, które mogą oczekiwać przed zaksięgowaniem nowego uzupełnienia w przypadku ujemnego stanu zapasów (innymi słowy, liczbę dni, w których jesteś gotów dalej opóźniać popyt). Ponadto towary w tej samej grupie zapotrzebowania powinny mieć podobny czas realizacji.

Jeśli wartość w polu liczby dni ujemnych wynosi **0** (zero) i nie zostanie użyta dynamiczna ujemna liczba dni, MRP zawsze tworzy nowe planowane zamówienie w celu zaspokojenia popytu. W tej sytuacji ważne jest, aby pracować z komunikatami akcji w celu upewnienia się, że zapasy nie zostaną gromadzone.

Może być konieczne ustawienie liczby dni z ujemnym horyzontem czasowym, a następnie rozpoczęcie pracy z komunikatami akcji. Ta metoda daje dobre wyniki w planowaniu, ale jest też nieco wolniejsza. Analiza może również być trudniejsza, ponieważ należy przeanalizować i zastosować komunikaty akcji. Oto przykład:

- Towar DemoProduct ma sześciodniowy czas realizacji zakupu.
- W dniu zero (1 stycznia) zapas dla towaru DemoProduct wynosi 0 (zero).
- W dniu zero (1 stycznia) jest uzyskane zamówienie sprzedaży na ilość 10 sztuk towaru DemoProduct.
- W dniu 10 (10 stycznia) jest uzyskane zamówienie sprzedaży na ilość 10 sztuk towaru DemoProduct.
- W dniu 12 (12 stycznia) istnieje zamówienie zakupu na ilość 10 sztuk DemoProduct.
- Liczba dni ujemnych jest ustawiona na **20**, co jest liczba znacznie większą niż czas realizacji towaru.

Poniższa ilustracja pokazuje graficzny widok tego, co dzieje się.

![Graficzna pprzegląd przykładu](./media/negative-days-19.png)

MRP daje następujące wyniki.

![Wyniki](./media/negative-days-20.png)

W poprzednim zrzucie ekranu datą zapotrzebowania zamówienia sprzedaży jest 9 stycznia, a nie 10 stycznia. Ponieważ ten zrzut został pobrany w 2015, kiedy 10 stycznia była sobota, wymaganą datą zamówienia powinien być poprzedni dzień roboczy, czyli piątek 9 stycznia.

Moduł MRP tworzy planowane zamówienie zakupu do realizacji zapotrzebowania, które jest wymagane przez pierwsze zamówienie sprzedaży, ale również zaleca anulowanie zamówienia planowanego, co pozwoli na zaliczenie istniejącego zamówienia zakupu i zwiększenie jego ilości.

Wyniki nie są błędne, ale czas działania MRP może być dłuższy, ponieważ MRP musi tworzyć wszystkie opóźnienia i sugestie. Ponadto planista może potrzebować więcej czasu na zrozumienie wyników MRP. Najważniejsze w tym przypadku ważne jest, aby planista zrozumiał i używał komunikatów akcji.

Jeśli liczba dni ujemnych zostanie zredukowana do liczby bliższej czasowi realizacji towaru, a w systemie jest używana dynamiczna ujemna liczba dni, system MRP generuje następujące wyniki:

![Wyniki](./media/negative-days-21.png)

MRP tworzy zamówienie planowane które jest dołączone do pierwszego zamówienia sprzedaży. Następnie, zgodnie z oczekiwaniami, drugie zamówienie sprzedaży będzie uzależnione od istniejącego zamówienia zakupu, na podstawie ustawienia dni ujemnych. Ten wynik planowania jest również poprawny, a czas pracy dla MRP może być krótszy. W tym przypadku nie jest konieczne zrozumienie i umiejętność pracy z komunikatami akcji.

Aby zagwarantować wprowadzanie poprawnych wartości do firmy, należy wziąć pod uwagę zarówno funkcję, jak i czas działania MRP. W związku z tym określenie optymalnych wartości może zająć trochę czasu i kilkakrotnych prób.

## <a name="see-also"></a>Informacje dodatkowe

Aby kontynuować dyskusję, zapoznaj się z oryginałem [Jak uzyskać informacje o liczbie (dynamicznych) dni ujemnych](https://blogs.msdn.microsoft.com/axmfg/2015/02/19/more-about-dynamic-negative-days/) na blogu.
