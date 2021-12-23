---
title: Podgląd Dynamics 365 Supply Chain Management 10.0.24 (luty 2022 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 1b5742ddf7e5e2c5c32c446a0bde08f4964d6b95
ms.sourcegitcommit: 96515ddbe2f65905140b16088ba62e9b258863fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2021
ms.locfileid: "7891881"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10024-february-2022"></a>Podgląd Dynamics 365 Supply Chain Management 10.0.24 (luty 2022 r.)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.24. Ta wersja ma numer kompilacji 10.0.1084 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** grudzień 2021 r.
- **Ogólna dostępność wydania (samoaktualizacja):** styczeń 2022
- **Ogólna dostępność wydania (samoaktualizacja):** luty 2022

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał funkcje wprowadzone do kompilacji po początkowym opublikowaniu tego tematu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Rozproszona topologia hybrydowa | [Rozszerzone obciążenia wykonania w magazynie dla jednostkach skalowania](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md) | Domyślnie włączone. |
| Planowanie | [Obsługa optymalizacji planowania w przypadku marży ponownego zamawiania i marży wydania](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Marginesy bezpieczeństwa](../master-planning/planning-optimization/safety-margins.md) | Domyślnie włączone. |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Kontrola produkcji | Sprawdzanie dostępności materiałów na żądanie dla zleceń produkcyjnych | Ta funkcja przyspiesza otwieranie strony **Zlecenia produkcyjne do zwolnienia** dostępnej w obszarze roboczym **Zarządzanie halą produkcyjną**. Bez tej funkcji system automatycznie sprawdza, czy materiały są dostępne dla wszystkich wymienionych zleceń produkcyjnych po otwarciu strony, co może potrwać znacznie dłużej w przypadku dużej liczby zleceń. Gdy ta funkcja jest włączona, w systemie jest wyświetlany przycisk paska narzędzi, który umożliwia inicjowanie sprawdzania materiałów tylko w razie potrzeby i tylko dla wybranych zamówień. |
| Kontrola produkcji | (Wersja zapoznawcza) Rejestrowanie zużycia materiału w interfejsie wykonania hal produkcyjnych (inne niż WMS) | Ta funkcja umożliwia pracownikom używanie interfejsu wykonywania produkcji do rejestrowania zużycia materiałów, numerów partii i numerów seryjnych. Ta funkcja obsługuje tylko pozycje, dla których nie włączono obsługi zaawansowanych procesów magazynowych (WMS). Obsługa pozycji z obsługą usług WMS jest zaplanowana w przyszłym wydaniu.<p>Niektórzy producenci, w szczególności branże zajmujące się przetwarzaniem, muszą jawnie rejestrować ilość zużytych materiałów dla poszczególnych partii lub zlecenia produkcyjnego. Na przykład pracownicy mogą używać wagi do zważenia ilości zużytego materiału podczas pracy. Aby zapewnić pełne śledzenie materiałów, organizacje te muszą także zarejestrować numery partii zużyte podczas produkcji każdego produktu. |
| Kontrola produkcji | Zgłaszanie pozycji jako gotowych w obciążeniach zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego | Ta funkcja pozwala pracownikom używać aplikacji mobilnej Warehouse Management do zgłaszania zamówień produkcyjnych lub zamówień partii jako zakończonych, gdy aplikacja jest uruchamiana z obciążeniem pracą zarządzania magazynem w jednostce skalowania chmurze lub na urządzeniu brzegowym. Aby uzyskać więcej informacji, zobacz [Zgłoś jako gotowe i odłóż na jednostce skalowania](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF)wagi. |
| Kontrola produkcji | Uruchamianie zlecenia produkcyjnego w obciążeniach zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego | Ta funkcja pozwala pracownikom używać aplikacji mobilnej Warehouse Management do uruchamiania zamówień produkcyjnych lub zamówień partii jako zakończonych, gdy aplikacja jest uruchamiana z obciążeniem pracą zarządzania magazynem w jednostce skalowania chmurze lub na urządzeniu brzegowym. |
| Zarządzanie magazynem | Nowe strony pulpitu planowania wysyłki ładunku | Włącza dwie nowe strony pulpitu planowania wysyłki ładunku: **Pulpit planowania wysyłki ładunku przychodzącego** i **Pulpit planowania wysyłki ładunku wychodzącego**. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Te tematy nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Zarządzanie kosztami | [Raporty wartości zapasów](../cost-management/inventory-value-report-storage.md) |
| Zarządzanie kosztami | [Przykłady i logika raportu wartości zapasów](../cost-management/inventory-value-report-examples.md) |
| Planowanie główne | [Parametry daty i godziny używane przez optymalizację planowania](../master-planning/planning-optimization/date-time-used.md) |
| Planowanie główne | [Ustawienia prognozowania popytu](../master-planning/demand-forecasting-setup.md) |
| Planowanie główne | [Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania dla pozycji](../master-planning/safety-stock-journal.md) |
| Kontrola produkcji | [Dostosowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-customize.md) |
| Kontrola produkcji | [Stylizacja interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-styles.md) |
| Sprzedaż i marketing | [Ulepszenia wydajności oczyszczania historii sprzedaży](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Zarządzanie magazynem | [Konta użytkownika urządzenia przenośnego](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.24 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.24 aplikacji Finance and Operations (listopad 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.24, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2021 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2021 r.](/dynamics365-release-plan/2021wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
