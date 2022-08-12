---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.28 (sierpień 2022 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 7e17127ff6ef6c52034b8aa5e0c8404772363ca9
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186528"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10028-august-2022"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.28 (sierpień 2022 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.28. Ta wersja ma numer kompilacji 10.0.1264 i jest dostępna w następującym harmonogramie:

- **Wersja podglądu:** maj 2022
- **Ogólna dostępność wydania (samoaktualizacja):** lipiec 2022 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** lipiec 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Zapasy i logistyka | [Podmioty integrujące koszty lądowe dla zewnętrznych spedytorów](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Przegląd podmiotów ponoszących koszty lądowe](../landed-cost/landed-cost-entities-overview.md) | Domyślnie włączone |
| Planowanie | [Planowanie zapotrzebowania materiałowego sterowane popytem (Demand Driven Material Requirements Planning - DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | [Planowanie zapotrzebowania materiałowego sterowane popytem – omówienie](../master-planning/planning-optimization/ddmrp-overview.md) | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) DDMRP dla optymalizacji planowania* |
| Planowanie | [Optymalizacja planowania Wsparcie dla zdolności do osiągnięcia celu (CTP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capable-to-promise-ctp) | Wkrótce | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) CTP dla optymalizacji planowania* |
| Planowanie | [Wsparcie optymalizacji planowania dla okresu trwałości](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Wkrótce | Domyślnie włączone |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Zarządzanie zapasami i magazynem | Włącz międzyfirmowy stan dostępnych zapasów, aby wyświetlać tylko ilość dostępnych zapasów inną niż zero | Dzięki tej funkcji możesz zdecydować, czy pozycje z zerową ilością na stanie powinny być uwzględniane na liście stanów magazynowych w rozliczeniach między spółkami. Możesz kontrolować tę opcję za pomocą ustawienia **Nie pokazuj pozycji z zerową ilością w obrocie na międzyfirmowej liście w obrocie**, które ta funkcja dodaje do strony **Parametry inwentaryzacji i gospodarki magazynowej**. |
| Zarządzanie zapasami i magazynem | (Indie) W przypadku reguł ceny przeniesienia ignoruj lokalizację, gdy ustawienie „Z kodu magazynu” ma wartość „Wszystko” | <p>Ta cecha dotyczy tylko lokalizacji Indie. Dzięki temu proces ustalania cen transferowych dla pozycji w transferach magazynowych jest bardziej intuicyjny.</p><p>Ceny transferowe ustalasz, konfigurując dla każdej pozycji reguły cen transferowych. Jednym ze sposobów na taką konfigurację jest dołączenie linii reguły, w której pole **Kod magazynu** jest ustawione na *Wszystkie*. To ustawienie wskazuje, że cena transferowa określona przez linię powinna obowiązywać niezależnie od magazynu, z którego pobierany jest dany artykuł. Gdy ta funkcja jest włączona, reguły cen transferowych, w których pole **Kod magazynu** jest ustawione na *Wszystkie*, będą ignorować ustawienie **Lokalizacja**. Dlatego reguła ta będzie obowiązywać niezależnie od lokalizacji podanej w poleceniu przelewu. Takie zachowanie jest prawdopodobnie oczekiwane, ponieważ lokalizacja znajduje się poniżej magazynu w hierarchii wymiarów magazynowych.</p><p>Bez tej funkcji system zastosuje reguły tego typu tylko wtedy, gdy lokalizacja na zleceniu transferu dokładnie odpowiada lokalizacji ustawionej dla tej reguły. (Jeśli w regule zostanie ustawiona pusta lokalizacja, system zastosuje tę regułę tylko do zleceń transferu, które również mają pustą wartość dla lokalizacji).</p> |
| Zarządzanie zapasami i magazynem | Czyszczenie danych raportu dostępnych zapasów | Ta funkcja pozwala na oczyszczenie danych używanych do tworzenia raportów *Przechowywanie raportów o stanie zapasów*. |
| Kontrola produkcji | Przypisanie działań projektu do umowy serwisowej i wierszy zlecenia serwisowego | Ta funkcja dodaje pole o nazwie **Działanie projektu** do linii umów serwisowych i zleceń serwisowych, abyś mógł ustawić dla nich działanie projektu. Funkcja ta pomoże uniknąć błędów blokowania, kiedy zamieszczasz arkusze projektów zarządzania usługami, które wymagają ustawienia aktywności projektowej.  |
| Zarządzanie magazynem | Ręczna usługa pobierania wierszy przeniesienia dla administratora lub podobnych zaufanych użytkowników | Ta funkcja pozwala administratorom na ręczne wybieranie transakcji inwentaryzacyjnych, które są powiązane z liniami transferowymi. W skład tych linii wchodzą linie, które zostały już wydane do magazynu. Administratorzy powinni wykonywać tę kompletację tylko w wyjątkowych przypadkach, np. gdy system jest w stanie uszkodzonym. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły Pomocy. Te artykuły nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Zarządzanie kosztami | [Odchylenia od ceny ewidencyjnej](../cost-management/fixed-receipt-price.md) |
| Zarządzanie kosztami | [Najczęściej zadawane pytania dotyczące kalkulacji kosztów inwentaryzacji](../cost-management/inventory-costing-faq.md) |
| Zarządzanie kosztami | [Księgowanie na koncie obciążeniowym zasada księgowania](../cost-management/post-to-charge-account-accounting-principle.md) |
| Zarządzanie zapasami | [Szczegóły transakcji inwentaryzacyjnej](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji finansowych i operacyjnych

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.28 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.28 aplikacji finansowych i operacyjnych (czerwiec 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.28, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.](/dynamics365-release-plan/2022wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W artykule [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

