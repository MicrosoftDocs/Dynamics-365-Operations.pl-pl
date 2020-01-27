---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 października 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7506953c797f5a55a93f1169bf48af8b06eb440e
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896803"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (23 października 2019 r.)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard
Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2569. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Aktualizacja Platform update 30 dla aplikacji Finance and Operations

Aby uzyskać więcej informacji, należy zapoznać się z [Nowości i zmiany w aktualizacji Platform update 30 dla aplikacji Finance and Operations (Listopad 2019)](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Usuń funkcję podglądu rejestracji otwartych świadczeń

W powiązaniu z naszymi oświadczeniami w wpisie na blogu pt. [Strategiczne inwestycje w Core HR zwiększają doskonałość operacyjną](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), firma Microsoft usuwa funkcję otwartej rejestracji świadczeń z podglądu publicznego 18 października 2019. Zamiast tego nowa funkcjonalność zostanie opublikowana w przyszłości. Korzystanie z funkcji korzystania z otwartej rejestracji świadczeń, która aktualnie znajduje się w podglądzie publicznym, nie będzie obsługiwane.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Błąd podczas wybierania kraju/regionu dla formularza pracownika po raz drugi (350294)

W przypadku wydania tego tygodnia rozchód został skorygowany podczas wybierania kraju/regionu w formularzu **Pracownik**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>Wartości wymiaru finansowego są domyślne dla pola wyświetlania kombinacji, jeśli pozycja nie zezwala na ręczne wprowadzanie wartości jako prawdziwej (340097)

Dzięki tej zmianie, jeśli podczas konfigurowania wymiarów finansowych i używania opcji nie zezwala się na wprowadzanie ręczne, system będzie poprawnie określać wartość wymiaru w polu **Wyświetlanie kombinacji**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>Nowe typy relacji należy dodawać do wyszukiwania relacji w formularzu kontakty osobiste (347691)

Ta wersja zawiera nowe możliwości dodawania nowych typów relacji w tabeli **Typy relacji** oraz odzwierciedlenia tych zmian w wyszukiwaniu relacji kontaktów osobistych.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Dodatkowe wartości listy w polach niestandardowych nie są odzwierciedlane w Common Data Service (379599)

W przypadku aktualizacji z tego tygodnia dodanie nowej wartości listy do istniejącego pola niestandardowego, które jest już zsynchronizowane z Common Data Service, spowoduje wyświetlenie nowych wartości listy pobrania po zastosowaniu zmian w jednostce.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>Na stronie Warunki zatrudnienia, warunki zatrudnienia wszystkich pracowników są wyświetlane po wybraniu polecenia Otwórz w programie Excel (348073)

W tej wersji rozwiązania, w programie Excel zostaną otwarte warunki zatrudnienia tylko dla wybranych pracowników. Wszystkie zabezpieczenia firmy są również honorowane.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service-324178"></a>Brak skojarzenia między Jednostką roboczą kalendarza pracy a Jednostką kalendarza pracy w Common Data Service (324178)

Ta relacja została dodana razem z tą wersją. Ta zmiana spowoduje włączenie dni roboczych pracownika do wyświetlania w aplikacji PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Błąd podczas korzystania z przepływów pracy samoobsługi pracownika z konfigurowalnymi hierarchiami (370132)

W tej wersji jest dostępna lepsza obsługa komunikatów o sposobach konfigurowania przepływów pracy przy użyciu konfigurowalnych hierarchii. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>System umożliwia tworzenie nowych stanowisk, gdzie data Dostępu do przypisania jest wcześniejsza niż Data aktywacji (340103)

Ta zmiana spowoduje wyświetlenie ostrzeżenia, jeśli data **Dostępne do przypisania** jest wcześniejsza niż data **Aktywacji** pozycji.

## <a name="coming-soon"></a>Wkrótce

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.

### <a name="feature-management-workspace"></a>Obszar roboczy zarządzanie funkcjami

Funkcje są dodawane i aktualizowane w każdym wydaniu. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.

Aby dowiedzieć się więcej o zmianach pochodzących z zarządzania funkcjam, zobacz [Omówienie zarządzania funkcjami](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
