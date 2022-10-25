---
title: Wersja zapoznawcza Dynamics 365 Supply Chain Management 10.0.30 (listopad 2022)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 18fec49f2388159cae0809c63685102a04e90c57
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689200"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.30 (listopad 2022 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.30. Ta wersja ma numer kompilacji 10.0.1362 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza:** wrzesień 2022
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2022 r.
- **Ogólna dostępność wydania (samoaktualizacja):** Listopad 2022

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Produkcja | [Monitorowanie sprzętu za pomocą Sensor Data Intelligence](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Sensor Data Intelligence — strona główna](../sensor-data-intelligence/sdi-home-page.md) | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) Analiza danych czujnika* |
| Zarządzanie magazynem | [Wielopoziomowe przekierowanie dla aplikacji mobilnej Warehouse Management](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Konfiguracja obejść dla kroków w elementach menu urządzeń mobilnych](../warehousing/warehouse-app-detours.md) | Zarządzanie funkcjami:<br>*Wielopoziomowe przekierowanie dla aplikacji mobilnej Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Kontrola produkcji | Informacje o stanie na stronie zlecenia produkcyjnego do zwolnienia | Dodaje kolumnę ilości dostępnych zapasów dla pozycji w wierszu w sekcji wierszy na stronie **Zleceń produkcyjnych do zwolnienia**. |
| Zarządzanie transportem | Przypisz wysyłki do powiązanych segmentów marszruty | Ta funkcja umożliwia systemowi bardziej dokładne podzielenie kosztów frachtu wysyłki, w tym ładunków z wieloma wysyłkami dostarczanymi do różnych miejsc docelowych segmentu na jednej trasie. Każda wysyłka jest przypisywana do najbardziej odpowiedniego segmentu marszruty na podstawie adresów docelowych wysyłki i segmentu. Funkcja ta oblicza koszt transportu każdej wysyłki jako odsetek łącznego kosztu frachtu ładunku na podstawie względnej masy, objętości, ilości i odległości przesyłki. Ta funkcja dotyczy wyłącznie wysyłek zarządzanych za pomocą modułu Zarządzanie transportem (TMS). |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.30 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.30 aplikacji Finanse i Operacje (listopad 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.29, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

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
