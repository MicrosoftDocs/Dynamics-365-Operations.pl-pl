---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (5 listopada 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4068cf81782d2f9559179b91da31e049c006059
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527127"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (5 listopada 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2598. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Kopiowanie podstawowego Core HR

W wersji tego tygodnia można skorzystać z usług cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services(usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Talent: Core HR do środowiska piaskownicy. Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy. Aby uzyskać więcej informacji, zobacz:

- [Szersze zarządzanie środowiskiem](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) w Dynamics 365:2019 plan wydania rozwiązania 2

- [Kopiowanie wystąpienia Core HR](hr-copy-instance.md) w dokumentacji Talent

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Zadania wsadowe integracji Common Data Service nie są tworzone, gdy integracja Common Data Service jest włączona (388030)

Ta zmiana spowoduje utworzenie zadań wsadowych dla integracji Common Data Service, gdy jest ona włączona.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>HcmPersonImageEntity nie zmienia rozmiaru obrazu osoby po przekazaniu (369469)

Wersja tego tygodnia zmienia sposób zmiany rozmiaru obrazów w celu uzyskania lepszej wydajności podczas importowania za pomocą zarządzania danymi.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>Pozycja dostępna dla daty przypisania może być wcześniejsza niż Data aktywacji (340103)

W przypadku zmiany zostanie wyświetlone ostrzeżenie, jeśli zostanie wybrana opcja **dostępna dla daty przypisania** wcześniejsza niż **data aktywacji pozycji**.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Nie można utworzyć żądania zmiany wynagrodzenia w module samoobsługi dla pracowników w planach opartych na krokach (376872)

Ta wersja koryguje usterkę w przypadku żądania zmian dotyczących wynagrodzenia za pomocą funkcji samoobsługi w ramach modułu Employee dla planów opartych na krokach. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>Kod przyczyny nie zostanie zsynchronizowany do Common Data Service, jeśli opis jest dłuższy niż 30 znaków, liczba Core HR zezwala na 60 (352682)

W przypadku tej zmiany kody przyczyn zawierające więcej niż 30 znaków zostaną zaktualizowane w Common Data Service. Zmiany wprowadzone w Common Data Service zostaną również odzwierciedlone w Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Integracja adresu z modułu Talent do Finance and Operations (351961)

Ta wersja rozwiązuje problem polegający na tym, że adresy zaktualizowane w programie Talent nie były aktualizowane w module Finance and Operations. Zmiany w blokach adresów zostaną teraz zaktualizowane.

## <a name="coming-soon"></a>Wkrótce

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.

### <a name="feature-management-workspace"></a>Obszar roboczy zarządzanie funkcjami

Funkcje są dodawane i aktualizowane w każdym wydaniu. Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.

Aby dowiedzieć się więcej o zmianach pochodzących z zarządzania funkcjam, zobacz [Omówienie zarządzania funkcjami](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).


[!INCLUDE[footer-include](../includes/footer-banner.md)]