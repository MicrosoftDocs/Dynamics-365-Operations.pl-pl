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
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896780"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="e85e0-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (5 listopada 2019 r.)</span><span class="sxs-lookup"><span data-stu-id="e85e0-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

<span data-ttu-id="e85e0-104">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="e85e0-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="e85e0-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="e85e0-105">Changes in Attract</span></span>

<span data-ttu-id="e85e0-106">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="e85e0-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="e85e0-107">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="e85e0-107">Changes in Onboard</span></span>

<span data-ttu-id="e85e0-108">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="e85e0-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="e85e0-109">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="e85e0-109">Changes in Core HR</span></span>

<span data-ttu-id="e85e0-110">Zmiany opisane w tej części dotyczą kompilacji 8.1.2598.</span><span class="sxs-lookup"><span data-stu-id="e85e0-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="e85e0-111">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e85e0-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="e85e0-112">Kopiowanie podstawowego Core HR</span><span class="sxs-lookup"><span data-stu-id="e85e0-112">Copy a Core HR instance</span></span>

<span data-ttu-id="e85e0-113">W wersji tego tygodnia można skorzystać z usług cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services(usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Talent: Core HR do środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="e85e0-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="e85e0-114">Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="e85e0-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="e85e0-115">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="e85e0-115">For more information, see:</span></span>

- <span data-ttu-id="e85e0-116">[Szersze zarządzanie środowiskiem](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) w Dynamics 365:2019 plan wydania rozwiązania 2</span><span class="sxs-lookup"><span data-stu-id="e85e0-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="e85e0-117">[Kopiowanie wystąpienia Core HR](hr-copy-instance.md) w dokumentacji Talent</span><span class="sxs-lookup"><span data-stu-id="e85e0-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="e85e0-118">Zadania wsadowe integracji Common Data Service nie są tworzone, gdy integracja Common Data Service jest włączona (388030)</span><span class="sxs-lookup"><span data-stu-id="e85e0-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="e85e0-119">Ta zmiana spowoduje utworzenie zadań wsadowych dla integracji Common Data Service, gdy jest ona włączona.</span><span class="sxs-lookup"><span data-stu-id="e85e0-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="e85e0-120">HcmPersonImageEntity nie zmienia rozmiaru obrazu osoby po przekazaniu (369469)</span><span class="sxs-lookup"><span data-stu-id="e85e0-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="e85e0-121">Wersja tego tygodnia zmienia sposób zmiany rozmiaru obrazów w celu uzyskania lepszej wydajności podczas importowania za pomocą zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="e85e0-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="e85e0-122">Pozycja dostępna dla daty przypisania może być wcześniejsza niż Data aktywacji (340103)</span><span class="sxs-lookup"><span data-stu-id="e85e0-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="e85e0-123">W przypadku zmiany zostanie wyświetlone ostrzeżenie, jeśli zostanie wybrana opcja **dostępna dla daty przypisania** wcześniejsza niż **data aktywacji pozycji**.</span><span class="sxs-lookup"><span data-stu-id="e85e0-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="e85e0-124">Nie można utworzyć żądania zmiany wynagrodzenia w module samoobsługi dla pracowników w planach opartych na krokach (376872)</span><span class="sxs-lookup"><span data-stu-id="e85e0-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="e85e0-125">Ta wersja koryguje usterkę w przypadku żądania zmian dotyczących wynagrodzenia za pomocą funkcji samoobsługi w ramach modułu Employee dla planów opartych na krokach.</span><span class="sxs-lookup"><span data-stu-id="e85e0-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="e85e0-126">Kod przyczyny nie zostanie zsynchronizowany do Common Data Service, jeśli opis jest dłuższy niż 30 znaków, liczba Core HR zezwala na 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="e85e0-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="e85e0-127">W przypadku tej zmiany kody przyczyn zawierające więcej niż 30 znaków zostaną zaktualizowane w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e85e0-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="e85e0-128">Zmiany wprowadzone w Common Data Service zostaną również odzwierciedlone w Talent.</span><span class="sxs-lookup"><span data-stu-id="e85e0-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="e85e0-129">Integracja adresu z rozwiązania Talent do rozwiązania Finance and Operations (351961)</span><span class="sxs-lookup"><span data-stu-id="e85e0-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="e85e0-130">Ta wersja rozwiązuje problem polegający na tym, że adresy zaktualizowane w programie Talent nie były aktualizowane w module Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e85e0-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="e85e0-131">Zmiany w blokach adresów zostaną teraz zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="e85e0-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e85e0-132">Wkrótce</span><span class="sxs-lookup"><span data-stu-id="e85e0-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="e85e0-133">Drukowanie przeglądów wydajności</span><span class="sxs-lookup"><span data-stu-id="e85e0-133">Print performance reviews</span></span>

<span data-ttu-id="e85e0-134">Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.</span><span class="sxs-lookup"><span data-stu-id="e85e0-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="e85e0-135">Obszar roboczy zarządzanie funkcjami</span><span class="sxs-lookup"><span data-stu-id="e85e0-135">Feature management workspace</span></span>

<span data-ttu-id="e85e0-136">Funkcje są dodawane i aktualizowane w każdym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="e85e0-136">Features are added and updated in every release.</span></span> <span data-ttu-id="e85e0-137">Środowisko zarządzania funkcjami udostępnia obszar roboczy, w którym można wyświetlić listę funkcji, które zostały dostarczone w każdej wersji.</span><span class="sxs-lookup"><span data-stu-id="e85e0-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="e85e0-138">Domyślnie nowe funkcje są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="e85e0-138">By default, new features are turned off.</span></span> <span data-ttu-id="e85e0-139">Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich.</span><span class="sxs-lookup"><span data-stu-id="e85e0-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="e85e0-140">Aby dowiedzieć się więcej o zmianach pochodzących z zarządzania funkcjam, zobacz [Omówienie zarządzania funkcjami](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e85e0-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
