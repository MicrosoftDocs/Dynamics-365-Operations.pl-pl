---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (10 grudnia 2019 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528178"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (10 grudnia 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2660. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Obszar roboczy zarządzanie funkcjami

Obszar roboczy **zarządzanie funkcjami** zawiera listę funkcji dostarczanych w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich. Aby uzyskać więcej informacji o zarządzaniu funkcjami funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym **zarządzanie funkcjami** można je włączyć. Niektóre funkcje mogą być domyślnie włączone.
 
Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym **zarządzanie funkcjami**).
 
Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza **Zarządzanie funkcjami** wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>Udoskonalony formularz pracowników został przeniesiony do obszaru roboczego zarządzania funkcjami (390583)

Dzięki tej zmianie można teraz włączyć udoskonalony formularz pracowników w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja została przeniesiona z formularza **Parametry systemu** w obszarze **Administrowanie systemem**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Zapobieganie zapisaniu rekordów HcmWorkerPayrollInfo bez wartości pracownika (394526)

W tym wydaniu rekordy **HcmWorkerPayrollInfo** nie są już tworzone bez odwołania pracownika w tym scenariuszu. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>Dziennik komunikatów skojarzony z akcją nie jest wypełniany, gdy akcja zakończy się niepowodzeniem (374007)

To wydanie zawiera zmianę pozwalającą na wypełnianie dziennika komunikatów akcji, gdy akcja nie powiedzie się w niektórych scenariuszach. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Tworzenie zadania wsadowego integracji usługi Common Data Service (388030)

Dzięki tej zmianie zadania wsadowe integracji usługi Common Data Service są tworzone, gdy usługa jest włączona.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Dodatkowe wartości listy wyboru w polach niestandardowych nie są odzwierciedlane w usłudze Common Data Service po kliknięciu przycisku Zastosuj w formularzu pól niestandardowych (379599)

Dzięki tej zmianie nowe wartości listy pobrania wprowadzone w aplikacji Talent są teraz synchronizowane do usługi Common Data Service po zastosowaniu zmian.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>Aktualizacja usługi Common Data Service na potrzeby jednostki transakcji banku urlopów zmienia się we wstawianie po stronie aplikacji Talent (352938)

Ta zmiana rozwiązuje problem polegający na tym, że aktualizacja transakcji banku urlopowego tworzy nowy rekord w aplikacji Talent.

## <a name="in-preview"></a>Wersja próbna

Funkcje w wersji zapoznawczej będą włączone tylko w środowiskach **Piaskownica**.

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.



[!INCLUDE[footer-include](../includes/footer-banner.md)]