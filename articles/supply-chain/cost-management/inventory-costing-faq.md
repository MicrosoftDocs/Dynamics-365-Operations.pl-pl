---
title: Wycena zapasów – FAQ
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące kosztorysowania zapasów w programie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45f65bd4a5cfb9bd0c4eb03ceb56eca452f6ec95
ms.sourcegitcommit: cbe9493d479f96f271d94599ec1b85131b26169f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809292"
---
# <a name="inventory-costing-faq"></a>Wycena zapasów – FAQ

[!include [banner](../includes/banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące kosztorysowania zapasów w programie Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Zamknięcie zapasów, korekty i przeliczenia

### <a name="is-the-inventory-close-required"></a>Czy wymagane jest zamknięcie zapasów?

Jeśli planujesz korzystać z funkcji archiwizacji zapasów, wymagane jest zamknięcie zapasów. Jeśli nie planujesz korzystać z funkcji archiwizacji zapasów, zdecydowanie zalecamy, abyś nadal przeprowadzał zamknięcie inwentaryzacji, niezależnie od modeli kalkulacji kosztów, których używasz.

### <a name="how-often-should-the-inventory-close-be-run"></a>Jak często powinno być uruchamiane zamykanie zapasów?

Zamknięcie inwentaryzacji powinno być przeprowadzane co najmniej raz na okres księgi. Na przykład, jeśli twoja księga jest ustawiona na kalendarz fiskalny oparty na miesiącu kalendarzowym, powinieneś przeprowadzać zamknięcie inwentaryzacji raz w miesiącu.

### <a name="is-the-inventory-recalculation-required"></a>Czy wymagane jest ponowne przeliczenie zapasów?

Nie, przeliczanie zapasów nie jest wymagane. Jeśli stosujesz model rachunku kosztów okresowych, taki jak pierwsze weszło, pierwsze wyszło (FIFO), ostatnie weszło, pierwsze wyszło (LIFO) lub średnia ważona, powinieneś dokładnie rozważyć, czy będziesz przeprowadzał przeliczanie zapasów. Może zapewnić dokładniejsze wyliczanie kosztów w modelach heurystycznych, które wybrałeś.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>Jak często powinno być uruchamiane ponowne szacowanie zapasów?

Jeśli planujesz przeprowadzać przeliczanie stanów magazynowych, zalecamy, byś rozważył przeprowadzanie go codziennie jako procesu wsadowego. Jeśli Twoja organizacja nie wymaga częstego raportowania wartości zapasów dla modeli rachunku kosztów okresowych, możesz rozważyć rzadsze wykonywanie obliczeń zapasów.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>Kiedy należy użyć korekty stanu zapasów na stanie magazynowym na stronie Zamknięcie i korekty?

Korektę stanów magazynowych w toku można przeprowadzić dopiero po zakończeniu zamknięcia magazynu. Zazwyczaj jest on uruchamiany w dniu następującym po ostatnim zamknięciu. Korekta stanu magazynowego może korygować tylko zapasy, które są jeszcze w posiadaniu na dzień, w którym przeprowadzasz korektę.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>Kiedy należy użyć korekty transakcji inwentaryzacji na stronie Zamknięcia i korekty?

Przed przeprowadzeniem zamknięcia inwentaryzacji powinieneś użyć korekty transakcji inwentaryzacyjnych. Zazwyczaj używa się go, by poprawić błędny odbiór. Nie możesz zamieścić korekty transakcji magazynowej po przeprowadzeniu zamknięcia inwentaryzacji i rozliczeniu transakcji.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>Czy zwroty zamówień zakupu są traktowane jak inne sprawy podczas zamknięcia inwentaryzacji?

Tak. Pokwitowanie zamówienia zakupu to sprawa, która jest rozliczana z pokwitowaniem w modelu heurystycznym, który wybrałeś dla danej pozycji. Jeśli używasz modelu rachunku kosztów okresowych, możesz użyć znakowania, aby zastąpić koszt heurystyczny.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>Co dzieje się ze zwrotami zamówień sprzedaży podczas zamknięcia inwentaryzacji?

Kiedy przeprowadzasz zamknięcie inwentaryzacji, zwrot zamówienia sprzedaży jest traktowany jak przyjęcie do inwentaryzacji. Zagadnienia są rozliczane z inwentarzem w oparciu o model heurystyczny, który wybierzesz dla danej pozycji.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Jakiej ceny kosztu używa się przy zwrocie zamówienia sprzedaży?

Kiedy tworzysz zwrot związany z zamówieniem sprzedaży, wartość pola **Cena jednostkowa** jest kopiowana z oryginalnego zamówienia sprzedaży, a pole **Cena kosztu zwrotu** na zwrocie jest ustawiane na skorygowaną cenę kosztu z oryginalnej transakcji inwentaryzacyjnej dla wiersza zamówienia sprzedaży, który jest zwracany. Jeśli opcja **Wartość otwarta** dla powiązanej transakcji inwentaryzacyjnej jest ustawiona na *Tak*, zamknięcie inwentaryzacji może spowodować aktualizację kosztu wydania na oryginalnym zleceniu sprzedaży. W tym scenariuszu pole **Cena kosztu zwrotu** nie jest aktualizowane. Jednak gdy opublikujesz kartę pakowania zamówienia zwrotnego, system sprawdzi cenę kosztu i użyje zaktualizowanego kosztu na transakcji inwentaryzacji zwrotnej.

W przypadku zwrotu pozycji kosztu standardowego, która jest powiązana z zamówieniem sprzedaży, system użyje kosztu standardowego z czasu pierwotnego zamówienia sprzedaży, nawet jeśli dla danej pozycji jest aktywny nowy koszt standardowy.

Kiedy tworzysz zwrot, który nie jest związany z zamówieniem sprzedaży, pole **Cena kosztu zwrotu** jest ustawiane na aktywną cenę przedmiotu, jaką masz dla niego w witrynie, dla której tworzysz zamówienie zwrotu. Jeśli nie masz aktywnej ceny kosztu w wersji kalkulacji kosztów dla danego artykułu, wartość ta będzie równa 0 (zero). Jeśli pozostawisz tę wartość jako 0 (zero), otrzymasz ostrzeżenie, że nie określono ID partii zwrotnej lub ceny kosztu zwrotu.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Jaka jest oczekiwana wydajność zamknięcia magazynu?

Wiele czynników może wpłynąć na wydajność zamknięcia zapasów. Czynniki te obejmują całkowitą liczbę pozycji, całkowitą liczbę transakcji w okresie, modele inwentaryzacji, których używasz, oraz liczbę pomocników partii, które konfigurujesz w parametrach inwentaryzacji i zarządzania magazynem. Możesz się spodziewać, że zamknięcie może trwać od kilku minut do kilku godzin. Nie ma konkretnych wskazówek co do czasu, jaki powinien upłynąć do zamknięcia. Powinieneś określić swoje niefunkcjonalne wymagania biznesowe dotyczące przeprowadzania zamknięcia inwentaryzacji i ściśle współpracować z partnerem, aby określić harmonogram przeprowadzania procesu zamknięcia inwentaryzacji. Jeśli doświadczysz niespodziewanie niskiej wydajności procesu zamykania zapasów, powinieneś otworzyć zgłoszenie do pomocy technicznej.

## <a name="costing-sheet-and-indirect-costs"></a>Arkusz kalkulacyjny i koszty pośrednie

### <a name="which-costing-models-support-the-costing-sheet"></a>Które modele wyceny obsługują arkusz wyceny?

Chociaż arkusz kalkulacji kosztów jest najczęściej używany w organizacjach, które stosują standardowy rachunek kosztów, możesz go używać z każdym modelem kalkulacji kosztów, który jest dostępny w Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Czy mogę mieć wiele arkuszy wyceny dla różnych części mojej organizacji?

Nie Można mieć tylko jeden arkusz wyceny dla firmy.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Czy dla każdego miejsca można utworzyć różne arkusze wyceny?

Nie, nie możesz mieć różnych arkuszy kalkulacyjnych dla różnej placówki. Dla każdej osoby prawnej możesz utworzyć tylko jeden arkusz kalkulacji kosztów. Możesz jednak skonfigurować węzły całkowite, grupy kosztów lub węzły kosztów pośrednich na stronę. Ta konfiguracja jest procesem ręcznym i musisz zachować hierarchię i przypisanie pozycji w arkuszu kalkulacji kosztów, gdy następują zmiany organizacyjne lub operacyjne. Jeśli pojedyncza pozycja jest produkowana lub kupowana w więcej niż jednym miejscu, nie ma mechanizmu, który pozwoliłby ci traktować tę pozycję inaczej w arkuszu kalkulacji kosztów dla każdego miejsca. Dodatkowo pamiętaj, że wszystkie kody kosztów pośrednich mają stawkę lub dopłatę, która jest zdefiniowana w twojej wersji rachunku kosztów. Koszty, które określasz, są zawsze specyficzne dla danej placówki.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Czy można dezaktywować i aktywować wersje arkusza wyceny?

Wprawdzie dla arkusza wyceny nie jest zachowywana żadna szczegółowa historia wersji, można jednak wprowadzać zmiany w arkuszu wyceny, a następnie, gdy jest gotowy, zapisywać i sprawdzać poprawność arkusza. Nie istnieje mechanizm, który umożliwia powrót do starszej wersji arkusza wyceny lub wyświetlenie zmian w nim wprowadzonych. Jeśli zaczniesz wprowadzać zmiany i nie chcesz, by weszły one w życie, możesz zamknąć stronę bez zapisywania i zatwierdzania zmian. Zostaniesz poproszony o odrzucenie zmian.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Czy mogę utworzyć koszty pośrednie dla każdej pozycji?

W arkuszu kalkulacji kosztów możesz tworzyć kody kosztów pośrednich, w których pole **Typ węzła** jest ustawione na *Dopłata*, *Stawka* lub *Jednostka wyjściowa*. Możesz wtedy zdefiniować stawkę lub dopłatę tak, by była ona specyficzna dla numeru artykułu. Na skróconej karcie **Stawka** lub **Dopłata** dodaj wiersz do siatki. Ustaw pole **Ważne dla** na *Stół*, a pole **Relacja** na konkretny numer elementu.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Czy mogę utworzyć koszt pośredni, który nie jest związany z konkretną pozycją?

Tak. Możesz utworzyć kod kosztu pośredniego, w którym pole **Typ węzła** jest ustawione na *Oparte na jednostkach wyjściowych*. Następnie możesz ustawić w polu **Podtyp** wartość *ilość*, *waga* lub *objętość*, aby określić ilość, wagę lub objętość produkowanego przedmiotu. Stawka, którą określisz na skróconej karcie **Stawka**, zostanie zastosowana do podtypu, który wybrałeś. Na przykład ustawiasz w polu **Podtyp** wartość *ilość*, a w polu **Stawka** wartość *1,00 USD*, a następnie tworzysz zlecenie produkcyjne lub zbiorcze na 10 sztuk. W tym przypadku koszt pośredni, który zostanie dodany do wyrobu gotowego, wynosi 10,00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Czy mogę użyć arkusza kalkulacji kosztów, aby podzielić koszty produkcji na godziny i materiały?

Tak. W arkuszu kalkulacji kosztów możesz utworzyć węzły **Całkowite**, aby rozdzielić koszty według dowolnych grup, które wybierzesz. Na przykład możesz utworzyć jeden węzeł **Suma** o nazwie *Godziny* i drugi o nazwie *Materiały*. W węźle **Godziny** dodaj każdą grupę kodów, która jest związana z twoimi godzinami. W węźle **Materiały** dodaj każdą grupę kosztów, która jest związana z twoimi materiałami.

## <a name="dimension-groups"></a>Grupy wymiarów

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Czy mogę zarządzać kosztami na poziomie partii lub numeru seryjnego?

Tak, jeśli używasz modelu rachunku kosztów okresowych, takiego jak FIFO, LIFO, LIFO data, średnia ważona lub średnia ważona data, możesz włączyć opcję **Inwentaryzacja finansowa** dla wymiaru **Seria** lub **Numer seryjny** w grupie wymiarów śledzenia, aby śledzić koszty na poziomie szczegółowym.

### <a name="can-i-manage-costs-at-the-location-level"></a>Czy można zarządzać kosztami na poziomie lokalizacji?

Nie, nie można włączyć opcji **Magazyn finansowy** dla wymiaru **Lokalizacja** w grupie wymiarów magazynowania. Jeśli Twoja organizacja musi śledzić koszty na bardziej szczegółowym poziomie, zastanów się, czy możesz utworzyć wirtualne magazyny, a następnie wybierz opcję **Inwentaryzacja finansowa** dla wymiaru **Magazyn** w swojej grupie wymiarów magazynowych.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Czy powinienem włączyć opcję Użyj procesów zarządzania magazynem dla grupy wymiarów magazynowych?

Jeśli uważasz, że w przyszłości możesz chcieć korzystać z zaawansowanych funkcji zarządzania magazynem, powinieneś włączyć opcję **Używaj procesów zarządzania magazynem**. Po zapisaniu grupy wymiarów magazynowych nie można już zmienić dla niej ustawienia opcji **Używaj procesów zarządzania magazynem**. Jeśli zdecydujesz się na używanie procesów zarządzania magazynem później, będziesz musiał stworzyć nowy magazyn, w którym opcja ta będzie włączona. Nie istnieje żaden zautomatyzowany proces, którego możesz użyć, aby przenieść wszystkie zapasy z jednego magazynu do drugiego lub skopiować związane z nimi konfiguracje do nowego magazynu.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>Czy mogę włączyć opcję Używaj procesów zarządzania magazynem dla grupy wymiarów magazynowych, nawet jeśli nie zamierzam używać zaawansowanego magazynowania?

Tak, nawet jeśli nie planujesz korzystać z zaawansowanych funkcji zarządzania magazynem, możesz włączyć opcję **Używaj procesów zarządzania magazynem** dla grupy wymiarów magazynowych. Aby tworzyć i przetwarzać transakcje, musisz wykonać minimalną konfigurację, taką jak hierarchie rezerwacji i grupy sekwencji jednostek. Jednak ustawienia dla zaawansowanego magazynowania są zazwyczaj ignorowane podczas ręcznego przetwarzania list pobrań, listów przewozowych i potwierdzeń odbioru produktów (np. na stronach zamówień sprzedaży i zamówień zakupu).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Kiedy należy włączyć opcję Spis fizycznych zapasów dla grupy wymiarów przechowywania lub śledzenia?

Powinieneś włączyć opcję **Zapasów fizycznych** dla grup wymiarów przechowywania i śledzenia, jeśli musisz prowadzić szczegółową ewidencję zapasów fizycznych w oparciu o ten wymiar. Zazwyczaj każdy wymiar, który jest aktywny, będzie również śledzony fizycznie. Dlatego każdy odbiór, wydanie lub ruch zapasów będzie śledzony przez wybrany wymiar. Jeśli wymiar nie jest obowiązkowy (np. tablica rejestracyjna), możesz włączyć opcje **Dozwolone puste pokwitowanie** i **Dozwolone puste wydanie**, aby umożliwić użytkownikom przyjmowanie, wydawanie i przenoszenie zapasów, nawet jeśli wymiar nie jest określony.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Kiedy należy włączyć opcję Spis zapasów finansowych dla grupy wymiarów przechowywania lub śledzenia?

Powinieneś włączyć opcję **Zapasy finansowe** dla grup wymiarów przechowywania i śledzenia, jeśli musisz prowadzić szczegółową ewidencję zapasów finansowych w oparciu o ten wymiar. Wymiary **Placówka** są zawsze monitorowane finansowo, podczas gdy inne wymiary są opcjonalne w monitorowaniu finansowym. Jeśli używasz modelu rachunku kosztów okresowych, takiego jak FIFO, LIFO lub średnia ważona, włączenie opcji **Zapasy finansowe** dla wymiaru oznacza, że będziesz dokonywać rozliczeń tylko w przypadkach, gdy przyjęcie i wydanie mają takie same wartości wymiaru. Na przykład, jeśli włączysz opcję **Zapasy finansowe** dla wymiaru **Magazyn**, w każdym magazynie będziesz miał inny koszt, a przyjęcia i wydania z różnych magazynów nie będą mogły być rozliczane.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Czy mogę wprowadzać zmiany w grupie wymiarów produktu, magazynowania lub śledzenia po zaistnieniu transakcji?

Po utworzeniu grupy modeli artykułów możesz zmienić ustawienia pól **Plan pokrycia według wymiarów**, **Dla cen zakupu** i **Dla cen sprzedaży**, jeśli dla wymiaru w grupie modeli artykułów jest zaznaczone pole wyboru **Aktywny**. Żadne inne zmiany nie są dozwolone. Na przykład nie możesz włączyć ani wyłączyć opcji **Aktywny**, **Dozwolone puste wydanie**, **Dozwolone puste pokwitowanie**, **Zapasy fizyczne** i **Zapasy finansowe**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Czy mogę zmienić grupę wymiarów produktu, przechowywania lub śledzenia dla wydanego produktu?

Jeśli stan magazynowy dla danego produktu wynosi 0 (zero), a opcja **Wartość otwarta** jest ustawiona na *Nie* dla wszystkich transakcji inwentaryzacyjnych, możesz zmienić grupy wymiarów przechowywania i śledzenia na stronie zwolnionej produkcji. Nie możesz zmienić grupy wymiarów produktu po utworzeniu rekordu.

## <a name="item-model-groups"></a>Grupy modeli pozycji

### <a name="when-should-i-enable-the-stocked-product-option"></a>Kiedy powinienem włączyć opcję Produkt magazynowany?

Powinieneś włączyć opcję **Produkt magazynowany** dla każdego elementu, który będzie śledzony w twoim inwentarzu. Gdy ta opcja jest włączona, przechowywane są szczegółowe transakcje inwentaryzacyjne, które śledzą odbiór i wydanie przedmiotu. Ta opcja jest zazwyczaj włączana dla każdego przedmiotu materialnego, który przechowujesz na przykład w swoim magazynie. Powinieneś także włączyć tę opcję, jeśli planujesz dodawać do zestawień materiałów (BOM) lub formuł pozycje niematerialne, takie jak pozycje usługowe. Jeśli nie włączysz opcji **Zaopatrzony produkt**, żadne transakcje inwentaryzacyjne nie są śledzone w księdze pomocniczej inwentaryzacji, a koszt pozycji jest zazwyczaj odpisywany do księgi głównej. Ta opcja jest często używana, na przykład, do zaopatrzenia sklepu lub usług, które nie są uwzględnione w twoich zestawieniach materiałowych lub formułach.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>Kiedy powinienem włączyć opcję Księguj zapasy fizyczne?

Opcja **Księgowanie zapasów fizycznych** jest zazwyczaj włączona, gdy włączona jest opcja **Produkty magazynowane**. Gdy włączysz tę opcję, system będzie śledził fizyczną aktualizację pozycji na transakcji magazynowej. Opcja ta jest używana w koordynacji z parametrami w kontach zobowiązań, należności i kontroli produkcji, które określają, że aktualizacja fizyczna powinna tworzyć voucher. Zazwyczaj włączasz tę opcję, gdy chcesz, by księga była aktualizowana za każdym razem, gdy fizycznie aktualizujesz stany magazynowe. Jeśli Supply Chain Management nie jest Twoim systemem ewidencji danych finansowych, możesz wyłączyć tę opcję.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>Kiedy powinienem włączyć opcję Księguj zapasy finansowe?

Opcja **Księgowanie zapasów finansowych** jest zazwyczaj włączona, gdy włączona jest opcja **Produkty magazynowane**. Opcja ta jest używana w koordynacji z parametrami w kontach zobowiązań, należności i kontroli produkcji, które określają, że aktualizacja finansowa powinna tworzyć voucher. Zazwyczaj włączasz tę opcję, gdy chcesz, by księga była aktualizowana za każdym razem, gdy finansowo aktualizujesz stany magazynowe (np. fakturując zlecenia sprzedaży i zamówienia zakupu lub kończąc zlecenie produkcyjne). Jeśli Supply Chain Management nie jest Twoim systemem ewidencji danych finansowych, możesz wyłączyć tę opcję.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>Kiedy należy włączyć opcję księgowania na koncie przychodów przyszłych okresów w momencie dostawy?

Używasz opcji **Przeksięgowanie na konto przychodów przyszłych okresów w momencie dostawy**, aby wskazać, czy chcesz rozpoznać przychód w księdze głównej, gdy zaksięgujesz dokument dostawy dla zamówienia sprzedaży. Tej opcji używa się zwykle, gdy między listem przewozowym a fakturą za zamówienie sprzedaży jest duży odstęp czasu lub gdy nie jest możliwe zafakturowanie wszystkich zamówień sprzedaży w danym okresie. Zazwyczaj wyłączasz tę opcję, jeśli faktury z zamówień sprzedaży są księgowane zaraz po wysłaniu listu przewozowego. W ten sposób unikniesz generowania dodatkowych księgowań w księdze głównej, które zostaną natychmiast odwrócone, gdy wystawisz fakturę na zamówienie sprzedaży.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>Kiedy należy włączyć opcję naliczania zobowiązań przy odbiorze produktu?

W większości organizacji będziesz chciał włączyć opcję **Naliczenie zobowiązania przy odbiorze produktu** dla wszystkich grup modeli artykułów, niezależnie od tego, czy masz produkt magazynowany, czy nie. Ta opcja służy do księgowania naliczenia w księdze głównej na podstawie ceny dokumentu przyjęcia produktów. Ponieważ zazwyczaj występuje opóźnienie między zaksięgowaniem przyjęcia produktu w ramach zamówienia zakupu a zaksięgowaniem faktury, większość organizacji musi ująć zobowiązanie w bilansie, aby zachować zgodność z lokalnymi przepisami, takimi jak ogólnie przyjęte praktyki księgowe (GAAP). Jeśli Supply Chain Management nie jest Twoim systemem ewidencji danych finansowych, możesz wyłączyć tę opcję. Jeśli Twoja organizacja używa kategorii zakupowych na zamówieniach zakupu, możesz kontrolować wymóg naliczania kosztów poprzez włączenie opcji **Rozliczaj koszty zakupu przy odbiorze** dla reguły polityki kategorii na stronie **Polityki zakupowe**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Jak mogę uniemożliwić użytkownikowi wysłanie potwierdzenia zakupu produktu z zamówienia, jeśli rejestracja potwierdzenia nie została jeszcze wysłana?

Możesz uniemożliwić użytkownikowi zaksięgowanie odbioru produktu zamówienia zakupu, jeśli rejestracja zamówienia zakupu jeszcze nie nastąpiła, włączając opcję **Wymagania rejestracji** dla grupy modelu artykułu. Ta opcja jest zwykle używana w organizacjach, które stosują dwuetapowy proces odbierania lub w sytuacjach, gdy musisz zarejestrować np. numer partii lub serii na odbieranych przedmiotach. Opcja **Wymóg rejestracji** ma zastosowanie do *wszystkich* kwitów inwentaryzacyjnych dla danej pozycji, a nie tylko do zamówień zakupu. Na przykład ma ono zastosowanie do arkusza magazynowego z ilością dodatnią oraz do arkusza zlecenia produkcyjnego, który jest zgłaszany jako gotowy.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Jak mogę uniemożliwić użytkownikowi zaksięgowanie faktury za zamówienie zakupu, jeśli odbiór nie został jeszcze zaksięgowany?

Możesz uniemożliwić użytkownikowi zaksięgowanie faktury produktu zamówienia zakupu, jeśli rejestracja odbioru produktu jeszcze nie nastąpiła, włączając opcję **Wymagania dotyczące przyjmowania** dla grupy modelu artykułu. Ta opcja jest zwykle używana w organizacjach, które wymagają, aby wpływy były fizycznie ujmowane w księdze głównej dla rozliczeń międzyokresowych. Opcja **Wymóg przyjęcia** ma zastosowanie do *wszystkich* kwitów inwentaryzacyjnych dla danej pozycji, a nie tylko do zamówień zakupu. Na przykład ma ono zastosowanie do arkusza magazynowego z ilością dodatnią oraz do arkusza zlecenia produkcyjnego, który jest zgłaszany jako gotowy. Jeśli Twoja organizacja używa kategorii zakupowych na odbiorach, możesz kontrolować wymóg naliczania kosztów poprzez włączenie opcji **Wymagania dotyczące przyjmowania** dla reguły polityki kategorii na stronie **Polityki zakupowe**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Jak uniemożliwić użytkownikowi wysłanie dokumentu pakowania, jeśli lista kompletacji zamówienia sprzedaży nie została jeszcze wysłana?

Możesz uniemożliwić użytkownikowi wysłanie listu przewozowego lub faktury, jeśli nie została jeszcze utworzona lista kompletacji zamówienia sprzedaży, włączając opcję **Wymagania pobierania** dla grupy modelu artykułu. Ta opcja jest zwykle używana w organizacjach, które przeprowadzają fizyczny proces kompletacji w magazynie (np. używając urządzenia mobilnego w magazynie do kompletacji). Opcja **Wymóg pobrania** ma zastosowanie do *wszystkich* spraw inwentaryzacyjnych dla danego przedmiotu, a nie tylko zleceń sprzedaży. Na przykład dotyczy to arkusza inwentaryzacji, który ma ilość ujemną oraz arkusza listy pobrań zlecenia produkcyjnego.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Jak mogę uniemożliwić użytkownikowi zaksięgowanie faktury za zamówienie sprzedaży, jeśli nie zaksięgowano jeszcze dokument dostawy?

Możesz uniemożliwić użytkownikowi wysłanie listu przewozowego lub faktury, jeśli nie została jeszcze utworzona lista kompletacji zamówienia sprzedaży lub dokument dostawy, włączając opcję **Wymagania dotyczące odliczeń** dla grupy modelu artykułu. Ta opcja jest zwykle używana w organizacjach, które przeprowadzają fizyczny proces pakowania w magazynie (np. używając aplikacji mobilnej Warehouse Management do pakowania lub generując dokument, który zostanie dołączony do wysyłanych produktów). Opcja **Wymóg odliczenia** ma zastosowanie do *wszystkich* spraw inwentaryzacyjnych dla danego przedmiotu, a nie tylko zleceń sprzedaży. Na przykład dotyczy to arkusza inwentaryzacji, który ma ilość ujemną oraz arkusza listy pobrań zlecenia produkcyjnego.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Czy mogę zapobiec sprzedaży przedmiotów, które są zarejestrowane?

Kiedy artykuł jest zarejestrowany w twoim magazynie w Supply Chain Management, jego ilość jest fizycznie dostępna do wydania w systemie. Jeśli pozycje, które zostały zarejestrowane, ale nie zostały jeszcze odebrane, nie powinny być *nie* dostępne do wydania na przykład do zleceń sprzedaży lub zleceń produkcyjnych, rozważ użycie funkcji stanu zapasów, blokowania zapasów, zamówień jakościowych, zamówień kwarantanny lub rezerwacji do zarządzania procesem biznesowym.

## <a name="production-costing"></a>Wycena produkcji

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Czy mogę używać jednego modelu kalkulacji kosztów dla surowców i innego modelu kalkulacji kosztów dla wyrobów gotowych?

Tak, możesz używać różnych modeli kalkulacji kosztów dla każdej pozycji. Nierzadko producenci stosują model rachunku kosztów okresowych dla surowców, a koszt standardowy dla półproduktów i wyrobów gotowych.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Jak mogę obniżyć koszty ogólne maszyny?

Aby obniżyć koszty ogólne maszyn, musisz stworzyć zasoby i grupy zasobów dla każdej maszyny, zgodnie z wymaganiami biznesowymi. Każdy zasób lub grupa zasobów może być przypisana do kategorii kosztów, aby kontrolować koszt maszyny. Każda kategoria kosztów może być połączona z grupą kosztów, a każda grupa kosztów może być wykorzystana jako podstawa do obliczania kosztów pośrednich w arkuszu kalkulacyjnym.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Jak rozpoznać koszty związane z zużyciem energii (np. zużycie wody, energii lub gazu) w arkuszu kalkulacyjnym?

Koszty związane z zużyciem energii możesz generalnie rozpoznać na jeden z dwóch sposobów:

- Utwórz wiersz w BOM lub formule. Zazwyczaj ta linia jest tworzona jako pozycja usługowa i możesz określić jednostkę miary, którą zużywasz w stosunku do ilości, którą produkujesz. W ten sposób użytkownik może zużywać różne ilości podczas procesu produkcji. Możesz automatycznie zużywać elementy na podstawie wartości, którą wybierzesz w polu **Reguła rozliczania**.
- Utwórz koszt pośredni w swoim arkuszu kalkulacji kosztów. Zazwyczaj takie podejście stosuje się, by rozdzielić całkowity koszt zużycia energii na cały proces produkcyjny. Możesz użyć grupy kosztów i podstawy absorpcji, aby skalować zużycie na przykład na podstawie materiałów lub pracy na trasie.

Powinieneś wybrać najlepszą opcję w oparciu o swoje wymagania dotyczące raportowania, uzgadniania i operacji.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Czy mogę przechwytywać szczegóły zasobów w BOM-ie lub formule?

Szczegóły zasobu mogą być przechwycone tylko w operacji trasy. Chociaż możesz stworzyć pozycję usługi reprezentującą zasób i przypisać jej koszt, aby zwiększyć kalkulację kosztu gotowego produktu, to zazwyczaj nie zalecamy takiego podejścia. Zamiast tego zalecamy stworzenie prostej trasy z jednym wierszem do śledzenia kosztów zasobów i skonfigurowanie operacji tak, by były one automatycznie zużywane na początku lub na końcu zlecenia produkcyjnego.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Czy mogę zobaczyć szczegóły kalkulacji, jeśli koszt został wprowadzony ręcznie?

Nie Jeśli ręcznie wprowadzisz cenę na stronie **Cena towaru**, przyciski **Zobacz szczegóły obliczeń** i **Zgromadź szczegóły obliczeń** nie będą dostępne. Jeśli wybierzesz przycisk **Akumulacja kosztów według grupy kosztów** dla kosztu wprowadzonego ręcznie, pojawi się podsumowany wiersz, a wszystkie koszty zostaną akumulowane do pozycji towaru gotowego.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>Czy system oblicza wariancje na zleceniu produkcyjnym, gdy ręcznie wprowadzam koszt?

Tak, system oblicza wariancje, gdy ręcznie wprowadzasz koszt standardowy. Jeśli jednak ręcznie wprowadzisz koszt standardowy, zamiast go obliczać, wszystkie zużycie materiałów, trasy i koszty pośrednie w zleceniu produkcyjnym są traktowane jako wariancja zastąpienia. Jeśli wystąpią dodatkowe odchylenia, takie jak zużycie dodatkowych materiałów lub robocizny, zostaną one również zarejestrowane jako odchylenia od BOM-u produkcyjnego. Dlatego zdecydowanie zalecamy, abyś zawsze przeprowadzał kalkulację dla elementów, które mają BOM, trasę lub koszty pośrednie.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Jak mogę przenieść odchylenia ze zlecenia podprodukcyjnego do nadrzędnego zlecenia produkcyjnego?

Gdy używasz modelu rachunku kosztów okresowych, takiego jak FIFO, LIFO czy średnia ważona, koszty z podprodukcji zostaną uwzględnione w modelu heurystycznym, który wybrałeś dla poszczególnych pozycji. Jeśli potrzebujesz rzeczywistego rachunku kosztów, rozważ użycie zasady znakowania, aby wskazać, która podprodukcja jest wydawana do nadrzędnego zlecenia produkcyjnego. Alternatywnie można na przykład użyć opcji **Magazyn finansowy** dla wymiaru **Seria** lub **Numer seryjny** w grupie wymiarów śledzenia.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>Jak zasada rozliczania wpływa na konsumpcję?

Zasada rozliczania na BOM-ie, formule lub linii trasy kontroluje czas i technikę, która jest używana do zużywania elementu lub pracy. Wybranie opcji *Rozpocznij* spowoduje automatyczne zużycie towaru lub robocizny w momencie rozpoczęcia zlecenia produkcyjnego. Wybranie opcji *Zakończ* spowoduje automatyczne zużycie towaru lub robocizny w momencie zgłoszenia zakończenia zlecenia produkcyjnego. W przypadku wybrania opcji *Ręcznie* użytkownik musi ręcznie pobrać materiały lub zarejestrować czas w arkuszu zadania lub karty marszruty. BOM i formuły mają również opcję *Dostępne w lokalizacji*. Jeśli wybierzesz tę opcję, elementy są automatycznie zużywane po przeniesieniu ich do hali produkcyjnej.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Jak należy uruchamiać obliczanie kosztów, jeśli są dla mnie wielopoziomowe BOM lub formuły?

Ogólnie rzecz biorąc, zalecamy, byś rozpoczął obliczenia od najniższego poziomu BOM-u lub formuły. Aby ułatwić filtrowanie podczas masowego wykonywania kalkulacji kosztów, możesz użyć grup kalkulacji, które pomogą posegregować produkty. Zaleca się również uruchomienie zadania okresowego *Ponowne obliczanie poziomów BOM* przed rozpoczęciem masowego obliczania kosztów. Każda organizacja powinna rozważyć mieszankę produktów i określić strategię, która odpowiada specyficznym potrzebom jej produktów i struktur BOM lub receptur.

## <a name="transfer-order-costing"></a>Kosztorysowanie zlecenia transferu

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>Czy istnieje sposób alokowania frachtu do kosztu zamówienia przeniesienia?

Aby dodać koszty do polecenia przelewu, możesz dodać opłaty. Kod opłat definiuje debet i kredyt dla dodawanej opłaty. Należy najpierw utworzyć kody opłat w module **Zarządzanie zapasami**. Aby dodać opłatę do zamówienia przeniesienia, wybierz opcję **Opłaty** w wierszu zamówienia przeniesienia, do którego chcesz dodać opłatę.

## <a name="variances"></a>Odchylenia

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>Czy mogę traktować wariancje w różny sposób, w zależności od miejsca lub magazynu?

Nie ma możliwości skonfigurowania kont odchylenia dla poszczególnych placówek. W przypadku korzystania z wyceny standardowej dla zwolnionego produktu można wybrać konto główne, które będzie używane do księgowania odchylenia kosztów standardowych na stronie **Księgowanie**. Konta można skonfigurować dla jednego towaru, grupy towarów lub wszystkich towarów. Możesz także skonfigurować jedną grupę kosztów, grupę grup kosztów lub wszystkie grupy kosztów.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Czy mogę oddzielić odchylenia wynikające z kursów wymiany walut od innych rodzajów?

Jeśli odchylenie jest wynikiem różnicy kursów walutowych między ceną zamówienia zakupu a standardowym kosztem pozycji, nie ma sposobu na oddzielenie różnicy kursów walutowych od innych odchyleń.

## <a name="reporting"></a>Raportowanie

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Ile konfiguracji raportu o wartości zapasów mogę utworzyć i używać?

Nie ma ograniczeń co do liczby konfiguracji raportów wartości zapasów, które możesz utworzyć. Powinieneś ocenić swoje specyficzne wymagania dotyczące raportowania i stworzyć taką liczbę konfiguracji, jaka jest potrzebna, aby spełnić te wymagania. Do uruchomienia raportu lub opcji przechowywania raportu potrzebna jest co najmniej jedna konfiguracja raportu wartości zapasów.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>Czy mogę użyć raportu wartości zapasów, aby przeanalizować koszt danej pozycji w każdym magazynie?

Tak. Możesz włączyć opcję **Wyświetl** lub **Łącznie** dla każdego wymiaru **Magazynu** w konfiguracji raportu wartości zapasów. Jednak raport pokaże wartości tylko dla tych wymiarów, w których dla grupy wymiarów magazynowych włączona jest opcja **Zapasy finansowe**. Dla innych wymiarów zostaną wyświetlone puste kolumny. - aby uzyskać więcej informacji, przejrzyj [Raport wartości zapasów przykłady i logika](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Jak mogę wyświetlić ilość zapasów na konkretny dzień przy użyciu średniej ważonej?

Możesz użyć raportu **Starzenie zapasów**, który zawiera kolumnę **Średni koszt jednostkowy**, która pokazuje wartość zapasów na konkretny dzień. Aby uzyskać więcej informacji, przejrzyj [Raport starzenia się zapasów przykłady i logika](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Jak mogę zobaczyć, które transakcje przychodu są rozliczane z transakcją wydania?

Możesz przejrzeć rozliczenia transakcji inwentaryzacyjnej, wybierając **Rozliczenia** lub **Eksplorator kosztów** z zakładki **Zapasy** na pasku akcji strony **Transakcja inwentaryzacyjna** lub **Szczegóły transakcji inwentaryzacyjnej**. Jeśli wybierzesz odbiór, aby zobaczyć sprawy związane z transakcją, eksplorator kosztów nie pokazuje szczegółów. Szczegóły są widoczne tylko wtedy, gdy wybierzesz transakcję wydania.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>W jaki sposób raport wartości inwentarza pokazuje pozycje, które mają dodatnią ilość fizyczną i ujemną wartość finansową?

Raport wartości zapasów rozdziela kwoty i ilości fizyczne i finansowe na osobne kolumny. Wartości pokazywane w raporcie pochodzą z zakresu dat, który wybrałeś podczas tworzenia raportu. Wyświetlany poziom podsumowania zależy od wybranych przez ciebie ustawień. Jeśli pozycja ma transakcje, które zostały fizycznie otrzymane i finansowo wydane, ilości i wartości są sumowane niezależnie od siebie. Jeśli wybrałeś opcję wyświetlania poziomu szczegółowości jako transakcji, wiersze dla każdego przyjęcia i wydania są wyświetlane osobno, a ilości i kwoty fizyczne i finansowe są odpowiednio pokazywane. - aby uzyskać więcej informacji, przejrzyj [Raport wartości zapasów przykłady i logika](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Jaki jest wpływ grup wymiarów magazynowania i śledzenia na raport wartości zapasów?

Po włączeniu opcji **Wartość finansowa** dla wymiaru w grupie wymiarów magazynowania lub śledzenia można wybrać opcję **Wyświetl** lub **Suma** dla wymiaru w konfiguracji raportu o wartości zapasów. Jeśli wybierzesz opcję **Wyświetl** lub **Suma** dla wymiaru, którego opcja **Wartość finansowa** nie jest zaznaczona, kolumna będzie pusta w wynikach raportu. Jeśli opcja **Wartość finansowa** dla wymiaru w grupie wymiarów magazynowania lub śledzenia nie zostanie wybrana opcja **Wyświetl** lub **Suma** w konfiguracji raportu o wartości zapasów, system podsumuje wartości wybranych wymiarów, w których są śledzone finansowo.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Czy mogę dostosować wbudowane raporty Power BI do kalkulacji kosztów?

Tak, użytkownicy z odpowiednimi uprawnieniami mogą aktualizować wygląd raportu dla każdego raportu osadzonego w Power BI w Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Dostosowywanie raportów osadzonych w analitycznych przestrzeniach roboczych](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Gdzie można wyświetlić sprawozdanie z analizy odchylenia?

Możesz uzyskać dostęp do zestawienia analizy odchylenia, przechodząc do **Zarządzanie kosztami \> Zapytania i raporty \> Księgowość zapasów - raporty analiz** lub **Zarządzanie kosztami \> Zapytania i raporty \> Księgowość produkcji - raporty analiz**. Obie opcje otwierają ten sam raport, a raport zachowuje się tak samo.

## <a name="item-prices-and-default-costs"></a>Ceny przedmiotów i koszty domyślne

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Czy mogę zachować koszt dla każdego wariantu produktu?

Tak. Możesz włączyć opcję **Używaj ceny według wariantu** w zakładce **Zarządzaj kosztami** na stronie **Wprowadzonego produktu**, aby umożliwić ustalanie cen według wariantu produktu. (Ta opcja jest dostępna tylko dla mistrzów produktu). Następnie na stronie **Ceny artykułu** (którą możesz otworzyć ze strony **Wersji kosztorysowej** lub ze strony **Wprowadzonego produktu**) możesz wybrać **Wyświetlanie wymiarów**, aby określić, czy chcesz pokazać wymiar **Konfiguracji**, **Rozmiaru**, **Koloru** czy **Stylu**. Aby zapisać ustawienia i używać wybranych wymiarów za każdym razem, gdy otwierasz stronę, włącz opcję **Zapisz ustawienia**, a następnie wybierz **OK**. Możesz wprowadzić wymiary tylko dla artykułów, dla których są one aktywne w grupie wymiarów produktu.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Czy mogę zachować koszt dla każdego magazynu?

Nie, nie możesz utrzymać ceny przedmiotu według magazynu. Możesz jednak prowadzić umowy handlowe dotyczące cen zakupu lub cen sprzedaży z podziałem na magazyny. Najpierw zaznacz opcję **Dla cen zakupu** lub **Dla cen sprzedaży** dla wymiaru na stronie **Grupa wymiarów magazynowania**. Następnie, gdy tworzysz dziennik umowy handlowej i otwierasz wiersze dla wymiarów, wybierz **Zapasy \> Wyświetl wymiary**, aby wybrać, który wymiar ma być widoczny w siatce. Aby zapisać ustawienia i używać wybranych wymiarów za każdym razem, gdy otwierasz stronę, włącz opcję **Zapisz ustawienia**, a następnie wybierz **OK**. Możesz wprowadzić wymiary tylko dla artykułów, dla których są one aktywne w grupie wymiarów produktu.

### <a name="what-are-price-charges"></a>Czym są opłaty dla ceny?

Opłaty dla ceny zapewniają dodanie stałej kwoty do ceny jednostkowej ceny pozycji lub umowy handlowej. Po wprowadzeniu kwoty w polu **Opłaty dla ceny** można także wprowadzić wartość w polu **Opłaty — ilość**. Opłaty cenowe są amortyzowane przez ilość opłat, którą określisz. Włącz opcję **Zawarte w cenie jednostkowej**, jeśli chcesz, aby opłaty za cenę były wliczane do ceny jednostkowej przedmiotu. Ta opcja jest zawsze włączona dla kosztu standardowego.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Jak powinienem skonfigurować ceny dla przedmiotów, które są zamawiane w wielu walutach?

Jeśli wprowadzisz domyślną cenę w polu **Cena zakupu** na stronie **Wprowadzony produkt**, to przyjmuje się, że będzie ona w walucie księgowej księgi głównej dla osoby prawnej, którą prowadzisz. Podobnie, jeśli wprowadzasz cenę zakupu w wersji kalkulacji kosztów, w której pole **Typ ceny** jest ustawione na *Zakup*, przyjmuje się, że cena jest w walucie księgowej twojej osoby prawnej. Kiedy tworzysz zamówienie zakupu dla sprzedawcy, który ma inną walutę, system automatycznie przeliczy walutę z kwoty w walucie księgowej na walutę transakcji, korzystając z kursu wymiany, który określisz w polu **Typ kursu waluty księgowej** w swojej księdze.

Kiedy tworzysz dziennik umowy handlowej, w każdym wierszu możesz określić walutę, w której wyrażona jest cena. Możesz tworzyć umowy handlowe dla wielu walut, konkretnych sprzedawców i wielu innych kombinacji czynników. Jeśli tworzysz zamówienie zakupu, w którym istnieje umowa handlowa dla wybranej przez ciebie waluty, system użyje tej umowy handlowej, która ma odpowiadającą jej walutę. Kiedy księgujesz transakcje, takie jak odbiór produktów lub faktury, kwota zostanie przeliczona na walutę księgową księgi przy użyciu kursu wymiany waluty księgowej, który określisz w księdze.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Jak powinienem skonfigurować koszty dla przedmiotów, które są zamawiane w wielu walutach?

Kosztów nie można skonfigurować w więcej niż jednej walucie. Koszty, które określasz jako cenę artykułu, lub koszty domyślne, które wprowadzasz w polu **Cena** w zakładce **Zarządzaj kosztami** na stronie **Wprowadzony produkt**, są zawsze wyrażone w walucie księgowej księgi dla wybranej przez ciebie osoby prawnej.

Jeśli twoja organizacja używa standardowego rachunku kosztów, powinieneś określić strategię definiowania kosztów, gdy istnieje wiele walut. Powinieneś także zdefiniować proces regularnego aktualizowania kosztów, aby zmniejszyć liczbę księgowanych wariancji.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>Czy mogę używać ustawienia Zysk na stronie grupy Koszty do obliczania cen sprzedaży?

Tak, możesz użyć ustawienia **Zysk** na stronie **Grupy kosztów**, aby dodać procent, gdy ceny sprzedaży są obliczane z wykorzystaniem kalkulacji kosztów. Aby uzyskać więcej informacji, zobacz [Obliczenia BOM](bom-calculations.md).

## <a name="marking"></a>Zaznaczanie

### <a name="how-does-marking-affect-periodic-costing-models"></a>Jak znakowanie wpływa na modele rachunku kosztów okresowych?

Jeśli używasz modelu rachunku kosztów okresowych, takiego jak FIFO, LIFO lub średnia ważona, i zaznaczyłeś transakcję przyjęcia do magazynu w stosunku do transakcji wydania, model heurystyczny pozycji jest ignorowany podczas procesu zamknięcia inwentaryzacji. Zamiast tego system użyje rzeczywistego kosztu odchylenia do określenia kosztu wydania.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>Co się dzieje podczas zamykania zapasów, gdy używam oznaczeń?

Gdy zaznaczysz odbiory i wydania, zamknięcie zapasów rozliczy transakcje, które są zaznaczone razem. Jeśli to pole jest używane do tworzenia rozliczenia, pole **Zasada** na stronie **Rozliczenie** ma wartość *Zaznaczanie*. Jeśli transakcja zostanie oznaczona, zanim zostanie fizycznie lub finansowo zaktualizowana, w wydaniu zostanie użyty koszt oznaczonego odchylenia zamiast bieżącego średniego kosztu. Jeśli transakcje zostaną zaznaczone po aktualizacji finansowej, proces zamknięcia i korekty inwentaryzacji skoryguje koszt wydania tak, by odpowiadał kosztowi otrzymania.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Czy mogę ręcznie oznaczać transakcje, gdy używam standardowego rachunku kosztów lub średniej ruchomej?

Nie, nie możesz ręcznie oznaczać wpływów lub wydań, gdy używasz standardowego rachunku kosztów lub średniej ruchomej. Jeśli transakcje (np. zamówienia z dostawą bezpośrednią lub między firmami) są automatycznie oznaczane, zapis oznaczenia pozostanie i będzie działał jak twarda rezerwacja. Jednak gdy stosujesz standardowy rachunek kosztów lub średnią ruchomą, oznaczenie zapisów nie ma wpływu na koszt pozycji.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>W jaki sposób oznaczenie wpływa na zestawienie zysków i strat?

Gdy zaznaczysz transakcję wydania do odbioru, koszt wydania będzie zgodny z wybranym odbiorem. Kiedy fizycznie i finansowo zaksięgujesz wydanie, księgowanie wpłynie na konta **Koszt sprzedanych towarów, dostarczonych** i **Koszt sprzedanych towarów, zafakturowanych**, które określisz w profilu księgowania zapasów. Jeśli transakcja zostanie zaznaczona po aktualizacji fizycznej lub finansowej, proces *Zamknięcie i korekta zapasów* utworzy korektę, która będzie miała kupon dopasowujący, który skoryguje konto **Koszt sprzedanych towarów, zafakturowane** i skompensuje konto, które określisz dla **Koszt jednostek, zafakturowane** (zapasy).

### <a name="how-does-marking-affect-master-planning"></a>Jak znakowanie wpływa na planowanie ogólne?

Zakładka **Standardowa aktualizacja** na stronie **Parametry planowania głównego** zawiera pole o nazwie **Aktualizacja oznaczenia**. Opcja, którą tam wybierzesz, jest używana, gdy firmujesz planowane zamówienie wygenerowane przez planowanie główne. Dostępne są następujące opcje:

- *Nie* — System nie wykonuje żadnego oznaczenia.
- *Standard* — System zaznacza odbiory względem wydań zgodnie z oznaczeniem transakcji. Zamówienie zapotrzebowania jest zaznaczane na podstawie zamówienia realizacji. Jeśli jakaś ilość pozostaje na wypełnieniu, zlecenie wypełnienia nie jest oznaczane.
- *Rozszerzona* — System zaznacza zarówno zlecenia zapotrzebowania, jak i zlecenia realizacji, niezależnie od tego, czy na zleceniu realizacji jest jeszcze otwarta jakaś ilość.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Ujemny poziom zapasów

### <a name="when-should-i-allow-physical-negative-inventory"></a>Kiedy powinienem zezwalać na ujemne wartości magazynu fizycznego?

Ogólnie rzecz biorąc, nie zalecamy dopuszczania fizycznego ujemnego stanu zapasów ponieważ nie jest możliwe posiadanie w magazynie mniej niż 0 (zero) danej pozycji materialnej. Jednak procesy biznesowe w niektórych branżach i scenariusze biznesowe mogą ograniczać operacje, które wymagają, by zapasy były fizycznie ujemne. Na przykład, sprzedawcy mogą nie chcieć uniemożliwić sprzedaży artykułu, który został przyniesiony do rejestru, nawet jeśli system wskazuje, że nie ma żadnych dostępnych artykułów. Innym przykładem są producenci procesów. W przypadku tych producentów ilość używanego towaru może przekraczać to, co jest zalecane w formule. Ewentualnie zużycie może być szacunkowe, a nie dokładne, tak by przekraczało ilość w konkretnym miejscu, np. w zbiorniku.

Kiedy tylko jest to możliwe, powinieneś ocenić swój proces biznesowy i spróbować go ulepszyć, by mieć pewność, że zapasy nie mogą być ujemne. Jeśli musisz dopuścić ujemny poziom zapasów, powinieneś mieć jasny proces biznesowy korygowania ujemnych zapasów, ponieważ może ona negatywnie wpłynąć na kalkulację kosztów.

### <a name="when-should-i-allow-financial-negative-inventory"></a>Kiedy powinienem zezwalać na ujemne wartości magazynu finansowego?

Ogólnie rzecz biorąc, zalecamy, by większość organizacji zezwalała na negatywne zapasy finansowe. (W większości przypadków faktury za zamówienia zakupu nie są przetwarzane przed wysyłką produktów). Powinieneś włączyć tę opcję, jeśli masz specyficzne procesy biznesowe, które wymagają, by cena sprzedaży odzwierciedlała ostateczny koszt zamówienia. Wymaganie to może być na przykład stosowane w branży „make-to-order” lub w określonych regionach, w których wynika to z przepisów prawa.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>Co się dzieje z kosztem moich wydań, gdy zapasy są ujemne?

Jeśli stan zapasów towaru jest ujemny i wydajesz więcej towarów niż masz ich fizycznie, system użyje domyślnej ceny towaru do obliczenia średniej ważonej, jeśli zostanie uruchomiony okresowy model wyceny, taki jak FIFO, LIFO czy średnia ważona. Jeśli dla towaru nie zostanie określona domyślna cena, system będzie wystawiać zapasy z wartością 0 (zero). Takie działanie może spowodować, że przyszłe obliczenia średniej kroczącej lub średniej ruchomej będą niedokładne.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Czy można uniemożliwić, aby towary były odbierane, pakowane lub sprzedawane na zamówieniach sprzedaży i zleceniach produkcyjnych w przypadku wystarczającej ilości dostępnych zapasów?

Tak. Zalecamy wyłączenie opcji **Negatywne fizycznie** dla grupy modeli artykułów, aby zapobiec pobieraniu, pakowaniu lub sprzedawaniu artykułów w zamówieniach sprzedaży i zleceniach produkcyjnych.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Czy mogę zapobiec fakturowaniu pozycji na zleceniu sprzedaży, jeśli na tę samą pozycję nie zostało zafakturowane żadne zlecenie zakupu?

Tak. Zalecamy wyłączenie opcji **Ujemna wartość finansowa** dla grupy modelu artykułu, aby zapobiec fakturowaniu pozycji na zlecenie sprzedaży, jeśli na tę samą pozycję nie zostało wystawione żadne zlecenie zakupu.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>Jak ujemne zapasy wpływają na wskaźniki finansowe, takie jak marża zysku brutto?

Jeśli pozwolisz, by stan zapasów był ujemny, wartość zapasów w bilansie oraz koszt sprzedanych towarów w rachunku zysków i strat mogą być zaniżone, zwłaszcza jeśli nie masz skonfigurowanej ceny domyślnej dla swoich produktów. Dlatego raporty finansowe i wskaźniki, takie jak marża zysku brutto, mogą być zawyżone, ponieważ koszt jest nieprawidłowy. Jeśli stosujesz model rachunku kosztów okresowych, taki jak FIFO, LIFO lub średnia ważona, wartość wydania może zostać skorygowana, gdy przeprowadzasz proces zamknięcia i korekty zapasów po skorygowaniu ujemnych ilości zapasów. Jeśli jednak używasz średniej ruchomej, nie ma sposobu, by zrewaloryzować poszczególne transakcje.

### <a name="how-should-i-correct-negative-inventory"></a>Jak powinienem skorygować ujemny stan zapasów?

Zalecamy, byś często monitorował i korygował ujemne stany magazynowe, jeśli wymagania organizacyjne lub biznesowe nakazują ci dopuszczenie do ujemnych stanów magazynowych. Możesz skorygować wartości zapasów, wykonując liczenie cykliczne, księgując korektę lub księgując dziennik przemieszczeń. Jeśli musisz ująć nieoczekiwane zyski z zapasów na konkretnym koncie księgi głównej, powinieneś zaplanować wykorzystanie dziennika ruchów. W przeciwnym razie, gdy korzystasz z procesu liczenia cyklicznego lub korekty, system zaksięguje korektę inwentaryzacji na **konto przyjęcia zapasów** i kompensatę na **konta rozchodów zapasów, zysk**, które określisz w profilu księgowania zapasów.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Czy muszę utworzyć nową pozycję, jeśli moje zapasy są ujemne, a używam średniej ruchomej?

Nie Jeśli twoja organizacja pozwala na fizycznie ujemne stany magazynowe, a ty używasz średniej ruchomej jako modelu inwentaryzacji, system użyje sekwencji kosztów awaryjnych, która jest przypisana na stronie **Parametry inwentaryzacji i gospodarki magazynowej**, aby określić, w jaki sposób koszt zostanie przypisany do twoich wydań. Ogólnie rzecz biorąc, zalecamy, byś nie dopuścił do tego, by twoje zapasy były fizycznie ujemne. Aby uzyskać więcej informacji, zapoznaj się z pozostałymi pytaniami w [Negatywny poziom zapasów](#negative-inventory) we wcześniejszej części tego tematu.

## <a name="not-stocked-products"></a>Produkty niedostępne w magazynie

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Czy mogę publikować listy kompletacji zamówień sprzedaży dla produktów, których nie ma w magazynie?

Kiedy generujesz listę kompletacji dla zamówienia sprzedaży zawierającego artykuły z grupy modeli artykułów, które nie są magazynowane, nie zobaczysz żadnych wierszy dla tych nie magazynowanych artykułów. Nie możesz używać aplikacji mobilnej Warehouse Management, by przetwarzać pozycje, których nie ma w magazynie.

Kiedy generujesz dokument pakowania dla zamówienia sprzedaży, które zawiera pozycje należące do grupy modelu artykułu, który nie jest magazynowany, ustaw pole **ilość** na *Pobrana ilość i produkty nie magazynowane*, aby uwzględnić pozycje nie magazynowane w generowanym dokumencie. W przypadku wybrania opcji *Wszystko* w dokumencie dostawy będą uwzględniane tylko towary magazynowe.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Czy powinienem użyć produktu, którego nie ma w magazynie, czy kategorii (kategorii sprzedaży lub kategorii zaopatrzenia)?

Wybór pomiędzy kategorią a produktem, którego nie ma w magazynie, zależy od Twoich specyficznych wymagań biznesowych. Produkty niezaopatrzone oferują zazwyczaj większą kontrolę nad wartościami domyślnymi, takimi jak ilości i ceny na zamówieniach zakupu i sprzedaży. Dlatego produkty niezaopatrzone są preferowane w scenariuszach, w których ten sam produkt lub usługa jest kupowany lub sprzedawany więcej niż raz. Kategorie są przydatne w scenariuszach, w których cena, przedmioty, opisy itd. są niespójne w różnych transakcjach. Kategorie mogą być także używane w przypadku każdego produktu, by pomóc sklasyfikować typ produktu, który jest sprzedawany lub kupowany.

## <a name="service-items"></a>Pozycje usługi

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Jaka jest różnica między artykułem serwisowym a produktem, którego nie ma w magazynie?

Element usługi jest typem produktu. Kiedy tworzysz nowo wydany produkt, możesz ustawić pole **Typ produktu** na *Produkt* lub *Usługa*. *Produkt* jest zazwyczaj wybierane, by wskazać, że przedmiot jest materialny, natomiast *Usługa* jest zazwyczaj wybierane, by wskazać, że element jest niematerialny.

Każdy wypuszczony produkt, niezależnie od tego, czy jest to produkt materialny czy usługowy, może być magazynowany lub niemagazynowany. Ustawienie „magazynowane” lub „nie magazynowane” jest kontrolowane przez grupę modeli pozycji, która jest wybierana dla zwolnionego produktu. Kiedy wybierzesz grupę artykułów, która nie jest magazynowana, system nie tworzy transakcji inwentaryzacyjnych dla powiązanych z nią np. zamówień sprzedaży czy zamówień zakupu.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Czy mogę umieścić w BOM elementy, których nie ma w magazynie?

Nie, nie możesz włączyć do BOM-u lub formuły produktu, który został wydany i jest powiązany z grupą modelu artykułu, w której opcja **Magazynowane** jest wyłączona. Nie ma znaczenia, czy w polu **Typ produktu** ustawiono *Produkt* czy *Usługę*. W BOM lub liniach formuł mogą być uwzględniane tylko te pozycje, które są na stanie.

## <a name="costing-modelspecific-questions"></a>Pytania związane z modelem kalkulacji kosztów

### <a name="which-costing-model-should-i-use"></a>Którego modelu wyceny należy używać?

Modele kalkulacji kosztów, które powinieneś wybrać, zależą od Twoich wymagań biznesowych. Zanim wybierzesz model kalkulacji kosztów do wykorzystania w Supply Chain Management, powinieneś upewnić się, że jest on dozwolony przez lokalne przepisy. Zalecamy, byś potwierdził swój wybór u certyfikowanego księgowego w swoim regionie.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Czy w mojej organizacji można używać więcej niż jednego modelu wyceny?

Tak. Nie ma ograniczeń co do liczby grup modeli towaru lub modeli wyceny, które można wybrać w Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Czy mogę używać więcej niż jednego modelu kalkulacji kosztów dla każdej pozycji?

Nie Dla każdego wydanego produktu możesz wybrać tylko jeden model kalkulacji kosztów. To zachowanie jest kontrolowane przez grupę modelu elementu. Jeśli do raportu wartości zapasów jest uwzględniany więcej niż jeden model wyceny, warto rozważyć użycie dodatku Globalne księgowanie zapasów.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>Której metodologii wyceny należy użyć podczas wykonywania produkcji?

Modele kalkulacji kosztów, które powinieneś wybrać, zależą od Twoich wymagań biznesowych. Nie ma żadnej szczególnej zalety ani wady stosowania jakiegokolwiek modelu rachunku kosztów, gdy twoja organizacja stosuje również wykonanie produkcyjne.

### <a name="when-is-fefo-used"></a>Kiedy stosuje się FEFO?

Pierwsza utrata ważności, pierwsze wyjście (FEFO) nie jest metodologią kalkulacji kosztów. Jest to metoda rezerwacji, która jest często używana w organizacjach produkcyjnych. Możesz włączyć rezerwacje FEFO dla grupy modelu artykułu, włączając opcję **FEFO kontrolowane datą**, a następnie wybierając wartość w polu **Kryteria wyboru**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Czy istnieją korzyści związane z wydajnością, które przemawiają za wyborem jednego modelu kalkulacji kosztów zamiast drugiego?

Ogólnie rzecz biorąc, model kalkulacji kosztów, który wybierzesz dla danej pozycji, ma minimalny wpływ na ogólną wydajność systemu. Jednak na ilość czasu potrzebnego do przeprowadzenia procesu zamknięcia lub przeliczenia inwentaryzacji może mieć wpływ model kalkulacji kosztów zapasów, który wybierzesz. Na przykład, jeśli używasz kosztu standardowego lub średniej ruchomej, proces zamknięcia inwentaryzacji ma minimalny wpływ na system, ponieważ nie aktualizuje każdej transakcji inwentaryzacyjnej i nie tworzy rozrachunków. Jednak model rachunku kosztów okresowych, taki jak FIFO, LIFO czy średnia ważona, może zwiększyć ilość czasu potrzebnego do zakończenia procesu zamknięcia inwentaryzacji. W szczególności proces zamknięcia może być dłuższy, jeśli w polu **Maksymalna liczba iteracji na pozycję** wpiszesz wysoką liczbę lub w polu **Minimalna dozwolona kwota** wpiszesz niską liczbę dla procesu *Zamknij inwentaryzację*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>Kiedy powinienem używać opcji Stała cena przychodu?

Gdy zaznaczysz pole wyboru **Stała cena odbioru** na stronie **Grupa modelu jednostki** dla danej pozycji, system użyje ceny odbioru jako kosztu standardowego dla odchylenia. Jeśli cena zakupu i domyślna cena kosztu artykułu skonfigurowana dla danego produktu różnią się, różnica jest księgowana na koncie **Zysk ze stałej ceny przyjęcia** lub **Strata ze stałej ceny przyjęcia** i kompensowana na koncie Kompensata ze stałej ceny przyjęcia, które określasz na stronie **Profil księgowania zapasów**. (Wszystkie te konta są określone w Strona **księgowania**).

Pole wyboru **Stała cena odbioru** należy zaznaczyć w przypadku korzystania z okresowego modelu wyceny, takiego jak FIFO, LIFO czy średnia ważona. Jeśli cena przychodu różni się od domyślnego kosztu towaru, odchylenie cen zakupu powinno być śledzone w księdze.

### <a name="moving-average"></a>Średnia ruchoma

### <a name="is-moving-average-the-same-as-a-floating-average"></a>Czy średnia ruchoma jest taka sama jak średnia ruchoma?

Terminy Średnia ruchoma, Średnia ruchoma i Średnia ruchoma są często używane jako opisy. Z punktu widzenia tych warunków średnia ruchoma jest jedynym oficjalnym modelem wyceny dostępnym w Supply Chain Management. Chociaż średnia bieżąca nie jest oficjalnym modelem wyceny, jest to metoda używana w przypadku używania okresowego modelu wyceny, takiego jak FIFO, LIFO czy średnia ważona. Termin „średnia zmienna” nie jest używany w Supply Chain Management i może mieć różne konotacje w innych systemach.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>W jaki sposób można uwzględnić różnicę między ceną dokumentu przyjęcia produktów a ceną faktury przy używaniu średniej ruchomej?

W przypadku korzystania ze średniej ruchomej koszt fizyczny (cena odbioru) jest używany do obliczania średniej ruchomej dla wszystkich transakcji rozchodów. W przypadku różnicy między kosztem fizycznym (cena na odbiorze) a kosztem finansowym (cena na fakturze), system automatycznie zaksięguje różnicę na koncie głównym określonym dla typu księgowania **Różnica w cenie średniej ruchomej** w dniu na karcie **Zasoby** na stronie **Profil publikowania zasobów**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Gdzie w księdze głównej jest prezentowana różnica cen dla średniej ruchomej?

Gdy istnieje różnica cen między zaksięgowaniem aktualizacji fizycznej i aktualizacji finansowej dla przyjęcia, różnica jest księgowana na koncie głównym, które jest określone dla typu księgowania **Różnica cen dla średniej ruchomej** w zakładce **Zasoby** stronie **Profil księgowania zapasów**. Aby uzyskać więcej informacji, zobacz [Średnia krocząca](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Kiedy używam średniej ruchomej, co się stanie, jeśli problem pojawi się przed paragonem?

Zazwyczaj problem może pojawić się przed przyjęciem, ponieważ zezwalasz na fizyczne zapasy ujemne dla grupy modelu artykułu lub ponieważ wydanie miało miejsce w przeszłości. Więcej informacji znajduje się w sekcji [Ujemny stan zapasów](#negative-inventory) we wcześniejszej części tego tematu.

Jeśli dokonujesz wstecznych transakcji, zalecamy, byś dokładnie przeanalizował swój proces biznesowy i działania, by ustalić, czy istnieje sposób na uniknięcie tego scenariusza. Jeśli dokonasz wstecznej korekty transakcji dla pozycji, która wykorzystuje średnią ruchomą, system przypisze do transakcji bieżącą średnią ruchomą. Późniejsze wydania nie są korygowane. Więcej informacji na temat średniej ruchomej z transakcjami z datą wsteczną znajdziesz w dziale [Średnia ruchoma](moving-average.md).

### <a name="standard-costing"></a>Wycena standardowa

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Jaka jest różnica między wyceną standardową a stałą ceną przychodu?

Standardowy rachunek kosztów wymaga, byś zdefiniował cenę artykułu i aktywował koszt w wersji rachunku kosztów. Ten koszt jest używany dla wszystkich wpływów i wydań. Wariancje dla wpływów do inwentarza są zapisywane w księdze głównej za pomocą kont wariancji kosztów standardowych, które określasz w zakładce **Koszty standardowe** na stronie **Profilu księgowania zapasów**.

Jednak gdy używasz stałej ceny odbioru, tylko koszt jest stały, a system używa kosztu, który określasz w zakładce **Zarządzaj kosztami** na stronie **Realizowany produkt**. Różnice między kosztem domyślnym a ceną zamówienia zakupu spowodują, że odchylenie ceny zakupu zostanie zaksięgowane na kontach zysków i strat związanych ze stałą ceną odbioru. Wydania nie używają stałej ceny przychodu. Zamiast tego wydania będą wyceniane według średniej bieżącej w momencie księgowania (chyba że używasz oznaczeń), a następnie będą przeszacowywane według modelu heurystycznego, który wybierzesz podczas zamykania zapasów.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Czy można używać rezerwacji FEFO z wyceną standardową?

Tak, podczas wyboru wyceny standardowej można użyć rezerwacji FEFO w grupie modeli pozycji. Rezerwacje FEFO sterują logiką rezerwacji używaną do fizycznej obsługi towarów, podczas gdy koszt standardowy steruje kosztem fizycznym i finansowym towaru.

### <a name="can-i-upload-pending-prices"></a>Czy można przekazać oczekujące ceny?

Tak, możesz użyć dodatku do Excela lub Data Management Framework, aby przesłać cenę oczekującą. Zalecane jest użycie następujących encji:

- Oczekujące ceny pozycji (wersja 2)
- Oczekujące koszty jednostkowe kategorii kosztów marszruty
- Współczynniki obliczeń węzłów arkusza wyceny (wersja 2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>Jak często można aktualizować koszt standardowy towaru?

Częstotliwość, pod która można aktywować nowy koszt standardowy, nie ma żadnego limitu. Jeśli aktywujesz nowy koszt dla danej pozycji w tym samym dniu, w którym został aktywowany ostatni koszt, system użyje ostatnio aktywowanego kosztu w nowych transakcjach lub aktualizacjach (np. aktualizacjach istniejących transakcji).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Czy mogę dezaktywować lub usunąć aktywowany koszt?

Nie, nie możesz dezaktywować ani usunąć aktywowanego kosztu. Jeśli nieprawidłowo aktywowałeś koszt, możesz aktywować nowy koszt, który ma prawidłowy koszt.

### <a name="are-calculation-groups-used-with-standard-costing"></a>Czy grupy kalkulacyjne są używane w standardowym rachunku kosztów?

Grupy obliczania mogą być używane z dowolnym towarem, niezależnie od wybieranych grup modeli pozycji. Grupy kalkulacji są używane podczas procesu akumulacji kosztów lub kalkulacji kosztów, aby określić ustawienia, które powinny być zastosowane dla pozycji, dla których przeprowadzasz kalkulację. Aby uzyskać więcej informacji na temat grup kalkulacji, zobacz [Grupy kalkulacji BOM](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>Kiedy powinienem używać wersji planowanego rachunku kosztów?

Wersje wyceny mogą mieć typ *Koszt standardowy* lub *Koszt planowany*. Typ *Koszt standardowy* jest używany dla kosztów aktywnych w systemie i księgowanych w transakcjach. Typ *Koszt planowany* jest używany do uruchamiania symulacji kosztów i nie ma wpływu na koszt transakcji.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>Czy całkowity koszt poniesiony przez jedną jednostkę może zostać przeniesiony do innej jednostki jako koszt sprzedaży?

Nie ma zautomatyzowanego sposobu na kopiowanie kosztów z jednej firmy do drugiej. Dodatkowo, nie ma zautomatyzowanego sposobu na kopiowanie kosztów z ceny zakupu do ceny sprzedaży. Jeśli twoja organizacja musi wykonać jedno z tych zadań, zastanów się, czy możesz użyć Data Management Framework, aby wyeksportować dane z wersji kalkulacji kosztów i załadować je do innej firmy, albo jako cenę sprzedaży w wersji kalkulacji kosztów, albo jako umowę handlową. Może być konieczne ręczne przetworzenie plików.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>Jaki jest najlepszy sposób na skopiowanie planowanych kosztów do wersji standardowej rachunku kosztów?

Możesz użyć przycisku **Kopiuj** na stronie **Wersje kalkulacji**, aby skopiować ceny pozycji, ceny kategorii kosztów lub koszty pośrednie z jednej wersji kalkulacji kosztów do drugiej.
