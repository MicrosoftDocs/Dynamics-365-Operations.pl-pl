---
title: Nowości i zmiany w programie Dynamics 365 Supply Chain Management w wersji 10.0.18 (maj 2021 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.18.
author: kamaybac
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d84520b8f551df847cb5d77d8dcbce1701d3795b
ms.sourcegitcommit: d77b2175a3364694b5c74e0062e317f612416796
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5934974"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10018-may-2021"></a>Nowości i zmiany w programie Dynamics 365 Supply Chain Management w wersji 10.0.18 (maj 2021 r.)

[!include [banner](../includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.18. Ta wersja ma numer kompilacji 10.0.793 i jest dostępna w następujący sposób:

- **Wersja podglądu:** marzec 2021
- **Ogólna dostępność wydania (Samoaktualizacja):** kwiecień 2021 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** maj 2021 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Postępuj zgodnie z łączami do [planu wydania](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), aby przejrzeć oficjalne daty zwolnienia dla każdej z funkcji.

- Automatyczne zwalnianie zamówień zakupu (rozszerzenie dla [Wykonywanie w magazynie z jednostkami skalowania w chmurze](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-scale-units-cloud))<br> - Aby uzyskać więcej informacji, zobacz temat [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md).

- [Usprawnienia wydajności zapasów i archiwizacja na poziomie przedsiębiorstwa](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enterprise-scale-inventory-performance-improvements-archiving)<br> - Aby uzyskać więcej informacji, zobacz temat [Archiwizuj transakcje magazynowe](../inventory/archive-inventory-transactions.md).

- [Zarządzanie rabatami](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/rebate-management)<br> - Aby uzyskać więcej informacji, zajrzyj do omówienia [Omówienie modułu Zarządzanie rabatami](../rebate-management/rebate-management-overview.md)

- [Zasady ustawień eksportu jednostek danych sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-data-entity-export-setup-policy)

- [Rejestracja wiersza zamówienia zwrotu sprzedaży z dokładnością do wartości dziesiętnych wraz z i bez ilości efektywnej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight)

- [Potwierdzenie zamówienia sprzedaży za jednym kliknięciem](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation)

- [Zasady usuwania wiersza zamówienia sprzedaży do zamówienia zakupu](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy)

- Uproszczony interfejs tylko do wejścia i wyjścia do pracy (ulepszona funkcja [Ulepszony interfejs wykonywania hali produkcyjnej do celów produkcyjnych](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing))<br> - Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md).

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać.

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

- [Dodatek Widoczność magazynu](../inventory/inventory-visibility.md)
- [Moduł Kosztów z wyładunkiem](../landed-cost/landed-cost-overview.md)
- [Interfejs urządzeń do obsługi materiałów (MHAX)](../warehousing/mhax.md)
- [Analiza dopasowań optymalizacji planowania](../master-planning/planning-optimization/planning-optimization-fit-analysis.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.18 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.18 aplikacji Finance and Operations (maj 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.18, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=561679&dbType=3&qc=13bb1641c1be430ead8b21ae3d4e0f800d5b81c39b3a56e890db1de7ede59e46).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: plan wydania 2021 aktualizacja 1

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zajrzyj do [Dynamics 365: plan wydania 2021 aktualizacja 1](/dynamics365-release-plan/2021wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]