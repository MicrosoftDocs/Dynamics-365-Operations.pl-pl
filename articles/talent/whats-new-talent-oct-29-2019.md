---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (29 października 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897449"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (29 października 2019 r.)

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2586. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Usuwanie jednostek bez ról powinno być włączone domyślnie (371233)

Jeśli w talentów jest inicjowane nowe środowisko, należy **usunąć jednostki, jeśli nie istnieją** żadne role domyślnie włączone. Po usunięciu pracownika jednostka skojarzona z pracownikiem nie jest usuwana, o ile to ustawienie nie jest włączone. Ta zmiana powoduje ograniczenie duplikatów rekordów w globalna książka adresowa, gdy zachodzi potrzeba importu, zmiany lub od importowania pracowników.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>Należy zezwolić na usuwanie roboczych i anulowanych żądań urlopów w Common Data Service (376999)

Dzięki tej zmianie można teraz usuwać żądania urlopu ze stanem **wersja robocza** lub **anulowane** w systemie Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Dodatkowe wartości listy w polach niestandardowych nie są odzwierciedlane Common Data Service po kliknięciu przycisku Zastosuj w formularzu pola niestandardowe (379599)

Po dodaniu nowych wartości do istniejącego pola niestandardowego Common Data Service, które jest już zsynchronizowane, są one dostępne w popularnych serivce danych po zastosowaniu zmian w formularzu **pola niestandardowe**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Stosowanie list kontrolnych na wejściu do firmy w przypadku istnienia więcej niż jednego zatrudnienia (371270)

W wersji tego tygodnia można zastosować listy kontrolne do pracowników, którzy mają więcej niż jedno zatrudnienie w **Formularz pracownika >listy kontrolne**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>Funkcja zapoznawcza Otwarte zapisy na świadczenia została usunięta.

W powiązaniu z naszymi oświadczeniami w wpisie na blogu pt. [Strategiczne inwestycje w Core HR zwiększają doskonałość operacyjną](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), firma Microsoft usunęła funkcję otwartej rejestracji świadczeń z podglądu publicznego. Nowa funkcjonalność zostanie opublikowana w przyszłości. Nie jest obsługiwane korzystanie z funkcji rejestrowania świadczeń otwartych w produkcji.

## <a name="coming-soon"></a>Wkrótce

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.

### <a name="feature-management-workspace"></a>Obszar roboczy zarządzanie funkcjami

Funkcje są dodawane i aktualizowane w każdym wydaniu. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.

Aby dowiedzieć się więcej o zmianach pochodzących z zarządzania funkcjam, zobacz [Omówienie zarządzania funkcjami](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
