---
title: Nowości i zmiany w programie Dynamics 365 Supply Chain Management w wersji 10.0.19 (czerwiec 2021)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7c8994a11c9d1d90fd8b66b17900248f941e307b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579791"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Nowości i zmiany w programie Dynamics 365 Supply Chain Management w wersji 10.0.19 (czerwiec 2021)

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.19. Ta wersja ma numer kompilacji 10.0.837 i jest dostępna w następujący sposób:

- **Wersja zapoznawcza wydania:** kwiecień 2021
- **Ogólna dostępność wydania (samoaktualizacja):** czerwiec 2021 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** czerwiec 2021 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie obejmuje następujące nowe funkcje. Kolumna *Funkcja* zawiera łącza do [planu wersji](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), w którym można zobaczyć oficjalne daty wydania poszczególnych funkcji. Kolumna *Więcej informacji* zawiera łącza do większej liczby szczegółów i dokumentacji pokrewnej.

Większość tych funkcji należy włączyć, korzystając z [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), zanim będzie można z nich korzystać.

| Obszar funkcji | Funkcja | Więcej informacji |
|---|---|---|
| Zapasy&nbsp;i&nbsp;logistyka | [Zatwierdzanie i zapisywanie szczegółów banku przesłanych przez dostawcę](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [Obsługa informacji o koncie bankowym dostawcy](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| Zapasy i logistyka | [Optymalizacja eksportu jednostki danych osoby kontaktowej](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | Jeśli ta funkcja jest włączona, zmiany danych, do których występuje odwołanie, nie będą powodować sytuacji, w której powiązane kontakty będą uwzględniane w następnym eksportowaniu przyrostowym. Jeśli ta funkcja jest wyłączona, zmiany danych, do których występuje odwołanie, nie będą powodować sytuacji, w której powiązane kontakty będą uwzględniane w następnym eksportowaniu przyrostowym. |
| Zapasy i logistyka | [Przyrostowe rozszerzenia możliwości wykonywania magazynów za pomocą jednostek skalowania](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Komunikaty procesora komunikatów](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Korekta zapasów w magazynie](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Zapasy i logistyka | [Funkcje wyszukiwania w polach Wstęp do dokumentu i Wnioski dokumentu na stronie Oferta sprzedaży](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Dodana jest funkcja wyszukiwania w polach **Wstęp do dokumentu** i **Wnioski dokumentu** na stronie **Oferta sprzedaży**.<br><br>Ten funkcjonalność jest włączona domyślnie. |
| Zapasy i logistyka | [Wykonywanie magazynu z jednostkami skalowania urządzeń brzegowych na niestandardowym sprzęcie](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Rozmieszczanie jednostek skalowania urządzeń brzegowych na niestandardowym sprzęcie przy użyciu funkcji LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Produkcja | [Wykonywanie produkcji z jednostkami skalowania urządzeń brzegowych na niestandardowym sprzęcie](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Rozmieszczanie jednostek skalowania urządzeń brzegowych na niestandardowym sprzęcie przy użyciu funkcji LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planowanie | Ustalanie zamówienia planowanego oparte na zapytaniu | [Zaakceptuj zamówienia planowane](../master-planning/planning-optimization/planned-order-firming.md) |
| Zarządzanie informacjami o produktach | [Ulepszenia strony sugestii dotyczących wariantów](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Tworzenie wstępnie zdefiniowanych wariantów produktu](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji zawarte w tym wydaniu. Każdy z nich zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej). Aby korzystać z tych funkcji, należy jawnie włączyć te funkcje w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Obszar funkcji | Nazwa&nbsp;funkcji w&nbsp;zarządzaniu&nbsp;funkcjami | Więcej informacji |
|---|---|---|
| Sprzedaż i marketing | Poprawa wydajności czyszczenia historii sprzedaży | Czyszczenie historii sprzedaży może trwać długo, jeśli jest wykonywane rzadko w środowiskach z dużą ilością aktualizacji sprzedaży. Aby skrócić czas trwania i poprawić niezawodność, funkcja ta dzieli czyszczenie na partie, które działają przez określony czas. Tam, gdzie to możliwe, zostaną wykorzystane możliwości bazy danych, aby zminimalizować blokowanie i uniknąć łączenia tabel transakcyjnych podczas czyszczenia. |
| Sprzedaż i marketing | Aktualizuj żądaną datę odbioru na datę potwierdzoną dla zamówień międzyfirmowych | Ta funkcja pozwala kontrolować, co stanie się z wartościami pól daty sprzedaży i zakupu podczas korzystania z bezpośredniej dostawy między firmami. Możesz wybrać, czy system będzie aktualizował żądane daty, czy też pominie ich aktualizację. Jeśli pominiesz aktualizację, żądane daty będą odpowiadały temu, czego zażądał klient. Jeżeli włączysz aktualizację, to żądane daty (przy zastosowaniu sterowania datą dostawy) tylko początkowo będą odpowiadać temu, czego zażądał klient. Kontrola daty dostawy (jeśli jest inna niż *Brak*) spowoduje ponowne przeliczenie pierwotnie żądanych danych. Tę opcję można ustawić za pomocą nowego ustawienia **Aktualizuj żądaną datę przyjęcia z datą potwierdzoną** w ustawieniach dostawcy lub odbiorcy międzyfirmowego.<br><br>Jeśli funkcja jest wyłączona, system nadpisze żądaną datę odbioru na oryginalnych zamówieniach sprzedaży w oparciu o regułę kontroli daty dostawy, ale żądana data wysyłki pozostanie bez zmian. |
| Zarządzanie magazynem | Zaokrąglij ilości w dół do najbliższej jednostki sprzedaży podczas zwalniania do magazynu | Ta funkcja dodaje opcję, która może ograniczyć ilość zamówień w momencie wydania do magazynu. Po włączeniu tej opcji ilości zamówień będą zaokrąglane w dół do najbliższej pełnej jednostki sprzedaży, a zamówienia zawierające ilości mniejsze niż jedna jednostka sprzedaży będą odrzucane do wydania. |
| Zarządzanie magazynem | Metoda grupy czynności „Planuj tworzenie pracy” w całej organizacji | Po włączeniu tej funkcji, metoda grupy *Tworzenie harmonogramu pracy* zostanie skonfigurowana tak, aby działała równolegle we wszystkich podmiotach prawnych. Wpłynie to również na kilka dodatkowych ustawień. Aby uzyskać szczegółowe informacje, zobacz temat [Planowanie tworzenia pracy podczas obsługi grupy czynności](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy pomocy. Nie zawsze są one związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji, ale mogą ułatwić efektywniejsze korzystanie z istniejących funkcji.

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Zarządzanie zmianami projektowymi | [Zarządzanie zmianami projektowymi — FAQ](../engineering-change-management/change-management-faq.md) |
| Zaopatrzenie i sourcing | [Wnioski o nadanie kategorii od dostawców](../procurement/category-requests-from-vendors.md) |
| Zarządzanie informacjami o produktach | [Zarządzanie jednostką miary](../pim/tasks/manage-unit-measure.md)<br><br>[Obliczenia na potrzeby modelu konfiguracji produktu](../pim/config-model-calculations.md) |
| Kontrola produkcji | [Zunifikowana sekwencja numerów dla identyfikatorów zadań](../production-control/unified-job-ids.md) |
| Zarządzanie transportem | [Klasy LTL](../transportation/ltl-class.md)<br><br>[Kody NMFC](../transportation/nmfc-codes.md) |
| Zarządzanie magazynem, tworzenie i przetwarzanie grupy czynności | [Tworzenie i przetwarzanie grupy czynności](../warehousing/wave-processing.md)<br><br>[Parametry magazynu dla przetwarzania grupy czynności](../warehousing/wave-warehouse-parameters.md)<br><br>[Szablony grupy czynności](../warehousing/wave-templates.md)<br><br>[Alokacja grupy czynności](../warehousing/wave-allocation-method.md)<br><br>[Tworzenie planu pracy podczas grupy czynności](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Konteneryzacja](../warehousing/wave-containerization.md)<br><br>[Powiadomienia dotyczące wykonania grupy czynności](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja platformy dla aplikacji Finance and Operations

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.19 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.19 aplikacji Finance and Operations (czerwiec 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

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
