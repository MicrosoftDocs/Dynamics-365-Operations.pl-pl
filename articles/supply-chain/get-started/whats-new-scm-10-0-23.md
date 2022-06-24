---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management w wersji 10.0.23 (styczeń 2022 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: acffe97cf1844f16a70c716a7f2078b1e9a072d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849482"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management w wersji 10.0.23 (styczeń 2022 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.23. Ta wersja ma numer kompilacji 10.0.1037 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** Październik 2021
- **Ogólna dostępność wydania (Samoaktualizacja):** Grudzień 2021
- **Ogólna dostępność wydania (Samoaktualizacja):** Styczeń 2022

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej. Aby określić sposób włączania funkcji, zobacz kolumnę *Włączane przez*. Aby uzyskać więcej informacji o zarządzaniu funkcjami, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Firma Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał funkcje wprowadzone do kompilacji po początkowym opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Globalna książka adresowa | Zdefiniuj domyślny stan/województwo dla każdego kraju/regionu w konfiguracji adresu | Można teraz zdefiniować domyślny stan/prowincję dla każdego kraju/regionu w ustawieniach adresu dla globalnej książki adresowej. Gdy ustawiony jest domyślny stan/prowincja, będzie to domyślna wartość wprowadzona w polach stanu/prowincji podczas tworzenia nowego rekordu hrabstwa lub miasta dla tego kraju/regionu. Zobacz też [Ustawienia adresu](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Domyślnie włączone. |
| Zapasy&nbsp;i&nbsp;logistyka | [Wstrzymywanie zadań w aplikacji mobilnej Warehouse Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Konfiguracja obejść dla kroków w elementach menu urządzeń mobilnych](../warehousing/warehouse-app-detours.md) | Zarządzanie funkcjami (*Obejścia: Aplikacja do zarządzania magazynem*) |
| Zapasy&nbsp;i&nbsp;logistyka | [Promowane pola aplikacji magazynowej](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Skonfiguruj promowane pola dla kroków w urządzeniu mobilnym](../warehousing/warehouse-app-promoted-fields.md)| Zarządzanie funkcjami (*Pola promowane w aplikacji magazynowej*) |
| Produkcja | [Integracja systemów realizacji produkcji](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Integracja z systemami wykonywania produkcji innych firm](../production-control/mes-integration.md) | Nazwa funkcji: (*integracja systemu w systemie realizacji produkcji*) |
| Produkcja | [Raport dotyczący produktów towarzyszących i ubocznych z interfejsu wykonania hal produkcyjnych](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-use.md) | Zarządzanie funkcjami (*Raport dotyczący produktów towarzyszących i ubocznych z interfejsu wykonania hal produkcyjnych*) |
| Planowanie | [Wsparcie optymalizacji planowania dla planowania opartego na priorytetach](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Planowanie oparte na priorytecie](../master-planning/planning-optimization/priority-based-planning.md) | Nazwa funkcji: (*Obsługa MRP opartego na priorytecie dla optymalizacji planowania*) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są nowe w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Jeśli chcesz włączyć lub wyłączyć którąkolwiek z tych funkcji, musisz to zrobić w menu [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), gdzie są one wymienione przy użyciu nazw pokazanych w kolumnie *Nazwa funkcji w menu zarządzania funkcjami* w poniższej tabeli.

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie składnikami majątku | Konta przeciwstawne dla wydatków w arkuszach zlecenia pracy | Ta funkcja umożliwia określenie konta kompensacyjnego dla każdego wydatku wymienionego w dzienniku zlecenia pracy. Zazwyczaj z każdym wydatkiem można powiązać konto sprzedawcy, ale obsługiwane są również inne typy kont. Dodaje dwie nowe kolumny (**Typ konta rozliczeniowego** i **Konto rozliczeniowe**) do skróconej karty **Koszty** na stronie **Dziennika zleceń roboczych**.|
| Zarządzanie kosztami | Utwórz powiązane załączniki dla przeszacowań zaokrąglania kosztu standardowego | <p>W przypadku księgowania finansowego zapasów (np. faktury zamówienia sprzedaży lub transakcji magazynowej) ta funkcja powoduje, że system tworzy oddzielny załącznik dla dowolnych powiązanych przeszacowań zaokrąglania kosztów standardowych i dołącza go do finansowego załącznika księgowania jako powiązany załącznik.</p><p>Bez tej funkcji system rejestruje standardowe przeszacowania zaokrąglania kosztów na tym samym księgowaniu załącznika. Takie zachowanie może czasem powodować konflikt z informacjami o datach, ponieważ w przeszacowaniach jest używana daty sesji lub systemowa, podczas gdy w księgowaniach finansowych jest używana data księgowania.</p> |
| Zarządzanie zapasami i magazynem | \[Rosja\] Księgowanie finansowych transakcji magazynowych Storno zgodnie z flagą korekty w załączniku finansowym dla zamówień sprzedaży | Ta funkcja ma wpływ na funkcjonalność korekt not kredytowych w Rosji. Umożliwia księgowanie transakcji inwentaryzacyjnych do faktur sprzedaży zgodnie z opcją korekty w księdze głównej. Po włączeniu tej funkcji nie ma już rozbieżności pomiędzy znacznikiem **Korekta** na kwicie finansowym transakcji inwentaryzacyjnej a znacznikiem **Storno** na transakcjach inwentaryzacyjnych. |
| Zarządzanie zapasami i magazynem | (Rosja) Uruchom obliczanie raportu obrotów salda zapasów w partii | Dla rosyjskich lokalizacji Supply Chain Management ta funkcja umożliwia uruchomienie raportu *obrotów salda zapasów w partii*, jego przechowywanie i przeglądanie raportów wygenerowanych wcześniej. |
| Zarządzanie zapasami i magazynem | (Rosja) W zarządzaniu zapasami używaj tłumaczeń na język lokalny w specyficznych dla kraju lub regionu formularzach podstawowych | Dla rosyjskich lokalizacji Supply Chain Management funkcja ta umożliwia używanie rosyjskich tłumaczeń nazw produktów/pozycji i jednostek miary na następujących wydrukach zapasów specyficznych dla Rosji:Lista zliczania (INV-3), Lista zliczania (INV-5), Lista zliczania (INV-6). |
| Planowanie główne | Usługa Azure Machine Learning Service do prognozowania popytu | Ta funkcja umożliwia usłudze Azure Machine Learning Service generowanie prognoz popytu na podstawie danych historycznych. Aby uzyskać więcej informacji, zobacz [Konfigurowanie prognozowania popytu](../master-planning/demand-forecasting-setup.md). |
| Zaopatrzenie i sourcing | Wyczyść historię aktualizacji zamówień zakupu | Ta funkcja pozwala na wyczyszczenie tymczasowych zapisów historycznych związanych z aktualizacjami zamówień zakupu. Dodaje nowy przycisk o nazwie **Wyczyść historię aktualizacji zakupu** do panelu akcji na stronie **Wszystkie zamówienia zakupu**. Ten funkcjonalność jest włączona domyślnie. |
| Kontrola produkcji | (Wersja zapoznawcza) Automatyczne pobieranie materiałów z obsługą magazynu dla automatycznie księgowanych list pobrania | Funkcja ta pozwala na automatyczne wybieranie i rozwiązywanie wymiarów inwentaryzacji dla automatycznie wysyłanych, pochodnych i wstecznie przepłukiwanych dzienników listy kompletacji. |
| Kontrola produkcji | Weryfikacja ważności surowców w stosunku do planowanej daty zużycia | Ta funkcja zmienia sposób walidacji dat ważności partii podczas rezerwowania partii surowca do wykorzystania podczas produkcji. Gdy ta funkcja jest włączona, data ważności partii jest sprawdzana względem planowanej daty zużycia (daty surowca), ustalonej w linii BOM produkcji lub linii formuły zamówienia partii. Gdy ta funkcja jest wyłączona, data ważności partii jest weryfikowana względem planowanej daty dostawy zlecenia produkcyjnego lub partyjnego (jak poprzednio). |
| Sprzedaż i marketing | Oczyszczanie historii aktualizacji sprzedaży na podstawie wieku | Ta funkcja umożliwia ustawienie maksymalnego wieku rekordów, które mają być zachować podczas uruchamiania zadania okresowego **czyszczenia historii aktualizacji sprzedaży**. Starsze rekordy zostaną usunięte. Jest to przydatne w przypadku okresowego uruchamiania zadania, ponieważ wiek jest zawsze obliczany w odniesieniu do daty uruchomienia zadania. Bez tej funkcji można ustawić tylko określoną datę dla najstarszych rekordów do zachowania. Aby uzyskać więcej informacji, zobacz [Zaplanuj czyszczenie danych historii sprzedaży](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Sprzedaż i marketing | Popraw wydajność raportu „100 najlepszych” odbiorców | Ta funkcja poprawia wydajność raportu **Top 100** klientów poprzez uruchamianie raportu zawsze dla wszystkich klientów (co jest jego przeznaczeniem), a nie poprzez umożliwienie zapytań niestandardowych. Gdy ta funkcja jest włączona, wszystkie ustawienia **Rekordy powinny zawierać** są wyłączone w oknie dialogowym raportu **Top 100**. |
| Zarządzanie magazynem | Obsługa jednostki skalowania do zwalniania do magazynu zamówień wychodzących | Gdy ta funkcja jest włączona, zamówienia wychodzące mogą być zwalniane z hubu bezpośrednio do jednostki wagowej, gdzie będą realizowane. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły pomocy. Te artykuły nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Zarządzanie zmianami projektowymi | [Atrybuty inżynierii i wyszukiwanie atrybutów inżynierskich](../engineering-change-management/engineering-attributes-and-search.md) opisuje teraz jak działa dziedziczenie atrybutów inżynierskich. |
| Planowanie główne | [Planowanie główne z prognozami zapotrzebowania](../master-planning/planning-optimization/demand-forecast.md) oraz [Klucze redukcji prognoz](../master-planning/reduction-keys.md) zawierają teraz więcej informacji na temat pracy z kluczami redukcji. |
| Planowanie główne | [Bezpieczne uzupełnianie zapasów dla elementów](../master-planning/safety-stock-replenishment.md) zawiera teraz więcej informacji na temat używania kluczy minimum/maksimum. |
| Planowanie główne | [Prognozy zapasów](../master-planning/inventory-forecast.md) zawierają więcej informacji na temat alokowania prognoz. |
| Planowanie główne | [Harmonogram dostaw](../master-planning/supply-schedule.md) |
| Zarządzanie magazynem | [Globalne parametry urządzenia przenośnego](../warehousing/mobile-device-parameters.md) |
| Zarządzanie magazynem | [Kotwiczenie](../warehousing/anchoring.md) |
| Sprzedaż i marketing | Handel między przedsiębiorstwami jest teraz szczegółowo opisany, począwszy od [Konfiguracja handlu między przedsiębiorstwami](../sales-marketing/intercompany-trade-set-up.md) i powiązanych artykułów. |
| Sprzedaż i marketing | [Ulepszenia wydajności oczyszczania historii sprzedaży](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Zarządzanie zapasami | Dokumentacja dotycząca widoczności zapasów została rozszerzona i zaktualizowana, począwszy od [Przegląd dodatku Widoczność zapasów](../inventory/inventory-visibility.md) i powiązanych artykułów. |
| Zarządzanie magazynem | [Konta użytkownika urządzenia przenośnego](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.23 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.23 aplikacji Finanse i Operacje (listopad 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.23, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

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
