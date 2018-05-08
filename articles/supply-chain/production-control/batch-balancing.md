---
title: Bilansowanie partii
description: "W tym temacie opisano proces równoważenia partii."
author: johanhoffmann
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7d00df6263530ba9fff4c246cb3593cd607f6719
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="batch-balancing"></a>Bilansowanie partii

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak jest obsługiwany proces równoważenia partii. 

Obejrzyj [film o równoważeniu partii w programie Microsoft Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be).

W procesie równoważenia partii ilość substancji, jaka ma zostać użyta w partii produkcji, jest obliczana na podstawie stężenia substancji aktywnych w wybranych partiach produktów.

<a name="products-that-have-an-active-ingredient"></a>Produkty zawierające substancje aktywne
---------------------------------------

Produkt może być definiowany przez stężenie zawartej w nim substancji aktywnej. Substancja aktywna produktu jest modelowana za pomocą specyficznego dla produktu atrybutu partii, który ma wartość minimalną, wartość maksymalną i poziom docelowy.

Poziom docelowy atrybutu partii wyraża szacowany udział procentowy substancji aktywnej w produkcie. Wartości minimalna i maksymalna reprezentują akceptowane odchylenie od poziomu docelowego. Można ich używać na przykład jako dopuszczalnych poziomów tolerancji dla partii w trakcie przyjęć produktu.

Produkt może mieć tylko jedną substancję aktywną. Aby określić substancję aktywną produktu, należy najpierw zdefiniować atrybutu partii specyficzny dla produktu. Następnie atrybut jest ustawiany jako atrybut bazowy produktu.

Na poziomie produktu należy również określić sposób rejestrowania poziomu substancji aktywnej w partii produktu: jako część procesu przyjęcia zakupu lub jako część procesu zlecenia kontroli jakości.

Aby skojarzyć atrybut bazowy z produktem, należy dokonać następującej konfiguracji:

-   Produkt musi być kontrolowany za pomocą partii. Aby ustawić produkt jako kontrolowany za pomocą partii, należy do produktu przypisać grupę wymiarów śledzenia zawierającą aktywny wymiar Partia.

-   Atrybut wskazujący poziomy substancji musi być zdefiniowany jako atrybut partii specyficzny dla tego produktu.

Na stronie **Atrybuty partii zapasów** można odszukać i edytować rzeczywistą wartość substancji aktywnej w partii. 

-  Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Wymiary śledzenia** \> **Partie** \> **Atrybuty partii zapasów**.

<a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Typy substancji i sposoby ich interakcji w procesie równoważenia partii
---------------------------------------------------------------------

Tworzony wiersz formuły może mieć jeden z następujących typów substancji:

-   None

-   Aktywne

-   Kompensacja

-   Wystawca

Pozostała części tej sekcji zawiera przykłady pokazujące sposób działania każdego typu substancji. Przykłady są oparte na następującej formule, która ma łączną wielkość partii równą 100 litrów.

| **Typ substancji** | **Kod towaru** | **Ilość w wierszu formuły** | **Jednostka** |
|---------------------|-----------------|---------------------------|----------|
| None                | A               | 20                        | litr    |
| Aktywne              | W               | 30                        | litr    |
| Kompensacja        | F               | 10                        | litr    |
| Wystawca              | D               | 40                        | litr    |

### <a name="active"></a>Aktywne

Gdy produkt zawierający atrybut bazowy zostanie dodany do wiersza formuły, jest nazywany *substancją aktywną* formuły. Szarże produkcyjne, które mają formuły zawierające substancje aktywne, mogą być wykorzystywane w procesie równoważenia partii. Dla każdej substancji w formule proces równoważenia partii szacuje ilość wymaganą do wytworzenia produktu. Szacunki ilości są oparte na stężeniu substancji aktywnych w wybranych partiach.

**Przykład**

Substancja B ma atrybut bazowy X i docelowy poziom 30 oraz jest uwzględniona w formule, która wymaga 30 litrów substancji B na każde 100 litrów produktu. Jest tworzona szarża produkcyjna o rozmiarze partii 100 litrów. Następuje uruchomienie szarży produkcyjnej. W trakcie procesu równoważenia partii użytkownik wybiera partię substancji B o poziomie zawartości 35. Ponieważ poziom zawartości 35 jest wyższy niż poziom docelowy 30, zbilansowana ilość substancji B zostanie zmniejszona poprzez podzielenie wartości zawartości przez docelowy poziom dla partii, a następnie pomnożenie wyniku przez szacowaną ilość. Obliczenie zbilansowanej ilości wygląda następująco:

(30 ÷ 35) x 30 litrów = 25,71 litra

| **Kod towaru** | **Typ substancji** | **Ilość szacowana** | **Zbilansowana ilość** | **Aktywna ilość** | **Jednostka** | **Wartość podstawowa** |
|-----------------|---------------------|------------------------|-----------------------|---------------------|----------|----------------|
| A               | None                | 20                     | 20                    |                     | litr    |                |
| W               | Aktywne              | 30                     | 25.71                 | 9.00                | litr    | 30.00          |
| F               | Kompensacja        | 10                     | 14.72                 |                     | litr    |                |
| D               | Wystawca              | 40                     | 39.57                 |                     | litr    |                |

### <a name="none"></a>None

Jeśli zastosujesz proces równoważenia partii, gdy typem substancji jest **Brak**, szacowana ilość jest taka sama, jak zbilansowana ilość w wierszu formuły w szarży produkcyjnej.

**Przykład**

Substancja A jest przypisana do substancji o typie **Brak** i dodana do formuły wyrobu gotowego. Formuła wymaga 10 litrów substancji A na każde 100 litrów wyrobu gotowego. Jeśli szarża produkcyjna wymaga 200 litrów, szacowana ilość i zbilansowana ilość substancji A są obie obliczane na 20 litrów.

### <a name="compensating"></a>Kompensacja

Substancja kompensująca może przesuwać lub uzupełniać efekt działania substancji aktywnej w produkcie. Z tego względu zużywana ilość substancji kompensującej zależy od zawartości istniejącej w produkcie:

-   **Wpływ przeciwstawny** — jeśli ilość substancji aktywnej jest większa niż przewidywana, należy dodać mniej substancji kompensującej.

-   **Wpływ uzupełniający** — jeśli ilość substancji aktywnej jest mniejsza niż przewidywana, należy dodać więcej substancji kompensującej.

Relację między substancją aktywną a substancją uzupełniającą ustawia się na stronie **Reguła kompensacji**.

Aby skonfigurować relacje między substancjami, wykonaj następujące czynności:

1.  Wybierz kolejno opcje **Zarządzanie informacjami o produktach** \> **Listy składowe (BOM) i formuły** \> **Formuły**, otwórz wiersz formuły, a następnie wybierz opcję **Substancje**, aby otworzyć stronę **Reguła kompensacji**.

2.  Zaznacz wiersz reprezentujący regułę kompensacji, a następnie zaznacz substancję aktywną, która ma być kompensowana.

>   W regule kompensacji należy także wprowadzić dodatni lub ujemny współczynnik kompensujący, które będzie określał skalę kompensacji oraz wskazywał, czy zasada ma być przeciwstawna, czy uzupełniająca. Dodatni współczynnik określa wpływ uzupełniający, a ujemny współczynnik określa wpływ przeciwstawny.

**Przykład**

Substancja B jest substancją aktywną, która ma atrybut bazowy X i poziom docelowy 30. Jest uwzględniona w formule, która wymaga 30 litrów substancji B na każde 100 litrów produktu. Substancja C jest substancją kompensującą, a w tej samej formule jej ilość jest określona na 10. W regule kompensacji ustawiono współczynnik kompensujący 1,10. W związku z tym zbilansowana ilość substancji kompensującej zostanie zmniejszona o różnicę między zbilansowaną ilością substancji aktywnej a szacowaną ilością wymaganą pomnożoną przez 1,10.

W przykładzie dla substancji o typie **Aktywna** zbilansowana ilość wymaganej substancji aktywnej została obliczona na 25,71, a szacowana wymagana ilość została obliczona na 30. W tym przypadku zbilansowana ilość substancji kompensującej zostanie obliczona następująco:

1.  Najpierw jest wyznaczana różnica między ilościami szacowaną i zbilansowaną:

>   25,71 – 30 = –4,29

2.  Wynik jest mnożony przez współczynnik kompensujący:

>   4,29 × 1,10 = –4,72

3.  Szacowana ilość kompensująca jest zmniejszana o –4,72 w celu wyznaczenia zbilansowanej ilości kompensującej:

>   10 – (–4,72) = 14,72

Ponieważ 1,10 jest dodatnim współczynnikiem kompensującym, ta regule kompensacji wpływ uzupełniający. W tym przypadku substancje aktywne mają większe stężenie, niż przewidywano. Z tego względu jest potrzebne więcej substancji kompensującej.

### <a name="filler"></a>Wystawca

*Substancja wypełniająca* to substancja neutralna, która służy do osiągnięcia wymaganej ilości wyjściowej wyrobu gotowego. Korekty ilości wypełniacza są obliczane na podstawie wahań ilości substancji aktywnej i kompensującej w stosunku do ilości standardowej.

**Przykład**

Utworzono formułę produktu zawierającą substancje A, B, C i D w przeliczeniu na 100 litrów wyrobu końcowego. Obliczono zbilansowaną ilość dla wszystkich typów substancji, z wyjątkiem substancji o typie **Wypełniacz**, która jest używana w jednym wierszu.
Zbilansowana ilość substancji wypełniającej jest obliczana jako różnica między rozmiarem partii 100 litrów a sumą ilości substancji A, B i C:

100 – (20 + 25,71 + 14,72) = 39,57

<a name="the-batch-balancing-process"></a>Proces równoważenia partii
---------------------------

Proces równoważenia partii jest wykonywany na stronie **Równoważenie partii**.
Wybierz kolejno opcje **Zarządzanie kosztami** \> **Szarże produkcyjne**, a następnie na karcie **Proces** wybierz opcję **Równoważenie partii**. Funkcja równoważenia partii jest dostępna dla szarż produkcyjnych znajdujących się w stanie **Rozpoczęcie**.

Zasadniczo równoważenie partii można stosować do szarż produkcyjnych, jeśli formuła zawiera co najmniej jeden wiersz formuły, w którym substancja jest typu **Aktywna**. (Wyjątki od tej reguły opisano w sekcji sekcję „Szarże produkcyjne, do których nie można stosować równoważenia partii” w dalszej części tego tematu).

Proces równoważenia partii można podzielić na dwa podprocesy:

1.  Składniki salda partii

2.  Potwierdzenie i zwolnienie formuły

### <a name="balance-batch-ingredients"></a>Składniki salda partii

W podprocesie Równoważenie składników partii ilość substancji, jaka ma zostać użyta w partii produkcji, jest obliczana na podstawie wybranych partii zawierających substancje aktywne. Co do zasady obliczenia można wykonać tylko wtedy, gdy jest pełne pokrycie na wszystkie substancje. Nie można zrównoważyć tylko części partii, która ma zostać wytworzona wskutek szarży produkcyjnej.

[!NOTE]
Nie można zapisać obliczeń, a następnie później wykonać proces równoważenia partii. W przypadku zamknięcia strony **Równoważenie partii** trzeba powtórzyć całe obliczenia, aby ukończyć proces.

### <a name="confirm-and-release-the-formula"></a>Potwierdzenie i zwolnienie formuły

Po obliczeniu ilości substancji można potwierdzić i zwolnić formułę. Proces zwalniania różni się w zależności od tego, czy produkty mogą podlegać procesom zarządzania magazynem:

-   Jeśli w ustawieniach produktu włączono obsługę procesów zarządzania magazynem, wiersz formuły jest zwalniany do magazynu zgodnie z zasadami tych procesów. Wiersz formuły jest zwalniany w ilościach odpowiadających zbilansowanym ilościom oraz dla konkretnych partii wybranych dla substancji aktywnych.

> [!NOTE]
>   Wiersze formuły mogą być zwalniane do magazynu tylko w ramach procesu równoważenia partii. Mimo że istnieją inne opcje zwalniania materiałów produkcyjnych do magazynu, nie można ich używać dla wierszy formuł.

-   Jeśli w produkcie nie włączono obsługi procesów zarządzania magazynem, dla produktu jest tworzona lista pobrania produkcji podczas potwierdzania i zwalniania formuły.

W jednej formule można połączyć produkty, w których włączono i nie włączono obsługi procesów zarządzania magazynem. Jeśli w jednej formule znajdują się dwa rodzaje produktów, produkty z włączoną obsługą procesów zarządzania magazynem są zwalniane do magazynu. Dla produktów, które nie mają włączonej obsługi procesów zarządzania magazynem, jest tworzona lista pobrania podczas potwierdzania i zwalniania formuły.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Szarże produkcyjne, do których nie można stosować równoważenia partii

Istnieje jeden wyjątek od reguły mówiącej o tym, że równoważenie partii można stosować do szarż produkcyjnych, jeśli formuła zawiera co najmniej jeden wiersz formuły, w którym substancja jest typu **Aktywna**.

Jeżeli formuła zawiera substancję aktywną dla produktu, w którym włączono obsługę procesów zarządzania magazynem, ale numer partii jest poniżej lokalizacji w hierarchii rezerwacji, do szarży produkcyjnej nie można zastosować równoważenia partii.

Szarża produkcyjna, do której nie można zastosować równoważenia partii, przechodzi przez zwykły cykl przetwarzania szarż produkcyjnych.

