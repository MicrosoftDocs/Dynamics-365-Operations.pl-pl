---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.25 (kwiecień 2022)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: d6aa5a0cb49e5871a50a2ac5ac2c29cc09e232fc
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403711"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10025-april-2022"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.25 (kwiecień 2022)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.25. Ta wersja ma numer kompilacji 10.0.1149 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza:** luty 2022 r.
- **Ogólna dostępność wydania (samoaktualizacja):** marzec 2022 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** kwiecień 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Firma Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał funkcje wprowadzone do kompilacji po początkowym opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Zapasy&nbsp;i&nbsp;logistyka | [Rozszerzenie materiałów niebezpiecznych](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Wkrótce | Zarządzanie funkcjami:<br>*Rozszerzenie materiałów niebezpiecznych* |
| Zapasy&nbsp;i&nbsp;logistyka | [Praca pakowania dla stacji pakowania](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | [Praca pakowania do pakowania kontenerów wychodzących i przetwarzania wysyłek](../warehousing/packing-work.md) | Zarządzanie funkcjami:<br>*Praca pakowania dla stacji pakowania* |
| Zapasy&nbsp;i&nbsp;logistyka | [Skanowanie kodów kreskowych w magazynie przy użyciu standardów formatu GS1](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [Kody kreskowe GS1 i kody QR](../warehousing/gs1-barcodes.md) | Zarządzanie funkcjami:<br>*Zeskanuj kody kreskowe GS1* |
| Produkcja | [Rejestrowanie zużycia materiału i rezerwacji w interfejsie wykonania hal produkcyjnych (inne niż WMS)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-use.md) | Zarządzanie funkcjami:<br>*Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (inne niż WMS)*<br><br>I/lub:<br><br>Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (z obsługą WMS)* |
| Planowanie | [Obsługa kalendarza scentralizowanego optymalizacji planowania](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [Kalendarze i planowanie główne](../master-planning/supply-chain-calendars-master-planning.md) | Domyślnie włączone |
| Planowanie | [Optymalizacja planowania – propozycje optymalizacji istniejących dostaw](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Komunikaty akcji](../master-planning/action-messages.md) | Domyślnie włączone |
| Planowanie | Uproszczone zamówienia planowane | [Uproszczone zamówienia planowane](../master-planning/planning-optimization/planned-orders-simplified.md ) | Zarządzanie funkcjami:<br>*Uproszczone zamówienia planowane* |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie zapasami i magazynem | (Polska) Zezwalaj na łączenie kilku faktur SAD do jednego wiersza zamówienia zakupu w jednej bazie danych SAD | Ta funkcja pozwala ci rozdzielić wiersze zamówień zakupu i połączyć je z pojedynczym dokumentem administracyjnym (SAD), gdy te wiersze zamówień zakupu zostały zaksięgowane dla kilku różnych faktur (np. dla różnych wysyłek). |
| Zaopatrzenie i sourcing | Konsolidacja wielu zapotrzebowań na zakup w jedno zamówienie zakupu według daty księgowania | Ta funkcja pozwala na konsolidację wielu zapotrzebowań na zakup w jedno zamówienie, jeśli poszczególne zamówienia mają różne daty księgowania. Reguły polityki zakupowej dotyczące tworzenia zamówień i konsolidacji zapotrzebowania mogą być tworzone w celu zautomatyzowania decyzji o grupowaniu wierszy zapotrzebowania według daty księgowania na poziomie zamówienia. Konsolidacja zamówień według daty księgowania nie jest obsługiwana, jeśli włączona jest kontrola budżetowa, ponieważ data księgowania jest używana do rezerw budżetowych i obciążeń. Dlatego powinien on być zachowany podczas przejścia od zamówienia zakupu do zlecenia zakupu. |
| Zaopatrzenie i sourcing | Wyświetl starsze domyślne ustawienia pola odpowiedzi ZO | Ta funkcja przywraca dotychczasowe domyślne ustawienia pola odpowiedzi na zapytanie ofertowe (RFQ), które wcześniej zostały usunięte z interfejsu użytkownika. Te ustawienia nie zapewniają żadnej funkcjonalności po wyjęciu z pudełka, ale mogą być dostosowane tak, by zapewniały ją w razie potrzeby. Włącz tę funkcję, jeśli twoja organizacja dodała już funkcjonalność dla domyślnych ustawień pola odpowiedzi RFQ lub planuje to zrobić. Kiedy ta funkcja jest włączona, możesz uzyskać dostęp do ustawień, przechodząc na stronę **Parametry zamówień i zaopatrzenia**, otwierając zakładkę **Zapytanie ofertowe** i wybierając **Domyślne pola odpowiedzi na zapytanie ofertowe**. |
| Zaopatrzenie i sourcing | Scal wymiary finansowe od dostawcy z aktywnym wymiarem finansowym łącza wymiaru w zamówieniu zakupu | Ta funkcja pozwala na łączenie wymiarów finansowych od dostawców z aktywnymi wymiarami finansowymi łączącymi wymiary po zatwierdzeniu zamówienia zakupu, jeśli ustawisz powiązanie między wymiarem finansowym a wymiarem zasobów miejsca. Reguły polityki zakupowej dotyczące tworzenia zamówień i konsolidacji zapotrzebowania mogą być ustawione tak, aby podejmować decyzje o łączeniu wymiarów finansowych od dostawców z aktywnym wymiarem łączącym wymiar finansowy na poziomie nagłówka zamówienia zakupu. |
| Kontrola produkcji | (Rosja) Włącz domyślne ustawienia lokalizacji dla formuły/BOM oraz automatycznej rezerwacji/zużycia GTD w produkcji | Funkcja ta umożliwia dodatkowe opcje produkcji z importowanych surowców (tylko lokalizacja w Rosji):<ul><li>Opcja ustawienia automatycznej domyślnej lokalizacji dla formuł produkcyjnych i zestawień materiałów zarówno na grupach zasobów, jak i na magazynach.</li><li>Automatyczna rezerwacja surowców według wymiaru *numeru GTD* w magazynach aktywowanych przez system WMS zgodnie z algorytmem rezerwacji bez systemu WMS. Dotyczy to sytuacji, gdy istnieje polityka pracy dla *Pobierania surowców* z **Metodą tworzenia pracy** ustawioną na *Nigdy*, a ustawienia magazynu, lokalizacji i numeru pozycji odpowiadają transakcjom inwentaryzacyjnym zlecenia produkcyjnego (seryjnego).</li><li>Automatyczne zużycie surowców według wymiaru *numeru GTD* przy księgowaniu listy pobrań, zgodnie z nabytą rezerwacją opisaną wcześniej.</li></ul> |
| Zarządzanie magazynem | (Wersja zapoznawcza) Obsługa jednostki skalowania dla przychodzących i wychodzących zamówień magazynu | Funkcja ta powoduje, że system tworzy zlecenia wychodzące z magazynu podczas procesu wydania do magazynu oraz tworzy zlecenia przychodzące z magazynu, gdy zlecenia transferu są księgowane jako wysłane. Następnie system synchronizuje każde przychodzące lub wychodzące zamówienie magazynowe z jednostką wagi odpowiedzialną za wysyłkę lub odbiór zamówienia. Zwróć uwagę, że po włączeniu tej funkcji należy zaktualizować obciążenia wykonawcze magazynu. Aby uzyskać więcej informacji, zobacz temat [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Ta funkcja wymaga funkcji *Oddzielenie pracy odkładania od ASN-ów* i umożliwi przyjmowanie zleceń transferu przy użyciu procesu przyjmowania tablic rejestracyjnych w aplikacji mobilnej Warehouse Management. |

## <a name="feature-state-changes-in-this-release"></a>Zmiany w stanie funkcji w tym wydaniu

Poniższa tabela zawiera listę cech, które stały się obowiązkowe lub domyślnie włączone począwszy od 10.0.25. Wszystkie te funkcje zostaną automatycznie włączone w twoim systemie, gdy tylko zaktualizujesz go do wersji 10.0.25. Nie można wyłączyć funkcji obowiązkowych, ale funkcje, które są domyślnie włączone, mogą być nadal wyłączone za pomocą funkcji [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tabela zawiera również listę funkcji, które były wcześniej w publicznej wersji zapoznawczej, ale zostały zmienione i stały się ogólnie dostępne w 10.0.25, co oznacza, że są teraz zalecane do użycia w środowiskach produkcyjnych. Te funkcje są domyślnie wyłączone, o ile nie zaznaczono inaczej, należy więc włączyć funkcję [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), jeśli chcesz z nich korzystać.

| Moduł | Nazwa funkcji | Stan funkcji |
| --- | --- | --- |
| Zarządzanie składnikami majątku | [Zastosuj reguły grupowania zleceń pracy podczas uruchamiania planu konserwacji](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Ogólnie dostępne |
| Zarządzanie składnikami majątku | [Ulepszenia konserwacji opartej na licznikach](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Ogólnie dostępne |
| Zarządzanie kosztami | [Poziom obliczania kosztu](../cost-management/cost-calculation-level.md) | Ogólnie dostępne |
| Zarządzanie kosztami | Włącz definiowane przez użytkownika ustawienia numerów partii dla wycofania zamknięcia magazynu | Ogólnie dostępne |
| Zarządzanie kosztami | [Szczegóły postępu zamknięcia zapasów](whats-new-scm-10-0-21.md) | Ogólnie dostępne |
| Zarządzanie kosztami | [Opcje ustawiania wartości domyślnych wymiarów finansowych dla ponownej oceny standardowego kosztu zapasów](../cost-management/manage-standard-cost-updates.md) | Ogólnie dostępne |
| Zarządzanie kosztami | Czyszczenie danych raportu wartości zapasów | Domyślnie włączona |
| Zarządzanie kosztami | [Magazyn raportów wartości zapasów](../cost-management/inventory-value-report-storage.md) | Domyślnie włączona |
| Zarządzanie kosztami | Pokaż dziennik zamykania magazynu w siatce | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Włącz zarządzanie zmianami w istniejących produktach](../engineering-change-management/change-management-existing-products.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Zarządzanie zmianami projektowymi](../engineering-change-management/product-engineering-overview.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Powiadomienia projektowe dla produkcji](../engineering-change-management/engineering-change-management.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Poprawione dziedziczenie atrybutów dla zarządzania zmianami produkcyjnymi](../engineering-change-management/engineering-attributes-and-search.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Zarządzanie zmianami dotyczącymi formuł i ich substancji](../engineering-change-management/manage-formula-changes.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Kontrole gotowości produktu](../engineering-change-management/product-readiness.md) | Domyślnie włączona |
| Zarządzanie zmianami projektowymi | [Generowanie wariantów produktów projektowych](../engineering-change-management/engineering-variants.md) | Domyślnie włączona |
| Zarządzanie zapasami i magazynem | Nawigacja do wersji listy składowej (BOM) z wierszy listy składowej (BOM) | Wymagana |
| Planowanie główne | [Akceptowanie i konsolidacja, które mogą być przeprowadzane w partiach, dla planowanych zamówień partii masowych i paczkowanych](whats-new-scm-10-0-20.md) | Ogólnie dostępne |
| Planowanie główne | Planowanie zasobów z obsługą konserwacyjną | Ogólnie dostępne |
| Planowanie główne | Włączanie funkcji kreatora konfiguracji planu głównego | Wymagana |
| Planowanie główne | [Wybór modelu prognozy w szczegółach prognozy popytu](../master-planning/manual-adjustments-baseline-forecast.md) | Wymagana |
| Planowanie główne | [Wizualizacja postępu planowania głównego](../master-planning/tasks/monitor-master-planning-run.md) | Wymagana |
| Planowanie główne | [Równoległa akceptacja zamówień planowanych](../master-planning/planning-optimization/planned-order-firming.md) | Wymagana |
| Planowanie główne | [Akceptowanie zamówień planowanych z filtrowaniem](../master-planning/planning-optimization/planned-order-firming.md) | Domyślnie włączona |
| Planowanie główne | [Zapisane widoki dla planowanych zamówień](saved-views-scm.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | Wyłącz przycisk resetowania dystrybucji zapotrzebowania na zakup | Ogólnie dostępne |
| Zaopatrzenie i sourcing | [Włącz resetowanie przepływów pracy związanych z zaopatrzeniem](whats-new-scm-10-0-20.md) | Ogólnie dostępne |
| Zaopatrzenie i sourcing | Możliwość zbiorczego potwierdzania zaakceptowanych zamówień zakupu z portalu współpracy z dostawcami | Wymagana |
| Zaopatrzenie i sourcing | Stan umowy zakupu Zamknięta | Wymagana |
| Zaopatrzenie i sourcing | Dodaj wiersze do faktur do zamówienia zakupu skojarzonych z umową zakupu | Domyślnie włączona |
| Zaopatrzenie i sourcing | Dodaj pole Ilość zamówiona na stronie Księgowanie dokumentu przyjęcia produktów | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Zezwól dostawcom na zgłoszenie się do kategorii zaopatrzenia za pośrednictwem współpracy z dostawcami](../procurement/category-requests-from-vendors.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | Kwoty od i do opłat dla zamówień zakupu | Domyślnie włączona |
| Zaopatrzenie i sourcing | Konfiguracja opłat dla obiektu i magazynu | Domyślnie włączona |
| Zaopatrzenie i sourcing | Włącz obliczanie cła od zakupu na podstawie rocznej taryfy | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Strona odpowiedzialna za umowę zakupu](../procurement/purchase-agreements.md) | Domyślnie włączona |
| Zaopatrzenie i sourcing | [Zapisane widoki dla zamówień zakupu](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie informacjami o produktach | [Ścisła weryfikacja w domyślnych ilościach zamówienia](../production-control/default-order-settings.md) | Wymagana |
| Zarządzanie informacjami o produktach | Przetwarzanie wstępne raportu listy składowej (BOM) w celu uniknięcia limitu czasu | Domyślnie włączona |
| Zarządzanie informacjami o produktach | Domyślne wymiary finansowe osobno w przypadku korzystania z szablonów pozycji | Domyślnie włączona |
| Zarządzanie informacjami o produktach | Włącz grupy wymiarów produktów dla szablonów pozycji | Domyślnie włączona |
| Zarządzanie informacjami o produktach | Generuj ponownie nazwy wariantów produktu na podstawie nazewnictwa | Domyślnie włączona |
| Zarządzanie informacjami o produktach | [Ulepszenia strony sugestii dotyczących wariantów](../pim/tasks/create-predefined-product-variants.md) | Domyślnie włączona |
| Kontrola produkcji | Poprawione pobieranie ilości efektywnej produkcji | Ogólnie dostępne |
| Kontrola produkcji | Do strony Terminal kart zadań dodany został nowy przycisk Zatrzymaj przerwę | Wymagana |
| Kontrola produkcji | [Włącz automatyczną generację numeru identyfikacyjnego podczas zgłaszania wyrobów gotowych w urządzeniu karty zadań](../production-control/production-floor-execution-configure.md) | Wymagana |
| Kontrola produkcji | Włącz częściowe przyjęcie pozycji podwykonawczych i rozwiąż problem z obliczaniem odpadków dla wierszy listy składowej (BOM) typu Dostawca | Wymagana |
| Kontrola produkcji | [Funkcja umożliwiająca blokowanie urządzenie karty zadań i terminalu karty zadań w celu ich wyczyszczenia](../production-control/production-floor-execution-configure.md) | Wymagana |
| Kontrola produkcji | Ulepszenia w oknach dialogowych Zadania zatwierdzania i Zadania przenoszenia | Wymagana |
| Kontrola produkcji | [Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań](../production-control/production-floor-execution-configure.md) | Wymagana |
| Kontrola produkcji | [Drukowanie etykiety z menu Urządzenie karty zadań](../production-control/production-floor-execution-configure.md) | Wymagana |
| Kontrola produkcji | [Wykonanie hali produkcyjnej](../production-control/production-floor-execution-configure.md) | Wymagana |
| Kontrola produkcji | [Funkcje zarządzania zasobami dla interfejsu wykonania hali produkcyjnej](../production-control/production-floor-execution-configure.md) | Domyślnie włączona |
| Kontrola produkcji | [Wyszukiwanie zadań dla interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) | Domyślnie włączona |
| Kontrola produkcji | [Zastąp domyślną rezerwację produkcji](../production-control/override-default-reservation-principle.md) | Domyślnie włączona |
| Kontrola produkcji | [Pokaż pełne numery seryjne, partii i numery identyfikacyjne w interfejsie wykonania hal produkcyjnych](whats-new-scm-10-0-21.md) | Domyślnie włączona |
| Sprzedaż i marketing | [Rozszerzenie wydajności szczegółów zamówienia sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Ogólnie dostępne |
| Sprzedaż i marketing | Rozszerzenie wydajności szczegółów oferty sprzedaży | Ogólnie dostępne |
| Sprzedaż i marketing | Zasady eksportu danych, do których odwołuje się zamówienie sprzedaży | Wymagana |
| Sprzedaż i marketing | [Zasady usuwania wiersza zamówienia sprzedaży do zamówienia zakupu](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Wymagana |
| Sprzedaż i marketing | [Zasady eksportu danych, do których odwołuje się oferta sprzedaży](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Wymagana |
| Sprzedaż i marketing | [Optymalizacja eksportu jednostki danych osoby kontaktowej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Domyślnie włączona |
| Sprzedaż i marketing | Włącz wyszukiwanie pól wprowadzenia do dokumentu i wniosków z dokumentu ofert sprzedaży | Domyślnie włączona |
| Sprzedaż i marketing | [Popraw wydajność raportu „100 najlepszych” odbiorców](whats-new-scm-10-0-23.md) | Domyślnie włączona |
| Sprzedaż i marketing | Ponowne obliczanie szacowanego salda odbiorcy | Domyślnie włączona |
| Sprzedaż i marketing | [Rejestracja wiersza zamówienia zwrotu sprzedaży z dokładnością do wartości dziesiętnych wraz z i bez ilości efektywnej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Domyślnie włączona |
| Sprzedaż i marketing | [Zapisane widoki dla sprzedaży i marketingu](saved-views-scm.md) | Domyślnie włączona |
| Sprzedaż i marketing | Potwierdzenie zamówienia sprzedaży za jednym kliknięciem | Domyślnie włączona |
| Zarządzanie magazynem | [Szablony przeładunku kompletacyjnego z dyrektywami lokalizacji](../warehousing/planned-cross-docking.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Wyłącz oczekiwane przyjęcia ze zleceń kontroli jakości, które pobierają próbki zablokowanych zapasów](../inventory/inventory-blocking.md) | Ogólnie dostępne |
| Zarządzanie magazynem | Historia odbierania numeru identyfikacyjnego | Ogólnie dostępne |
| Zarządzanie magazynem | [Interfejs urządzeń do obsługi materiałów](../warehousing/mhax.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Zaokrąglij ilości w dół do najbliższej jednostki sprzedaży podczas zwalniania do magazynu](whats-new-scm-10-0-19.md) | Ogólnie dostępne |
| Zarządzanie magazynem | Obsługa jednostki skalowania dla list pracy aplikacji magazynowej | Ogólnie dostępne |
| Zarządzanie magazynem | Szczegóły etykiety grupy czynności wysyłki | Ogólnie dostępne |
| Zarządzanie magazynem | [Użyj szybszego interfejsu API do zamykania/ponownego otwierania kontenerów na stacji pakowania](whats-new-scm-10-0-21.md) | Ogólnie dostępne |
| Zarządzanie magazynem | [Weryfikuj szablony wybrane dla zadań uzupełniania zapasów](whats-new-scm-10-0-20.md) | Ogólnie dostępne |
| Zarządzanie magazynem | Zezwalaj szablonowi uzupełniania zapasów na użycie istniejącej pracy natychmiastowego uzupełniania zapasów (między jednostkami) | Wymagana |
| Zarządzanie magazynem | Automatyczne przypisywanie identyfikatorów GUID przy tworzeniu użytkownika WHS | Wymagana |
| Zarządzanie magazynem | Przechwytywanie wariantów produktu i wymiarów śledzenia w aplikacji magazynowej podczas przyjmowania pozycji ładunku | Wymagana |
| Zarządzanie magazynem | [Zmień stan zapasów dla pozycji kontrolowanych przez wymiary śledzenia](../inventory/inventory-statuses.md) | Wymagana |
| Zarządzanie magazynem | [Zmień pulę pracy w pracy](../warehousing/change-work-pool-on-work.md) | Wymagana |
| Zarządzanie magazynem | [Stanowisko w grupie pełne](../warehousing/cluster-position-full.md) | Wymagana |
| Zarządzanie magazynem | [Funkcja odłożenia grupy](../warehousing/putaway-clusters.md) | Wymagana |
| Zarządzanie magazynem | [Potwierdź i przenieś](../warehousing/confirm-and-transfer.md) | Wymagana |
| Zarządzanie magazynem | [Potwierdź wychodzące wysyłki z zadań wsadowych](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Wymagana |
| Zarządzanie magazynem | [Określ, czy wyświetlać stronę podsumowania odbierania na urządzeniach przenośnych](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Wymagana |
| Zarządzanie magazynem | [Odroczone przetwarzanie operacji ręcznego przenoszenia zapasów](../warehousing/deferred-processing-manual-inventory-movement.md) | Wymagana |
| Zarządzanie magazynem | Nie zezwalaj na tworzenie ładunków, które nie spełniają wymagań szablonu kompilowania ładunku grupy czynności | Wymagana |
| Zarządzanie magazynem | [Rozszerzone układy etykiet numerów identyfikacyjnych](../warehousing/document-routing-layout-for-license-plates.md) | Wymagana |
| Zarządzanie magazynem | [Ocenianie wszystkich akcji dla dyrektyw lokalizacji wielu jednostek SKU](/troubleshoot/dynamics-365/supply-chain/warehousing/evaluate-multiple-location-directive-actions) | Wymagana |
| Zarządzanie magazynem | Ukryj pole Wartość całkowita na stronach „Wszystkie ładunki” i „Szczegóły ładunku” | Wymagana |
| Zarządzanie magazynem | Konfiguracja kompilacji etykiet numerów identyfikacyjnych | Wymagana |
| Zarządzanie magazynem | Ręczna korekta wiersza obciążenia pracą dla administratora lub podobnych zaufanych użytkowników | Wymagana |
| Zarządzanie magazynem | [Stanowisko obiektu o numerze identyfikacyjnym w lokalizacji](../warehousing/location-license-plate-positioning.md) | Wymagana |
| Zarządzanie magazynem | [Mieszanie wymiarów produktów w lokalizacji](../warehousing/location-product-dimension-mixing.md) | Wymagana |
| Zarządzanie magazynem | Umożliwia edytowanie pola stanu zapasów dla przeniesienia magazynowego urządzeń przenośnych | Wymagana |
| Zarządzanie magazynem | [Ręczna usługa pobierania wierszy sprzedaży dla administratora lub podobnych zaufanych użytkowników](../warehousing/manual-order-line-picking-exception-handling.md) | Wymagana |
| Zarządzanie magazynem | [Zapobiegaj używaniu numerów identyfikacyjnych wysłanych zamówień przeniesienia w magazynach innych niż magazyn docelowy](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Wymagana |
| Zarządzanie magazynem | Monituj o rozwiązanie niejednoznacznych nazw typu „Lokalizacja/numer identyfikacyjny” | Wymagana |
| Zarządzanie magazynem | [Kontrola jakości](../warehousing/quality-check.md) | Wymagana |
| Zarządzanie magazynem | [Ustawienia użytkownika, ikony i tytuły kroków dla nowej aplikacji magazynowej](../warehousing/install-configure-warehouse-management-app.md) | Wymagana |
| Zarządzanie magazynem | [Dodatkowa strefa lokalizacji](../warehousing/additional-location-zones.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Tworzenie i przetwarzanie zamówień przeniesienia z aplikacji magazynowej](../warehousing/create-transfer-order-from-warehouse-app.md) | Domyślnie włączona |
| Zarządzanie magazynem | Włączanie funkcji szybkiej weryfikacji dla urządzeń przenośnych używanych w magazynie | Domyślnie włączona |
| Zarządzanie magazynem | [Maksymalny czas wykonywania zadania oczyszczania wpisów dostępnych zapasów w zarządzaniu magazynem](../warehousing/onhand-cleanup.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Wychodzące wizualizacje obciążenia pracą](../warehousing/outbound-workload-visualization.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Przetwarzanie zdarzeń aplikacji magazynowej](../warehousing/warehouse-app-events.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Zapisane widoki dla warsztatu planowania wysyłki ładunku](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Zapisany widok dla strony szczegółów pracy](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Zapisany widok dla przetwarzania grupy czynności](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Zapisane widoki dla przetwarzania ładunku](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Zapisane widoki dla przetwarzania wysyłki](saved-views-scm.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Szczegóły zadania wsadowego grupy czynności](../warehousing/wave-processing.md) | Domyślnie włączona |
| Zarządzanie magazynem | [Powiadomienia dotyczące wykonania grupy czynności](../warehousing/wave-execution-notifications.md) | Domyślnie włączona |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji finansowych i operacyjnych

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.25 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.25 aplikacji finansowych i operacyjnych (kwiecień 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.25, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.](/dynamics365-release-plan/2022wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W artykule [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

