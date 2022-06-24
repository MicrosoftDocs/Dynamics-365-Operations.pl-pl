---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management (10.0.21 październik 2021 r.)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a78b4c37bfca9fedbd46cd8a16b47bd4444fbfee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849540"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management (10.0.21 październik 2021 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.21. Ta wersja ma numer kompilacji 10.0.960 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** sierpień 2021 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** wrzesień 2021 r.
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2021 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać.

| Obszar funkcji | Funkcja | Więcej informacji |
|---|---|---|
| Zapasy&nbsp;i&nbsp;logistyka | [Dodatek Globalne księgowanie zapasów do aplikacji Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Globalne księgowanie zapasów — strona główna](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Księgowanie korekt dostępnych zapasów za pomocą konfigurowalnych kodów przyczyn połączonych z kontami przeciwstawnymi](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Kody przyczyn zliczania zapasów](../warehousing/reason-codes-for-counting-journals.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Zasady eksportu danych, do których odwołuje się oferta sprzedaży](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Wskaż, czy zmiany danych, do których występuje odwołanie, będą powodować sytuację, w której powiązane oferty sprzedaży (lub wiersze) będą uwzględniane w następnym eksportowaniu przyrostowym. Eksport przyrostowy będzie uruchamiany szybciej, jeśli nie uwzględnisz takich ofert lub wierszy.<br><br>Ta funkcja dodaje ustawienie o nazwie **Pomiń przywoływane dane oferty sprzedaży podczas śledzenia zmian** do strony **Parametry modułu rozrachunków z odbiorcami**. |
| Zapasy&nbsp;i&nbsp;logistyka | [Zapieczętowany przetarg](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [Oferty zapieczętowane na potrzeby ZO](../procurement/sealed-bidding.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Rezerwacja wstępna dla dodatku Widoczność magazynu](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Rezerwacje dodatku Widoczność magazynu](../inventory/inventory-visibility-reservations.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Ulepszenia dotyczące potrąceń i ilości efektywnej w zakresie zarządzania rabatami](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Zarządzanie potrąceniami przy użyciu pulpitu potrącenia](../rebate-management/deduction-workbench.md )<br><br>[Przetwarzanie, przegląd i księgowanie rabatów](../rebate-management/process-review-post.md)<br><br>[Zarządzanie rabatami — umowy](../rebate-management/rebate-management-deals.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Instrukcje kroku aplikacji magazynowej](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Dostosowywanie tytułów kroków i instrukcji dla aplikacji mobilnej Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Zapasy&nbsp;i&nbsp;logistyka | [Aktualizacje przerw w pracy i śledzenia kosztów z wyładunkiem](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Aktualizuj śledzenie do odłożenia](../landed-cost/update-tracking-putaway.md )<br><br>[Przetwarzanie towarów w transporcie](../landed-cost/in-transit-processing.md) |
| Planowanie główne | [Dni ujemne dla optymalizacji planowania](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolerancja opóźnienia (dni z ujemnym opóźnieniem)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji zawarte w tym wydaniu. Każdy z nich zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej). Aby korzystać z tych funkcji, należy jawnie włączyć te funkcje w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa&nbsp;funkcji w&nbsp;zarządzaniu&nbsp;funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie kosztami | Szczegóły postępu zamknięcia zapasów | Ta funkcja w wersji zapoznawczej umożliwia szczegółowy widok postępu zamknięcia zapasów. |
| Zaopatrzenie i sourcing | Zapobieganie nadmiernej konsumpcji rezerwacji środków w budżecie, gdy w przepływie pracy znajduje się wiele zapotrzebowań na zakup | Ta funkcja w wersji zapoznawczej poprawia sprawdzanie błędów podczas przesyłania i zatwierdzania przez użytkowników zapotrzebowania na zakup, które przekraczają pozostałe saldo wiersza rezerwacji budżetu ogólnego. Pomaga to zapobiec nadmiernemu wykorzystaniu rezerwacji budżetu ogólnego, gdy wiele zapotrzebowań na zakup jest w przepływie pracy. |
| Kontrola produkcji | Pokaż pełne numery seryjne, partii i numery identyfikacyjne w interfejsie wykonania hal produkcyjnych | Ta funkcja zapewnia lepsze środowisko wyświetlania list numerów seryjnych, partii i numerów identyfikacyjnych w interfejsie wykonywania dla hali produkcyjnej. Wyświetlanie zmienia się z widoku karty z ograniczoną liczbą znaków do widoku listy, który zapewnia wystarczająco dużo miejsca, aby wyświetlić pełne wartości. Lista umożliwia również wyszukiwanie określonych liczb. |
| Sprzedaż i marketing | Ograniczenie liczby zamówień sprzedaży, które można wybierać do księgowania | Ta funkcja umożliwia zdefiniowanie maksymalnej liczby zamówień sprzedaży, które można wybrać podczas księgowania potwierdzeń, list pobrania, dokumentów dostawy i faktur z strony listy zamówień sprzedaży. Jest włączane automatycznie. Ta funkcja dodaje ustawienie o nazwie **Maksymalna liczba zamówień sprzedaży do zaksięgowania** do strony **Parametry rozrachunków z odbiorcami**. Nowe ustawienie domyślnie ma wartość *100*. Ta funkcja pomaga zwiększyć wydajność strony listy zamówień sprzedaży po wybraniu znaczącej liczby zamówień sprzedaży. Nie ma to wpływu na liczbę zamówień sprzedaży, które mogą być przetwarzane przez zadanie okresowe. |
| Zarządzanie magazynem | Odłączanie pracy odłożonej od powiadomień WPW | Ta funkcja jest wymagana do wysyłania i odbierania powiadomień o wysyłce z wyprzedzeniem (ASN) podczas uruchamiania obciążenia zarządzania magazynem w jednostce skalowania (jako część rozproszonej topologii hybrydowej). Dodaje nową tabelę bazy danych przeznaczoną do przechowywania informacji o pracy odkładania. Wcześniej te informacje były przechowywane w tabelach używanych również dla powiadomień ASN. |
| Zarządzanie magazynem | Umieść jednostki mieszane | Umożliwia systemowi umieszczanie elementów w lokalizacjach, które zawierają jednostki mieszane (takie jak pudełka i skrzynki). Dla każdego wiersza szablonu umieszczania ta funkcja umożliwia wybór, czy wiersz powinien umieścić pozycje w lokalizacjach z jednostkami mieszanymi, czy pojedynczymi. |
| Zarządzanie magazynem | Użyj szybszego interfejsu API do zamykania/ponownego otwierania kontenerów na stacji pakowania | Gdy ta funkcja w wersji zapoznawczej jest włączona, transakcje magazynowe związane z kontenerami są tworzone przy użyciu nowego uproszczonego procesu, który poprawia wydajność zamykania lub ponownego otwierania kontenerów podczas ręcznego przetwarzania stacji pakowania. |

## <a name="features-turned-on-by-default-in-this-release"></a>Funkcje włączone domyślnie w tej wersji

Poniższa tabela zawiera listę funkcji, które są domyślnie włączone w wersji 10.0.21. Większość funkcji, które zostały włączone, można wyłączyć w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Nazwa funkcji | Włącz dane | Funkcja dodana | Stan funkcji | Moduł |
| :--- | :--- | :--- | :--- | :--- |
| Magazyn raportu dostępnych zapasów | 1/9/2021 | 1/4/2020 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Anulowanie zamówienia przeniesienia | 1/9/2021 | 13/7/2020 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Odblokuj arkusz zapasów | 1/9/2021 | 17/8/2020 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Zapisane widoki dla zarządzania zapasami | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Nawigacja do wersji listy składowej (BOM) z wierszy listy składowej (BOM) | 1/9/2021 | 11/11/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Użycie jednostki miary i ilości jednostkowej w arkuszach magazynowych | 1/9/2021 | 11/11/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Zezwalaj na puste wartości atrybutów partii | 1/9/2021 | 11/11/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Automatyczne zwiększanie numerów wierszy zamówienia przeniesienia zapasów | 1/9/2021 | 11/10/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Przepływ pracy zatwierdzania arkusza magazynowego | 1/9/2021 | 6/1/2020 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Włącz funkcję ostrzegania o parametrach zarządzania jakością zapasów | 1/9/2021 | 7/10/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Utwórz zamówienie przeniesienia z wiersza sprzedaży | 1/9/2021 | 31/8/2019 | Domyślnie włączona | Zarządzanie zapasami i magazynem |
| Wybór modelu prognozy w szczegółach prognozy popytu | 1/9/2021 | 11/10/2019 | Domyślnie włączona | Planowanie główne |
| Wizualizacja postępu planowania głównego | 1/9/2021 | 7/10/2019 | Domyślnie włączona | Planowanie główne |
| Automatyczne akceptowanie w module Optymalizacja planowania | 1/9/2021 | 11/10/2019 | Domyślnie włączona | Planowanie główne |
| Równoległa akceptacja zamówień planowanych | 1/9/2021 | 31/8/2019 | Domyślnie włączona | Planowanie główne |
| Komunikat o pomyślnym wysłaniu oferty | 1/9/2021 | 15/5/2019 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Odnośnik odwołania do ZO dodany do zamówienia zakupu | 1/9/2021 | 31/8/2019 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Możliwość zbiorczego potwierdzania zaakceptowanych zamówień zakupu z portalu współpracy z dostawcami | 1/9/2021 | 10/9/2019 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Udoskonalenia cXML dotyczące zakupów | 1/9/2021 | 11/11/2019 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Wyświetl link &quot;Otwórz opublikowane zapytania ofertowe&quot; jako kafelek | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Pytania i odpowiedzi dotyczące ZO | 1/9/2021 | 19/2/2020 | Domyślnie włączona | Zaopatrzenie i sourcing |
| Informacje o produkcie i dokumentacja wysyłki dla materiałów niebezpiecznych | 1/9/2021 | 14/6/2020 | Domyślnie włączona | Zarządzanie informacjami o produktach |
| Ścisła weryfikacja w domyślnych ilościach zamówienia | 1/9/2021 | 24/6/2020 | Domyślnie włączona | Zarządzanie informacjami o produktach |
| Funkcja zarządzania krajem pochodzenia | 1/9/2021 | 13/7/2020 | Domyślnie włączona | Zarządzanie informacjami o produktach |
| Zapisane widoki zwolnionych produktów | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Zarządzanie informacjami o produktach |
| Ulepszenia w oknach dialogowych Zadania zatwierdzania i Zadania przenoszenia | 1/9/2021 | 11/10/2019 | Domyślnie włączona | Kontrola produkcji |
| Numer identyfikacyjny do zgłoszenia wyrobów gotowych został dodany do urządzenia karty zadań | 1/9/2021 | 31/8/2019 | Domyślnie włączona | Kontrola produkcji |
| Do strony Terminal kart zadań dodany został nowy przycisk Zatrzymaj przerwę | 1/9/2021 | 19/2/2020 | Domyślnie włączona | Kontrola produkcji |
| Włącz częściowe przyjęcie pozycji podwykonawczych i rozwiąż problem z obliczaniem odpadków dla wierszy listy składowej (BOM) typu Dostawca. | 1/9/2021 | 11/11/2019 | Domyślnie włączona | Kontrola produkcji |
| Zapisane widoki kontroli produkcji | 1/9/2021 | 17/8/2020 | Domyślnie włączona | Kontrola produkcji |
| Dynamics 365 Guides dla produkcji | 1/9/2021 | 13/7/2020 | Domyślnie włączona | Kontrola produkcji |
| Wykonanie hali produkcyjnej | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Kontrola produkcji |
| Funkcja umożliwiająca blokowanie urządzenie karty zadań i terminalu karty zadań w celu ich wyczyszczenia | 1/9/2021 | 10/5/2020 | Domyślnie włączona | Kontrola produkcji |
| Alokacja opłat do zamówienia sprzedaży | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Sprzedaż i marketing |
| Ograniczenie liczby zamówień sprzedaży, które można wybierać do księgowania | 1/9/2021 | 1/9/2021 | Domyślnie włączona | Sprzedaż i marketing |
| Wyczyść historię aktualizacji zamówień sprzedaży | 1/9/2021 | 1/9/2021 | Domyślnie włączona | Sprzedaż i marketing |
| Zmień numerację dla pracy inwentaryzacji ciągłej | 1/9/2021 | 7/10/2019 | Domyślnie włączona | Zarządzanie magazynem |
| Zadaniowe uzupełnianie zapasów dla popytu grupy czynności | 1/9/2021 | 7/10/2019 | Wymagana | Zarządzanie magazynem |
| Ukryj pole Wartość całkowita na stronach &quot;Wszystkie ładunki&quot; i &quot;Szczegóły ładunku&quot; | 1/9/2021 | 7/10/2019 | Domyślnie włączona | Zarządzanie magazynem |
| Drukowanie etykiety grupy czynności | 1/9/2021 | 19/2/2020 | Wymagana | Zarządzanie magazynem |
| Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem | 1/9/2021 | 6/1/2020 | Wymagana | Zarządzanie magazynem |
| Rozszerzone układy etykiet numerów identyfikacyjnych | 1/9/2021 | 19/2/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Blokowanie pracy na poziomie organizacji | 1/9/2021 | 19/2/2020 | Wymagana | Zarządzanie magazynem |
| Szczegóły wiersza pracy | 1/9/2021 | 11/10/2019 | Domyślnie włączona | Zarządzanie magazynem |
| Umożliwia edytowanie pola stanu zapasów dla przeniesienia magazynowego urządzeń przenośnych | 1/9/2021 | 16/10/2019 | Domyślnie włączona | Zarządzanie magazynem |
| Potwierdź wychodzące wysyłki z zadań wsadowych | 1/9/2021 | 13/7/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Określ, czy wyświetlać stronę podsumowania odbierania na urządzeniach przenośnych | 1/9/2021 | 1/4/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Monituj o rozwiązanie niejednoznacznych nazw typu &#39;Lokalizacja/numer &#39; identyfikacyjny | 1/9/2021 | 1/4/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Przechwytywanie wariantów produktu i wymiarów śledzenia w aplikacji magazynowej podczas przyjmowania pozycji ładunku | 1/9/2021 | 10/5/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Nie zezwalaj na tworzenie ładunków, które nie spełniają wymagań szablonu kompilowania ładunku grupy czynności. | 1/9/2021 | 17/8/2020 | Domyślnie włączona | Zarządzanie magazynem |
| Ocenianie wszystkich akcji dla dyrektyw lokalizacji wielu jednostek SKU | 1/9/2021 | 9/30/2020 | Domyślnie włączona | Zarządzanie magazynem |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Planowanie główne | [Prognoza zapasów](../master-planning/inventory-forecast.md) |
| Planowanie główne | [Parametry nieużywane przez optymalizację planowania](../master-planning/planning-optimization/not-used-parameters.md) |
| Planowanie główne | [Metody uzupełniania zapasów i modyfikacja ilości](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Planowanie główne | [Planowanie z nieskończoną zdolnością produkcyjną](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Planowanie główne | [Wyświetlanie historii planu i dzienników planowania](../master-planning/planning-optimization/plan-history-logs.md) |
| Zarządzanie magazynem | [Strategie pakowania kontenerów](../warehousing/container-packing-strategy-overview.md) |
| Zarządzanie magazynem | [Przykładowe scenariusze inwentaryzacji ciągłej](../warehousing/cycle-counting-scenarios.md) |
| Zarządzanie magazynem | [Importowanie przychodzących wcześniejszych powiadomień o wysyłce za pomocą jednostki danych V3](../warehousing/import-asn-data-entity.md) |
| Zarządzanie magazynem | [Pobranie nadmiarowe dla zamówień sprzedaży i zamówień przeniesienia](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Zarządzanie magazynem | [Planowanie drukowania etykiety grupy czynności podczas grupy czynności](../warehousing/configure-task-based-wave-label-printing.md) |
| Zarządzanie magazynem | [Nowości lub zmiany w aplikacji mobilnej Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.21 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.21 aplikacji Finanse i Działania (październik 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.21, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

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
