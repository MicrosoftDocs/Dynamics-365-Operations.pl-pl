---
title: Przegląd Dynamics 365 Supply Chain Management 10.0.20 (sierpień 2021)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a782416bdb12a8ac7f1ba807452ca54072af3ab5
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301753"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10020-august-2021"></a>Przegląd Dynamics 365 Supply Chain Management 10.0.20 (sierpień 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.20. Ta wersja ma numer kompilacji 10.0.886 i jest dostępna w następujący sposób:

- **Wersja podglądu:** maj 2021
- **Ogólna dostępność wydania (samoaktualizacja):** lipiec 2021 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** sierpień 2021 r.


## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać. Niektóre z tych funkcji są nadal w wersji zapoznawczej, a inne mogą być już ogólnie dostępne.

| Obszar funkcji | Funkcja | Więcej informacji |
|---|---|---|
| Zapasy&nbsp;i&nbsp;logistyka | [Rozszerzenie wydajności szczegółów zamówienia sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Ta funkcja sprawia, że interfejs użytkownika jest bardziej responsywny podczas otwierania zamówień sprzedaży, zwłaszcza zamówień zawierających wiele linii. |
| Produkcja | [Wywoływanie przepływów automatyzacji procesów w celu tworzenia zleceń wysokiej jakości](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Wywoływanie przepływów automatyzacji procesów w celu tworzenia zleceń wysokiej jakości](../production-control/process-automation-quality-orders.md ) |
| Produkcja | [Ulepszony interfejs wykonawczy hali produkcyjnej dla produkcji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Konfigurowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md) |
| Zarządzanie informacjami o produktach | [Zarządzanie zmianami w formułach i ich składnikach](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Zarządzanie zmianami w formułach i ich składnikach](../engineering-change-management/manage-formula-changes.md) |
| Zarządzanie informacjami o produktach | [Testy gotowości produktu](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Gotowość produktu](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji zawarte w tym wydaniu. Każdy z nich zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej). Aby korzystać z tych funkcji, należy jawnie włączyć te funkcje w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Obszar funkcji | Nazwa&nbsp;funkcji w&nbsp;zarządzaniu&nbsp;funkcjami | Więcej informacji |
|---|---|---|
| Planowanie główne | Dni ujemne dla optymalizacji planowania | Ta funkcja podglądu umożliwia optymalizację planowania, aby uwzględnić tolerancję opóźnienia na podstawie parametru **Liczby dni ujemnych** zdefiniowanych w grupach zapotrzebowania. |
| Planowanie główne | Równoległe autoryzowanie skorygowanej prognozy popytu | Ta funkcja umożliwia równoległe autoryzowanie skorygowanej prognozy popytu ze strony **Skorygowana prognoza popytu**. Celem tej funkcji jest zwiększenie wydajności podczas autoryzacji dużej liczby prognoz. Podczas autoryzowania użytkownik może określić **liczbę wątków** w oknie dialogowym autoryzowania. |
| Planowanie główne | (Wersja zapoznawcza) Akceptowanie i konsolidacja, które mogą być przeprowadzane w partiach, dla planowanych zamówień partii masowych i paczkowanych | Ta funkcja umożliwia używanie zadań w partiach do tworzenia i konsolidowania planowanych zamówień masowych i paczkowanych. |
| Kontrola produkcji | Kopiuj ogólne trasy | Ta funkcja rozszerza funkcję kopiowania trasy, umożliwiając użytkownikom kopiowanie tras, które nie są specyficzne dla danego elementu. Umożliwia to systemowi aktualizację wszystkich istotnych informacji (takich jak miejsce, grupa trasowania, wymagania dotyczące zasobów i różne czasy) po użyciu funkcji kopiowania trasy w celu nadpisania trasy, która nie jest jeszcze przypisana do elementu. |
| Kontrola produkcji | Aktualizuj powiązane zapotrzebowania na zasoby w przypadku zmiany operacji marszruty | Ta funkcja umożliwia systemowi aktualizowanie powiązanych zapotrzebowań na zasoby, gdy użytkownik zmieni operację istniejącego etapu marszruty. |
| Zarządzanie informacjami o produktach | Wstępne przetwarzanie raportu BOM, aby zapobiec przekroczeniu limitu czasu | Ta funkcja powoduje wstępne przetworzenie raportu BOM. Pozwoli to uniknąć problemów z upłynięciem limitu czasu w przypadku dużego obciążenia danymi dla raportu. |
| Zaopatrzenie i sourcing | Włącz resetowanie przepływów pracy związanych z zaopatrzeniem | Ta funkcja wersji zapoznawczej umożliwia zresetowanie następujących przepływów pracy do stanu wersja robocza: Zamówienie zakupu, Zmiana dostawcy i Zapotrzebowania zakupu. |
| Zarządzanie transportem | Włącz tworzenie arkusza faktury od dostawcy podczas odrzucania opłaty frachtowej | Gdy ta funkcja jest włączona, odpowiedni arkusz faktur od dostawcy jest tworzony tylko dla przyczyn uzgodnienia, jeśli jest używasz opcji dostawca-płatność. W przeciwnym razie arkusz faktur będzie zawsze tworzony. |
| Zarządzanie magazynem | Weryfikuj szablony wybrane dla zadań uzupełniania zapasów | Ta funkcja pomaga użytkownikom wybrać prawidłowe szablony uzupełniania zapasów podczas konfigurowania zadania uzupełniania zapasów. Uniemożliwia to użytkownikom tworzenie zadania uzupełniania zapasów bez szablonu oraz wybieranie szablonów typu *Popyt grupy*, które nie będą tworzyć żadnej pracy uzupełniania zapasów i przetwarzanie może potrwać dłuższy czas. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Zarządzanie zmianami projektowymi | [Stany cyklu życia produktu i transakcje](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Zarządzanie zapasami | [Dodatek Widoczność magazynu](../inventory/inventory-visibility.md)<br><br>[Omówienie zarządzania jakością i niezgodnością](../inventory/quality-management-processes.md) (plus wszystkie pokrewne tematy dotyczące zarządzania jakością) |
| Zaopatrzenie i sourcing | [Obsługa certyfikacji dostawcy](../../finance/public-sector/manage-vendor-certification.md) |
| Kontrola produkcji | [Stylizacja interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-styles.md) |
| Zarządzanie magazynem | [Przypisanie ikon i tytułów kroków dla aplikacji mobilnej Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Odroczone przetwarzanie ręcznego przesunięcia magazynowego](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.20 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.20 aplikacji Finance and Operations (lipiec 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md). <!-- KFM: Confirm link -->

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.20, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

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
