---
title: Wersja zapoznawcza aplikacji Dynamics 365 Supply Chain Management 10.0.29 (październik 2022 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 5a87fb4ac2d01ef3b188b63dfc98bcfac2daf033
ms.sourcegitcommit: d2046cad5de570e6302a4390b41881a7ecb12e26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2022
ms.locfileid: "9520758"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10029-october-2022"></a>Wersja zapoznawcza aplikacji Dynamics 365 Supply Chain Management 10.0.29 (październik 2022 r.)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.29. Ta wersja ma numer kompilacji 10.0.1326 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza wydania:** sierpień 2022 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** wrzesień 2022 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Zapasy i logistyka | [Alokuj i rezerwuj elementy WMS w Widoczności zapasów](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Wkrótce | Domyślnie włączone |
| Zapasy i logistyka | [Wstępnie załaduj ujednolicone listy dostępnych zapasów](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | [Używanie aplikacji Inventory Visibility](../inventory/inventory-visibility-power-platform.md) | Włączone przez konfigurację usługi |
| Automatyzacja dostaw produktów na zamówienie | [Automatyzacja dostaw produktów na zamówienie](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Automatyzacja dostaw produktów na zamówienie](../master-planning/make-to-order-supply-automation.md) | Zarządzanie funkcjami:<br>*Automatyzacja dostaw produktów na zamówienie* |
| Planowanie | [Wyświetl i zastosuj szczegółowe dane do DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Planowanie zapotrzebowania materiałowego sterowane popytem – omówienie](../master-planning/planning-optimization/ddmrp-overview.md) | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) DDMRP dla optymalizacji planowania* |
| Kontrola produkcji | [Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe](../production-control/deferred-posting.md) | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) Przed zaksięgowaniem w arkuszach udostępnij fizycznie towary gotowe* |
| Zarządzanie magazynem | [Przeszukaj odpowiednie dane w aplikacji mobilnej magazynu](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Przeszukuj dane za pomocą objazdów aplikacji mobilnej Warehouse Management](../warehousing/warehouse-app-data-inquiry.md) | Zarządzanie funkcjami:<br>*Przepływ zapytania o dane aplikacji Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie kosztami | Optymalizacja obliczania oczekującej ceny produktu towarzyszącego | Ta funkcja usuwa konflikt, który może wystąpić, gdy ceny produktów u produktów współpracownika są obliczane przy użyciu wielu wątków. Powoduje to, że system zapewnia, że każda cena produktu zostanie obliczona tylko raz. Wynik tego obliczenia jest następnie używany jako dane wejściowe dla wszystkich innych obliczeń. Jeśli istnieje już oczekująca cena, zostanie ona użyta. |
| Planowanie główne | Grupuj transakcje w optymalizacji planowania | Ta funkcja pomaga redukować liczbę planowanych zamówień generowanych w celu zapewnienia jednego wiersza zamówienia sprzedaży, gdy jest w użyciu optymalizacji planowania. Gdy ta funkcja jest włączona, Optymalizacja planowania grupuje wszystkie transakcje magazynowe dla wiersza zamówienia w jedno zapotrzebowanie na pełną ilość. (To zachowanie pasuje do zachowania wbudowanego aparatu planowania.) Podaż i popyt są grupowane osobno. W związku z tym funkcja pomaga zmniejszyć wolumen transakcji w przypadku podzielonych transakcji i korzystania z wymiarów (takich jak numery partii lub numery seryjne), które nie są wymiarami pokrycia. |
| Zaopatrzenie i sourcing | Wstrzymanie dostawcy dla zamówień zakupu | Ta funkcja umożliwia wstrzymanie dostawcy dla zamówień zakupu. Powoduje dodanie nowego typu wstrzymywania *zamówienia zakupu*, który oznacza dostawcę jako wstrzymanego dla zamówień zakupu. Nie będzie można tworzyć nowych zamówień zakupu dla dostawców, którzy są wstrzymani dla zamówień zakupu, ale nadal będzie można kontynuować wszelkie otwarte faktury lub płatności dla tych dostawców. |
| Sprzedaż i marketing | Oblicz kwotę netto wiersza podczas importu | Ta funkcja umożliwia kontrolowanie, czy system powinien ponownie przeliczać sumy wierszy podczas importowania danych za pośrednictwem jednostki *Wiersze zamówienia sprzedaży*, *wierszy oferty sprzedaży* lub *Wierszy zamówienia zwrotu* przy użyciu danych OData czy podwójnego zapisu. Ma to zastosowanie tylko wtedy, gdy obowiązują również zasady oceny umów handlowych, które ograniczają zmiany w polu **Kwota netto** dla wierszy zamówienia sprzedaży, wierszy oferty sprzedaży i/lub wierszy zamówienia zwrotu. Dodaje ustawienie o nazwie **Obliczanie kwoty netto wiersza** do strony **Rozrachunki z odbiorcami > Ustawienia > Parametry rozrachunków z odbiorcami**. Gdy to ustawienie ma wartość *Tak*, system w razie potrzeby będzie zawsze ponownie przeliczać kwoty wiersza (w ten sposób zignoruje wszelkie zasady oceny umowy handlowej dla kwoty netto wiersza). Jeśli to ustawienie ma wartość *Nie*, system nigdy nie będzie automatycznie obliczać kwoty netto wiersza, nawet jeśli przychodzące zmiany cen, ilości i/lub rabatów powinny wymagać ponownego obliczenia kwoty netto wiersza. Ta funkcja jest domyślnie włączona i początkowo dla pola **Oblicz kwotę netto wiersza** ustawia wartość *Tak*. Ustawienie *Nie* pasuje do zachowania systemu sprzed wersji 10.0.23 i jest dostarczane głównie do obsługi starszych scenariuszy integracji.<br><br>Aby uzyskać więcej informacji, zobacz temat [Ponowne obliczanie kwot netto wiersza podczas importowania zamówień sprzedaży, ofert i zwrotów](../sales-marketing/calc-line-net-amounts-import.md). |
| Sprzedaż i marketing | Oblicz sumy sprzedaży za pomocą wielu wątków | Ta funkcja pomaga zwiększyć wydajność, umożliwiając systemowi korzystanie z przetwarzania równoległego podczas obliczania sum sprzedaży w partii. Funkcja dodaje nowe pole **Liczby wątków** do okna dialogowego **Obliczanie sum sprzedaży**. Jeśli wybierzesz uruchamianie obliczenia w partii, możesz użyć tego pola, aby ustawić maksymalną liczbę wątków. Jeśli zostanie ustawiona wartość *0* (zero) lub *1*, zostanie użyty jeden wątek. Wartości powyżej 1 umożliwiają wielowątkowanie. |
| Sprzedaż i marketing | Aktualizacja cen i rabatów wprowadzonych ręcznie dla wielu firm | Ta funkcja dodaje obsługę zasad zmian ręcznych dla zamówień międzyfirmowych. Zawiera on obsługę przenoszenia zasad ręcznej zmiany między międzyfirmowym zamówieniem sprzedaży i zakupu. Wcześniej zasady zmian ręcznych były obsługiwane tylko dla zamówień innych niż międzyfirmowe. Gdy ta funkcja jest włączona, po zapisaniu zmian w zamówieniu międzyfirmowym system wybierze opcję aktualizacji cen i rabatów. Ta opcja umożliwia określenie, czy nowe ceny i rabaty mają zostać zastosowania do zamówienia międzyfirmowego, czy też zamówienie pozostanie niezmienione. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły Pomocy. Te artykuły nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Planowanie główne, CTP | [Obliczanie dat dostawy zamówień sprzedaży przy użyciu CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Planowanie główne, DDMRP | [Planowanie zapotrzebowania materiałowego sterowane popytem – omówienie](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Włącz funkcję DDMRP w swoim systemie](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Lokalizacja zapasów](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Profil i poziomy buforu](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Planowanie oparte na popycie](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Wizualizacja i wykonanie pracy grupowej](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Zarządzanie magazynem | [Zapakuj kontenery do wysyłki](../warehousing/packing-containers.md)<br>[Praca pakowania do pakowania kontenerów wychodzących i przetwarzania wysyłek](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Zmiany w stanie funkcji w tym wydaniu

Poniższa tabela zawiera listę cech, które stały się obowiązkowe lub domyślnie włączone począwszy od 10.0.29. Wszystkie te funkcje zostaną automatycznie włączone w twoim systemie, gdy tylko zaktualizujesz go do wersji 10.0.29. Nie można wyłączyć funkcji obowiązkowych, ale funkcje, które są domyślnie włączone, mogą być nadal wyłączone za pomocą funkcji [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

W tabeli wymieniono również funkcje, które wcześniej były dostępne w publicznej wersji zapoznawczej, ale zostały zmienione i stały się ogólnie dostępne w wersji 10.0.29. Ta zmiana wskazuje, że funkcje są teraz zalecane do użycia w środowiskach produkcyjnych. Te funkcje są domyślnie wyłączone, chyba że zaznaczono inaczej. Dlatego musisz użyć [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby je włączyć, jeśli chcesz Użyj ich.

| Moduł | Nazwa funkcji | Nowy stan funkcji |
| --- | --- | --- |
| Zarządzanie składnikami majątku | [Funkcje zarządzania zasobami dla interfejsu wykonania hali produkcyjnej](../production-control/production-floor-execution-configure.md) | Wymagana |
| Zarządzanie kosztami | [Zmień etykietę anulowania w przypadku zamknięcia i korekty na wycofanie](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Wymagana |
| Zarządzanie kosztami | Czyszczenie niejednolitych wersji wyceny w szczegółach obliczania BOM | Wymagana |
| Zarządzanie kosztami | [Porównaj ceny pozycji — magazyn](../cost-management/compare-item-price.md) | Wymagana |
| Zarządzanie kosztami | [Poziom obliczania kosztu](../cost-management/cost-calculation-level.md) | Domyślnie włączona |
| Zarządzanie kosztami | Włącz definiowane przez użytkownika ustawienia numerów partii dla wycofania zamknięcia magazynu | Domyślnie włączona |
| Zarządzanie kosztami | [Szczegóły postępu zamknięcia zapasów](whats-new-scm-10-0-21.md) | Domyślnie włączona |
| Zarządzanie kosztami | [Magazyn raportów wartości zapasów](../cost-management/inventory-value-report-storage.md) | Wymagana |
| Zarządzanie kosztami | Czyszczenie danych raportu wartości zapasów | Wymagana |
| Zarządzanie kosztami | Średnia ruchoma, sekwencja kosztu rezerwowego | Wymagana |
| Zarządzanie kosztami | Pokaż dziennik zamykania magazynu w siatce | Wymagana |
| Zarządzanie kosztami | Pokaż pozycje z niecałkowicie rozliczonymi transakcjami w formacie podsumowania | Wymagana |
| Zarządzanie zapasami i magazynem | Zezwalaj na puste wartości atrybutów partii | Wymagana |
| Zarządzanie zapasami i magazynem | Automatyczne zwiększanie numerów wierszy zamówienia przeniesienia zapasów | Wymagana |
| Zarządzanie zapasami i magazynem | Utwórz zamówienie przeniesienia z wiersza sprzedaży | Wymagana |
| Zarządzanie zapasami i magazynem | Wyłącz pole wiersza arkusza zapasów w przepływie pracy | Wymagana |
| Zarządzanie zapasami i magazynem | Włącz funkcję ostrzegania o parametrach zarządzania jakością zapasów | Wymagana |
| Zarządzanie zapasami i magazynem | (Chiny) Wyklucz koszty fizycznych przyjęć i wydań ze średniego kosztu miesięcznego | Domyślnie włączona |
| Zarządzanie zapasami i magazynem | [Przepływ pracy zatwierdzania arkusza magazynowego](../inventory/inventory-journal-workflow.md) | Wymagana |
| Zarządzanie zapasami i magazynem | [Magazyn raportu dostępnych zapasów](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Wymagana |
| Zarządzanie zapasami i magazynem | [Zapisane widoki dla zarządzania zapasami](saved-views-scm.md) | Wymagana |
| Zarządzanie zapasami i magazynem | Anulowanie zamówienia przeniesienia | Wymagana |
| Zarządzanie zapasami i magazynem | Użycie jednostki miary i ilości jednostkowej w arkuszach magazynowych | Wymagana |
| Zarządzanie zapasami i magazynem | Odblokuj arkusz zapasów | Wymagana |
| Produkcja | [Automatyczne pobieranie materiałów z obsługą magazynu dla automatycznie księgowanych list pobrania](whats-new-scm-10-0-23.md) | Ogólnie dostępne |
| Produkcja | Włączenie wyświetlania wymiarów magazynowych na liście BOM na potrzeby operacji marszruty produkcji | Wymagana |
| Produkcja | [Włącz, aby wprowadzić numery seryjne i partii podczas zgłaszania jako gotowych z urządzenia karty zadań](../production-control/report-finished-job-device.md) | Domyślnie włączona |
| Produkcja | Poprawione pobieranie ilości efektywnej produkcji | Domyślnie włączona |
| Produkcja | [Wyszukiwanie zadań dla interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Wymagana |
| Produkcja | [Integracja systemu wykonania produkcji](../production-control/mes-integration.md) | Domyślnie włączona |
| Produkcja | [Widok „Mój dzień” dla interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Domyślnie włączona |
| Produkcja | [Sprawdzanie dostępności materiałów na żądanie dla zleceń produkcyjnych](whats-new-scm-10-0-24.md) | Domyślnie włączona |
| Produkcja | [Zastąp domyślną rezerwację produkcji](../production-control/override-default-reservation-principle.md) | Wymagana |
| Produkcja | [Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (inne niż WMS)](../production-control/production-floor-execution-configure.md) | Ogólnie dostępne |
| Produkcja | [Raport pozycji ilości efektywnej z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Ogólnie dostępne |
| Produkcja | [Raport dotyczący produktów towarzyszących i ubocznych z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Domyślnie włączona |
| Produkcja | [Raport dotyczący pozycji planowania w interfejsie wykonania hal produkcyjnych](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | Domyślnie włączona |
| Produkcja | [Zapisane widoki dla kontroli produkcji](saved-views-scm.md) | Wymagana |
| Produkcja | [Pokaż pełne numery seryjne, partii i numery identyfikacyjne w interfejsie wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Wymagana |
| Produkcja | [Weryfikacja ważności surowców w stosunku do planowanej daty zużycia](whats-new-scm-10-0-23.md) | Domyślnie włączona |
| Planowanie główne | [Automatyczne akceptowanie w module Optymalizacja planowania](../master-planning/planning-optimization/planned-order-firming.md) | Wymagana |
| Planowanie główne | [Akceptowanie i konsolidacja, które mogą być przeprowadzane w partiach, dla planowanych zamówień partii masowych i paczkowanych](whats-new-scm-10-0-20.md) | Domyślnie włączona |
| Planowanie główne | [Uwzględniaj pozycje z zapasami, gdy są włączone filtry przetwarzania wstępnego](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | Domyślnie włączona |
| Planowanie główne | [Planowanie nieskończonych zdolności produkcyjnych dla optymalizacji planowania](../master-planning/planning-optimization/infinite-capacity-planning.md) | Domyślnie włączona |
| Planowanie główne | [Marże dla optymalizacji planowania](../master-planning/planning-optimization/safety-margins.md) | Wymagana |
| Planowanie główne | [Dni ujemne dla optymalizacji planowania](../master-planning/planning-optimization/delay-tolerance.md) | Wymagana |
| Planowanie główne | [Równoległe autoryzowanie skorygowanej prognozy popytu](whats-new-scm-10-0-20.md) | Wymagana |
| Planowanie główne | [Akceptowanie zamówień planowanych z filtrowaniem](../master-planning/planning-optimization/planned-order-firming.md) | Wymagana |
| Planowanie główne | [Planowane zlecenia produkcyjne na potrzeby optymalizacji planowania](../master-planning/planning-optimization/production-planning.md) | Wymagana |
| Planowanie główne | [Umowy handlowe dotyczące zakupu na potrzeby optymalizacji planowania](../master-planning/planning-optimization/purchase-trade-agreement.md) | Wymagana |
| Planowanie główne | [Zapisane widoki dla planowanych zamówień](saved-views-scm.md) | Wymagana |
| Zaopatrzenie i sourcing | Kwoty od i do opłat dla zamówień zakupu | Wymagana |
| Zaopatrzenie i sourcing | Wyłącz przycisk resetowania dystrybucji zapotrzebowania na zakup | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Włącz resetowanie przepływów pracy związanych z zaopatrzeniem](whats-new-scm-10-0-20.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Ogranicz liczbę wierszy zamówienia zakupu na zadanie wsadowe](whats-new-scm-10-0-27.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Scal wymiary finansowe od dostawcy z aktywnym wymiarem finansowym łącza wymiaru w zamówieniu zakupu](whats-new-scm-10-0-25.md) | Wymagana |
| Zaopatrzenie i sourcing | [Księguj zarejestrowane ilości produktów magazynowanych i reszty produktów niemagazynowanych dla dokumentów dostawy i faktur od dostawcy](whats-new-scm-10-0-26.md) | Ogólnie dostępne |
| Zaopatrzenie i sourcing | [Zapobieganie nadmiernej konsumpcji rezerwacji środków w budżecie, gdy w przepływie pracy znajduje się wiele zapotrzebowań na zakup](whats-new-scm-10-0-21.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Strona odpowiedzialna za umowę zakupu](../procurement/purchase-agreements.md) | Wymagana |
| Zaopatrzenie i sourcing | [Zapisane widoki dla zamówień zakupu](saved-views-scm.md) | Wymagana |
| Zarządzanie informacjami o produktach | Przetwarzanie wstępne raportu listy składowej (BOM) w celu uniknięcia limitu czasu | Wymagana |
| Zarządzanie informacjami o produktach | Domyślne wymiary finansowe osobno w przypadku korzystania z szablonów pozycji | Wymagana |
| Zarządzanie informacjami o produktach | Włącz grupy wymiarów produktów dla szablonów pozycji | Wymagana |
| Zarządzanie informacjami o produktach | Ulepszenia jednostki typu pozycja-kodu kreskowy | Wymagana |
| Zarządzanie informacjami o produktach | Generuj ponownie nazwy wariantów produktu na podstawie nazewnictwa | Wymagana |
| Zarządzanie informacjami o produktach | [Zapisane widoki zwolnionych produktów](saved-views-scm.md) | Wymagana |
| Zarządzanie informacjami o produktach | [Ulepszenia strony sugestii dotyczących wariantów](../pim/tasks/create-predefined-product-variants.md) | Wymagana |
| Sprzedaż i marketing | [Alokacja opłat do zamówienia sprzedaży](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Wymagana |
| Sprzedaż i marketing | Wyczyść historię aktualizacji zamówień sprzedaży | Wymagana |
| Sprzedaż i marketing | [Oczyszczanie historii aktualizacji sprzedaży na podstawie wieku](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Wymagana |
| Sprzedaż i marketing | [Optymalizacja eksportu jednostki danych osoby kontaktowej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Wymagana |
| Sprzedaż i marketing | Kopiuj grupę rabatów sumy dla faktury korygującej sprzedaży | Wymagana |
| Sprzedaż i marketing | [Włącz wyszukiwanie pól wprowadzenia do dokumentu i wniosków z dokumentu ofert sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Wymagana |
| Sprzedaż i marketing | [Popraw wydajność raportu „100 najlepszych” odbiorców](whats-new-scm-10-0-23.md) | Wymagana |
| Sprzedaż i marketing | Uwzględnij oczekujące rekordy w zadaniach oczyszczania historii | Wymagana |
| Sprzedaż i marketing | Ogranicz liczbę wierszy zamówienia sprzedaży na zadanie wsadowe | Domyślnie włączona |
| Sprzedaż i marketing | [Ograniczenie liczby zamówień sprzedaży, które można wybierać do księgowania](whats-new-scm-10-0-21.md) | Wymagana |
| Sprzedaż i marketing | Ponowne obliczanie szacowanego salda odbiorcy | Wymagana |
| Sprzedaż i marketing | [Rejestracja wiersza zamówienia zwrotu sprzedaży z dokładnością do wartości dziesiętnych wraz z i bez ilości efektywnej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Wymagana |
| Sprzedaż i marketing | [Zapisane widoki dotyczące sprzedaży i marketingu](saved-views-scm.md) | Wymagana |
| Sprzedaż i marketing | [Potwierdzenie zamówienia sprzedaży za jednym kliknięciem](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Wymagana |
| Zarządzanie transportem | Zezwól na usunięcie dopasowania opłat frachtowych z wierszy faktury frachtowej bez zaksięgowanego arkusza faktury od dostawcy | Domyślnie włączona |
| Zarządzanie transportem | [Włącz tworzenie arkusza faktury od dostawcy podczas odrzucania opłaty frachtowej](whats-new-scm-10-0-20.md) | Domyślnie włączona |
| Zarządzanie transportem | [Wysyłka małych paczek](../warehousing/small-parcel-shipping.md) | Wymagana |
| Zarządzanie transportem | [Dokument certyfikatu pochodzenia USMCA](../transportation/usmca-certification-of-origin.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Dodatkowa strefa lokalizacji](../warehousing/additional-location-zones.md) | Wymagana |
| Zarządzanie magazynem | [Anuluj pracę](../warehousing/cancel-warehouse-work.md) | Wymagana |
| Zarządzanie magazynem | [Konsoliduj wysyłkę](../warehousing/configure-shipment-consolidation-policies.md) | Wymagana |
| Zarządzanie magazynem | [Tworzenie i przetwarzanie zamówień przeniesienia z aplikacji magazynowej](../warehousing/create-transfer-order-from-warehouse-app.md) | Wymagana |
| Zarządzanie magazynem | Szablony przeładunku kompletacyjnego z dyrektywami lokalizacji | Domyślnie włączona |
| Zarządzanie magazynem | [Odłączanie pracy odłożonej od powiadomień WPW](whats-new-scm-10-0-21.md) | Wymagana |
| Zarządzanie magazynem | [Odroczone operacje odłożenia](../warehousing/deferred-processing-manual-inventory-movement.md) | Wymagana |
| Zarządzanie magazynem | Odroczone odłożenie — kontener | Domyślnie włączona |
| Zarządzanie magazynem | Odroczone przetwarzanie odłożenia — włącz dla funkcji szablonu inspekcji ze zdarzeniem wyzwalacza ustawionym na Poprzednie | Wymagana |
| Zarządzanie magazynem | [Wyłącz oczekiwane przyjęcia ze zleceń kontroli jakości, które pobierają próbki zablokowanych zapasów](../inventory/inventory-blocking.md) | Domyślnie włączona |
| Zarządzanie magazynem | Włączanie funkcji szybkiej weryfikacji dla urządzeń przenośnych używanych w magazynie | Wymagana |
| Zarządzanie magazynem | [Ulepszone analizowanie kodów kreskowych GS1](../warehousing/gs1-barcodes.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Zamówienie elastyczne — rezerwacja zatwierdzonego numeru identyfikacyjnego](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Wymagana |
| Zarządzanie magazynem | [Elastyczna rezerwacja wymiaru na poziomie magazynu](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Wymagana |
| Zarządzanie magazynem | [Wykorzystanie lokalizacji konsolidacji pozycji](../warehousing/item-consolidation-location-utilization.md) | Domyślnie włączona |
| Zarządzanie magazynem | Historia odbierania numeru identyfikacyjnego | Domyślnie włączona |
| Zarządzanie magazynem | [Ręczna konsolidacja wysyłki](../warehousing/consolidate-shipments-manual-workbench.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Ręczna usługa pobierania wierszy przeniesienia dla administratora lub podobnych zaufanych użytkowników](whats-new-scm-10-0-28.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Interfejs urządzeń do obsługi materiałów](../warehousing/mhax.md) | Wymagana |
| Zarządzanie magazynem | [Nowe strony pulpitu planowania wysyłki ładunku](whats-new-scm-10-0-24.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Wychodzące wizualizacje obciążenia pracą](../warehousing/outbound-workload-visualization.md) | Wymagana |
| Zarządzanie magazynem | [Planowany przeładunek kompletacyjny](../warehousing/planned-cross-docking.md) | Wymagana |
| Zarządzanie magazynem | [Przetwarzanie zdarzeń aplikacji magazynowej](../warehousing/warehouse-app-events.md) | Wymagana |
| Zarządzanie magazynem | Ulepszanie zapytań na potrzeby szablonu pracy odłożenia produktu towarzyszącego i ubocznego | Wymagana |
| Zarządzanie magazynem | [Zaokrąglij ilości w dół do najbliższej jednostki sprzedaży podczas zwalniania do magazynu](whats-new-scm-10-0-19.md) | Wymagana |
| Zarządzanie magazynem | [Zapisane widoki dla warsztatu planowania wysyłki ładunku](saved-views-scm.md) | Wymagana |
| Zarządzanie magazynem | [Zapisany widok dla strony szczegółów pracy](saved-views-scm.md) | Wymagana |
| Zarządzanie magazynem | [Zapisany widok dla przetwarzania grupy czynności](saved-views-scm.md) | Wymagana |
| Zarządzanie magazynem | [Zapisane widoki dla przetwarzania ładunku](saved-views-scm.md) | Wymagana |
| Zarządzanie magazynem | [Zapisane widoki dla przetwarzania wysyłki](saved-views-scm.md) | Wymagana |
| Zarządzanie magazynem | [Zeskanuj kody kreskowe GS1](../warehousing/gs1-barcodes.md) | Ogólnie dostępne |
| Zarządzanie magazynem | Szczegóły etykiety grupy czynności wysyłki | Wymagana |
| Zarządzanie magazynem | [Umieść jednostki mieszane](whats-new-scm-10-0-21.md) | Wymagana |
| Zarządzanie magazynem | [Użyj szybszego interfejsu API do zamykania/ponownego otwierania kontenerów na stacji pakowania](whats-new-scm-10-0-21.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Weryfikuj szablony wybrane dla zadań uzupełniania zapasów](whats-new-scm-10-0-20.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Promowane pola aplikacji magazynowej](../warehousing/warehouse-app-promoted-fields.md) | Wymagana |
| Zarządzanie magazynem | [Instrukcje kroku aplikacji magazynowej](../warehousing/mobile-app-titles-instructions.md) | Wymagana |
| Zarządzanie magazynem | [Stan lokalizacji w magazynie](../warehousing/warehouse-location-status.md) | Wymagana |
| Zarządzanie magazynem | [Przełączanie aplikacji Warehouse Management](../warehousing/warehouse-app-detours.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Szczegóły zadania wsadowego grupy czynności](../warehousing/wave-processing.md) | Wymagana |
| Zarządzanie magazynem | [Powiadomienia dotyczące wykonania grupy czynności](../warehousing/wave-execution-notifications.md) | Wymagana |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.29 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.29 aplikacji Finanse i Działania (październik 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.29, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.](/dynamics365-release-plan/2022wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W artykule [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
