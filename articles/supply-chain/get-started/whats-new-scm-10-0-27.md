---
title: Wersja zapoznawcza Dynamics 365 Supply Chain Management w wersji 10.0.27 (lipiec 2022)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e8ec20c361f76a6012a7c8e1f03296007f5a05aa
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645352"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10027-july-2022"></a>Wersja zapoznawcza Dynamics 365 Supply Chain Management w wersji 10.0.27 (lipiec 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji zapoznawczej 10.0.27. Ta wersja ma numer kompilacji 10.0.1227 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza wydania:** kwiecień 2022
- **Ogólna dostępność wydania (samoaktualizacja):** czerwiec 2022 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** lipiec 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten temat, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego tematu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Zapasy i logistyka | [Przydzielanie zapasów dla dodatku Widoczność zapasów](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | Wkrótce | Domyślnie włączone |
| Produkcja | Widok „Mój dzień” dla interfejsu wykonania hal produkcyjnych | [Jak pracownicy korzystają z interfejsu wykonawczego hali produkcyjnej](../production-control/production-floor-execution-use.md) oraz [Pokaż salda urlopów w interfejsie wykonawczym hali produkcyjnej](../production-control/production-floor-execution-payroll-stats.md) | Zarządzanie funkcjami:<br>*Widok „Mój dzień” dla interfejsu wykonania hal produkcyjnych* |
| Planowanie | [Wsparcie optymalizacji planowania dla podwykonawstwa](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Zarządzanie pracą podwykonawczą w produkcji](../production-control/manage-subcontract-work-production.md) | Domyślnie włączone |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Planowanie główne | Podczas tworzenia planowanego zamówienia przeniesienia weź pod uwagę czas realizacji zapasów | Kiedy tworzone jest planowane zlecenie transferu, funkcja ta powoduje, że system bierze pod uwagę czas realizacji zapasów, który jest określony w domyślnych ustawieniach zlecenia dla danej pozycji, kiedy oblicza datę otrzymania planowanego zlecenia transferu dla kontroli daty dostawy ustawionej jako czas realizacji typu *Brak* lub *Sprzedaż*. Gdy określony jest czas realizacji transferu, jego wartość zostanie użyta do obliczenia daty otrzymania, a dni transportu nie będą brane pod uwagę. |
| Zaopatrzenie i sourcing | Domyślne informacje o podatku umowy z brokerem w wierszach faktury od dostawcy | Ta funkcja wprowadza logikę pozwalającą na ustawienie domyślnych wartości dla pól **Podatek od sprzedaży** i **Podatek od sprzedaży od danej pozycji** w liniach faktur sprzedawców kontraktowych brokera. Ta logika jest stosowana tylko wtedy, gdy typ obciążenia na linii umowy brokera to księga/księga. Grupa podatków od sprzedaży pobierze swoją domyślną wartość albo z kategorii zamówień maklerskich (jeśli jest ustawiona), albo z typu opłaty. Grupa podatku od sprzedaży pobierze swoją domyślną wartość z konta sprzedawcy. |
| Zaopatrzenie i sourcing | Ogranicz liczbę wierszy zamówienia zakupu na zadanie wsadowe | Ta funkcja pomaga zoptymalizować wydajność systemu podczas wysyłania potwierdzeń i potwierdzeń odbioru produktów. Dodaje ono nowe ustawienie o nazwie **Wiersze na zadanie** do zakładki **Dostawy** na stronie **Parametry zamówień i zaopatrzenia**. To nowe ustawienie pozwala ograniczyć liczbę linii zamówień zakupu przetwarzanych przez każde zadanie wsadowe. Dlatego może pomóc w zapobieganiu spowalniania systemu przez duże zadania wsadowe. |
| Zarządzanie informacjami o produktach | Wypełnij wartości atrybutów produktów | Ta funkcja dodaje cykliczne zadanie o nazwie *Wypełnij wartości atrybutów produktu*. To nowe zadanie okresowe tworzy brakujące rekordy wartości atrybutów produktów dla atrybutów skojarzonych z produktami za pośrednictwem kategorii produktów. |
| Kontrola produkcji | Dodatkowa konfiguracja w interfejsie wykonania hal produkcyjnych | <p>Ta funkcja dodaje następujące opcje do strony **Konfiguracja wykonania hali produkcyjnej**:</p><ul><li>**Automatyczne otwieranie okna startowego po zakończeniu wyszukiwania** – kiedy ta opcja jest włączona, okno dialogowe **Rozpocznij pracę** jest automatycznie otwierane, kiedy pracownicy używają paska wyszukiwania, by znaleźć pracę.</li><li>**Automatyczne otwieranie okna postępu raportu po zakończeniu wyszukiwania** – gdy ta opcja jest włączona, okno dialogowe **Postęp raportu** dla danego zadania jest automatycznie otwierane, gdy pracownicy używają paska wyszukiwania, by znaleźć to zadanie.</li><li>**Domyślna ilość pozostała w oknie dialogowym raportu o postępie** – gdy ta opcja jest włączona, w oknie dialogowym **Raport o postępie** jest pokazywana ilość pozostała do zaraportowania dla zadania produkcyjnego.</li></ul><p>Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-configure.md).</p> |
| Kontrola produkcji | Zespoły produkcyjne w interfejsie wykonania hal produkcyjnych | <p>Kiedy wielu pracowników jest przydzielonych do tego samego zadania produkcyjnego, mogą oni teraz wyznaczyć jednego pracownika jako pilota. Pozostali pracownicy automatycznie stają się asystentami tego pilota. W powstałej w ten sposób drużynie tylko pilot musi zarejestrować status pracy, natomiast ewidencja czasu dotyczy wszystkich członków drużyny. Funkcja ta obsługuje także scenariusz o nazwie *zasób pomocniczy*. W tym scenariuszu pracownik może zarejestrować się jako asystent innego pracownika, który następnie staje się pilotem nowo utworzonej grupy.</p><p>Aby uzyskać więcej informacji, zobacz [Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-use.md).</p> |
| Kontrola produkcji | Raport dotyczący pozycji planowania w interfejsie wykonania hal produkcyjnych | Ta funkcja upraszcza proces raportowania zleceń wsadowych dla pozycji planowania w interfejsie wykonawczym hali produkcyjnej. Kiedy dla produktu tworzone jest zlecenie wsadowe, które ma typ produkcji *Planowanie pozycji*, raportowanie jako zakończone może dotyczyć tylko produktów ubocznych i wspólnych dla tego zlecenia wsadowego. Zlecenia wsadowe dla pozycji planowania są zwykle używane do wspierania procesów demontażu, w których surowiec jest rozkładany na wiele różnych produktów. Kiedy pracownik zgłasza zlecenie wsadowe dla pozycji planowania jako zakończone, okno dialogowe **Zgłoszenie postępu** pokazuje teraz tylko produkty uboczne i współprodukty. Wcześniej pokazywała również pozycję planowania, a takie zachowanie mogło dezorientować pracowników. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące tematy Pomocy. Te tematy nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane tematy |
|---|---|
| Zarządzanie kosztami | [Średnia ważona data z uwzględnieniem wartości fizycznej i znakowania](../cost-management/weighted-average-date.md) |
| Rozproszona topologia hybrydowa | [Wypróbowanie jednostki skalowania w dystrybuowanej topologii hybrydowej](../cloud-edge/cloud-edge-try-out.md) |
| Podwójny zapis | [Synchronizacja na żądanie z aparatem wyceny aplikacji Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Zarządzanie magazynem | [Zwolnij do magazynu](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.27 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.27 aplikacji finansowych i operacyjnych (czerwiec 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.27, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.](/dynamics365-release-plan/2022wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W temacie [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
