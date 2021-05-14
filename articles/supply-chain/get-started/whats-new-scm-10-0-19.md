---
title: Wersja zapoznawcza Dynamics 365 Supply Chain Management w wersji 10.0.19 (lipiec 2021)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8bb4a7c8085b40ab3eca72675dbe7a3be412d8c1
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961688"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10019-july-2021"></a>Wersja zapoznawcza Dynamics 365 Supply Chain Management w wersji 10.0.19 (lipiec 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.19. Ta wersja ma numer kompilacji 10.0.837 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** kwiecień 2021
- **Ogólna dostępność wydania (samoaktualizacja):** czerwiec 2021 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** lipiec 2021 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do dokumentacji pokrewnej.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać. Niektóre z tych funkcji są nadal w wersji zapoznawczej, a inne mogą być już ogólnie dostępne.

| Obszar funkcji | Funkcja | Więcej informacji |
|---|---|---|
| Zapasy i logistyka | [Optymalizacja eksportu jednostki danych osoby kontaktowej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | *Niedostępna* |
| Zapasy i logistyka | [Przyrostowe rozszerzenia możliwości wykonywania magazynów za pomocą jednostek skalowania](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Komunikaty procesora komunikatów](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Korekta zapasów w magazynie](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Zapasy i logistyka | [Funkcje wyszukiwania w polach Wstęp do dokumentu i Wnioski dokumentu na stronie Oferta sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | *Niedostępna* |
| Zapasy i logistyka | [Wykonywanie magazynu z jednostkami skalowania urządzeń brzegowych na niestandardowym sprzęcie](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Rozmieszczanie jednostek skalowania urządzeń brzegowych na niestandardowym sprzęcie przy użyciu funkcji LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Produkcja | [Wykonywanie produkcji z jednostkami skalowania urządzeń brzegowych na niestandardowym sprzęcie](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Rozmieszczanie jednostek skalowania urządzeń brzegowych na niestandardowym sprzęcie przy użyciu funkcji LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planowanie | Ustalanie zamówienia planowanego oparte na zapytaniu | [Zaakceptuj zamówienia planowane](../master-planning/planning-optimization/planned-order-firming.md) |
| Zarządzanie informacjami o produktach | [Ulepszenia strony sugestii dotyczących wariantów](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Tworzenie wstępnie zdefiniowanych wariantów produktu](../pim/tasks/create-predefined-product-variants.md) |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Zarządzanie zmianami projektowymi | [Zarządzanie zmianami projektowymi — FAQ](../engineering-change-management/change-management-faq.md) |
| Zaopatrzenie i sourcing | [Wnioski o nadanie kategorii od dostawców](../procurement/category-requests-from-vendors.md) |
| Zarządzanie informacjami o produktach | [Zarządzanie jednostką miary](../pim/tasks/manage-unit-measure.md)<br><br>[Obliczenia na potrzeby modelu konfiguracji produktu](../pim/config-model-calculations.md) |
| Kontrola produkcji | [Zunifikowana sekwencja numerów dla identyfikatorów zadań](../production-control/unified-job-ids.md) |
| Zarządzanie transportem | [Klasy LTL](../transportation/ltl-class.md)<br><br>[Numery NMFC](../transportation/nmfc-codes.md) |
| Zarządzanie magazynem | [Rozwiązywanie problemów z hierarchiami rezerwacji partii i numerów seryjnych w magazynie](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Zarządzanie magazynem, tworzenie i przetwarzanie grupy czynności | [Tworzenie i przetwarzanie grupy czynności](../warehousing/wave-processing.md)<br><br>[Parametry magazynu dla przetwarzania grupy czynności](../warehousing/wave-warehouse-parameters.md)<br><br>[Szablony grupy czynności](../warehousing/wave-templates.md)<br><br>[Alokacja grupy czynności](../warehousing/wave-allocation-method.md)<br><br>[Tworzenie planu pracy podczas grupy czynności](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Konteneryzacja](../warehousing/wave-containerization.md)<br><br>[Powiadomienia dotyczące wykonania grupy czynności](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.19 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.19 aplikacji Finance and Operations (lipiec 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.19, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

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
