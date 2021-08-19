---
title: Zarządzanie podróżami
description: W tym temacie opisano sposób pracy z podróżami. Podróż zazwyczaj przedstawia statek. Jednak w zależności od twoich praktyk i procedur może reprezentować dostawcę, zamówienie zakupu lub inny element, który ma sens dla Twojej organizacji.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 953677a0d7ebe3343b888fdff2867334ef69d861d85a9145aa003177617434d6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757837"
---
# <a name="manage-voyages"></a>Zarządzanie podróżami

[!include [banner](../../includes/banner.md)]

Podróż zazwyczaj przedstawia statek. Jednak w zależności od twoich praktyk i procedur może reprezentować dostawcę, zamówienie zakupu lub inny element, który ma sens dla Twojej organizacji.

Strona **Wszystkie podróże** zawiera szczegóły podróży, informacje dotyczące dostawy i wyceny, a także informacje o towarach, zamówieniach zakupu i zamówieniach przeniesienia. Aby otworzyć stronę **Wszystkie podróży**, przejdź do strony **Koszt z wyładunkiem \> Podróże \> Wszystkie podróże**. Ta strona pokazuje listę wszystkich aktualnych rejsów. Możesz używać przycisków w Okienku akcji do tworzenia, usuwania i pracy z podróżami. Wybierz dowolną podróży na liście, aby wyświetlić jej szczegóły.

> [!NOTE]
> Kontenery transportowe i folia są powiązane z podróżą. Linie zakupu są połączone z kontenerem wysyłkowym. Jeśli kontenery transportowe i folio są wyłączone, można je również połączyć bezpośrednio z podróżą. Ponadto wprowadzone tutaj koszty są rozdzielane na wszystkie dołączone wiersze zakupu.

## <a name="action-pane"></a>Okienko akcji

Okienko akcji na stronie **Podróży** zawiera przyciski, które umożliwiają pracę w wybranej podróży. Każdy przycisk wykonuje pojedynczą akcję. W okienku akcji znajdują się także karty, z których każdy z kolei zawiera zestaw powiązanych przycisków. Z wyjątkiem zaznaczonego widoku, wszystkie przyciski i karty są dostępne zarówno w widoku listy strony **Wszystkie podróże**, jak i w widoku szczegółowym dla wybranej podróży.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Przyciski wyświetlane bezpośrednio w okienku akcji

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio w okienku akcji.

| Przycisk | opis |
|---|---|
| Nowa | Tworzenie podróży. <!-- KFM: Link to scenario --> |
| Usuwanie | Usuwanie bieżącej podróży. Można usuwać tylko podróże o stanie *Potwierdzone*. Gdy podróż opuszcza port i przetwarza towary w tranzycie, nie można jej już usunąć. |
| Edytor podróży | Otwórz stronę **Edytora podróży**, na której możesz dodawać lub usuwać linie zakupu podróży, tworzyć nowe kontenery i modyfikować szczegóły samej podróży. |
| Koszty podróży | Otwórz stronę **Koszty podróży**, na której możesz przeglądać i dodawać koszty podróży do wszystkich towarów w podróży. Gdy koszty podróży są dodawane ręcznie do podróży, są one automatycznie dodawane do strony **Zapytania o koszty** i przydzielane do każdego towaru zgodnie z metodą określoną na stronie **Koszty podróży**. |

### <a name="buttons-on-the-voyage-tab"></a>Przyciski na karcie Podróż

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Podróż** w okienku akcji. Ta karta jest dostępna tylko podczas pracy w widoku listy na stronie **Wszystkie podróże**.

| Przycisk | opis |
|---|---|
| Kontener wysyłkowy | Otwórz stronę, która pokazuje wszystkie kontenery transportowe, które są powiązane z wybraną podróżą. Może być jeden kontener lub wiele kontenerów. |
| Folio | Otwórz stronę, która pokazuje wszystkie folio, które są powiązane z wybraną podróżą. Może istnieć jedno folio lub wiele folio. |

### <a name="buttons-on-the-manage-tab"></a>Przyciski na karcie Zarządzanie

W poniższej tabeli opisano akcje, które są dostępne bezpośrednio na karcie **Zarządzaj** w okienku akcji.

| Przycisk | opis |
|---|---|
| Otrzymano dokumenty | Zaktualizuj podróży, tak aby w opcji **Dokumenty otrzymane** ustawiono wartość *Tak*. Możesz użyć tego przycisku, aby zablokować pozycję i/lub linię zakupu, aby nie można było ich dalej aktualizować. |
| W trakcie przesyłania | Zaktualizuj pole **Stan podróży** do stanu w drodze, który jest ustalony na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)**. Nie istnieje żadna kolejna logika tego procesu. Podróż może być również automatycznie aktualizowana do statusu w tranzycie, na podstawie ustawień w [Centrum kontroli śledzenia](delivery-information-setup.md).
| Gotowa do wyceny | Zaktualizuj pole **Stan podróży** do stanu gotowy do wyceny, który jest ustalony na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)**. Koszt podróży można obliczyć, gdy wszystkie faktury zostały przetworzone (zarówno faktury magazynowe, jak i faktury z kosztami podróży), a towary zostały odebrane. Jeśli szacunkowe koszty związane z podróżą nie zostały wycenione, podczas próby przetworzenia wyceny podróży pojawia się błąd. |
| Wyceniono | Usuń wszelkie nieprawidłowości związane z kosztami po wystawieniu faktury na wszystkie zamówienia i koszty podróży. Po wybraniu tego przycisku pojawi się okno dialogowe wyboru **Aktualizacja podróży - wyceniona**. Tam możesz wybrać księgowanie w standardowym dniu finansowym lub określić datę księgowania, a następnie uruchomić akcję. Możesz ponownie uruchomić akcję tyle razy, ile chcesz. Można również użyć okna dialogowego **Aktualizacja podróży — Wycenone**, aby określić harmonogram, aby akcja działała jako zadanie okresowe (zadanie wsadowe). Zalecamy regularne uruchamianie akcji, konfigurując ją jako zadanie wsadowe. |
| Księguj listę przychodu | Opublikuj listę potwierdzeń dla wszystkich linii zamówień w podróży. W przypadku podróży obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania listy przyjęcia dla każdej firmy i należy je przetworzyć w każdej firmie. |
| Księguj dokument przyjęcia produktów | Zaksięguj pokwitowanie produktu dla wszystkich linii zamówienia w podróży. Proces przyjęcia produktów dla wierszy zamówienia zakupu, które są skojarzone z podróżą, będzie używany tylko wtedy, gdy towary **nie** zostaną przetworzone podczas transportu. Jeśli towary zostaną przetworzone podczas transportu, podczas próby zaksięgowania przyjęcia produktu dla wiersza zamówienia zakupu pojawi się błąd. W przypadku podróży obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania dokumentu dostawy dla każdej firmy. |
| Księguj fakturę | Opublikuj fakturę dla wszystkich linii zamówień w podróży. Jeśli towary w podróży przejdą przez proces przetwarzania towarów w tranzycie, wiersze zamówienia zakupu zostaną zafakturowane przed zakończeniem procesu odbioru. Po zafakturowaniu oryginalnego zamówienia zakupu zostaną utworzone zamówienia towarów w drodze, które są skojarzone z oryginalnymi wierszami zamówienia zakupu. Zamówienia te mogą następnie zostać odebrane przez magazyn. W przypadku wysyłek obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania faktur dla każdej firmy. |
| Wyślij zamówienie przeniesienia | Opublikuj zlecenie transferu dla wszystkich linii zlecenia transferu w podróży. Po wybraniu tego przycisku do aktualizacji będą dostępne tylko polecenia przeniesienia. |
| Przyjmuj zamówienie przeniesienia | Opublikuj paragonu zlecenia dla wszystkich linii zlecenia transferu w podróży. |
| Przyjmuj towar w drodze | Odbierz wszystkie linie zamówień, które są w trakcie podróży. Ten przycisk jest jedną z trzech dostępnych opcji odbioru towarów w tranzycie podczas podróży. (Pozostałe dwie opcje to przycisk **Utwórz arkusz przybycia**, który jest opisany w dalszej części tej tabeli, oraz aplikacja Warehouse Management). Ta opcja jest najprostszą opcją i umożliwia przetwarzanie towarów w tranzycie z magazynu towarów w tranzycie i do magazyn docelowy. Jeśli chcesz mieć większą kontrolę nad procesem, skorzystaj z dziennika przybycia lub urządzenia mobilnego, aby przetworzyć przyjęcie towarów. |
| Znajdź koszty automatyczne | Znajdź odpowiednie koszty podróży. Jeśli te koszty zostały już znalezione lub zaktualizowane, pojawi się następujący komunikat: „Istnieją niezafakturowane wiersze kosztów. Czy chcesz je zastąpić?" Wszelkie koszty, które nie były związane z podróżą w czasie tworzenia, zostaną znalezione. Koszty podróży, które są związane z podróżą i które zostały zafakturowane, nie zostaną nadpisane. |
| Utwórz arkusz przyjęcia | <p>Otwórz okno dialogowe **Tworzenie arkusza przybycia**, w którym można utworzyć arkusz przybycia określający lokalizację. W oknie dialogowym dostępne są następujące opcje:</p><ul><li>**Utwórz z towarów w drodze** lub **Utwórz z zamówienia przeniesienia** – Etykieta tej opcji zmienia się w zależności od tego, czy korzystasz z procesu transportu towarów. Ustaw ją na *Tak*, aby otworzyć stronę dziennika przybycia, która umożliwia przetwarzanie standardowego dziennika przybycia dla towarów w tranzycie, które są skojarzone z podróżą. Jeśli towar został już przyjęty w docelowym magazynie docelowym, nie zostanie dodany do wierszy arkusza przybycia.</li><li>**Inicjuj ilość** — Ustaw tę opcję na *Tak*, aby zainicjować ilość, która zostanie odebrana, na podstawie ilości towarów określonej w wierszu podróży. Jeżeli linia rejsu została częściowo odebrana, ta ilość będzie ilością pozostałą. Zaleca się, aby ta opcja była ustawiona na wartość *Tak*.</li><li>**Utwórz z wierszy zamówienia** – Ustaw tę opcję na *Tak*, aby pobrać wartość z wierszy zamówienia.</li></ul><p>Ten przycisk jest jedną z trzech dostępnych opcji odbioru towarów podczas podróży. (Pozostałe opcje to przycisk **Odbierz towary w drodze**, który opisano wcześniej w tej tabeli, oraz aplikację Warehouse Management.)</p> |
| Nalicz koszty | Koszty można naliczać, gdy typ kosztu ma konto księgowe określone dla obciążenia. Ten przycisk jest zwykle używany, gdy zapasy są w transporcie lub gdy towary zostały odebrane i zafakturowane. |
| Agreguj koszty | Przenieś koszty z poziomu kontenera wysyłkowego do poziomu podróży. Możesz użyć tego przycisku w scenariuszu usług wspólnych/wysyłki, w którym wiele podmiotów współdzieli pojemnik wysyłkowy lub miejsce na karton. Na przykład podróż ma 40-stopowy kontener transportowy i 20-stopowy kontener transportowy, a podział odbywa się według objętości. W takim przypadku towary/podmioty, które dzielą lub wykorzystują przestrzeń w 20-stopowym kontenerze wysyłkowym, mogą zostać ukarane. Aby sprawiedliwie rozłożyć koszty, niektóre organizacje mogą chcieć przenieść koszty na podróż i rozłożyć je na podstawie metody podziału na poziomie podróży. |
| Zmień szablon podróży | Otwórz okno dialogowe, w którym możesz zmienić szablon podróży. Po zmianie szablonu koszty podróży zostaną usunięte. W związku z tym konieczne może być wybranie opcji **Znajdź koszty automatyczne** (zobacz opis wcześniejszy w tej tabeli) lub ręczne ręczne dodanie kosztów ponownie. |

### <a name="buttons-on-the-general-tab"></a>Przyciski na karcie Ogólne

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Ogólne** w okienku akcji.

| Przycisk | opis |
|---|---|
| Lista przychodu | Otwórz listę przyjęć produktów dla wszystkich linii zamówień w rejsie. W przypadku podróży obejmujących wiele firm otwierana jest nowa lista rachunków dla każdej firmy. Jeśli nie przetworzono żadnych list przyjęć produktów, ten przycisk jest niedostępny. |
| Dokument przyjęcia produktów | Otwórz rekord przyjęcia produktu dla wierszy zamówienia zakupu, które są skojarzone z podróżą, jeśli ten rekord jest używany. Jeśli nie zostały zaksięgowane żadne potwierdzenia produktów, ten przycisk jest niedostępny. Proces przyjmowania produktów nie będzie używany, jeśli korzystasz z przetwarzania towarów w drodze. |
| Przyjęcie pozycji | Otwórz arkusz przybycia towaru, jeśli jest używany. |
| Śledzenie | Otwórz stronę **Śledzenia przychodzącego**, na której można zaktualizować oczekiwaną datę przybycia towarów do kontenera wysyłkowego i podróży, a następnie zaktualizować oczekiwane daty dostawy w wierszach zamówienia zakupu. |
| Zapytanie dotyczące kosztów | <p>Otwórz stronę **Zapytania o koszty**, na której widać wszystkie koszty podróży.</p><p>W okienku akcji wybierz opcję **Widok**, aby dostosować widok. Możesz wyświetlić dowolny poziom, a także kod towaru i typu kosztu.</p><p>Tylko kody typów kosztów, które są bezpośrednio związane z transakcjami magazynowymi, są wyświetlane na stronie **Zapytania o koszty**. Usuwając kody typów kosztów, możesz dostosować stronę, grupując koszty razem. Ta funkcja może być przydatna, jeśli używasz rozmiarów i kolorów.</p><p>Na stronie **Zapytania o koszty** są dostępne tylko kody typów kosztów, dla których w polu **Debet** jest ustawiona wartość *Pozycja*.</p> |
| Zamówienia towaru w drodze | Otwórz stronę **Zamówienia towarów w drodze**, która zawiera rekordy towarów w drodze dla wybranej podróży. |

## <a name="lines-view"></a>Widok wierszy

Aby otworzyć widok **Wiersze**, otworzyć podróż, a następnie wybrać kartę **Wiersze** w prawym górnym rogu nagłówka podróży.

### <a name="information-on-the-voyage-header-fasttab"></a>Informacje na skróconej karcie nagłówek podróży

Skrócona karta **Nagłówka podróży** w widoku **Wierszy** podróży zawiera podstawowe informacje opisujące podróż. Wiele pól wyświetlanych na tej skróconej karcie również pojawia się w widoku **Nagłówek**, zgodnie z opisem dalej w tym temacie.

### <a name="information-on-the-voyage-lines-fasttab"></a>Informacje na skróconej wiersza nagłówek podróży

Skrócona karta **Wierszy podróży** w widoku **Wierszy** jest związana ze szczegółami podróży i informacjami o wycenie, które mają zastosowanie na poziomie podróży. Tutaj możesz przejrzeć kontenery transportowe, folio i elementy dołączone do podróży. Wyświetlana jest również cena i ilość przedmiotów w podróży. Możesz wyświetlić dowolny kontener wysyłkowy lub folio, które są na liście, wybierając odpowiednie łącze.

### <a name="information-on-the-line-details-fasttab"></a>Informacje na skróconej karcie szczegółów wiersza

Skrócona karta **Szczegóły wiersza** w widoku **Wiersze** podróży zawiera więcej informacji o wierszu, który jest aktualnie wybrany na skróconej karcie **Wiersze podróży**. Zwróć uwagę, że ta skrócona karta zawiera szczegółowe informacje o pozycji zajmowanej przez każdy wiersz w kontenerze oraz o zadeklarowanej ilości.

## <a name="header-view"></a>Widok nagłówka

Aby otworzyć widok **Nagłówek**, otworzyć podróż, a następnie wybrać kartę **Nagłówek** w prawym górnym rogu nagłówka podróży.

### <a name="settings-on-the-general-fasttab"></a>Ustawienia na skróconej karcie Ogólne

W poniższej tabeli opisano pola dostępne na skróconej karcie **Ogólne** w widoku **Nagłówka** podróży.

| Pole | opis |
|---|---|
| Podróż | Umożliwia wprowadzenie podróży lub numeru lotu. |
| Odwołanie do rezerwacji | Jeśli Twój nadawca lub ośrodek wysyłkowy podaje numer referencyjny umożliwiający identyfikację podróży (czyli wewnętrzny numer nadawcy lub ośrodka wysyłkowego), wprowadź go tutaj. |
| Statek | Wprowadź lub wybierz środek transportu. Jeśli środek transportu nie jest wymieniony jako wartość, można wprowadzić identyfikator statku jako tekst wolny. W takim przypadku główna tabela nie jest aktualizowana, aby można było później wybrać w tym polu identyfikator statku. |
| Identyfikator podróży zewnętrznej | Wprowadź publicznie dostępny identyfikator podróży (taki jak numer lotu). |
| Kapitański lotniczy list przewozowy/list przewozowy | Wprowadź numer głównego lotniczego listu przewozowego lub listu przewozowego. Możesz określić tę wartość w przypadku wysyłki drogą lotniczą. |
| Spedytorski lotniczy list przewozowy/list przewozowy | Wprowadź domowy lotniczy list przewozowy lub list przewozowy dla kontenera wysyłkowego. |
| Wynajem | To pole wyboru należy zaznaczyć, aby wskazać, że kontener jest kontenerem wynajmowanym, który należy zwrócić. |
| opis | Wprowadź opis podróży, aby ułatwić rozpoznawanie. |
| Stan podróży | Stan podróży. Wartości obejmują: *Utworzone*, *W drodze*, *Dokumenty otrzymane* i *Wycenone*. To pole nie jest obliczane na podstawie logiki. Jest aktualizowany tylko za pośrednictwem akcji księgowania. Wartość *Wyceny* wskazuje, że otrzymano fakturę za zapasy oraz wszystkie koszty podróży. Dopóki nie zostanie odebrana faktura, podróż nie może osiągnąć stanu *Wycena*. |
| Stan zamówienia zakupu | Najwyższy stan osiągnięty wśród wszystkich zamówień zakupu skojarzonych z podróżą. |
| Otrzymano dokumenty | Wartość wskazująca, czy firma odebrała wszystkie dokumenty skojarzone z podróżą. Aby zmienić tę wartość, wybierz pozycję **Dokumenty odebrane** w grupie **Aktualizacji podróży** na karcie **Zarządzaj** w okienku akcji. |
| Firma przewozowa | Wybierz firmę przewozową dla tej podróży. To pole służy do określania kosztów automatycznych. |
| Imię i nazwisko | Nazwa firmy wybranej w polu **Firma przewozowa**. |
| Miara | To pole umożliwia określenie miary w koszcie automatycznym. Pomiary są często używane przez organizacje, które nie znają indywidualnej objętości lub wagi towarów, ale wymagają dokładniejszego podziału niż ilość lub ilość. Spedytor poda wagę lub miarkę sześcienną i możesz ją umieścić na poziomie towaru lub zamówienia. Może być aktualizowany automatycznie, jeśli parametr jest wybrany, lub może zostać wprowadzony ręcznie. |
| Jednostka miary | Jednostka miary, która ma zastosowanie do numeru w polu **Miara**. |
| Liczba palet | Określ liczbę palet w wierszu podróży. To pole jest aktualizowane automatycznie, jeśli w opcji **Automatycznie aktualizuj liczbę kartonów** jest ustawiona wartość *Tak* na karcie **Ogólne** na stronie **Parametry kosztów z wyładunkiem**. |

### <a name="settings-on-the-delivery-fasttab"></a>Ustawienia na skróconej karcie Dostawa

W poniższej tabeli opisano pola dostępne na skróconej karcie **Dostawa** w widoku **Nagłówka** podróży.

| Pole | opis |
|---|---|
| Data i godzina utworzenia | Data i czas utworzenia rekordu podróży. |
| Ex-factory — data | W tym polu wybiera się najwcześniejszą datę byłej fabryki spośród zamówień zakupu powiązanych z podróżą. Data z ex-fabryki jest dostępna w nagłówku zamówienia zakupu i jest aktualizowana za pomocą funkcji kontroli śledzenia. |
| Data wysyłki | Szacunkowa data opuszczenia miejsca opuszczenia pierwotnego portu przez samolot lub statek. |
| Data wyjazdu | Datą wyjazdu jest zazwyczaj data, kiedy samolot lub statek faktycznie opuszcza port zamorski. Data wysyłki i data wyjazdu nie muszą być zgodne. Pole **Data wyjazdu** ma wyłącznie informacyjny cel. Nie jest używane do szacowania oczekiwanej daty dostawy. Funkcja kontroli śledzenia służy do szacowania oczekiwanej daty dostawy i to pole można skonfigurować, aby to pole było automatycznie wypełniane przez funkcję kontroli śledzenia. |
| Data przekazania do magazynu | W tym polu wybiera się najwcześniejszą datę, kiedy towary z zamówień zakupu, które są powiązane z rejsem, będą dostępne do sprzedaży. |
| Szacowana data dostawy | Szacowana data dostawy jest zazwyczaj datą przybycia towarów do magazynu. To pole jest używane wyłącznie w celach informacyjnych. Nie jest używane do planowania głównego towarów. Oczekiwana data dostawy w wierszu zamówienia zakupu jest używana do planowania głównego towarów w podróży i jest aktualizowana za pomocą funkcji kontroli śledzenia. To pole można skonfigurować tak, aby było wypełniane przez funkcję kontroli śledzenia. |
| Rzeczywista data dostawy | Najwcześniejsza data dostawy oparta na towarach połączonych z podróżą. |
| Szacowany czas przybycia w porcie wysyłki | Wprowadź datę, kiedy spodziewasz się, że podróż dotrze do portu wysyłkowego, na podstawie informacji dostarczonych przez agenta spedycyjnego. |
| Otrzymano oryginalne dokumenty | Wprowadź datę, kiedy otrzymano oryginalne dokumenty. |
| Polecony broker | Wprowadź datę poinformowania brokera. |
| Oryginalny list przewozowy został wysłany | Wprowadź datę wysłania oryginalnego listu przewozowego. |
| Zwolnione towary | Wprowadź datę, kiedy towary zostały zwolnione z urzędu celnego. |
| Termin odbiorcy | Wprowadź datę terminu dostawy, czyli oczekiwaną przez klienta datę wejścia w posiadanie towarów. |
| Dostarczono do magazynu | Wprowadź datę dostarczenia towarów do magazynu. |
| Data weryfikacji | Wprowadź datę potwierdzenia. |
| Instrukcje dotyczące dostawy | Wprowadź datę otrzymania instrukcji dostawy. |
| Metoda dostawy | To pole zawiera informacje o metodzie używanej do dostarczenia podróży oraz o wyborze kosztów samochodów, które są powiązane z tą metodą dostawy. |
| Port źródłowy | Port wysyłkowy, z którego wypływa rejs. |
| Port docelowy | Port wysyłki, w którym kończy się podróż. Kontenery wysyłkowe mogą mieć różne porty, ponieważ wysyłka może być zatrzymywana na wielu portach. Weryfikowanie portu „do” na poziomie kontenera wysyłkowego umożliwia podanie dokładnych szczegółów portu dla każdego kontenera wysyłkowego w podróży. Koszt automatyczny skojarzony z transportem jest ustalany na podstawie kombinacji typu kontenera wysyłkowego, portu „do” i portu „od”. |
| Lokalny spedytor | To pole jest używane wyłącznie w celach informacyjnych. Lokalną usługę przesyłania dalej można wybrać z tabeli dostawców. |
| Data lokalnego transportu | Data rezerwacji transportu lokalnego. To pole może ułatwić planowanie magazynu. |
| Godzina lokalnego transportu | Przedział czasu zarezerwowany dla transportu lokalnego. To pole może ułatwić planowanie magazynu. |
| Szablon podróży | Szablon podróży określony dla podróży. Szablon podróży służy do wprowadzania portu „do” i „od” kontenera wysyłkowego oraz podróży. Te wartości z kolei ułatwiają identyfikację automatycznych kosztów skojarzonych z podróżą. |

### <a name="settings-on-the-other-fasttab"></a>Ustawienia na skróconej karcie Inne

W poniższej tabeli opisano pola dostępne na skróconej karcie **Inne** w widoku **Nagłówka** podróży.

| Pole | opis |
|---|---|
| Uwagi | Służy do wprowadzania dodatkowych informacji powiązanych z podróżą. |
| Data szacowania | Wybierz najwcześniejszą datę loco fabryka dla zamówień zakupu, które są powiązane z podróżą. |
| Oczekująca podróż | Funkcji tej można użyć w celu wskazania, czy wysyłka lub podróż jeszcze się nie rozpoczęła. Służy wyłącznie do celów informacyjnych.  |
| Zmiana nazwy kontenerów wysyłkowych | W przypadku podróży, które mają więcej niż jeden kontener, liczba kontenerów, które nie zostały jeszcze odebrane. |

## <a name="voyage-update-periodic-tasks"></a>Zadania okresowe aktualizacji podróży

Moduł **Koszt z wyładunkiem** zawiera kilka zadań okresowych związanych z podróżą, które mogą masowe aktualizować kilka aspektów podróży. Aby uruchomić lub zaplanować te zadania okresowe, przejdź do **Koszt z wyładunkiem \> Zadania okresowe \> Aktualizacje podróży** i wybierz jeden z następujących typów zadań:

- **Dokumenty odebrane** — To zadanie umożliwia ustawienie opcji **Dokumenty odebrane** na wartość *Tak* dla kilku podróży jednocześnie. Za pomocą ustawień **Filtru** zdefiniuj zestaw podróży, które chcesz zaktualizować.
- **W drodze** — To zadanie umożliwia ustawienie dla pola **Stan podróży** na stan w drodze, który jest ustalany na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)** dla kilku podróży w tym samym czasie. Za pomocą ustawień **Filtru** zdefiniuj zestaw podróży, które chcesz zaktualizować.
- **Gotowe do wyceny** — To zadanie umożliwia ustawienie dla pola **Stan podróży** na stan gotowe do wyceny, który jest ustalany na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)** dla kilku podróży w tym samym czasie. Zazwyczaj zadanie to jest uruchamiane zgodnie z harmonogramem.
- **Wycenone**  – To zadanie umożliwia ustawienie dla pola **Stan podróży** na stan Wycena, który jest ustalony na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)** dla kilku podróży w tym samym czasie, pod warunkiem, że zostały poddane wycenie, ale nie zostały jeszcze zaktualizowane w podróży. Zazwyczaj zadanie to jest uruchamiane zgodnie z harmonogramem.
