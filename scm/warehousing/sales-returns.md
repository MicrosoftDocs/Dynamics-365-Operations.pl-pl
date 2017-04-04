---
title: "Zwroty sprzedaży"
description: "Ten temat zawiera informacje na temat procesu dla zamówienia zwrotu. Zawiera ona informacje o zwroty i ich wpływ na wyceny i dostępnych ilości zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Zwroty sprzedaży

Ten temat zawiera informacje na temat procesu dla zamówienia zwrotu. Zawiera ona informacje o zwroty i ich wpływ na wyceny i dostępnych ilości zapasów.

Klienci może zwracać elementy z różnych powodów. Na przykład element może być uszkodzony lub nie może spełniać oczekiwania klientów. Gdy klient wysyła żądanie zwrotu, rozpoczyna się proces zwrotu. Po odebraniu żądania klienta zamówienie zwrotu jest tworzony w programie Microsoft Dynamics 365 dla operacji.

## <a name="return-order-process"></a>Proces zamówienia zwrotu
Poniższa ilustracja przedstawia procesu zamówienia zwrotu.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Istnieją dwa typy procesu zamówienia zwrotu: fizyczne wróć i tylko kredytowe.

-   **Fizyczny zwrot** – zamówienie zwrotu autoryzuje fizyczny zwrot produktów.
-   **Tylko kredytowe** – zamówienie zwrotu autoryzuje kredyt klienta, ale nie wymaga, aby klient fizycznie zwrotu produktów.

### <a name="physical-return-order-process"></a>Procesu fizycznego zamówienia zwrotu

1.  **Utwórz zamówienie zwrotu.** Formalnie dokumentu autoryzacji dla klienta, aby zwrócić wszelkie produkty wadliwe lub niechciane. Zamówienie zwrotu nie wymaga, że firma zaakceptować zwróconych produktów lub udzielenia kredytu dla nabywcy. W przypadku przyjęcia zwrotu, można autoryzować wymienianego zapasu do wysłania, zanim wadliwych przesyłka została zwrócona.
2.  **Przybycie w magazynie dla kontroli.** Ukończ wstępnej kontroli i sprawdzania poprawności dokumentu zamówienia zwrotu. Zamówienie zwrotu obsługuje również kwarantanny zwróconych towarów dodatkowych inspekcji i kontroli jakości.
3.  **Określić dyspozycji.** Zakończyć proces kontroli i określić, co należy zrobić z zwróconych produktów. W ramach tego etapu zdecydować, czy użytkownik będzie Kredyt nabywcy, odrzucić zwrotu produktu lub przyjęcia zwrotu produktu, złom produktu i następnie wyśle produkt do klienta.
4.  **Generowanie dokumentu dostawy.** Generowanie dokumentu dostawy i zatwierdź decyzji dyspozycji, które wprowadzono w kroku 3. Można zakończyć procesów logistycznych.
5.  **Generowanie faktury.** Zamknij zamówienie zwrotu.

### <a name="credit-only-process"></a>Przetwarzaj, tylko kredytowe

1.  **Utwórz zamówienie zwrotu.** Formalnie dokumentu autoryzacji dla klienta, aby otrzymać kredyt bez powrotu produkty wadliwe lub niechciane. **Kredytu tylko** kod dyspozycji autoryzuje decyzji do odbiorcy bez fizycznego powrotu po stronie kredytowej.
2.  **Generowanie faktury.** Generowanie faktury korygującej, a następnie Zamknij zamówienie zwrotu.

## <a name="return-material-authorization"></a>Autoryzacja
Przetwarzanie zwrotu produkt (RMA) opiera się na funkcjonalność zamówienia sprzedaży. RMA jest zarejestrowany jako zamówienie zwrotu, która jest tworzona jako zamówienie sprzedaży i może mieć innego zamówienia sprzedaży skojarzone z nim o nazwie zamówienia wymiany. Zarówno zamówień sprzedaży powiązać pochodzących z numeru autoryzacji zwrotu.

-   **Zamówienie zwrotu** — Aby zarejestrować RMA, Utwórz zamówienie zwrotu jest zamówienie sprzedaży, która ma przypisany typ, **zwrócił zamówienia.** Wszelkie zmiany, które wprowadzasz do informacji autoryzacji zwrotu jest automatycznie aktualizowana w zamówieniu sprzedaży. Do czasu zamówienia zwrotu **Otwórz**, nie pojawią się na liście zamówień sprzedaży. Użyj RMA do obsługi przybycia i przyjęcia zwróconych towarów, jak również do autoryzowania kredytu tylko akcja dyspozycji (zobacz sekcja **kodów dyspozycji i akcje dyspozycji**). Wszystkie procesy uzupełniającego muszą być obsługiwane w zamówieniu sprzedaży.
-   **Zamówienie wymiany** — Kiedy zamówienie zastępcze muszą być wysłane do klienta, RMA może zawierać drugiego skojarzonego zamówienia sprzedaży. Można ręcznie utworzyć zamówienia wymiany dla RMA umożliwia natychmiastową wysyłkę. Alternatywnie zamówienie zastępcze mogą być tworzone automatycznie, po ukończeniu przyjazdu, inspekcji i przyjęcia dla pozycji RMA zawierający kod dyspozycji, który wskazuje wymiany. Zamówienie wymiany ma taką samą funkcjonalność, który jest skojarzony z zamówieniem sprzedaży. Na przykład służy on do konfigurowania niestandardowych produktu jako element zastępczy, utworzyć zlecenie produkcyjne do naprawy zwróconego towaru, tworzenie zamówienia zakupu dostawy bezpośredniej do wysyłania zastąpienia od dostawcy lub obsługi innych celów.

## <a name="create-a-return-order"></a>Tworzenie zamówienia zwrotu
Kiedy klient skontaktuje się danej organizacji, aby zwrócić produkt wadliwy lub niechciane i/lub ma być zapisana, rozpoczyna się proces zamówienia zwrotu. Po organizacji akceptuje zwrot, zwrot jest udokumentowane przez zamówienie zwrotu. To zamówienie zwrotu staje się centralnym punktem wewnętrzne przetwarzanie zwróconego produktu. Poniżej przedstawiono procedurę tworzenia zamówienia zwrotu.  

[![Procedura tworzenia zamówienia zwrotu](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Tworzenie nagłówka zamówienia zwrotu

Po utworzeniu zamówienia zwrotu musi zostać dołączone informacje w poniższej tabeli.

| Pole              | opis                                              | Komentarze                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konto odbiorcy   | Odwołanie do tabeli Klienci                       | Należy podać istniejące konto odbiorcy.                                                                                                                                                                                                                                                                                                  |
| Adres dostawy   | Adres, który element jest zwracany do                 | Domyślnie jest używana w adresie organizacji. Po zaznaczeniu określonego magazynu w nagłówku adresu dostawy jest zmieniany na adres dostawy z magazynu. Adres ten można zmienić na **szczegóły zamówienia zwrotu** strony.                                                                                                  |
| Oddział/magazyn     | Witryny lub magazyn, który odbiera zwracany produkt | Adres dostawy dla zamówienia zwrotu jest określana na podstawie adresu dostawy z witryny lub z magazynu.                                                                                                                                                                                                                                 |
| Numer autoryzacji zwrotu         | Identyfikator przypisany do zamówienia zwrotu              | Numer autoryzacji zwrotu jest używany jako klucza alternatywnego w całym procesie zamówienia zwrotu. Numer autoryzacji zwrotu, który jest przypisywany opiera się na sekwencji numerów RMA jest ustawiony na **rozrachunków z odbiorcami Parametry** strony.                                                                                                                              |
| Termin realizacji           | Ostatnia data może być zwrócony element               | Wartość domyślna jest obliczana jako data bieżąca plus okres ważności. Na przykład, jeśli znak powrotu jest prawidłowy tylko 90 dni od daty, gdy tworzone jest zamówienie zwrotu i zamówienie zwrotu zostało utworzone w dniu 1 maja, wartość w polu jest **30 lipca**. Okres ważności jest ustawiona na **rozrachunków z odbiorcami Parametry** strony. |
| Kod przyczyny zwrotu | Przyczyna zwrotu produktu przez klienta          | Kod przyczyny jest zaznaczone na liście kodów przyczyny zdefiniowane przez użytkownika. Pole to można aktualizować w dowolnym momencie.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Utwórz wiersze zamówienia zwrotu

Po zakończeniu nagłówku zwrotu można utworzyć wiersze zwrotu przy użyciu jednej z następujących metod:

-   Ręcznie wprowadź szczegóły elementu, ilość i innych informacji dla każdego wiersza zwrotu.
-   Utwórz wiersz zwrotu za pomocą **znajdowanie zamówienia sprzedaży** funkcji. Firma Microsoft zaleca, aby użyć tej funkcji podczas tworzenia zamówienia zwrotu. **Znajdowanie zamówienia sprzedaży** funkcja ustanawia odwołanie z wiersza zwrotu do wiersza zafakturowanego zamówienia sprzedaży i pobiera wiersza szczegółów, takich jak kod towaru, ilości, ceny, rabatu i wartości kosztów z wiersza sprzedaży. Odwołanie pomaga zagwarantować, że gdy produkt jest zwracany do firmy, to jest o wartości sam koszt jednostkowy to, że została sprzedana. Odwołanie sprawdza też, że zwrotu zamówienia nie są tworzone dla ilości, która przekracza ilość, która została sprzedana na fakturze.

**Uwaga:** wiersze zwrotu, które mają odniesienie do zamówienia sprzedaży są obsługiwane jako korekty lub zwiększenia sprzedaży. Aby uzyskać więcej informacji zobacz sekcję "Księgowanie w księdze", w dalszej części tego tematu.

### <a name="charges"></a>Opłaty

Prowizje i opłaty mogą być dodawane do zamówienia zwrotu za pośrednictwem jednego lub kilku z następujących metod:

-   Opłaty dodatkowe można ręcznie dodać do nagłówka zamówienia zwrotu i/lub wiersza zamówienia zwrotu.
-   Opłaty mogą być automatycznie dodawane do nagłówka zamówienia zwrotu jako funkcja kodu przyczyny zwrotu.
-   Opłaty mogą być automatycznie dodawane do wiersza zamówienia zwrotu, na podstawie kodu dyspozycji linii.

Opłaty dodatkowe są automatycznie dodawane po kodu przyczyny zwrotu lub kod dyspozycji jest przypisany do wiersza. Jeśli kod przyczyny zostanie później zmieniona, nie będzie można usunąć istniejący wpis bezpłatnie, ale nowy wpis opłat mogą zostać dodane, oparte na nowy kod przyczyny. Po dodaniu opłaty do wierszy zamówienia zwrotu opłat, które są obliczane jako procent wartości wiersza lub zlecenia ujemnych kiedy wiersza lub wiersza zlecenia jest ujemna, o ile procent również jest liczbą ujemną. Opłaty, która ma wartość ujemną reprezentuje zwrot do odbiorcy.

### <a name="return-reason-codes"></a>Kody przyczyn zwrotu

Zastosowanie kodów przyczyny do zwrotów, może pomóc ułatwiają analizowanie wzorców zwrotu. Kody przyczyn informują o Dlaczego klient chce przywrócić elementów. Niektóre organizacje mają wiele kodów przyczyn. Tych organizacji zgrupować kody przyczyny do grupy kod przyczyny, aby uzyskać lepszy przegląd i raportowaniu narastająco.

### <a name="disposition-codes-and-disposition-actions"></a>Kody dyspozycji i akcje dyspozycji

Ważny krok w procesie zamówienia zwrotu jest przypisanie kod dyspozycji do wiersza zamówienia zwrotu jako część rejestracji przyjęcia. Kod dyspozycji określa następujące informacje:

-   **Następstwa finansowe** – powinny zwiększać nabywcy za zwrócone towary i należy dodać wszelkie opłaty dodatkowe do wiersza zamówienia zwrotu?
-   **Dyspozycja zwróconego towaru** – należy element może być dodany do magazynu, powinien on zostać uznane za odpadki lub powinny to być zwrócone do klienta?
-   **Logistyka zwróconego towaru** – przedmiot zastępczy zaległego do odbiorcy?

Oprócz ustalenia, jak towary są unieszkodliwiane, kodów dyspozycji może powodować opłat, które mają być stosowane do wiersza zwrotu. Ich pomocą można również grupować zwraca do analizy statystycznej. Kody dyspozycji są definiowane jako część instalacji zamówień zwrotu. Jednak każdy kod dyspozycji musi odwoływać się jedną z czynności dyspozycji wbudowane. Poniższa tabela zawiera listę kodów dyspozycji wbudowane i ich działania. **Ważne:**, jeśli element nie powinny być zwrócone, ale klient wciąż powinna zostać zaksięgowana, przypisać **kredytu tylko** kod dyspozycji do wiersza zwrotu.

<table>
<thead>
<tr class="header">
<th>Kod dyspozycji</th>
<th>Następstwa finansowe</th>
<th>Wpływ na logistykę</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tylko kredytowe</td>
<td><ul>
<li>Klient jest po stronie kredytowej cena sprzedaży minus koszty lub opłaty.</li>
<li>Strata z likwidacji towaru jest księgowany w księdze.</li>
</ul></td>
<td>Element nie powinny być zwrócone. Ta akcja dyspozycji jest używany w następujących przypadkach:
<ul>
<li>Istnieje wystarczający zaufanie między stronami.</li>
<li>Koszty zwrotu towarów wadliwych są wygórowane.</li>
<li>Elementy nie można zezwolić na powrót do magazynu. Ze względu na inne warunki fizyczny zwrot nie jest wymagany.</li>
</ul></td>
</tr>
<tr class="even">
<td>Strona kredytowa</td>
<td><ul>
<li>Klient jest po stronie kredytowej cena sprzedaży minus koszty lub opłaty.</li>
<li>Wartość zapasów jest zwiększany o koszt zwróconego towaru.</li>
</ul></td>
<td>Element jest zwracany i dodany do magazynu.</td>
</tr>
<tr class="odd">
<td>Zastąp i zaksięguj po stronie kredytowej</td>
<td><ul>
<li>Klient jest po stronie kredytowej cena sprzedaży minus koszty lub opłaty.</li>
<li>Wartość zapasów jest zwiększany o koszt zwróconego towaru.</li>
<li>Oddzielne zamówienia sprzedaży dla wymiany jest tworzony i jest obsługiwane osobno.</li>
</ul></td>
<td>Element jest zwracany i dodany do magazynu.</td>
</tr>
<tr class="even">
<td>Zastąp i zlikwiduj</td>
<td><ul>
<li>Klient jest po stronie kredytowej cena sprzedaży minus koszty lub opłaty.</li>
<li>Strata z likwidacji towaru jest księgowany w księdze.</li>
<li>Oddzielne zamówienia sprzedaży dla wymiany jest tworzony i jest obsługiwane osobno.</li>
</ul></td>
<td>Element jest zwracany i uznane za odpadki.</td>
</tr>
<tr class="odd">
<td>Zwrot do odbiorcy</td>
<td>Brak, z wyjątkiem jakichkolwiek kosztów i opłat.</td>
<td>Element jest zwracany, ale jest wysyłany do klienta po kontroli. Ta akcja dyspozycji może być używany, jeśli element został umyślnie uszkodzony lub gwarancji został unieważniony.</td>
</tr>
<tr class="even">
<td>Odpadki</td>
<td><ul>
<li>Klient jest po stronie kredytowej cena sprzedaży minus koszty lub opłaty.</li>
<li>Strata z likwidacji towaru jest księgowany w księdze.</li>
</ul></td>
<td>Element jest zwracany lub uznane za odpadki.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Przybycia do magazynu dla inspekcji
Aby fizycznie otrzymywać zwróconych towarów do ewidencji magazynowej przez księgowanie dokumentu dostawy, elementy musi przejść przez rejestracji przyjęcia i opcjonalne inspekcji. Poniższa ilustracja przedstawia procesu przyjazdu. Następnych sekcjach opisano każdy krok, który jest wyświetlany na rysunku.  

[![Proces przyjazdu](./media/salesreturn03.png)](./media/salesreturn03.png)  

Proces składa się z kilku innych zmian, które nie są omówione w tym temacie. Oto niektóre z tych zmian:

-   Nie należy używać **przeglądu przyjęć** liście, aby utworzyć arkusz przyjęcia. Zamiast ręcznie utworzyć arkusza przyjęcia. Zwrotu zamówienia będą miały **zamówienie sprzedaży** jako punkt odniesienia.
-   Jeśli używasz zarządzania magazynem, generowanie transportów palet. Wiersz zwrotu będzie mieć stan **dostarczone** podczas transportu palet.
-   Zarejestrować przybycia zwróconego towaru bezpośrednio z wiersza zamówienia zwrotu za pomocą **rejestracji** funkcji.

Podczas procesu przyjęcia zwrotów są zintegrowane z ogólnego procesu do przyjęcia magazynowego. Proces przyjazdu umożliwia także tworzenie zleceń kwarantanny zwróconych towarów, które muszą zostać poddane kontroli oddzielne.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identyfikacji produktów na liście Przegląd przyjazdu

**Przeglądu przyjęć** stronie znajduje się lista wszystkich planowanych przyjazdów przychodzących. **Uwaga:** przywozów z zamówień zwrotu muszą być przetwarzane oddzielnie od innych typów transakcji przyjazdu. Po zidentyfikowaniu przychodzących pakietów na **przeglądu przyjęć** strona (na przykład za pomocą dokumentu towarzyszącego RMA), w okienku akcji, kliknij przycisk **Rozpocznij przyjęcie** do tworzenia i zainicjuj arkusz przyjęcia pasujący przybycia.

### <a name="edit-the-arrival-journal"></a>Edytowanie arkusza przyjęcia

Przez ustawienie **kwarantanny zarządzania** opcji w celu **tak**, można utworzyć zlecenie kwarantanny dla wiersza zwrotu. Jeśli wiersz został wysłany do kwarantanny do inspekcji, nie można określić kod dyspozycji. **Uwaga:** po ustawieniu **kwarantanny zarządzania** opcji w celu **tak** w grupy modeli magazynu towaru, **kwarantanny zarządzania** opcji na **wierszy dziennika** strony zostaną oznaczone do wiersza arkusza przyjęcia towaru i nie można zmienić. Jeśli wiersz jest przesyłany do kwarantanny, należy określić magazynu kwarantanny właściwe. Jeśli wiersz przyjęcia nie są wysyłane do kontroli, przyjazdu Magazynier musi określić kod dyspozycji bezpośrednio w wierszu arkusza przyjęcia, a następnie zaksięguj arkusza przyjęcia. Jeśli ten sam kod dyspozycji nie powinny być przypisane do całej ilości wiersza zwrotu lub pełną ilość w wierszu nie został otrzymany, możesz podzielić wiersz. Gdy podział wiersza arkusza przyjęcia towaru, również podzielić wiersz zwrotu (**SalesLine**) i utworzyć nowy identyfikator partii. Można podzielić wiersz, poprzez zmniejszenie ilości wiersza arkusza przyjęcia towaru. Po zaksięgowaniu arkusza utworzono nowy wiersz zwrotu, która ma stan **oczekiwana** na pozostałą ilość. Można także podzielić wiersz, klikając **funkcje**&gt;**podziału**.

### <a name="process-the-quarantine-order"></a>Przetwarzanie zlecenia kwarantanny

Jeśli zwróconych produktów są wysyłane do inspekcji w magazynie kwarantanny, zlecenie kwarantanny jest wykonywane żadnych dodatkowych czynności. Dla każdego wiersza przyjęcia, który jest przesyłany do kwarantanny jest tworzone jedno zamówienie kwarantanny. Kod dyspozycji wskazuje, w wyniku procesu kontroli. Można podzielić zlecenie kwarantanny, tak jak można podzielić arkusza przyjęcia. Dzielenie zlecenia kwarantanny, spowodować odpowiedniego podziału wiersza zwrotu. Po wprowadzeniu kodu dyspozycji zakończyć zlecenia kwarantanny przy użyciu formatu **koniec** funkcji lub **zgłoszone jako gotowe** funkcji. Jeśli wybierzesz **zgłoszone jako gotowe**, Nowy Nabytek jest tworzony w wyznaczonych magazynu. Ten przyjazdu może następnie przetwarzać przy użyciu **przeglądu przyjęć** strony. Jeżeli przybyciu pochodzi ze zlecenia kwarantanny, nie można zmienić kodu dyspozycji, które są przypisywane podczas inspekcji. Jeśli zlecenia kwarantanny, które możesz wykonać za pomocą **koniec** funkcji, partia jest automatycznie rejestrowany. Czasami element może być wysłana z kwarantanny do wysyłki i przyjęcia działu. Na przykład Inspektor kwarantanny może nie wiedzieć, gdzie do przechowywania towaru w magazynie. W takim przypadku odpowiednie dostawy należy zaktualizować poprawnie zarejestrować i działają na kod dyspozycji, która jest określona z powodu kwarantanny. Potwierdzenie odbioru mogą być wysyłane do klienta po zarejestrowaniu wiersza zwrotu. **Potwierdzenie zwrotu** raport podobny dokument zamówienia zwrotu. **Potwierdzenie zwrotu** raportu nie jest zapisany w arkuszu lub w przeciwnym razie zarejestrowanej w systemie i nie jest to wymaganym krokiem w procesie zamówienia zwrotu.

## <a name="replace-a-product"></a>Wymiana produktu
Istnieją dwie metody zarządzania wymiany produktów:

-   **Zamiennik zawczasu** – wymiany produktu przed zwracany produkt jest otrzymane od klienta.
-   **Zastąpienie przez kod dyspozycji** – automatycznie utworzyć nowy wiersz zamówienia wymiany.

### <a name="up-front-replacement"></a>Zamiennik zawczasu

W Zamiennik zawczasu element zastępczy mogą być dostarczane do nabywcy, zanim element zostanie zwrócony. Ta metoda jest przydatna, jeśli na przykład element jest część maszyny, których nie można usunąć, chyba że część zamienna jest dostępny na jej miejsce lub jeśli chcesz tylko klienta o produkt zastępczy możliwie jak najszybciej. Zamiennik zawczasu kolejność jest niezależne zamówienia sprzedaży. Informacje nagłówka jest od klienta, a informacje o wierszu jest inicjowany z zamówienia zwrotu. Można edytować, przetworzyć i usunąć zamówienie wymiany niezależnie od zamówienia zwrotu. Po usunięciu zamówienie zastępcze, pojawi się komunikat, że zamówienie zostało utworzone jako zamówienie zastępcze. Następująca ilustracja przedstawia proces dla Zamiennik zawczasu.  

[![Zamiennik zawczasu procesu](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

Zamówienie zwrotu zawiera odwołanie do zamówienia wymiany. Jeśli dla zamówienia zwrotu zamówienia Zamiennik zawczasu utworzono przed zwróceniem wadliwego elementu, nie można wybrać kodów dyspozycji do wymiany po wadliwych przesyłka została zwrócona.

### <a name="replacement-by-disposition-code"></a>Zastąpienie przez kod dyspozycji

Jeśli dostawy przedmiotu zastępczego do klienta i użyć **Zastąp i zlikwiduj** lub **zamienić i kredytu** akcja dyspozycji na zamówienie zwrotu, należy użyć procesu, który przedstawiono na poniższej ilustracji.  

[![Procedura wymiany, gdy używany jest kod dyspozycji](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

Element zastępczy będą dostarczane za pomocą niezależnych zamówienia sprzedaży, zamówienia sprzedaży wymiany. To zamówienie sprzedaży jest tworzony podczas generowania dokumentu dostawy dla zamówienia zwrotu. Nagłówek zamówienia używa informacji od nabywcy, do którego odwołuje się w nagłówku zamówienia zwrotu. Informacje o wierszu są zbierane od informacji wprowadzonej w **element zastępczy** strony. **Element zastępczy** strona musi być wypełniona dla wierszy, które mają działania dyspozycji, rozpoczynających się od słowa "Zamień". Jednakże ilość ani tożsamości element zastępczy nie jest zatwierdzone lub ograniczone. Takie zachowanie umożliwia dla przypadków, w których odbiorca chce otrzymywać tego samego towaru, ale w innej konfiguracji lub rozmiaru, a także przypadki gdzie klientów chce całkowicie inny element. Domyślnie wprowadzana jest identyczny towar **element zastępczy** strony. Można jednak wybrać inny element, pod warunkiem, że funkcja została prawidłowo skonfigurowana. **Uwaga:** można edytować i usuwać zamówienia sprzedaży wymiany po jego utworzeniu.

## <a name="generate-a-packing-slip"></a>Generowanie dokumentu dostawy
Zanim zwróconych towarów może być przyjęta do magazynu, należy zaktualizować dokument dostawy dla zamówienia, które elementy należą do. Podobnie, jak proces aktualizacji faktury jest aktualizacja transakcji finansowej, dokumentu dostawy aktualizacji proces jest fizycznej aktualizacji rekordu magazynowego. Innymi słowy proces ten zatwierdza zmiany do zapasów. W przypadku zwrotów, kroki, które są przypisane do dyspozycji działania są wykonywane podczas pakowania aktualizacji dokumentu dostawy. Podczas generowania dokumentu dostawy, zachodzą następujące zdarzenia:

-   W przypadku magazynu standardowego procesu służy do wykonywania fizycznego przychodu. Księgowań w księdze są generowane, gdy grupa modelu zapasów (**Księguj magazyn fizyczny**) i parametrów rozrachunków z odbiorcami (**Księgowanie dokumentów dostawy w księdze**) są prawidłowo ustawione.
-   Elementy, które zostały oznaczone akcja dyspozycji, które zawiera słowo "złom" zostały uznane za braki, a strata zapasów jest księgowany w księdze.
-   Elementy, które zostały oznaczone **zwrot do odbiorcy** akcja dyspozycji są odbierane i dostarczane do odbiorcy. Te elementy nie netto wpływają na zapasy.
-   Zamówienia sprzedaży dla wymiany jest tworzony. To zamówienie sprzedaży na podstawie informacji o **element zastępczy** strony.

Można wygenerować dostawy tylko dla wierszy, które mają stan zwrotu **zarejestrowane**i tylko w odniesieniu do całej ilości na wiersza zwrotu. Jeśli masz kilka wierszy w zamówieniu zwrotu **zarejestrowane** stanu, można wygenerować dokumentu dostawy dla podzbioru wierszy usuwając wiersze z **Księgowanie dokumentów dostawy** strony. Częściowe zwroty są definiowane zgodnie z wierszy zamówienia zwrotu, nie chodzi o dostawach zamówień zwrotu. W związku z tym jeśli otrzymujesz pełną ilość, która jest wskazany w jednym wierszu zamówienia zwrotu, ale nic nie otrzymują od innych wierszy w zamówieniu zwrotu, dostawa nie jest dostawa częściowa. Jednakże jeśli wiersza zamówienia zwrotu wymaga, by były zwracane 10 sztuk towaru, ale zostanie wyświetlony tylko cztery jednostki, dostawa jest dostawa częściowa. W przeciwnym razie przybyły oczekiwanego zwrotu towarów, można odłogowanych wysyłki i czekać na resztę zwracanej ilości. Alternatywnie można zarejestrować i zaksięgować częściowe ilości. Jako część procesu księgowania dokumentów dostawy numer dokumentu dostawy odniesienia z dokumentów dostawy odbiorcy można skojarzyć z wierszy zamówienia. To skojarzenie jest opcjonalny i jest tylko w celach informacyjnych. To nie tworzy żadnych aktualizacji transakcyjnej. Ogólnie, można pominąć pakowania dokumentu dostawy procesu i przejść bezpośrednio do fakturowania. W takim przypadku podczas fakturowania wykonywane są czynności, które będzie mieć wykonać podczas pakowania generowania dokumentu dostawy.

## <a name="generate-an-invoice"></a>Generuj fakturę
Chociaż **zamówienia zwrotu** strona zawiera informacje i akcje, które są wymagane w celu obsługi szczególne aspekty logistyczne zamówienia zwrotu, należy użyć **zamówienie sprzedaży** stronę, aby ukończyć proces fakturowania. Organizacji mogą następnie faktury zamówień sprzedaży i zamówień zwrotu, w tym samym czasie i tej samej osoby można ukończyć procesu fakturowania, zgodnie z wymaganiami. Aby wyświetlić zamówienia zwrotu z **zamówienie sprzedaży** strony, kliknij łącze odpowiednie dla numeru zamówienia sprzedaży otworzyć skojarzonego zamówienia sprzedaży. Zamówienie zwrotu można także znaleźć w **zamówienia sprzedaży wszystkich** strony. Zwrotu zamówienia są zamówień sprzedaży, które mają typ zamówienia z **zwrócone zamówienie**.

### <a name="credit-correction"></a>Korekta z czerwonym stornem

Jako część procesu fakturowania Sprawdź poprawność wszystkich opłat dodatkowych. Aby spowodować księgowań w księdze stać się korekt (Storno), należy rozważyć użycie **kredytu korekty** opcji na **innych** na karcie **Księgowanie faktury** strony podczas księgowania faktury/faktury korygującej. **Uwaga:** domyślnie **kredytu korekty** opcja jest aktywna, jeśli **faktury korygującej jako korekta** opcji na **rozrachunków z odbiorcami Parametry** strony zostało włączone. Firma Microsoft zaleca jednak nie Księguj zwraca wartość z Storno.

## <a name="create-intercompany-return-orders"></a>Tworzenie międzyfirmowych zamówień zwrotu
Zamówienia zwrotu mogą być wykonywane w przypadku dwóch przedsiębiorstw w obrębie organizacji. Obsługiwane są następujące scenariusze:

-   Proste zwraca międzyfirmowych między firmami, które uczestniczą w relacji międzyfirmowych
-   Łańcuch międzyfirmowy jest ustanawiane, gdy zamówienie zwrotu klienta jest tworzony w firmie sprzedającej
-   Łańcuch międzyfirmowy jest ustanawiane, gdy zamówienie zwrotu dostawcy jest tworzony w firmy kupującej
-   Zwraca dostawy bezpośredniej dostawy od odbiorcy zewnętrznego do dwóch przedsiębiorstw, które uczestniczą w relacji międzyfirmowych

### <a name="setup"></a>Konfiguracja

Poniższa ilustracja minimalnej konfiguracji, co jest wymagane dla dwóch przedsiębiorstw do udziału w relacji międzyfirmowych i skorzystać z handlu międzyfirmowego.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

W następującym scenariuszu CompBuy jest firmy kupującej i CompSell jest firma sprzedająca. Na ogół firma sprzedająca statki towarów do firmy kupującej albo, w scenariuszach dostawy Dostawa bezpośrednia, bezpośrednio do odbiorcy końcowego. W CompBuy, dostawca Międzyfirmowy\_CompSell jest zdefiniowany jako międzyfirmowego punktu końcowego, który jest skojarzony z firmy CompSell. W tym samym czasie, CompSell klienta IC\_CompBuy jest zdefiniowany jako międzyfirmowego punktu końcowego, który jest skojarzony z firmy CompBuy. Szczegóły zasad odpowiednich działań i mapowania wartości musi być zdefiniowana w obu firmach. W przypadku dostawy bezpośredniej dostawy międzyfirmowego zamówienia zwrotu, który jest również międzyfirmowego zamówienia sprzedaży, jest tworzony w firmie sprzedającej. Numer autoryzacji zwrotu z międzyfirmowego zamówienia zwrotu mogą być pobierane z sekwencji numerów RMA w CompSell, lub może zostać skopiowany z numeru autoryzacji zwrotu, który jest przypisany do oryginalnego zamówienia zwrotu w CompBuy. Ustawienia numeru autoryzacji zwrotu na **zapotrzebowanie zakupu** zasady dotyczące akcji w CompBuy określenia tych działań. Jeśli numer RMA jest synchronizowane, należy zaplanować załagodzić ryzyko kolizji numerów użycie dwóch przedsiębiorstw, ta sama sekwencja numerów.

### <a name="simple-intercompany-returns"></a>Proste zwraca międzyfirmowego

Ten scenariusz obejmuje dwa przedsiębiorstwa w tej samej organizacji, jak pokazano na poniższej ilustracji.  

[![Prostego powrotu międzyfirmowego](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

Łańcuch zamówienia może być ustalona, zamówienie zwrotu dostawcy jest tworzony w firmy kupującej lub zamówienie zwrotu klienta jest tworzony w firmie sprzedającej. Dynamics 365 dla operacji tworzy odpowiadające mu zamówienie w innej firmie i daje pewność, że nagłówek i informacje o wierszu na dostawcę zwrotu zamówienia odzwierciedla ustawienia na klienta zamówienia zwrotu. Zamówienie zwrotu, które zostało nawiązane można uwzględnić lub wykluczyć odwołania (**znajdowanie zamówienia sprzedaży**) do istniejącej faktury odbiorcy. Dostawy i fakturach zamówień dwóch mogą być przetwarzane pojedynczo. Na przykład nie musisz wygenerować dokumentu dostawy dla zamówienia zwrotu dostawcy przed wygenerowaniem dokument dostawy dla zamówienia zwrotu klienta.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Zwraca dostawy bezpośredniej przesyłki między trzema stronami

W tym scenariuszu można ustanowić, jeśli poprzedniego zbycie **dostawy bezpośrednie** typu zostało wypełnione oraz czy fakturę przed klienta znajduje się w firmie, która współdziała z klientem. Na poniższej ilustracji firmy CompBuy uprzednio sprzedanych i zafakturowanych produktów do odbiorcy zewnętrznego. Produkty zostały wysłane bezpośrednio z firmy CompSell do klienta za pośrednictwem łańcucha zamówień międzyfirmowych.  

[![Zwraca dostawy bezpośredniej przesyłki między trzema stronami](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Jeśli klient Extern chce wrócić do produktów, zamówienia zwrotu (RMA02) jest tworzony dla odbiorcy w firmie CompBuy. Ustanowienie łańcucha międzyfirmowego zamówienia zwrotu musi być zaznaczona dla dostawy bezpośredniej. Użycie **znajdowanie zamówienia sprzedaży** funkcji, aby wybrać faktury odbiorcy, aby powrócić, ustanawia się łańcuch zamówienia międzyfirmowego, który składa się z następujących dokumentów:

-   **Oryginalne zamówienie zwrotu:** RMA02 (firmy CompBuy)
-   **Zamówienie zakupu:** PO02 (firmy CompBuy)
-   **Międzyfirmowe zamówienie zwrotu:** RMA\_00032 (spółka CompSell)

Po utworzeniu łańcucha międzyfirmowego dostawa bezpośrednia, wszystkie czynności magazynowych i przetwarzania danych musi wystąpić w kontekście międzyfirmowe zamówienie zwrotu RMA\_00032 w firmie CompSell. Nie można odebrać produkty w firmie CompBuy. Kod dyspozycji jest przypisany do międzyfirmowego zamówienia zwrotu, jest synchronizowana z oryginalnego zamówienia zwrotu do umożliwienia właściwego Fakturowanie oryginalnego zamówienia.

## <a name="post-to-the-ledger"></a>Księgowanie w księdze
Księgowania w finansach, które są generowane po zafakturowaniu zamówienia zwrotu są pod wpływem kilka ważnych ustawień i parametrów:

-   **Koszt własny dla zwrotu** -magazynu modeli innych niż **koszt standardowy**, **koszt własny dla zwrotu** parametr określa koszt towaru, gdy przyjęte do magazynu lub uznane za odpadki. Aby obliczyć poprawne wyceny zapasów, jest ważne, aby ustawić **koszt własny dla zwrotu** parametr poprawnie. Jeśli używasz **znajdowanie zamówienia sprzedaży** funkcja służąca do tworzenia wiersza zamówienia zwrotu, który odwołuje się do faktury dla odbiorcy **koszt własny dla zwrotu** wartość jest równa kosztowi własnemu towaru, który jest sprzedawany. W przeciwnym wypadku wartość kosztu własnego pochodzi z ustawień towaru lub można wprowadzić ręcznie.
-   **Kredyt korekcji/Storno** — **kredytu korekty** parametru na **Księgowanie faktury** strona określa, czy komentarze powinny być zarejestrowane jako zapisy dodatnie (Dt/Ct) lub poprawiania, negatywnych wpisów.

W przykładach, które należy wykonać, koszt własny zwrotu jest reprezentowany jako **kalkulacji kosztu własnego**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Przykład 1: Zamówienie zwrotu nie odwoływać się fakturę dla odbiorcy

Zamówienie zwrotu nie odwoływać się do faktury dla odbiorcy. Zwrot towaru jest po stronie kredytowej. **Kredytu korekty** parametr nie jest zaznaczona, podczas generowania zamówienia zwrotu, faktury lub faktury korygującej.  

[![Zamówienie zwrotu nie odwoływać zaliczkową klienta](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Uwaga:** cenę wzorca jest używana jako wartość domyślna dla **koszt własny dla zwrotu** parametru. Domyślna cena różni się od kosztu własnego w momencie wydania zapasów. W związku z tym implikacją jest, że zostały poniesione straty 3. Ponadto zamówienia zwrotu nie zawiera rabat, który zostało udzielone klientowi w zamówieniu sprzedaży. W związku z tym występuje nadmierne kredytu.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Przykład 2: Korekta strony kredytowej jest zaznaczone dla zamówienia zwrotu

Przykład 2 jest taki sam, jak w przykładzie 1, ale **kredytu korekty** parametr jest wybrany, gdy generowane faktury zamówienia zwrotu.  

[![Zamówienie zwrotu z wybranym z czerwonym stornem](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Uwaga:** księgowań w księdze są wprowadzane jako korekty.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Przykład 3: Wiersza zamówienia zwrotu jest tworzony przy użyciu funkcji Znajdź zamówienie sprzedaży

W tym przykładzie wiersza zamówienia zwrotu jest tworzony przy użyciu **znajdowanie zamówienia sprzedaży** funkcji. **Kredytu korekty** parametr nie jest zaznaczona, podczas tworzenia faktury.  

[![Zwraca wiersza zamówienia, który jest tworzony przy użyciu Znajdź zamówienie sprzedaży](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Uwaga:****rabatu** i **koszt własny dla zwrotu** są poprawnie ustawione. W związku z tym występuje dokładne odwrócenie faktury odbiorcy.


