---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.17 (kwiecień 2021)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.17.
author: kamaybac
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4b4e551f5c687f0021ddba0c9f5b73af528b7140
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813178"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10017-april-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.17 (kwiecień 2021)

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.17. Ta wersja ma numer kompilacji 10.0.761 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza:** luty 2021 r.
- **Ogólna dostępność wydania (samoaktualizacja):** marzec 2021 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** kwiecień 2021 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje.  Postępuj zgodnie z łączami do [planu wydania](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), aby przejrzeć oficjalne daty zwolnienia dla każdej z funkcji.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać. Niektóre z wymienionych funkcji mogą być nadal dostępne w wersji zapoznawczej, chociaż większość z nich jest teraz ogólnie dostępna.

### <a name="asset-management"></a>Zarządzanie składnikami majątku

- [Stosowanie reguł grupowania zleceń pracy podczas uruchamiania planu konserwacji](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/apply-rules-grouping-work-orders-while-running-maintenance-plan)<br> - Aby uzyskać więcej informacji, zobacz temat [Tworzenie zleceń pracy](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md).

- [Fakturowanie odbiorców za pracę konserwacyjną](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/bill-customers-maintenance-work)<br> - Aby uzyskać więcej informacji, zobacz temat [Fakturowanie za konserwację składników majątku należących do klientów](../asset-management/integration-to-project-management-and-accounting/customer-billing.md).

- [Planowanie konserwacji na podstawie skumulowanych wartości liczników składników majątku](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/plan-maintenance-based-accumulated-asset-counter-values)<br> - Aby uzyskać więcej informacji, zobacz temat [Plany konserwacji](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md).

### <a name="inventory-and-logistics"></a>Zapasy i logistyka

- [Ramy integracyjne dla urządzeń do transportu materiałów dla zautomatyzowanych procesów magazynowych (wcześniej MHAX)](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/integration-framework-material-handling-equipment-automated-warehouse-processes-previously-mhax)<br> - Aby uzyskać więcej informacji, zobacz [Interfejs wyposażenia do transportu materiałów (MHAX)](../warehousing/mhax.md).

- [Koszt z wyładunkiem](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/landed-cost)<br> - Aby uzyskać więcej informacji, zobacz [Moduł Koszt z wyładunkiem](../landed-cost/landed-cost-overview.md).

- [Opakowanie a wymiary magazynowania](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/packing-vs.-storage-dimensions)<br> - Aby uzyskać więcej informacji, zobacz temat [Ustawianie różnych wymiarów w celu pakowania i przechowywania](../warehousing/packing-vs-storage-dimensions.md).

- [Zapisane widoki dla zapasów i logistyki](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-inventory-logistics)<br> - Aby uzyskać więcej informacji, zobacz temat [Standardowe zapisane widoki dla aplikacji Supply Chain Management](saved-views-scm.md).

- [Planowanie tworzenia pracy magazynowej](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-warehouse-work-creation)<br> - Aby uzyskać więcej informacji, zobacz temat [Planowanie tworzenia pracy podczas obsługi grupy czynności](../warehousing/configure-wave-schedule-work-creation.md).

- [Ustawianie domyślnych wymiarów finansowych dla załączników przeszacowania kosztów standardowych zapasów](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/set-default-financial-dimensions-inventory-standard-cost-revaluation-vouchers)<br> - Aby uzyskać więcej informacji, zobacz temat [Zarządzanie aktualizacjami kosztów standardowych](../cost-management/manage-standard-cost-updates.md).

- [Wysyłka małych paczek (SPS)](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/small-parcel-shipping-sps)<br> - Aby uzyskać więcej informacji, zobacz temat [Wysyłka małych paczek](../warehousing/small-parcel-shipping.md).

- [Wykonywanie w magazynie z jednostkami skalowania w chmurze](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-scale-units-cloud)<br> - Aby uzyskać więcej informacji, zobacz temat [Obciążenia zarządzania magazynem dla jednostek skalowania w chmurze i na urządzeniach brzegowych](../cloud-edge/cloud-edge-workload-warehousing.md) oraz [Zamówienia magazynowe dla jednostek skalowania w chmurze i na urządzeniach brzegowych](../cloud-edge/cloud-edge-warehouse-order.md).

- [Aplikacja mobilna Zarządzanie magazynem](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application)<br> - Aby uzyskać więcej informacji, zobacz temat [Instalowanie i łączenie aplikacji Zarządzanie magazynem](../warehousing/install-configure-warehouse-management-app.md) i [Ustawienia użytkownika urządzenia mobilnego](../warehousing/mobile-device-user-settings.md).

- Powiadomienia dotyczące wykonania grupy czynności<br> - Aby uzyskać więcej informacji, zobacz temat [Powiadomienia dotyczące wykonania grupy czynności](../warehousing/wave-execution-notifications.md)

### <a name="manufacturing"></a>Produkcja

- [Funkcje zarządzania składnikami majątku w interfejsie wykonywania w przedsiębiorstwie produkcyjnym](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/asset-management-capabilities-production-floor-execution-interface)<br> - Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md).

- Zunifikowana sekwencja numerów dla identyfikatorów zadań<br> - Aby uzyskać więcej informacji, zobacz 

- [Zastąpienie domyślnej reguły rezerwacji materiałów w produkcji](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/override-default-reservation-principle-materials-production)<br> - Aby uzyskać więcej informacji, zobacz temat [Zastępowanie domyślnej zasady rezerwacji materiałów w produkcji](../production-control/override-default-reservation-principle.md).

- [Zapisane widoki dla kontroli produkcji](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-production-control)<br> - Aby uzyskać więcej informacji, zobacz temat [Standardowe zapisane widoki dla aplikacji Supply Chain Management](saved-views-scm.md).

- [Wykonywanie produkcji z jednostkami skalowania w chmurze](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-scale-units-cloud)<br> - Aby uzyskać więcej informacji, zobacz temat [Obciążenia wykonywania produkcji dla jednostek skalowania w chmurze i na urządzeniach brzegowych](../cloud-edge/cloud-edge-workload-manufacturing.md).

### <a name="planning"></a>Planowanie

- [Obsługa horyzontów czasowych zapotrzebowania na potrzeby optymalizacji planowania](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/coverage-time-fence-support-planning-optimization)<br> - Aby uzyskać więcej informacji, zobacz temat [Horyzonty czasowe zapotrzebowania](../master-planning/planning-optimization/coverage-time-fence.md).

- [Obsługa modelu podrzędnego prognozy dla optymalizacji planowania](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/forecast-submodel-support-planning-optimization)<br> - Aby uzyskać więcej informacji, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](../master-planning/planning-optimization/demand-forecast.md).

- [Obsługa zapotrzebowań na zakupy na potrzeby optymalizacji planowania](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/purchase-requisition-support-planning-optimization)<br> - Aby dowiedzieć się więcej, zobacz temat [Zapotrzebowania na zakup](../master-planning/planning-optimization/purchase-requisitions.md).

- [Zapisane widoki dla planowanych zamówień](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-planned-orders)<br> - Aby uzyskać więcej informacji, zobacz temat [Standardowe zapisane widoki dla aplikacji Supply Chain Management](saved-views-scm.md).

### <a name="product-information-management"></a>Zarządzanie informacjami o produktach

- [Włącz zarządzanie zmianami w istniejących produktach](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enable-change-management-existing-products)<br> - Aby uzyskać więcej informacji, zobacz [Włącz zarządzanie zmianami w istniejących produktach](../engineering-change-management/change-management-existing-products.md).

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

### <a name="cost-management"></a>Zarządzanie kosztami

- [Rozwiązywanie problemów z zarządzaniem kosztami](../cost-management/troubleshoot-costmanagement.md)

### <a name="asset-management"></a>Zarządzanie składnikami majątku

- [Konfiguracja mobilnego obszaru roboczego zarządzania składnikami majątku](../asset-management/set-up-asset-management-mobile.md)

### <a name="inventory-and-logistics"></a>Zapasy i logistyka

- [Konfigurowanie filtrów produktów dla transakcji magazynowych](../warehousing/filters-and-filter-codes.md)

- [Częściowa inwentaryzacja ciągła w lokalizacji](../warehousing/partial-location-cycle-counting.md)

- [Grupowanie wierszy pobrania](../warehousing/pick-line-grouping.md)

- [Rozwiązywanie problemów z operacjami magazynowymi](../inventory/troubleshoot-inventory-operations.md)

- [Rozpisywanie na przedziały w magazynie](../warehousing/warehouse-slotting.md)

### <a name="manufacturing"></a>Produkcja

- [Projektowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-tabs.md)

### <a name="planning"></a>Planowanie

- [Planowanie międzyfirmowe](../master-planning/planning-optimization/Intercompany-planning.md)

- [Oznaczanie zapasów przy użyciu modułu Optymalizacja planowania](../master-planning/planning-optimization/marking.md)

- [Planowanie produkcji](../master-planning/planning-optimization/production-planning.md)

- [Zapotrzebowania na zakup w planowaniu głównym](../master-planning/planning-optimization/purchase-requisitions.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.17 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.17 aplikacji Finance and Operations (kwiecień 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.17, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=551039&dbType=3&qc=91219e7c3fc585acb17b810c915c3cbea499403538520c40e54de43a53aea6a8).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: plan wydania 2021 aktualizacja 1

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zajrzyj do [Dynamics 365: plan wydania 2021 aktualizacja 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]