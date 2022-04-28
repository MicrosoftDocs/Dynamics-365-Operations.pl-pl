---
title: Prognoza zapasów
description: W tym temacie opisano funkcje prognozowania dostaw i popytu, które można wykorzystać do tworzenia prognoz zapasów w systemie Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1446928c2f5fe606d1d0732764a2a4460643afcf
ms.sourcegitcommit: 4c8223c9540fbc1c1e554962938058d432e4c681
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2022
ms.locfileid: "8548175"
---
# <a name="inventory-forecasts"></a>Prognoza zapasów

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób wyświetlania i tworzenia prognoz zapasów. Można tworzyć i wyświetlać linie prognozy dostaw i popytu dla pozycji, grup pozycji, kluczy alokacji pozycji, kont klientów, grup klientów, kont sprzedawców i grup sprzedawców.

Dla każdego wiersza prognozy można wybrać model prognozy, który jest używany. Następnie można określić pozycję lub grupę pozycji, a także ilość lub kwotę transakcji. Można także skonfigurować harmonogram alokowania ilości prognozy.

Linie prognozy dostaw i popytu tworzą prognozę zapasów dla tej samej kombinacji pozycji i modelu. Ta prognoza zapasów stanowi równowagę między podażą a popytem, które zostały wprowadzone dla tej samej pozycji. Nie można tego edytować. Prognoza zapasów pomaga zespołowi zarządzającemu zapasami przejrzeć oczekiwane zmiany w zapasach na stanie magazynowym danej pozycji w nadchodzącym okresie, który został przewidziany.

Po wprowadzeniu popytu i/lub dostaw można uruchomić planowanie prognozy, aby obliczyć zapotrzebowanie brutto na materiały i pojemność oraz wygenerować planowane zamówienia.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Umożliwia wyświetlanie i ręczne wprowadzanie wierszy prognozy

Użyj tej procedury, aby ręcznie utworzyć wiersze prognozy dla produktów.

Istnieją również inne sposoby tworzenia wierszy prognozy:

- [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md).
- [Importowanie danych historycznych na potrzeby prognozowania popytu](import-historical-data.md).
- [Generowanie prognozy za pomocą usługi sieciowej Microsoft Azure Machine Learning](demand-forecasting-setup.md).
- [Importowanie wierszy prognoz popytu lub dostaw przy użyciu struktury zarządzania danymi (encje ForecastDemandForecastEntryStaging i ForecastSupplyForecastEntryStaging)](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).

Jak pokazuje tabela w kroku 1, istnieją różne sposoby dostępu do stron, które są używane.

1. W zależności od typu podmiotu, dla którego chcesz utworzyć prognozę oraz typu prognozy, którą chcesz utworzyć, otwórz stronę prognozy dostaw, popytu lub zapasów w sposób opisany w poniższej tabeli.

    | Jednostka | Instrukcje |
    |---|---|
    | Zwolnione produkty | <ol><li>Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</li><li>Wybierz produkt, dla którego chcesz utworzyć prognozę.</li><li>W okienku akcji, na karcie **Plan**, w grupie **Prognoza** wybierz opcję **Prognoza popytu**, **Prognoza dostaw** lub **Prognoza zapasów**, w zależności od typu prognozy, z którą chcesz pracować.</li></ol> |
    | Zwolnione warianty produktu | <ol><li>Przejdź do **Zarządzanie informacjami o produkcie \> Produkty \> Zwolnione warianty produktów**.</li><li>Wybierz wariant, dla którego chcesz utworzyć prognozę.</li><li>W okienku akcji, na karcie **Plan**, w grupie **Prognoza** wybierz opcję **Prognoza popytu**, **Prognoza dostaw** lub **Prognoza zapasów**, w zależności od typu prognozy, z którą chcesz pracować.</li></ol> |
    | Grupy pozycji | <ol><li>Kliknij kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Zapasy \> Grupy inwentaryzacji**.</li><li>Wybierz grupę produktów, dla której chcesz utworzyć prognozę.</li><li>W okienku akcji wybierz **Prognoza \> Popyt**, **Prognoza \> Prognoza dostaw** lub **Prognoza \> Prognoza zapasów**, w zależności od typu prognozy, z którą chcesz pracować.</li></ol> |
    | Klucze alokacji produktów | <ol><li>Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Prognoza**.</li><li>Wybierz klucz przydziału pozycji, dla którego chcesz utworzyć prognozę.</li><li>W okienku akcji wybierz pozycję **Prognoza popytu**.</li></ol> |
    | Odbiorcy | <ol><li>Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Klienci**.</li><li>Wybierz klienta, dla którego chcesz utworzyć prognozę.</li><li>W okienku akcji wybierz pozycję **Zdefiniuj prognozę popytu**.</li></ol> |
    | Grupy odbiorców | <ol><li>Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Grupy klientów**.</li><li>Wybierz grupę klientów, dla której chcesz utworzyć prognozę.</li><li>W okienku akcji wybierz pozycję **Zdefiniuj prognozę popytu**.</li></ol> |
    | Dostawcy | <ol><li>Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Dostawcy**.</li><li>Wybierz dostawcę, dla którego chcesz utworzyć prognozę.</li><li>Aby otworzyć stronę **Wpis**, w okienku akcji wybierz **Prognoza dostaw**.</li></ol> |
    | Grupy dostawców | <ol><li>Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Grupy dostawców**.</li><li>Wybierz grupę dostawców, dla której chcesz utworzyć prognozę.</li><li>Aby otworzyć stronę **Wpis**, w okienku akcji wybierz **Prognoza dostaw**.</li></ol> | 
    | Wszystkie wiersze | <ul><li>Przejdź do **Planowania głównego \> Prognozy \> Wiersze prognozy popytu** lub **Planowania głównego \> Prognozowania \> Wierszy prognozy dostaw**, w zależności od typu prognozy, która ma być utworzona.</li></ul> |

    W zależności od tego wyboru zostanie wyświetlona strona **Prognoza dostaw** lub **Prognoza popytu**. Zawiera wszystkie istniejące wiersze prognozy dla rekordu wybranego przed otwarciem strony.

1. W okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz prognozy do siatki w górnej części strony.
1. W nowym wierszu, w polu **Model** wybierz model prognozy, który ma być użyciu. Następnie wprowadź inne szczegóły w zależności od potrzeb, takie jak pozycja, grupa pozycji, konto lub grupa klienta lub sprzedawcy, ilość pozycji lub całkowita kwota transakcji. Aby uzyskać pełne szczegóły dotyczące pól dostępnych na stronach **Prognoza dostaw** i **Prognoza popytu**, zobacz dalsze sekcje tego tematu.
1. Aby rozdzielić prognozę dla okresu, na karcie **Przegląd** zaznacz pozycję **Alokuj prognozę** na pasku narzędzi.
1. Za pomocą siatki **Alokacja** można skonfigurować horyzont czasowy i odstępy w czasie przewidziane na dystrybucję prognozowanych ilości.

## <a name="supply-forecast-lines"></a>Wiersze prognozy dostaw

Prognoza dostaw umożliwia tworzenie planu dla towarów, które muszą zostać zakupione. Mówi on pracownikom działów zaopatrzenia, co mają zamówić.

Można wprowadzić prognozę dostaw według pozycji, grupy pozycji, klucza przydziału pozycji, sprzedawcy i grupy sprzedawców. Informacje o wszystkich sposobach otwierania strony **Prognoza zaopatrzenia** dla różnych podmiotów i rekordów znajdują się w rozdziale [Wyświetlanie i ręczne wprowadzanie wierszy prognozy](#manual-entry) wcześniej w tym temacie.

W górnej części strony **Prognoza dostaw** jest ustawiona siatka wierszy prognozy dostaw oraz zestaw kart, których można użyć do wyświetlania i ustawienia dodatkowych informacji o wybranym wierszu prognozy. W dolnej części strony jest siatka **Alokacja**.

W poniższych podsekcjach opisano wszystkie pola dostępne na każdej karcie oraz wszystkie polecenia dostępne w okienku akcji na stronie i na pasku narzędzi na karcie **Przegląd**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>Polecenia okienka akcji na stronie Prognoza dostaw

W poniższej tabeli opisano komendy, które są dostępne bezpośrednio w okienku akcji na stronie **Prognoza dostaw**.

| Polecenie | opis |
|---|---|
| Zapisz | Zapisz bieżące ustawienia. |
| Edycja | Włącz edytowanie ustawień na stronie. |
| Nowa | Dodaj linię prognozy do górnej siatki. |
| Usuwanie | Usuń wybrany wiersz prognozy z górnej siatki. |
| Prognozowane salda | Wyświetlenie prognozowanych sald, które zostały obliczone dla wybranego identyfikatora modelu linii na bieżący rok fiskalny. Salda są podzielone na okresy (miesiące). |
| Prognozy przepływów pieniężnych | Wyświetlanie prognozowanych transakcji, które zostały przypisane do księgi głównej. Aby uzyskać więcej informacji, zobacz [Prognozowanie przepływów pieniężnych](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Zapasy \> Wyświetl wymiary | Wybierz wymiary magazynowe, które powinny być widoczne w siatce na karcie **Przegląd**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Polecenia paska narzędzi na karcie Przegląd na stronie Prognoza dostaw

W poniższej tabeli opisano komendy, które są dostępne bezpośrednio w pasku narzędzi, na karcie **Przegląd** na stronie **Prognoza dostaw**.

| Polecenie | opis |
|---|---|
| Przydziel prognozę | Jeśli używasz metody alokacji, wygeneruj poszczególne wiersze harmonogramu dla prognozowanej transakcji. Ilość linii jest następnie rozdzielana według daty (zgodnie z wybranymi przedziałami czasowymi), ilości oraz kwoty dla całego horyzontu czasowego. (Zobacz sekcję [Alokacja zapasów](#allocate-forecast) w dalszej części tego tematu). |
| Aktualizacja zbiorcza | Otwórz stronę **Edycja transakcji prognozowych**. (Zobacz sekcję [Transakcje prognozowane aktualizacji zbioru](#bulk-update) w dalszej części tego tematu). |
| Prognoza zapasów | Umożliwia otwarcie widoku strony **Prognoza zapasów**, który jest filtrowany dla wybranej kombinacji towaru/modelu. (Zobacz sekcję [Prognoza zapasów](#inventory-forecast) w dalszej części tego tematu). |
| Utwórz zapotrzebowanie na towary | Otwiera okno dialogowe, w którym można utworzyć wymagania dotyczące pozycji oraz linie dziennika zamówień lub pozycji dla transakcji prognoz związanych z projektem. Chociaż polecenie to jest dostępne zarówno dla wierszy prognozy dostaw, jak i dla wierszy prognozy popytu, nie można go użyć na stronie **Prognoza dostaw**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>Zakładka Przegląd na stronie Prognoza dostaw

W poniższej tabeli opisano pola na karcie **Przegląd** strony **Prognoza dostaw**.

| Pole | opis |
|---|---|
| **Model** | Model prognozy, z którym jest skojarzona ta transakcja. |
| **Data** | Data rozpoczęcia transakcji. |
| **Konto dostawcy** | Konto dostawcy skojarzone z transakcją. |
| **Grupa dostawców** | Konto grupy dostawcy skojarzone z transakcją. |
| **Numer pozycji** | Identyfikator towaru. |
| **Grupa pozycji** | Grupa towarów, z którą jest skojarzona transakcja. |
| **Klucz alokacji produktów** | Klucz alokacji towaru skojarzony z prognozą. |
| **Ilość efektywna** | Przewidywana ilość w określonej jednostce ilości efektywnej. |
| **Jednostka ilości efektywnej** | Umożliwia ilości efektywnej, w której produkt jest kupowany. Wartość ta jest automatycznie pobierana z ustawienia pozycji. |
| **Ilość** | Przewidywana ilość w określonej jednostce zakupowej. |
| **Jednostka** | Jednostka, w której produkt jest kupowany. Wartość ta jest automatycznie pobierana z ustawienia pozycji. Jeśli jednak są ustawione konwersje jednostek, można to zmodyfikować. |
| **Ilość** | Kwota, którą transakcja prognozy wnosi do prognozy, czyli kwota brutto pomniejszona o rabaty. |
| **Waluta** | Kod waluty używanej dla danej prognozy transakcji. Domyślna waluta jest wprowadzana automatycznie, ale można wybrać inną walutę. |
| (Inne wymiary) | Dodatkowe wymiary mogą być wyświetlane jako kolumny w siatce. Aby wybrać dodatkowe wymiary, które będą wyświetlane, wybierz **Wyświetl wymiary** na pasku akcji. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>Zakładka Ogólne na stronie Prognoza dostaw

Zakładka **Ogólne** zawiera więcej informacji na temat wiersza, który jest aktualnie zaznaczony na zakładce **Przegląd**. Niektóre z tych informacji są powtórzone z zakładki **Przegląd**. Poniższa tabela opisuje pola, które są unikalne dla zakładki **Ogólne**.

| Pole | opis |
|---|---|
| Raport | Zaznaczenie tej opcji jako *Tak* spowoduje uwzględnienie transakcji w raportach. |
| Komentarze | Wprowadź wszelkie komentarze, które masz na temat prognozowanej transakcji. |
| Aktywni | Zaznacz to pole wyboru, aby uwzględnić transakcję w raportach budżetowych. |
| Uwzględnij w prognozach przepływów pieniężnych | Zaznacz pole wyboru, aby przypisać prognozowaną transakcję do księgi głównej. Ustawienie tego pola wyboru nie może być modyfikowane dla transakcji sprawozdawczych. |
| Grupa podatków | Grupa podatkowa, która jest używana do określenia podatku dla prognozowanej transakcji. |
| Grupa podatków dla pozycji | Grupa podatków dla towaru użyta w celu określenia podatku dla transakcji prognozy. |
| Metoda | <p>Wybierz metodę, która jest używana do alokacji prognozowanej transakcji:</p><ul><li>**Brak** — nie ma alokacji.</li><li>**Okres** — prognozuj tę samą ilość dla każdego okresu. Po wybraniu tej wartości należy określić ilość w polu **Na** oraz jednostkę czasu w polu **Jednostka**.</li><li>**Klucz** — przydzielenie prognozy zgodnie z kluczem alokacji okresu określonym w polu **Klucz okresu**. Ta metoda może być stosowana w celu uwzględnienia odchyleń sezonowych.</li></ol>|
| Na | <p>Umożliwia wprowadzenie liczby interwałów czasu w przyszłości, na które rozciąga się prognoza. To pole jest dostępne tylko w przypadku wybrania opcji *Okres* w polu **Metoda**.</p><p>Na przykład wybiera się *Okres* w polu **Metoda**, wpisuje się *1* w polu **Na**, wybiera się *Miesiące* w polu **Jednostka**. W polu **Zamknięcie** określ datę końcową wybiegającą o 1 rok w przyszłość. W tym przypadku zostanie utworzony jeden wiersz prognozy dla każdego miesiąca nadchodzącego roku, w oparciu o pozycję i ilość, które są określone w wierszu nagłówka.</p> |
| Jednostka | Umożliwia wybranie jednostki interwału czasu: *dni*, *miesiące* lub *lata*. Alokacja odpowiadająca liczbie dni, miesięcy lub lat określonej w polu **Na**.|
| Klucz okresu | Określ klucz alokacji okresu. |
| Zakończenie | Data końcowa w kontekście używania pól **Na** i **Jednostka**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>Zakładka Element na stronie Prognoza dostaw

Wybierz kartę **Element**, aby wyświetlić więcej informacji o elemencie aktualnie wybranym na karcie **Przegląd**.

Siatka w górnej części zakładki **Element** powtarza informacje z zakładki **Przegląd**. Dodatkowo zawiera pole **Cena jednostki**, które pokazuje cenę zakupu dla ilości sztuk określonej w polu **Jednostka**. Cena jednostkowa jest automatycznie pobierana z ustawień elementu, ale można ją modyfikować.

Pola poniżej siatki zawierają więcej szczegółów dotyczących pozycji. Niektóre z tych informacji są powtarzane na karcie **Przegląd**. W poniższej tabeli opisano pola unikatowe dla karty **Element**.

| Pole | opis |
|---|---|
| Jednostka cenowa | Liczba jednostek, których dotyczy cena zakupu. Wartość jest automatycznie pobierana z tabeli Elementy, ale możesz ją zmodyfikować. |
| Opłaty związane z zakupami | Opłaty stałe od ceny zakupu. Opłaty są niezależne od ilości. |
| Procent rabatu | Rabat wyrażony jako wartość procentowa. |
| Kwota rabatu | Rabat wyrażony w kwocie przypadającej na jednostkę sprzedaży. |
| Kwota brutto | Kwota, gdy nie są stosowane żadne rabaty. |
| Ilość | Ilość transakcji w jednostce inwentarzowej danej pozycji. |
| BOM podrzędny | Numer BOM określonego BOM podrzędnego. |
| Podmarszruta | Numer marszruty określonej podmarszruty. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>Zakładka Wymiary finansowe na stronie Prognoza dostaw

Na karcie **Wymiary finansowe** są podane wszystkie wartości wymiarów finansowych dla wiersza aktualnie wybranego na karcie **Przegląd**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>Zakładka Wymiary zapasów na stronie Prognoza dostaw

Na karcie **Wymiary zapasów** są podane wszystkie wartości wymiarów zapasów dla wiersza aktualnie wybranego na karcie **Przegląd**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>Zakładka Siatka alokacji na stronie Prognoza dostaw

Jeśli korzystasz z klucza przydziału pozycji lub wprowadziłeś prognozę pozycji na jeden lub więcej przyszłych okresów, możesz przydzielić prognozę, wybierając **Alokuj prognozę** na pasku narzędzi na zakładce **Przegląd**. Ilość jest wtedy rozdzielana w sposób wskazany przez linie w siatce **Przydziel**.

## <a name="demand-forecast-lines"></a>Wiersze prognozy popytu

Prognoza zapotrzebowania pozwala na wprowadzenie lub wygenerowanie zapotrzebowania dla klienta. Pomaga pracownikom działu sprzedaży i marketingu w informowaniu pracowników działu planowania głównego o przewidywanym popycie w nadchodzącym okresie prognozy.

Możesz wprowadzić prognozę popytu według pozycji, grupy pozycji, klucza przydziału pozycji, klienta i grupy klientów. Informacje o wszystkich sposobach otwierania strony **Prognoza popytu** dla różnych podmiotów i rekordów znajdują się w rozdziale [Wyświetlanie i ręczne wprowadzanie wierszy prognozy](#manual-entry) wcześniej w tym temacie.

W górnej części strony **Prognoza popytu** jest ustawiona siatka wierszy prognozy popytu oraz zestaw kart, których można użyć do wyświetlania i ustawienia dodatkowych informacji o wybranym wierszu prognozy. W dolnej części strony jest siatka **Alokacja**.

W poniższych podsekcjach opisano wszystkie pola dostępne na każdej karcie oraz wszystkie polecenia dostępne w okienku akcji na stronie i na pasku narzędzi na karcie **Przegląd**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>Polecenia okienka akcji na stronie Prognoza popytu

W poniższej tabeli opisano komendy, które są dostępne bezpośrednio w okienku akcji na stronie **Prognoza popytu**.

| Polecenie | opis |
|---|---|
| Zapisz | Zapisz bieżące ustawienia. |
| Edycja | Włącz edytowanie ustawień na stronie. |
| Nowa | Dodaj linię prognozy do górnej siatki. |
| Usuwanie | Usuń wybrany wiersz prognozy z górnej siatki. |
| Prognozowane salda | Wyświetlenie prognozowanych sald, które zostały obliczone dla wybranego identyfikatora modelu linii na bieżący rok fiskalny. Salda są podzielone na okresy (miesiące). |
| Prognoza przepływów pieniężnych | Wyświetlanie prognozowanych transakcji, które zostały przypisane do księgi głównej. Aby uzyskać więcej informacji, zobacz [Prognozowanie przepływów pieniężnych](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Wyświetl wymiary | Wybierz wymiary produktu, magazynowania i śledzenia, które powinny być widoczne w siatce na karcie **Przegląd**. |
| Podgląd księgi głównej | Wyświetlenie zapisów księgi głównej dla wybranej transakcji. |
| Przenieś wiersze oferty | Przenosi wiersze oferty do wybranego projektu. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Polecenia paska narzędzi na karcie Przegląd na stronie Prognoza popytu

W poniższej tabeli opisano komendy, które są dostępne bezpośrednio w pasku narzędzi, na karcie **Przegląd** na stronie **Prognoza popytu**.

| Polecenie | opis |
|---|---|
| Przydziel prognozę | Jeśli używasz metody alokacji, wygeneruj poszczególne wiersze harmonogramu dla prognozowanej transakcji. Ilość linii jest następnie rozdzielana według daty (zgodnie z wybranymi przedziałami czasowymi), ilości oraz kwoty dla całego horyzontu czasowego. (Zobacz sekcję [Alokacja zapasów](#allocate-forecast) w dalszej części tego tematu).|
| Aktualizacja zbiorcza | Otwórz stronę **Edycja transakcji prognozowych**. (Zobacz sekcję [Transakcje prognozowane aktualizacji zbioru](#bulk-update) w dalszej części tego tematu). |
| Prognoza zapasów | Umożliwia otwarcie widoku strony **Prognoza zapasów**, który jest filtrowany dla wybranej kombinacji towaru/modelu. (Zobacz sekcję [Prognoza zapasów](#inventory-forecast) w dalszej części tego tematu). |
| Utwórz zapotrzebowanie na towary | Otwiera okno dialogowe, w którym można utworzyć wymagania dotyczące pozycji oraz linie dziennika zamówień lub pozycji dla transakcji prognoz związanych z projektem. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>Zakładka Przegląd na stronie Prognoza popytu

W poniższej tabeli opisano pola na karcie **Przegląd** strony **Prognoza popytu**.

| Pole | opis |
|---|---|
| **Nazwa zadania** | Nazwa zadania wsadowego, które zostało użyte do utworzenia wiersza prognozy. |
| **Model** | Model prognozy, z którym jest skojarzona ta transakcja. |
| **Data** | Data rozpoczęcia transakcji. |
| **Konto odbiorcy** | Konto klienta, z którym powiązana jest transakcja. |
| **Grupa odbiorców** | Grupa klientów, z którą powiązana jest transakcja. |
| **Numer pozycji** | Identyfikator towaru. |
| **Nazwa produktu** | Opis towaru. |
| **Klucz alokacji produktów** | Klucz alokacji pozycji, który jest wykorzystywany podczas alokacji prognozy zapasów. |
| **Ilość sprzedaży** | Ilość transakcji w podanej jednostce sprzedaży. |
| **Jednostka** | Jednostka sprzedaży towaru. |
| **Ilość** | Kwota, którą transakcja prognozy wnosi do prognozy, czyli kwota brutto pomniejszona o rabaty. |
| **Cena sprzedaży** | Cena sprzedaży dla liczby jednostek określonej w polu **Jednostka cenowa**. Wartość jest pobierana z ustawienia elementu, ale można ją modyfikować. |
| **Waluta sprzedaży** | Kod waluty używanej dla danej prognozy transakcji. Domyślna waluta jest wprowadzana automatycznie, ale można wybrać inną walutę. |
| **Ilość efektywna** | Przewidywana ilość w określonej jednostce ilości efektywnej. |
| **Jednostka ilości efektywnej** | Umożliwia ilości efektywnej, w której produkt jest sprzedawany. Wartość ta jest automatycznie pobierana z ustawienia pozycji. |
| (Inne wymiary) | Dodatkowe wymiary produktu, magazynu i śledzenia mogą być wyświetlane w postaci kolumn w siatce. Aby wybrać dodatkowe wymiary, które będą wyświetlane, wybierz **Wyświetl wymiary** na pasku akcji. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>Zakładka Ogólne na stronie Prognoza popytu

Zakładka **Ogólne** zawiera więcej informacji na temat wiersza, który jest aktualnie zaznaczony na zakładce **Przegląd**. Niektóre z tych informacji są powtórzone z zakładki **Przegląd**. Poniższa tabela opisuje pola, które są unikalne dla zakładki **Ogólne**.

| Pole | opis |
|---|---|
| Numer sekwencyjny prognozy popytu | Unikatowy numer wiersza prognozy popytu. Ten numer jest generowany przy użyciu sekwencji numerów wybranej dla prognoz popytu na stronie **Parametry planowania głównego**. |
| Grupa pozycji | Grupa towarów, z którą jest skojarzona transakcja. |
| Raport | Zaznaczenie tej opcji jako *Tak* spowoduje uwzględnienie transakcji w raportach. |
| Komentarze | Wprowadź wszelkie komentarze, które masz na temat prognozowanej transakcji. |
| Aktywni | Zaznacz to pole wyboru, aby uwzględnić transakcję w raportach budżetowych. Ustawienie tego pola wyboru nie może być modyfikowane dla transakcji sprawozdawczych. |
| Uwzględnij w prognozach przepływów pieniężnych | Zaznacz pole wyboru, aby przypisać prognozowaną transakcję do księgi głównej. Ustawienie tego pola wyboru nie może być modyfikowane dla transakcji sprawozdawczych. Aby uzyskać więcej informacji, zobacz [Prognozowanie przepływów pieniężnych](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Grupa podatków | Grupa podatkowa, która jest używana do określenia podatku dla prognozowanej transakcji. |
| Grupa podatków dla pozycji | Grupa podatków dla towaru użyta w celu określenia podatku dla transakcji prognozy. |
| Metoda | <p>Wybierz metodę, która jest używana do alokacji prognozowanej transakcji:</p><ul><li>**Brak** — nie ma alokacji.</li><li>**Okres** — prognozuj tę samą ilość dla każdego okresu. Po wybraniu tej wartości należy określić ilość w polu **Na** oraz jednostkę czasu w polu **Jednostka**.</li><li>**Klucz** — przydzielenie prognozy zgodnie z kluczem alokacji okresu określonym w polu **Klucz okresu**. Ta metoda może być stosowana w celu uwzględnienia odchyleń sezonowych.</li><ul>|
| Na | <p>Umożliwia wprowadzenie liczby interwałów czasu w przyszłości, na które rozciąga się prognoza. To pole jest dostępne tylko w przypadku wybrania opcji *Okres* w polu **Metoda**.</p><p>Na przykład wybiera się *Okres* w polu **Metoda**, wpisuje się *1* w polu **Na**, wybiera się *Miesiące* w polu **Jednostka**. W polu **Zamknięcie** określ datę końcową wybiegającą o 1 rok w przyszłość. W tym przypadku zostanie utworzony jeden wiersz prognozy dla każdego miesiąca nadchodzącego roku, w oparciu o pozycję i ilość, które są określone w wierszu nagłówka. |
| Jednostka | Umożliwia wybranie jednostki interwału czasu: *dni*, *miesiące* lub *lata*. Alokacja odpowiadająca liczbie dni, miesięcy lub lat określonej w polu **Na**.|
| Klucz okresu | Umożliwia określenie klucza alokacji okresu używanego do alokacji prognozy. Aby uzyskać więcej informacji, zobacz [Priorytety planowania budżetu](../../finance/budgeting/budget-planning-data-allocation.md). |
| Zakończenie | Data końcowa w kontekście używania pól **Na** i **Jednostka**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>Zakładka Element na stronie Prognoza popytu

Zakładka **Element** zawiera więcej informacji na temat elementu, który jest aktualnie zaznaczony na zakładce **Przegląd**. Niektóre z tych informacji są powtórzone z zakładki **Przegląd**. Poniższa tabela opisuje pola, które są unikalne dla zakładki **Element**.

| Pole | opis |
|---|---|
| Jednostka cenowa | Liczba jednostek sprzedaży, które dotyczy cena sprzedaży. Wartość jest automatycznie pobierana z tabeli Elementy, ale możesz ją zmodyfikować. |
| Opłaty od sprzedaży | Opłaty stałe doliczane do ceny sprzedaży. Opłaty są niezależne od ilości. |
| Koszt własny | Koszt dla bieżącej transakcji prognozy na jednostkę magazynową. Wartość jest pobierana z tabeli towarów, ale można ją zmienić. |
| Procent rabatu | Rabat wyrażony jako wartość procentowa. |
| Kwota rabatu | Rabat wyrażony w kwocie przypadającej na jednostkę sprzedaży. |
| Kwota brutto | Kwota, gdy nie są stosowane żadne rabaty. |
| Stan zapasów | Ilość transakcji w jednostce inwentarzowej danej pozycji. |
| Użyj określonego BOM | Numer BOM określonego BOM. |
| Użycie określonej marszruty | Numer marszruty określonej podmarszruty. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>Zakładka Projekt na stronie Prognoza popytu

Zakładka **Projekt** zawiera więcej informacji na temat projektu, który jest aktualnie zaznaczony na zakładce **Przegląd**. Niektóre z tych informacji są powtórzone z zakładki **Przegląd**, **Ogólne** lub **Element**. Poniższa tabela opisuje pola, które są unikalne dla zakładki **Projekt**.

| Pole | opis |
|---|---|
| Data projektu | Data zawarcia transakcji prognozy popytu. |
| Identyfikator projektu | Identyfikator projektu, do którego odwołuje się bieżąca transakcja. |
| Źródło finansowania | Źródło finansowania, z którym związana jest prognoza popytu. |
| Numer działania | Czynność, która jest związana z transakcją prognozy popytu. |
| Kategoria | Kategoria kosztów dla bieżącej transakcji. |
| Właściwość wiersza | Stan, do którego dołączona jest transakcja. |
| Identyfikator transakcji | Identyfikator systemowy dla transakcji prognozy popytu. |
| Kwota kosztów | Kwota transakcji prognozy popytu. |
| Cena jednostkowa | Cena na jednostkę. |
| Zmodyfikowana przez | Identyfikator pracownika, który jako ostatni modyfikował wybraną transakcję. |
| Data faktury | Wprowadź oczekiwaną datę wystawienia faktury. |
| Data eliminacji | Umożliwia wyświetlenie lub zmianę daty eliminacji. Po utworzeniu prognozy data eliminacji jest ustawiana na datę końcową projektu. Jeśli projekt nie ma daty końcowej, stosowana jest data projektu. Pole dotyczy projektów z ceną stałą oraz projektów inwestycyjnych. |
| Data płatności kosztu | Należy wprowadzić oczekiwaną datę płatności za zakup. |
| Data płatności za sprzedaż | Należy wprowadzić oczekiwaną datę płatności za sprzedaż. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>Zakładka Wymiary finansowe na stronie Prognoza popytu

Na karcie **Wymiary finansowe** są podane wszystkie wartości wymiarów finansowych dla wiersza aktualnie wybranego na karcie **Przegląd**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>Zakładka Wymiary zapasów na stronie Prognoza popytu

Na karcie **Wymiary zapasów** są podane wszystkie wartości wymiarów zapasów dla wiersza aktualnie wybranego na karcie **Przegląd**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>Zakładka Siatka alokacji na stronie Prognoza popytu

Jeśli korzystasz z klucza przydziału pozycji lub wprowadziłeś prognozę pozycji na jeden lub więcej przyszłych okresów, możesz przydzielić prognozę, wybierając **Alokuj prognozę** na pasku narzędzi na zakładce **Przegląd**. Ilość jest wtedy rozdzielana w sposób wskazany przez linie w siatce **Przydziel**. (Zobacz sekcję [Alokacja zapasów](#allocate-forecast) w dalszej części tego tematu).

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Prognoza zapasów

Strony wierszy prognozy podaży i popytu mają przycisk **Prognoza zapasów**, który otwiera widok strony **Prognozy zapasów**, który jest filtrowany dla tej samej kombinacji towaru/modelu. Ta prognoza zapasów stanowi równowagę między podażą a popytem, które zostały wprowadzone dla tej samej pozycji. Nie można tego edytować. Prognoza zapasów pomaga zespołowi zarządzającemu zapasami przejrzeć oczekiwane zmiany w zapasach na stanie magazynowym danej pozycji w nadchodzącym okresie, który został przewidziany.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>Okienko akcji na stronie Prognoza zapasów

W poniższej tabeli opisano komendy, które są dostępne bezpośrednio w okienku akcji na stronie **Prognoza zapasów**.

| Akcja | opis |
|---|---|
| Prognoza dostaw | Umożliwia otwarcie widoku strony **Prognoza dostaw**, która jest filtrowana dla tej samej kombinacji pozycji/modelu/daty. |
| Prognoza popytu | Umożliwia otwarcie widoku strony **Prognoza popytu**, która jest filtrowana dla tej samej kombinacji pozycji/modelu/daty. |
| Zapasy \> Wyświetl wymiary | Wybierz wymiary produktu, magazynowania i śledzenia, które powinny być widoczne w siatce na siatce **Przegląd**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>Siatka na stronie prognozy zapasów

W poniższej tabeli opisano kolumny w polach na stronie **Prognoza zapasów**.

| Pole | opis |
|---|---|
| **Model** | Model prognozy, z którym jest skojarzona ta transakcja. |
| **Numer pozycji** | Identyfikator towaru. |
| **Data budżetu** | Data zawarcia transakcji prognozy. |
| **Typ budżetu** | Źródło transakcji (*Prognoza popytu* lub *Prognoza dostaw*). |
| **Ilość efektywna** | Przewidywana ilość w jednostce ilości efektywnej. |
| **Ilość** | Ilość prognozowana w jednostkach magazynowych. |
| **Ilość efektywna narastająco** | Skumulowana prognozowana ilość w jednostce ilości efektywnej, gdy dla tej samej pozycji skumulowano wiele wierszy prognozy. |
| **BOM podrzędny** | Numer BOM określonego BOM podrzędnego. |
| **Podmarszruta** | Numer marszruty określonej podmarszruty. |
| (Inne wymiary) | Dodatkowe wymiary mogą być wyświetlane jako kolumny w siatce. Aby wybrać dodatkowe wymiary, które będą wyświetlane, wybierz **Zapasy \> Wyświetl wymiary** na pasku akcji. |

## <a name="allocate-forecast"></a><a name="allocate-forecast"></a>Przydziel prognozę

Poniższa procedura umożliwia przetwarzanie wybranych wierszy transakcji prognozy. Podczas alokowania prognozy ilość jest dystrybuowana zgodnie z wierszami w siatce **Alokacja**.

1. W zależności od typu encji, dla której chcesz utworzyć prognozę, oraz typu prognozy, którą chcesz utworzyć, otwórz stronę prognozy podaży lub popytu zgodnie z opisem w temacie [Wyświetlanie i ręczne wprowadzanie wierszy prognozy](#manual-entry).
1. Na stronie wiersze prognozy podaży lub popytu zaznacz wiersz prognozy, a następnie na karcie **Przegląd** wybierz pozycję **Alokacja prognozy** na pasku narzędzi.
1. W oknie dialogowym **Alokacja prognozy** należy ustawić pola opisane w poniższej tabeli. (Wartość wybierana w polu **Metoda** określa, czy inne dostępne pola są dostępne).

    | Pole | opis |
    |---|---|
    | Metoda | <p>Wybierz metodę, która jest używana do alokacji prognozowanej transakcji:</p><ul><li>**Brak** — nie ma alokacji.</li><li>**Okres** — prognozuj tę samą ilość dla każdego okresu. Po wybraniu tej wartości należy określić ilość w polu **Na** oraz jednostkę czasu w polu **Jednostka**.</li><li>**Klucz** — przydzielenie prognozy zgodnie z kluczem alokacji okresu określonym w polu **Klucz okresu**. Ta metoda może być stosowana w celu uwzględnienia odchyleń sezonowych.</li><ul>|
    | Na | <p>Umożliwia wprowadzenie liczby interwałów czasu w przyszłości, na które rozciąga się prognoza. To pole jest dostępne tylko w przypadku wybrania opcji *Okres* w polu **Metoda**.</p><p>Na przykład wybiera się *Okres* w polu **Metoda**, wpisuje się *1* w polu **Na**, wybiera się *Miesiące* w polu **Jednostka**. Następnie w polu **Zamknięcie** określ datę końcową wybiegającą o jeden rok w przyszłość. W tym przypadku zostanie utworzony jeden wiersz prognozy dla każdego miesiąca nadchodzącego roku, w oparciu o pozycję i ilość, które są określone w wierszu nagłówka. |
    | Jednostka | Umożliwia wybranie jednostki interwału czasu: *dni*, *miesiące* lub *lata*. Alokacja odpowiadająca liczbie dni, miesięcy lub lat określonej w polu **Na**.|
    | Klucz okresu | Umożliwia określenie klucza alokacji okresu używanego do alokacji prognozy. Aby uzyskać więcej informacji, zobacz [Priorytety planowania budżetu](../../finance/budgeting/budget-planning-data-allocation.md). |
    | Zakończenie | Określ datę końcową obowiązującą dla ustawień w polach **Na** i **Jednostka**. |

1. Wybierz przycisk **OK**, aby potwierdzić wybór ustawień.
1. Wyniki można przejrzeć na karcie **Alokacja** dla tego samego wiersza.

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Zbiorcza aktualizacja prognoz transakcji

Ta procedura umożliwia przetwarzanie istniejących wierszy transakcji prognozy. Można kopiować, edytować i usuwać wiersze transakcji prognozy.

1. Na stronie wiersze prognozy popytu lub podaży wybierz opcję **Aktualizacja zbiorcza**.
1. W oknie dialogowym kliknij **Filtruj**.
1. Na karcie **Zakres** wybierz kryteria wyboru źródłowych danych prognozy, które chcesz kopiować, edytować lub usunąć. Dane mogą uwzględnić model prognozy, numer towaru i konto odbiorcy.
1. Wybierz przycisk **OK**, aby potwierdzić wybór opcji.

    Po wybraniu danych można użyć okna dialogowego **Edytuj prognozowane transakcje** , aby określić sposób ich kopiowania, edycji lub usunięcia.

    > [!NOTE]
    > Krok filtrowania jest warunkiem wstępnym używania funkcji **edycji zbiorczej**. Jeśli zostanie pominięty, program wybierze i aktualizuje **wszystkie** wiersze prognozy. W związku z tym może wystąpić nieumyślne przyczyny duplikowania lub usuwania transakcji.

1. W sekcji **Zarządzanie** określ, czy chcesz skopiować, zaktualizować czy usunąć wybrane transakcje prognoz.
1. Sekcja **Modyfikacje w polu** umożliwia zmianę parametrów prognozy. Zaznaczyć pole wyboru dla parametru, a następnie wybrać spośród dostępnych opcji. Na przykład zaznacz pole wyboru **Model**, a następnie wybierz numer modelu prognozy. Istniejące wiersze prognozy są kopiowane do wybranego modelu prognozy.
1. Sekcja **Zmiana okresu** zawiera informacje o przenoszeniu dat rozpoczęcia i zakończenia prognozy w przód lub w tył. Zaznacz pole wyboru, a następnie użyj pól ilość i okres, aby określić, w jaki sposób daty prognozy mają być przenoszone. Można wprowadzić ilość ujemną, aby przesunąć datę rozpoczęcia do przodu (czyli wcześniej).

    Na przykład, aby opóźnić datę rozpoczęcia prognozowanej transakcji o sześć miesięcy, należy zaznaczyć pole wyboru, wprowadzić *6* jako ilość oraz wybrać *Miesiące* jako okres.

1. Użyj sekcji **Poprawne pole**, aby zaktualizować aktualne dane prognozy. W polu **Pole** wybierz kryterium, które chcesz zmienić. W polu **Czynnik** wprowadź współczynnik mnożenia stosowany dla wybranego kryterium lub wprowadź stałą dodawania lub odejmowania. Na przykład wybierz jako kryterium *ilość*, a następnie wprowadź współczynnik *1,5*, aby pomnożyć ilość artykułu przez 1,5. Alternatywnie, wprowadź stałą *-25*, aby zmniejszyć ilość towaru o 25 jednostek.
1. Sekcja **Wymiary finansowe** jest dostępna do aktualizowania wymiarów finansowych wierszy prognozy. Wybierz wymiary finansowe, które chcesz zmienić, a następnie wprowadź wartość, która ma być mająca zastosowanie do wybranych wymiarów.
1. Wybierz **OK**, aby zastosować zmiany.

## <a name="use-forecasts-with-master-planning"></a>Wykorzystanie prognoz w planowaniu ogólnym

Po wprowadzeniu prognozy popytu i/lub podaży można uwzględnić prognozy podczas planowania nadrzędnego, aby uwzględnić oczekiwany popyt i/lub podaż w przebiegu planowania nadrzędnego. Gdy prognozy są uwzględniane w planowaniu ogólnym, obliczane jest zapotrzebowanie brutto na materiały i moce produkcyjne, a następnie generowane są planowane zamówienia.

### <a name="set-up-a-master-plan-to-include-an-inventory-forecast"></a>Stworzenie planu generalnego obejmującego prognozę zapasów

Aby skonfigurować plan główny tak, aby zawierał prognozę zapasów, należy wykonać następujące czynności.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz istniejący plan lub utwórz nowy plan.
1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - W polu **Model prognozy** wybierz model prognozy. Ten model będzie brany pod uwagę podczas generowania sugestii dostaw dla bieżącego planu głównego.
    - **Uwzględnij prognozę podaży** — tę opcję należy określić jako *wartość tak*, aby uwzględnić prognozę podaży w bieżącym planie głównym. Jeśli zostanie ustawiona wartość *nie*, transakcje prognozy podaży nie będą uwzględniane w planie głównym.
    - **Uwzględnij prognozę popytu** — tę opcję należy określić jako *wartość tak*, aby uwzględnić prognozę popytu w bieżącym planie głównym. Jeśli zostanie ustawiona wartość *nie*, transakcje prognozy popytu nie będą uwzględniane w planie głównym.
    - **Metoda używana do redukowania zapotrzebowań prognozowanych** — umożliwia wybór metody, która ma zostać użyta do zmniejszenia prognozowanych zapotrzebowań. Aby uzyskać więcej informacji, zobacz [Klucze do redukcji prognoz](planning-optimization/demand-forecast.md#reduction-keys).

1. Na karcie FastTab dla **Horyzontu czasowego w dniach** można ustawić następujące pola, aby określić okres, w którym Prognoza podaży jest uwzględniana w czasie:

    - **Plan wg prognozy** — ustawienie tej opcji na *tak* powoduje zastąpienie horyzontu czasowego planu wg prognozy, który pochodzi z poszczególnych grup zapotrzebowania. Ustaw na *nie*, aby używać wartości z poszczególnych grup zapotrzebowania dla bieżącego planu głównego.
    - **Okres prognozy** — w przypadku ustawienia **opcji planu według prognozy** na wartość *tak* należy określić liczbę dni (od dzisiejszej daty), jaka powinna zostać zastosowana w prognozie popytu.

    > [!IMPORTANT]
    > Osobne **planowanie prognozy** nie jest obsługiwane w przypadku optymalizacji planowania.

### <a name="run-a-master-plan-that-includes-an-inventory-forecast"></a>Wykonanie planu generalnego, który zawiera prognozę zapasów

Aby uruchomić plan generalny zawierający prognozę zapasów, należy wykonać poniższe kroki.

1. Przejdź do **Planowanie główne \> Obszary robocze \> Planowanie główne**.
1. W polu **Plan główny** wprowadź lub wybierz plan główny, który został ustawiony w poprzedniej procedurze.
1. Na kafelku **Planowanie główne** wybierz **Uruchom**.
1. W oknie dialogowym **Planowanie główne** ustaw opcję **Czas przetwarzania śledzenia** na *Tak*.
1. W polu **Liczba wątków** wprowadź liczbę.
1. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
1. Zostanie wyświetlone standardowe okno dialogowe edycji zapytania. Na karcie **Zakres** wybierz wiersz, w którym pole w **Polu** ma wartość *kod towaru*.
1. W polu **Kryteria** wybierz numer towaru, który ma być uwzględniany w planie.
1. Kliknij przycisk **OK**.

Aby wyświetlić obliczone zapotrzebowania, otwórz stronę **Zapotrzebowanie brutto**. Na przykład na stronie **Zwolnione produkty** na karcie **Plan** w sekcji **Zapotrzebowania** wybierz grupę **Zapotrzebowanie brutto**.

Aby wyświetlić wygenerowane zamówienia planowane, przejdź do **Planowania głównego \> Typowe \> Zamówienia planowane** i wybierz odpowiedni plan według prognozy.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie prognozowania popytu](introduction-demand-forecasting.md)
- [Ustawienia prognozowania popytu](demand-forecasting-setup.md)
- [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)
- [Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)
- [Planowanie główne z uwzględnieniem prognoz popytu](planning-optimization/demand-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]