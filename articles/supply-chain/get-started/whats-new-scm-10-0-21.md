---
title: Wersja zapoznawcza aplikacji Dynamics 365 Supply Chain Management 10.0.21 (październik 2021 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 08/02/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 517411512760374f1d1fd3b8ea3615563c47202c2e847569d00cb17a94657630
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012044"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10021-october-2021"></a>Wersja zapoznawcza aplikacji Dynamics 365 Supply Chain Management 10.0.21 (październik 2021 r.)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.21. Ta wersja ma numer kompilacji 10.0.960 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** sierpień 2021 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** wrzesień 2021 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2021 r.

## <a name="known-deployment-issue"></a>Znany problem z wdrażaniem
Podczas wdrażania wersji 10.0.21 w usłudze IaaS może pojawić się następujące ostrzeżenie dotyczące wdrożenia:

**Kod ostrzeżenia:** 95017

**Komunikat ostrzegawczy:** Wykonanie skryptu [SetupDiagnostics] nie powiodło się dla maszyny wirtualnej

Wdrożenie będzie działać pomimo ostrzeżenia, jednak następujące znane problemy mogą wystąpić w usługach Lifecycle Services (LCS):

-   Na stronie **Monitorowanie środowiska** nie pojawi się link **Wyświetl szczegółowe informacje o wersji**, więc nie będzie można zobaczyć określonych wersji modułów zainstalowanych w danym środowisku. Bez tych danych kolejne poprawki mogą zakończyć się niepowodzeniem, ponieważ proces, który stosuje poprawki, używa tych danych, aby sprawdzić, czy wymagania wstępne wersji modułu są spełnione. Ponieważ nie jest możliwe użycie kompilacji PEAP/wersji zapoznawczej w produkcji lub zastosowanie poprawek, wpływ powinien być minimalny.
-   Karty **Metryki wydajności** i **Analiza indeksów** na stronie **Monitorowanie środowiska** w obszarze SQL Insights nie będą zawierać żadnych danych. Wszystkie inne funkcje **monitorowania środowiska** będą działać zgodnie z oczekiwaniami.
-   Strona **Pełna diagnostyka systemu** nie będzie dostępna. Skojarzone dane o stanie uruchomień modułu zbierającego dane w nocy i problemy wykryte przez jego zasady również nie będą wyświetlane.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać. Niektóre z tych funkcji są nadal w wersji zapoznawczej, a inne mogą być już ogólnie dostępne.

| Obszar funkcji | Funkcja | Więcej informacji |
|---|---|---|
| Zapasy&nbsp;i&nbsp;logistyka | [Dodatek Globalne księgowanie zapasów do aplikacji Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Globalne księgowanie zapasów — strona główna](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Księgowanie korekt dostępnych zapasów za pomocą konfigurowalnych kodów przyczyn połączonych z kontami przeciwstawnymi](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Kody przyczyn zliczania zapasów](../warehousing/reason-codes-for-counting-journals.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Zasady eksportu danych, do których odwołuje się oferta sprzedaży](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Wskaż, czy zmiany danych, do których występuje odwołanie, będą powodować sytuację, w której powiązane oferty sprzedaży (lub wiersze) będą uwzględniane w następnym eksportowaniu przyrostowym. Eksport przyrostowy będzie uruchamiany szybciej, jeśli nie uwzględnisz takich ofert lub wierszy.<br><br>Ta funkcja dodaje ustawienie o nazwie **Pomiń przywoływane dane oferty sprzedaży podczas śledzenia zmian** do strony **Parametry modułu rozrachunków z odbiorcami**. |
| Zapasy&nbsp;i&nbsp;logistyka | [Skanowanie kodów kreskowych w magazynie przy użyciu standardów formatu GS1](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | *Wkrótce*<!-- KFM: Add doc link when ready. --> |
| Zapasy&nbsp;i&nbsp;logistyka | Zapieczętowany przetarg <!-- KFM: Add RP link when available --> | *Wkrótce*<!-- KFM: Add doc link when ready. --> |
| Zapasy&nbsp;i&nbsp;logistyka | [Ulepszenia dotyczące potrąceń i ilości efektywnej w zakresie zarządzania rabatami](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Zarządzanie potrąceniami przy użyciu pulpitu potrącenia](../rebate-management/deduction-workbench.md )<br><br>[Przetwarzanie, przegląd i księgowanie rabatów](../rebate-management/process-review-post.md)<br><br>[Zarządzanie rabatami — umowy](../rebate-management/rebate-management-deals.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Instrukcje kroku aplikacji magazynowej](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | *Wkrótce*<!-- KFM: Add doc link when ready --> |
| Zapasy&nbsp;i&nbsp;logistyka | [Aktualizacje przerw w pracy i śledzenia kosztów z wyładunkiem](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Aktualizuj śledzenie do odłożenia](../landed-cost/update-tracking-putaway.md )<br><br>[Przetwarzanie towarów w transporcie](../landed-cost/in-transit-processing.md) |
| Planowanie główne | [Dni ujemne dla optymalizacji planowania](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolerancja opóźnienia (dni z ujemnym opóźnieniem)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji zawarte w tym wydaniu. Każdy z nich zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej). Aby korzystać z tych funkcji, należy jawnie włączyć te funkcje w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Obszar funkcji | Nazwa&nbsp;funkcji w&nbsp;zarządzaniu&nbsp;funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie kosztami | Szczegóły postępu zamknięcia zapasów | Ta funkcja w wersji zapoznawczej umożliwia szczegółowy widok postępu zamknięcia zapasów. |
| Planowanie główne | (Wersja zapoznawcza) Obsługa MRP opartego na priorytecie dla optymalizacji planowania | Ta funkcja optymalizacji planowania w wersji zapoznawczej umożliwia planowanie główne oparte na priorytecie planowania z punktem ponownego zamawiania. Najważniejsze zmiany obejmują: pole **Priorytet planowania** w wierszach zamówienia sprzedaży, wierszach zamówienia zakupu, prognozie popytu i zamówieniach planowanych; nowa opcja kodu zapotrzebowania; pole **zapotrzebowania na towar** dla punktu ponownego zamówienia; formularze konfiguracji planowania głównego do kontrolowania konfiguracji priorytetu planowania i logika obliczania optymalizacji planowania w celu ustawienia i przestrzegania priorytetu planowania. |
| Zaopatrzenie i sourcing | Zapobieganie nadmiernej konsumpcji rezerwacji środków w budżecie, gdy w przepływie pracy znajduje się wiele zapotrzebowań na zakup | Ta funkcja w wersji zapoznawczej poprawia sprawdzanie błędów podczas przesyłania i zatwierdzania przez użytkowników zapotrzebowania na zakup, które przekraczają pozostałe saldo wiersza rezerwacji budżetu ogólnego. Pomaga to zapobiec nadmiernemu wykorzystaniu rezerwacji budżetu ogólnego, gdy wiele zapotrzebowań na zakup jest w przepływie pracy. |
| Kontrola produkcji | Pokaż pełne numery seryjne, partii i numery identyfikacyjne w interfejsie wykonania hal produkcyjnych | Ta funkcja zapewnia lepsze środowisko wyświetlania list numerów seryjnych, partii i numerów identyfikacyjnych w interfejsie wykonywania dla hali produkcyjnej. Wyświetlanie zmienia się z widoku karty z ograniczoną liczbą znaków do widoku listy, który zapewnia wystarczająco dużo miejsca, aby wyświetlić pełne wartości. Lista umożliwia również wyszukiwanie określonych liczb. |
| Zarządzanie magazynem | Odłączanie pracy odłożonej od powiadomień WPW | Ta funkcja jest wymagana do wysyłania i odbierania powiadomień o wysyłce z wyprzedzeniem (ASN) podczas uruchamiania obciążenia zarządzania magazynem w jednostce skalowania (jako część rozproszonej topologii hybrydowej). Dodaje nową tabelę bazy danych przeznaczoną do przechowywania informacji o pracy odkładania. Wcześniej te informacje były przechowywane w tabelach używanych również dla powiadomień ASN. |
| Zarządzanie magazynem | Umieść jednostki mieszane | Umożliwia systemowi umieszczanie elementów w lokalizacjach, które zawierają jednostki mieszane (takie jak pudełka i skrzynki). Dla każdego wiersza szablonu umieszczania ta funkcja umożliwia wybór, czy wiersz powinien umieścić pozycje w lokalizacjach z jednostkami mieszanymi, czy pojedynczymi. |
| Zarządzanie magazynem | Użyj szybszego interfejsu API do zamykania/ponownego otwierania kontenerów na stacji pakowania | Gdy ta funkcja w wersji zapoznawczej jest włączona, transakcje magazynowe związane z kontenerami są tworzone przy użyciu nowego uproszczonego procesu, który poprawia wydajność zamykania lub ponownego otwierania kontenerów podczas ręcznego przetwarzania stacji pakowania. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Planowanie główne | [Prognoza zapasów](../master-planning/inventory-forecast.md) |
| Planowanie główne | [Parametry nieużywane przez optymalizację planowania](../master-planning/planning-optimization/not-used-parameters.md) |
| Planowanie główne | [Metody uzupełniania zapasów i modyfikacja ilości](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Planowanie główne | [Planowanie z nieskończoną zdolnością produkcyjną](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Planowanie główne | [Wyświetlanie historii planu i dzienników planowania](../master-planning/planning-optimization/plan-history-logs.md) |
| Zarządzanie magazynem | [Strategie pakowania kontenerów](../warehousing/container-packing-strategy-overview.md) |
| Zarządzanie magazynem | [Przykładowe scenariusze inwentaryzacji ciągłej](../warehousing/cycle-counting-scenarios.md) |
| Zarządzanie magazynem | [Importowanie przychodzących wcześniejszych powiadomień o wysyłce za pomocą jednostki danych V2](../warehousing/import-asn-v2-data-entity.md) |
| Zarządzanie magazynem | [Pobranie nadmiarowe dla zamówień sprzedaży i zamówień przeniesienia](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Zarządzanie magazynem | [Planowanie drukowania etykiety grupy czynności podczas grupy czynności](../warehousing/configure-task-based-wave-label-printing.md) |
| Zarządzanie magazynem | [Nowości lub zmiany w aplikacji mobilnej Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.21 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.21 aplikacji Finance and Operations (październik 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.21, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

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
