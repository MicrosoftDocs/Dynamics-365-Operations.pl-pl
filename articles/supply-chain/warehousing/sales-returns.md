---
title: Zwroty sprzedaży
description: Ten temat zawiera informacje o procesie zamówień zwrotu. Opisuje koncepcję zwrotów od odbiorców oraz ich wpływ na wycenę i ilości dostępnych zapasów.
author: omulvad
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 159df9006feff96c98a704f8bdc88a8a6cf05939
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209106"
---
# <a name="sales-returns"></a>Zwroty sprzedaży

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o procesie zamówień zwrotu. Opisuje koncepcję zwrotów od odbiorców oraz ich wpływ na wycenę i ilości dostępnych zapasów.

Odbiorcy mogą zwracać towary z różnych powodów. Na przykład towar może być uszkodzony lub może nie spełniać oczekiwań odbiorcy. Proces zwrotu rozpoczyna się, gdy odbiorca wystawia wniosek o zwrot towaru. Po odebraniu wniosku od odbiorcy jest tworzone zamówienie zwrotu.

## <a name="return-order-process"></a>Proces zamówienia zwrotu
Na poniższej ilustracji przedstawiono przegląd procesu zamówienia zwrotu.  

[![Proces zamówienia zwrotu](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Istnieją dwa rodzaje procesu zamówienia zwrotu: zwrot fizyczny i tylko uznanie (kredyt).

-   **Fizyczny zwrot** — Zamówienie zwrotu autoryzuje fizyczny zwrot produktów.
-   **Tylko kredyt** — Zamówienie zwrotu autoryzuje uznanie konta odbiorcy (kredyt dla odbiorcy), ale nie wymaga, aby odbiorcy fizycznie zwrócić produkt.

### <a name="physical-return-order-process"></a>Proces zamówienia zwrotu fizycznego

1.  **Tworzenie zamówienia zwrotu.** Formalnie udokumentowanie pozwolenia dla odbiorcy, aby zwrócił wszelkie wadliwe lub niechciane produkty. Zamówienie zwrotu nie wymaga, aby firma zaakceptowała zwrócony produkt lub uznała konto odbiorcy określoną kwotą. W przypadku przyjęcia zwrotu można autoryzować wysłanie towaru zastępczego jeszcze przed otrzymaniem zwróconego wadliwego towaru.
2.  **Przybycie do magazynu w celu kontroli.** Przeprowadzenie wstępnej kontroli i sprawdzenie poprawności względem dokumentu zamówienia zwrotu. Zamówienie zwrotu obsługuje również funkcję kwarantanny zwróconych towarów w celu wykonania dodatkowych inspekcji i kontroli jakości.
3.  **Ustalenie dyspozycji.** Finalizacja procesu kontroli i zdecydowanie, co należy zrobić ze zwróconymi produktami. W ramach tego etapu zdecyduj, czy uznasz konto odbiorcy określoną kwotą, odrzucisz zwrot produktu czy też przyjmiesz zwrot produktu, zezłomujesz produkt, a odbiorcy wyślesz produkt zastępczy.
4.  **Generowanie dokumentu dostawy.** Wygenerowanie dokumentu dostawy i zatwierdzenie decyzji o dyspozycji podjętej w kroku 3. Finalizacja procesów logistycznych.
5.  **Generowanie faktury.** Zamykanie zamówienia zwrotu.

### <a name="credit-only-process"></a>Proces Tylko kredyt

1.  **Tworzenie zamówienia zwrotu.** Formalnie udokumentowanie pozwolenia, aby odbiorca otrzymał kredyt (jego konto zostało uznane określoną kwotą) bez zwracania wadliwych lub niechcianych produktów. Kod dyspozycji **Tylko kredyt** autoryzuje decyzję uznania konta odbiorcy bez fizycznego zwracania produktów.
2.  **Generowanie faktury.** Generowanie faktury korygującej, a następnie zamknięcie zamówienia zwrotu.

## <a name="return-material-authorization"></a>Autoryzacja zwrotu
Przetwarzanie autoryzacji zwrotu (RMA) opiera się na funkcjonalności zamówienia sprzedaży. RMA jest rejestrowana jako zamówienie zwrotu, które zostało utworzona jako zamówienie sprzedaży, i może mieć powiązane inne zamówienie sprzedaży nazywane zamówieniem wymiany. Oba zamówienia sprzedaży są powiązane z numerem źródłowego RMA.

-   **Zamówienie zwrotu** — Aby zarejestrować RMA, tworzysz zamówienie zwrotu, które jest zamówieniem sprzedaży z przypisanym typem **Zwrot towaru**. Wszelkie zmiany wprowadzane w informacjach RMA są automatycznie odzwierciedlane w zamówieniu sprzedaży. Dopóki zamówienie zwrotu nie uzyska stanu **Otwarte**, nie pojawi się na liście zamówień sprzedaży. RMA jest używane do obsługi przybycia i przyjęcia zwróconych towarów, jak również do autoryzowania czynności dyspozycji Tylko kredyt (zobacz sekcja **Kody dyspozycji i akcje dyspozycji**). Wszystkie pozostałe kolejne procesy muszą być obsługiwane w zamówieniu sprzedaży.
-   **Zamówienie wymiany** — Kiedy do odbiorcy trzeba wysłać zamówienie wymiany, RMA może zawierać drugie skojarzone zamówienie sprzedaży. Można ręcznie utworzyć zamówienie wymiany dla RMA, aby umożliwia natychmiastową wysyłkę. Alternatywnie zamówienie wymiany może być tworzone automatycznie po sfinalizowaniu przybycia, inspekcji i przyjęcia dla pozycji RMA zawierającej kod dyspozycji wskazujący wymianę. Zamówienie wymiany ma taką samą funkcjonalność, jak skojarzona z zamówieniem sprzedaży. Na przykład można go użyć do skonfigurowania niestandardowego produktu jako towaru zastępczego, utworzenia zlecenia produkcyjnego służącego naprawie zwróconego towaru, utworzenia zamówienia zakupu dostawy bezpośredniej w celu wysyłania produktu zastępczego od dostawcy itd.

## <a name="create-a-return-order"></a>Tworzenie zamówienia zwrotu
Proces zamówienia zwrotu rozpoczyna się, kiedy odbiorca kontaktuje się z organizacją, aby zwrócić wadliwy lub niechciany produkt i/lub otrzymać kredyt (uznanie). Gdy organizacja zaakceptuje zwrot, jest on dokumentowany za pomocą zamówienia zwrotu. To zamówienie zwrotu staje się centralnym punktem wewnętrznego przetwarzania dotyczącego zwróconego produktu. Na ilustracji poniżej przedstawiono procedurę tworzenia zamówienia zwrotu.  

[![Procedura tworzenia zamówienia zwrotu](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Tworzenie nagłówka zamówienia zwrotu

Podczas tworzenia zamówienia zwrotu należy podać informacje z poniższej tabeli.

| Pole              | opis                                              | Komentarze                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konto odbiorcy   | Odwołanie tabeli odbiorców                       | Należy podać istniejące konto odbiorcy.                                                                                                                                                                                                                                                                                                  |
| Adres dostawy   | Adres, na który jest zwracany towar                 | Domyślnie jest używany adres organizacji. Jeśli w nagłówku zostanie zaznaczony określony magazyn, adres dostawy zmienia się na adres dostawy magazynu. Adres ten można zmienić na stronie **Szczegóły zamówienia zwrotu**.                                                                                                  |
| Oddział/magazyn     | Oddział lub magazyn, który przyjmuje zwracany produkt | Adres dostawy dla zamówienia zwrotu jest określany na podstawie adresu dostawy oddziału lub magazynu.                                                                                                                                                                                                                                 |
| Numer autoryzacji zwrotu         | Identyfikator przypisany do zamówienia zwrotu              | Numer autoryzacji zwrotu jest używany jako klucz alternatywny w całym procesie zamówienia zwrotu. Przypisywany numer RMA bazuje na numeracji RMA skonfigurowanej na stronie **Parametry modułu rozrachunków z odbiorcami**.                                                                                                                              |
| Termin realizacji           | Ostatni dzień, do kiedy można zwrócić towar               | Wartość domyślna jest obliczana jako bieżąca data plus okres ważności. Na przykład jeśli zwrot jest ważny (dopuszczalny) tylko przed 90 dni od daty utworzenia zamówienia zwrotu, a zamówienie zwrotu utworzono w dniu 1 maja, wartością w tym polu jest **30 lipca**. Okres ważności jest ustawiany na stronie **Parametry modułu rozrachunków z odbiorcami**. |
| Kod przyczyny zwrotu | Przyczyna zwrotu produktu podawana przez odbiorcę          | Kod przyczyny jest wybierany z listy kodów przyczyny zdefiniowanych przez użytkownika. Pole to można zaktualizować w dowolnym momencie.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Tworzenie wierszy zamówienia zwrotu

Po wypełnieniu nagłówka zwrotu można utworzyć wiersze zwrotu przy użyciu jednej z następujących metod:

-   Ręczne wprowadzenie szczegółów towaru, ilości i innych informacji dla każdego wiersza zwrotu.
-   Utworzenie wiersza zwrotu za pomocą funkcji **Znajdź zamówienie sprzedaży**. Zalecamy używanie tej funkcji podczas tworzenia zamówienia zwrotu. Funkcja **Znajdź zamówienie sprzedaży** ustanawia odwołanie od wiersza zwrotu do wiersza zafakturowanego zamówienia sprzedaży, a następnie pobiera szczegóły wiersza, takie jak numer towaru, ilość, cena, rabat i wartości kosztów, z wiersza sprzedaży. Odwołanie pomaga zagwarantować, że podczas zwracania produktu do firmy jest on wyceniany według tego samego kosztu jednostkowego, jak przy sprzedaży. Odwołanie sprawdza też, czy zamówienia zwrotu nie są tworzone dla ilości przekraczającej ilość sprzedaną na fakturze.

>[Uwaga!] Wiersze zwrotu zawierające odwołania do zamówienia sprzedaży są obsługiwane jako korekty (cofnięcia) sprzedaży. Aby uzyskać więcej informacji, zobacz sekcję „Księgowanie w księdze" w dalszej części tego tematu.

### <a name="charges"></a>Opłaty

Prowizje i opłaty można dodawać do zamówienia zwrotu za pomocą jednej lub kilku z następujących metod:

-   Opłaty można dodać ręcznie do nagłówka zamówienia zwrotu i/lub wiersza zamówienia zwrotu.
-   Opłaty mogą być dodawane automatycznie do nagłówka zamówienia zwrotu jako funkcja kodu przyczyny zwrotu.
-   Opłaty mogą być dodawane automatycznie do wiersza zamówienia zwrotu na podstawie kodu dyspozycji ustawionego dla wiersza.

Opłaty dodatkowe są dodawane automatycznie po przypisaniu kodu przyczyny zwrotu lub kodu dyspozycji do wiersza. Jeśli kod przyczyny zostanie później zmieniony, istniejący wpis opłaty nie zostanie usunięty, ale może zostać dodany nowy wpis opłaty oparty na nowym kodzie przyczyny. Podczas dodawania opłat do wierszy zamówienia zwrotu opłaty, które są obliczane jako procent wartości wiersza lub zamówienia, stają się ujemne, gdy wiersz lub zamówienie są ujemne, chyba że procent również jest liczbą ujemną. Opłata mająca wartość ujemną reprezentuje kredyt (uznanie) dla odbiorcy.

### <a name="return-reason-codes"></a>Kody przyczyn zwrotu

Stosując kody przyczyn do zwrotów, można ułatwić analizowanie wzorców zwrotów. Kody przyczyn informują o tym, dlaczego odbiorca chce zwrócić towary. Niektóre organizacje mają zdefiniowanych wiele kodów przyczyn. Takie organizacje mogą łączyć kody przyczyn w grupy kodów przyczyn, aby uzyskać lepszy obraz i kumulować sprawozdawczość.

### <a name="disposition-codes-and-disposition-actions"></a>Kody dyspozycji i akcje dyspozycji

Ważnym krokiem w procesie zamówienia zwrotu jest przypisanie kodu dyspozycji do wiersza zamówienia zwrotu w ramach rejestracji przybycia. Kod dyspozycji określa następujące informacje:

-   **Następstwa finansowe** — Czy należy przyznać odbiorcy kredyt (uznać jego konto) za zwrócone towary i czy należy dodać jakiekolwiek opłaty do wiersza zamówienia zwrotu?
-   **Dysponowanie zwróconym towarem** — Czy towar należy dodać z powrotem do zapasów, zezłomować, czy zwrócić do odbiorcy?
-   **Logistyka zwróconego towaru** — Czy odbiorcy należy wysłać towar zastępczy?

Oprócz określenia sposobu postępowania ze zwróconym towarem kody dyspozycji mogą powodować dodawanie opłat do wiersza zwrotu. Mogą również służyć do grupowania zwrotów na potrzeby analizy statystycznej. Kody dyspozycji są definiowane w ramach konfigurowania zamówień zwrotu. Jednak każdy kod dyspozycji musi się odwoływać do jednej wbudowanej akcji dyspozycji. Poniższa tabela zawiera wbudowane kody dyspozycji i powiązane z nimi czynności. **Ważne:** Jeśli towar nie powinien być zwracany, ale i tak należy uznać konto odbiorcy określoną kwotą, przypisz do wiersza zwrotu kod dyspozycji **Tylko kredyt**.

<table>
<thead>
<tr class="header">
<th>Kod dyspozycji</th>
<th>Następstwa finansowe</th>
<th>Następstwa logistyczne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tylko kredytowe</td>
<td><ul>
<li>Konto odbiorcy jest uznawane ceną sprzedaży pomniejszoną o opłaty.</li>
<li>Strata z tytułu złomowania towaru jest księgowana w księdze.</li>
</ul></td>
<td>Towar nie powinien być zwracany. Ta akcja dyspozycji jest używana w następujących przypadkach:
<ul>
<li>Istnieje wystarczające zaufanie między stronami.</li>
<li>Koszt zwrotu wadliwych towarów jest bardzo wysoki.</li>
<li>Towarów nie można ze względów formalnych wprowadzić z powrotem do magazynu. Ze względu na inne okoliczności nie trzeba dokonywać fizycznego zwrotu.</li>
</ul></td>
</tr>
<tr class="even">
<td>Strona kredytowa</td>
<td><ul>
<li>Konto odbiorcy jest uznawane ceną sprzedaży pomniejszoną o opłaty.</li>
<li>Wartość zapasów jest powiększana o koszt zwróconego towaru.</li>
</ul></td>
<td>Towar jest zwracany i dodawany z powrotem do zapasów.</td>
</tr>
<tr class="odd">
<td>Zastąp i zaksięguj po stronie kredytowej</td>
<td><ul>
<li>Konto odbiorcy jest uznawane ceną sprzedaży pomniejszoną o opłaty.</li>
<li>Wartość zapasów jest powiększana o koszt zwróconego towaru.</li>
<li>Oddzielne zamówienie sprzedaży na wymianę jest tworzone i obsługiwane osobno.</li>
</ul></td>
<td>Towar jest zwracany i dodawany z powrotem do zapasów.</td>
</tr>
<tr class="even">
<td>Zastąp i zlikwiduj</td>
<td><ul>
<li>Konto odbiorcy jest uznawane ceną sprzedaży pomniejszoną o opłaty.</li>
<li>Strata z tytułu złomowania towaru jest księgowana w księdze.</li>
<li>Oddzielne zamówienie sprzedaży na wymianę jest tworzone i obsługiwane osobno.</li>
</ul></td>
<td>Towar jest zwracany i złomowany.</td>
</tr>
<tr class="odd">
<td>Zwrot do odbiorcy</td>
<td>Brak, z wyjątkiem ewentualnych opłat.</td>
<td>Towar jest zwracany, ale po kontroli wysyłany z powrotem do odbiorcy. Ta akcja dyspozycji może być używana, jeśli towar został umyślnie uszkodzony lub unieważniono gwarancję.</td>
</tr>
<tr class="even">
<td>Odpadki</td>
<td><ul>
<li>Konto odbiorcy jest uznawane ceną sprzedaży pomniejszoną o opłaty.</li>
<li>Strata z tytułu złomowania towaru jest księgowana w księdze.</li>
</ul></td>
<td>Towar jest zwracany lub złomowany.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Przybycie do magazynu w celu kontroli
Zanim będzie można fizycznie przyjąć zwrócone towary do zapasów poprzez zaksięgowanie dokumentu dostawy, towary muszą przejść przez rejestrację przybycia i opcjonalną inspekcję. Na poniższej ilustracji przedstawiono przegląd procesu przybycia. W następnych sekcjach opisano każdy krok pokazany na ilustracji.  

[![Proces przybycia](./media/salesreturn03.png)](./media/salesreturn03.png)  

Proces ma kilka innych wariantów, które nie są omówione w tym temacie. Oto wybrane możliwe warianty:

-   Nie używaj listy **Przegląd przyjęć**, aby utworzyć arkusz przybycia. Zamiast tego ręcznie utwórz arkusz przybycia. Zamówienia zwrotu będą miały odwołanie **Zamówienie sprzedaży**.
-   Jeśli używasz modułu Zarządzanie magazynem, wygeneruj transporty palet. Podczas transportu palet wiersz zwrotu będzie miał stan **Dostarczone**.
-   Zarejestruj przybycie zwróconego towaru bezpośrednio z wiersza zamówienia zwrotu za pomocą funkcji **Rejestracja**.

W trakcie procesu przybycia zwroty są integrowane z ogólnym procesem przybycia do magazynu. Proces przybycia umożliwia także tworzenie zleceń kwarantanny zwróconych towarów, które muszą zostać poddane oddzielnej kontroli.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identyfikacji produktów na liście Przegląd przyjęć

Na stronie **Przegląd przyjęć** znajduje się lista wszystkich planowanych przychodzących przybyć. 
>[Uwaga] Przywozy z zamówień zwrotu muszą być przetwarzane oddzielnie od innych typów transakcji przywozu. Po zidentyfikowaniu przychodzącej paczki na stronie **Przegląd przyjęć** (na przykład za pomocą towarzyszącego dokumentu RMA) w okienku akcji kliknij przycisk **Rozpocznij przyjęcie**, aby utworzyć i zainicjować arkusz przybycia pasujący do przybycia.

### <a name="edit-the-arrival-journal"></a>Edycja arkusza przybycia

Ustawiając w opcji **Zarządzanie kwarantanną** wartość **Tak**, można utworzyć zlecenie kwarantanny dla wiersza zwrotu. Jeśli wiersz został wysłany do kwarantanny w celu inspekcji, nie można określić kodu dyspozycji. 
 
Jeśli ustawisz w opcji **Zarządzanie kwarantanną** wartość **Tak** w grupie modeli zapasów towaru, opcja **Zarządzanie kwarantanną** na stronie **Wiersze arkusza** zostanie oznaczona dla wiersza arkusza przywozu i nie będzie można jej zmienić. Jeśli wiersz jest wysyłany do kwarantanny, należy określić właściwy magazyn kwarantanny. 

Jeśli wiersz przybycia nie jest wysyłany do inspekcji, magazynier zajmujący się przybyciami musi określić kod dyspozycji bezpośrednio w wierszu arkusza przybycia, a następnie zaksięgować arkusz przybycia. Jeśli ten sam kod dyspozycji nie ma być przypisywany do całej ilości wiersza zwrotu albo jeśli nie przyjęto całej ilości wiersza, należy podzielić wiersz. Podział wiersza arkusza przybycia powoduje również podział wiersza zwrotu (**SalesLine**) i utworzenie nowego identyfikatora partii. W celu podziału wiersza można zmniejszyć ilość w wierszu arkusza przybycia. Po zaksięgowaniu arkusza jest tworzony nowy wiersz zwrotu o stanie **Oczekiwane** na pozostałą ilość. Wierz można również podzielić, klikając kolejno opcje **Funkcje** &gt; **Podziel**.

### <a name="process-the-quarantine-order"></a>Przetwarzanie zlecenia kwarantanny

Jeśli zwrócone produkty są wysyłane do inspekcji w magazynie kwarantanny, wszelkie dodatkowe przetwarzanie odbywa się na podstawie zlecenia kwarantanny. Dla każdego wiersza przybycia wysyłanego do kwarantanny jest tworzone jedno zlecenie kwarantanny. Kod dyspozycji wskazuje wynik procesu inspekcji. 

Zlecenie kwarantanny można podzielić tak samo, jak się dzieli arkusz przybycia. Podział zlecenia kwarantanny powoduje odnośny podział wiersza zwrotu. Po wprowadzeniu kodu dyspozycji sfinalizuj zlecenie kwarantanny, używając funkcji **Koniec** lub **Zgłoś jako gotowe**. Jeśli wybierzesz funkcję **Zgłoś jako gotowe**, w wyznaczonych magazynie zostanie utworzone nowe przybycie. Następnie można przetwarzać to przybycie za pomocą opcji na stronie **Przegląd przyjęć**. 

Jeżeli przybycie ma swoje źródło w zleceniu kwarantanny, nie można zmienić kodu dyspozycji przypisanego podczas inspekcji. Jeśli sfinalizujesz zlecenie kwarantanny za pomocą funkcji **Koniec**, partia jest automatycznie rejestrowana. Czasami towar może być odsyłany z kwarantanny z powrotem do działu wysyłania i przyjmowania. Na przykład inspektor kwarantanny może nie wiedzieć, gdzie umieścić towar w zapasach. W takim przypadku należy zaktualizować odnośny dokument dostawy, aby poprawnie zarejestrować i przetwarzać kod dyspozycji ustawiony z powodu kwarantanny. 

Potwierdzenie przyjęcia można wysyłać odbiorcy podczas rejestrowania wiersza zwrotu. Raport **Potwierdzenie zwrotu** przypomina dokument zamówienia zwrotu. Raport **Potwierdzenie zwrotu** nie jest zapisywany w arkuszu ani w inny sposób rejestrowany w systemie i nie jest wymaganym krokiem w procesie zamówienia zwrotu.

## <a name="replace-a-product"></a>Wymiana produktu
Istnieją dwie metody zarządzania wymianą produktów:

-   **Wymiana zawczasu** — Wymiana produktu, zanim zwrócony produkt zostanie otrzymany od odbiorcy.
-   **Wymiana na podstawie kodu dyspozycji** — Automatyczne tworzenie nowego wiersza zamówienia wymiany.

### <a name="up-front-replacement"></a>Zamiennik zawczasu

W wymianie zawczasu towar zastępczy może być dostarczany odbiorcy przed otrzymaniem od niego zwróconego produktu. Ta metoda jest przydatna, gdy na przykład towar jest częścią maszyny, której nie można wymontować, jeśli na jej miejsce nie zostanie wstawiona część zamienna, albo gdy po prostu chcesz, aby odbiorca otrzymał produkt zastępczy jak najszybciej. Zamówienie wymiany zawczasu jest niezależnym zamówieniem sprzedaży. Informacje nagłówka są inicjowane przez odbiorcę, a informacje wiersza są inicjowane przez zamówienie zwrotu. Zamówienie wymiany można edytować, przetwarzać i usuwać niezależnie od zamówienia zwrotu. Podczas usuwania zamówienia wymiany pojawia się komunikat z informacją, że zamówienie zostało utworzone jako zamówienie wymiany. Poniższa ilustracja przedstawia proces wymiany zawczasu.  

![Proces wymiany zawczasu](./media/SalesReturn04.png)

Zamówienie zwrotu zawiera odwołanie do zamówienia wymiany. Jeśli zamówienie wymiany zawczasu zostanie utworzone dla zamówienia zwrotu przed zwróceniem wadliwego towaru, nie można wybrać kodów dyspozycji dla wymiany po zwrocie wadliwego towaru.

### <a name="replacement-by-disposition-code"></a>Wymiana na podstawie kodu dyspozycji

Jeśli wysyłasz towar zastępczy do odbiorcy i w zamówieniu zwrotu używasz akcji dyspozycji **Zastąp i zlikwiduj** lub **Zastąp i zaksięguj po stronie kredytowej**, użyj procesu przedstawionego na poniższej ilustracji.  

![Proces wymiany w przypadku używania kodu dyspozycji](./media/SalesReturn05.png)

Towar zastępczy zostanie dostarczony przy użyciu niezależnego zamówienia sprzedaży — zamówienia sprzedaży wymiany. To zamówienie sprzedaży jest tworzone podczas generowania dokumentu dostawy dla zamówienia zwrotu. Nagłówek zamówienia używa informacji od odbiorcy, do którego odwołuje się nagłówek zamówienia zwrotu. Informacje wiersza są pobierane z informacji wprowadzonych na stronie **Pozycja zastępcza**. Strona **Pozycja zastępcza** musi być wypełniona dla wierszy, które mają akcje dyspozycji rozpoczynające się słowem „zamień”. Jednak ani ilość, ani dane identyfikacyjne towaru zastępczego nie są weryfikowane ani w żaden sposób ograniczane. Takie zachowanie pozwala na przypadki, gdy odbiorca chce otrzymać ten sam towar, ale w innej konfiguracji lub rozmiarze, a także na przypadki, gdy odbiorca chce otrzymać całkowicie inny towar. Domyślnie na stronie **Pozycja zastępcza** jest wprowadzany identyczny towar. Można jednak wybrać inny towar, pod warunkiem, że funkcja została skonfigurowana. 

>[Uwaga] Po utworzeniu zamówienia sprzedaży wymiany można je edytować i usuwać.

## <a name="generate-a-packing-slip"></a>Generowanie dokumentu dostawy
Aby zwrócone towary mogły zostać przyjęte do zapasów, należy zaktualizować dokument dostawy dla zamówienia, do którego należą towary. Podobnie jak proces aktualizacji faktury jest aktualizacją transakcji finansowej, tak proces aktualizacji dokumentu dostawy jest fizyczną aktualizacją rekordu zapasów. Innymi słowy proces ten zatwierdza zmiany zapasów. W przypadku zwrotów kroki przypisane do akcji dyspozycji są implementowane podczas aktualizacji dokumentu dostawy. Podczas generowania dokumentu dostawy zachodzą następujące zdarzenia:

-   W magazynie standardowy proces jest używany wykonania fizycznego przyjęcia. Księgowania w księdze są generowane, jeśli grupa modeli zapasów (**Księguj magazyn fizyczny**) i parametry modułu rozrachunków z odbiorcami (**Księgowanie dokumentów dostawy w księdze**) są prawidłowo skonfigurowane.
-   Towary oznaczone akcją dyspozycji zawierającą słowo „złom” są brakowane, a strata na zapasach jest księgowana w księdze.
-   Towary oznaczone akcją dyspozycji **Zwrot do odbiorcy** są przyjmowane i dostarczane do odbiorcy. Towary te nie wpływają netto na zapasy.
-   Jest tworzone zamówienie sprzedaży wymiany. To zamówienie sprzedaży bazuje na informacjach ze strony **Pozycja zastępcza**.

Dokument dostawy można wygenerować tylko dla wierszy, które mają stan zwrotu **Zarejestrowane**, i tylko w odniesieniu do pełnej ilości w wierszu zwrotu. Jeśli kilka wierszy w zamówieniu zwrotu ma stan **Zarejestrowane**, można wygenerować dokument dostawy dla podzbioru wierszy, usuwając pozostałe wiersze ze strony **Księguj dokument dostawy**. 

Zwroty częściowe są definiowane w kategoriach wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu. Oznacza to, że jeśli otrzymasz pełną ilość wskazaną w jednym wierszu zamówienia zwrotu, ale nie otrzymasz nic z pozostałych wierszy tego zamówienia zwrotu, dostawa nie jest dostawą częściową. Jeśli jednak wiersz zamówienia zwrotu wymaga zwrotu na przykład dziesięciu jednostek określonego towaru, a otrzymasz tylko cztery jednostki, dostawa jest dostawą częściową. Jeśli nie przybędą wszystkie oczekiwane zwracane towary, można odstawić przesyłkę na bok i poczekać na przybycie reszty zwracanej ilości. Alternatywnie można zarejestrować i zaksięgować ilość częściową. W ramach procesu księgowania dokumentów dostawy można powiązać numer odwołania dokumentu dostawcy określony w dokumentach wysyłkowych odbiorcy z wierszami zamówienia. To skojarzenie jest opcjonalne i ma charakter wyłącznie informacyjny. Nie tworzy żadnych aktualizacji transakcji. 

Ogólnie rzecz biorąc można pominąć proces dokumentu dostawy i przejść bezpośrednio do fakturowania. W takim przypadku czynności, które byłyby wykonywane podczas generowania dokumentu dostawy, są wykonywane podczas fakturowania.

## <a name="generate-an-invoice"></a>Generuj fakturę
Chociaż strona **Zamówienie zwrotu** zawiera informacje i czynności, które są wymagane w celu obsługi szczególnych aspektów logistycznych zamówienia zwrotu, do finalizacji procesu fakturowania należy użyć strony **Zamówienie sprzedaży**. Organizacja może wtedy fakturować zamówienia zwrotu i zamówienia sprzedaży w tym samym czasie, a ta sama osoba może wykonać proces fakturowania zgodnie z wymaganiami. Aby wyświetlić zamówienie zwrotu ze strony **Zamówienie sprzedaży**, kliknij łącze numeru zamówienia sprzedaży, co spowoduje otwarcie skojarzonego zamówienia sprzedaży. Zamówienie zwrotu można także znaleźć na stronie **Wszystkie zamówienia sprzedaży**. Zamówienia zwrotu są zamówieniami sprzedaży o typie zamówienia **Zwrot towaru**.

### <a name="credit-correction"></a>Korekta z czerwonym stornem

W ramach procesu fakturowania sprawdź poprawność wszystkich opłat dodatkowych. Aby spowodować, że księgowania w księdze staną się korektami (stornem), rozważ użycie opcji **Korekta z czerwonym stornem** na karcie **Inne** na stronie **Księgowanie faktury** podczas księgowania faktury/faktury korygującej. 
>[Uwaga] Domyślnie opcja **Korekta z czerwonym stornem** jest aktywna, jeśli włączono opcję **Faktura korygująca z czerwonym stornem** na stronie **Parametry modułu rozrachunków z odbiorcami**. Jednak zalecamy, aby nie księgować zwrotów za pomocą funkcji storna.

## <a name="create-intercompany-return-orders"></a>Tworzenie międzyfirmowych zamówień zwrotu
Zamówienia zwrotu mogą być wykonywane między dwoma firmami wewnątrz organizacji. Obsługiwane są następujące scenariusze:

-   Proste zwroty międzyfirmowe między dwoma firmami uczestniczącymi w relacji międzyfirmowej
-   Łańcuch międzyfirmowy ustanawiany w momencie, gdy zamówienie zwrotu od odbiorcy jest tworzony w firmie sprzedającej
-   Łańcuch międzyfirmowy ustanawiany w momencie, gdy zamówienie zwrotu do dostawcy jest tworzony w firmie kupującej
-   Zwroty za pomocą wysyłki z dostawą bezpośrednią między zewnętrznym odbiorcą a dwoma firmami uczestniczącymi w relacji międzyfirmowej

### <a name="setup"></a>Konfiguracja

Poniższa ilustracja przedstawia minimalną konfigurację wymaganą, aby dwie firmy mogły uczestniczyć w relacji międzyfirmowej i korzystać z funkcji handlu międzyfirmowego.  

![Konfiguracja minimalna](./media/SalesReturn06.png)

W poniższym scenariuszu CompBuy jest firmą kupującą, a CompSell jest firmą sprzedającą. Na ogół firma sprzedająca sprzedaje towary do firmy kupującej albo, w scenariuszach wysyłki z dostawą bezpośrednią, prosto do odbiorcy końcowego. W firmie CompBuy dostawca IC\_CompSell jest zdefiniowany jako międzyfirmowego punkt końcowy skojarzony z firmą CompSell. Równocześnie w firmie CompSell odbiorca IC\_CompBuy jest zdefiniowany jako międzyfirmowego punkt końcowy skojarzony z firmą CompBuy. W obu firmach muszą być zdefiniowane odpowiednie szczegóły zasad działań i mapowania wartości. W scenariuszu wysyłki z dostawą bezpośrednią w firmie sprzedającej jest tworzone międzyfirmowe zamówienie zwrotu, które jest również międzyfirmowym zamówieniem sprzedaży. Numer autoryzacji zwrotu do międzyfirmowego zamówienia zwrotu może zostać pobrany z numeracji RMA w firmie CompSell lub skopiowany z numeru RMA przypisanego do oryginalnego zamówienia zwrotu w firmie CompBuy. O tych działaniach decydują ustawienia numeru autoryzacji zwrotu w zasadach działań **PurchaseRequisition** w firmie CompBuy. Jeśli numer RMA jest synchronizowany, należy zaplanować łagodzenie skutków konfliktu powstającego w przypadku, gdy obie firmy używają tej samej numeracji.

### <a name="simple-intercompany-returns"></a>Proste zwroty międzyfirmowe

Ten scenariusz obejmuje dwie firmy w tej samej organizacji, jak pokazano na poniższej ilustracji.  

![Prosty zwrot międzyfirmowy](./media/SalesReturn07.png)

Łańcuch zamówień można utworzyć w momencie, gdy zamówienie zwrotu do dostawcy jest tworzone w firmie kupującej lub zamówienie zwrotu od odbiorcy jest tworzone w firmie sprzedającej. Jest tworzone odnośne zamówienie w drugiej firmie i sprawdza, czy informacje nagłówka i wierszy w zamówieniu zwrotu do dostawcy odzwierciedlają ustawienia w zamówieniu zwrotu od odbiorcy. Tworzone zamówienie zwrotu może uwzględniać lub pomijać odwołanie (**Znajdź zamówienie sprzedaży**) do istniejącej faktury dla odbiorcy. Dokumenty dostawy i faktury powiązane z oboma zamówieniami mogą być przetwarzane indywidualnie. Na przykład nie trzeba generować dokumentu dostawy dla zamówienia zwrotu do dostawcy przed wygenerowaniem dokument dostawy dla zamówienia zwrotu od odbiorcy.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Zwroty za pomocą wysyłki z dostawą bezpośrednią między trzema stronami

Ten scenariusz można utworzyć, jeśli poprzednia sprzedaż typu **Dostawa bezpośrednia** została zakończona, a w firmie współpracującej z odbiorcą istnieje faktura wystawiona odbiorcy. Na poniższej ilustracji firma CompBuy uprzednio sprzedała produkty do odbiorcy Extern i wystawiła mu za to fakturę. Produkty zostały wysłane bezpośrednio z firmy CompSell do odbiorcy za pośrednictwem łańcucha zamówień międzyfirmowych.  

![Zwroty za pomocą wysyłki z dostawą bezpośrednią między trzema stronami](./media/SalesReturn08.png)

Jeśli odbiorca Extern chce zwrócić produkty, w firmie CompBuy jest dla niego tworzone zamówienie zwrotu (RMA02). Aby można było utworzyć łańcuch międzyfirmowy, zamówienie zwrotu musi być oznaczone dla dostawy bezpośredniej. Gdy użyjesz funkcji **Znajdź zamówienie sprzedaży**, aby wybrać fakturę odbiorcy do zwrotu, zostanie utworzony łańcucha zamówień międzyfirmowych składający się z następujących dokumentów:

-   **Oryginalne zamówienie zwrotu:** RMA02 (firmy CompBuy)
-   **Zamówienie zakupu:** PO02 (firmy CompBuy)
-   **Międzyfirmowe zamówienie zwrotu:** RMA\_00032 (firmy CompSell)

Po utworzeniu międzyfirmowego łańcucha dostawy bezpośredniej cała fizyczna obsługa i elektroniczne przetwarzanie zwrotów musi następować w kontekście międzyfirmowe zamówienie zwrotu RMA\_00032 w firmie CompSell. Produkty nie mogą być przyjmowane w firmie CompBuy. Po przypisaniu kodu dyspozycji do międzyfirmowego zamówienia zwrotu jest on synchronizowany z oryginalnym zamówieniem zwrotu, aby umożliwić właściwe fakturowanie oryginalnego zamówienia.

## <a name="post-to-the-ledger"></a>Księgowanie w księdze
Księgowania w księdze, które są generowane podczas fakturowania zamówienia zwrotu, zależą od kilku ważnych ustawień i parametrów:

-   **Koszt własny dla zwrotu** — W modelach zapasów innych niż **Koszt standardowy** parametr **Koszt własny dla zwrotu** określa koszt towaru, gdy jest on przyjmowany z powrotem do magazynu lub złomowany. Aby obliczyć poprawną wycenę zapasów, należy prawidłowo ustawić wartość parametru **Koszt własny dla zwrotu**. Jeśli używasz funkcji **Znajdź zamówienie sprzedaży** do tworzenia wiersza zamówienia zwrotu, który się odwołuje do faktury dla odbiorcy, wartość parametru **Koszt własny dla zwrotu** jest równa kosztowi własnemu sprzedawanego towaru. W przeciwnym wypadku wartość kosztu własnego pochodzi z konfiguracji towaru lub można ją wprowadzić ręcznie.
-   **Korekta z czerwonym stornem/Storno** — Parametr **Korekta z czerwonym stornem** na stronie **Księgowanie faktury** określa, czy księgowania powinny być rejestrowane jako zapisy dodatnie (po stronie winien/ma), czy jako zapisy korygujące (ujemne).

W przykładach poniżej koszt własny zwrotu jest reprezentowany jako **Inv. Cost price** (Koszt własny pozycji faktury).

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Przykład 1: Zamówienie zwrotu nie odwołuje się do faktury dla odbiorcy

Zamówienie zwrotu nie odwołuje się do faktury dla odbiorcy. Z tytułu zwrotu towaru jest uznawane konto odbiorcy. Parametr **Korekta z czerwonym stornem** nie jest zaznaczony podczas generowania faktury (lub faktury korygującej) do zamówienia zwrotu.  

![Zamówienie zwrotu nie odwołuje się do faktury dla odbiorcy](./media/SalesReturn09.png)  

>[Uwaga] Domyślną wartością parametru **Koszt własny dla zwrotu** jest cena z rekordu głównego towaru. Cena domyślna różni się od kosztu własnego w momencie wydawania zapasów. Ma to taką konsekwencję, że jest ponoszona strata wynosząca 3 jednostki pieniężne. Ponadto zamówienie zwrotu nie zawiera rabatu udzielonego odbiorcy w zamówieniu sprzedaży. W związku z tym następuje nadmierne uznanie konta odbiorcy.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Przykład 2: Dla zamówienia zwrotu wybrano korektę z czerwonym stornem

Przykład 2 jest taki sam, jak przykład 1, ale podczas generowania faktury do zamówienia zwrotu wybrano parametr **Korekta z czerwonym stornem**.  

![Zamówienie zwrotu z wybraną korektą z czerwonym stornem ](./media/SalesReturn10.png)  

>[Uwaga] Księgowania w księdze są wprowadzane jako ujemne korekty.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Przykład 3: Jest tworzony wiersz zamówienia zwrotu przy użyciu funkcji Znajdź zamówienie sprzedaży

W tym przykładzie jest tworzony wiersz zamówienia zwrotu przy użyciu funkcji **Znajdź zamówienie sprzedaży**. Podczas tworzenia faktury parametr **Korekta z czerwonym stornem** nie jest zaznaczony.  

![Wiersz zamówienia zwrotu tworzony przy użyciu funkcji Znajdź zamówienie sprzedaży ](./media/SalesReturn11.png)  

>[Uwaga] Opcje **Rabat** i **Koszt własny dla zwrotu** są poprawnie ustawione. W związku z tym następuje dokładne wycofanie faktury dla odbiorcy.



