---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.22 (listopad 2021 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: b95f131a45c11748cfd4c66c47e5a51c765ed486
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740418"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.22 (listopad 2021 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.22. Ta wersja ma numer kompilacji 10.0.995 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza:** wrzesień 2021
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2021 r.
- **Ogólna dostępność wydania (samoaktualizacja):** Listopad 2021

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej. Aby określić sposób włączania funkcji, zobacz kolumnę *Włączane przez*. Aby uzyskać więcej informacji o zarządzaniu funkcjami, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Firma Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał funkcje wprowadzone do kompilacji po początkowym opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Planowanie | [Obsługa optymalizacji planowania dla alokacji zasobów opartej na możliwościach](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Planowanie z wyborem zasobu na podstawie zdolności produkcyjnych](../master-planning/planning-optimization/capability-based-scheduling.md) | Zarządzanie funkcjami (*Planowanie nieskończonej pojemności dla optymalizacji planowania*) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej). Aby korzystać z tych funkcji, należy jawnie włączyć te funkcje w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Rozproszona topologia hybrydowa | *(Nie jest wymagane zarządzanie funkcjami).* | <p>Ta wersja rozszerza możliwości planowania wysyłki ładunku wychodzącego z obciążenia pracą zarządzania magazynem dla jednostek skalowania chmury i krawędzi.</p><p>Aby uzyskać więcej informacji, zobacz temat [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Zarządzanie zmianami projektowymi | Generowanie wariantów produktów projektowych | <p>Ta funkcja umożliwia generowanie kilku wariantów produktu inżynieryjnego na podstawie jego wymiarów koloru, rozmiaru, stylu lub konfiguracji.</p><p>Aby uzyskać więcej informacji, zobacz [Generowanie wariantów dla produktów inżynieryjnych](../engineering-change-management/engineering-variants.md).</p> |
| Zarządzanie zapasami i magazynem | Integracja Widoczności zapasów z przesunięciem rezerwacji | <p>Tę funkcję można włączyć tylko po włączeniu funkcji *Integracja z widocznością zapasów*. Zapewnia ona funkcjonalność kompensowania rezerwacji, które są dokonywane na widoczności zapasów.</p><p>Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](../inventory/inventory-visibility-reservations.md).</p> |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły pomocy. Te artykuły nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Zarządzanie zmianami projektowymi | [Omówienie zarządzania zmianami inżynieryjnymi](../engineering-change-management/product-engineering-overview.md) zawiera teraz listę wszystkich opcjonalnych funkcji dostępnych w zarządzaniu funkcjami |
| Planowanie główne | [Ustawienia prognozowania popytu](../master-planning/demand-forecasting-setup.md) |
| Planowanie główne | [Wymagania netto i informacje oznaczania transakcji](../master-planning/planning-optimization/net-requirements.md) |
| Zarządzanie magazynem | [Zwolnienie do magazynu](../warehousing/release-to-warehouse-process.md) umożliwia szczegółowy przegląd pełnego procesu zwalniania do magazynu |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji finansowych i operacyjnych

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.22 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.22 aplikacji finansowych i operacyjnych (listopad 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.22, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2021 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2021 r.](/dynamics365-release-plan/2021wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W artykule [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

