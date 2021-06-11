---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie opisano sposób skonfigurowania połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103576"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="82d7a-103">Konfigurowanie podwójnego zapisu z usług Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="82d7a-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="82d7a-104">W tym temacie opisano sposób włączenia połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="82d7a-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82d7a-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="82d7a-105">Prerequisites</span></span>

<span data-ttu-id="82d7a-106">Integrację Power Platform należy zakończyć w sposób opisany w poniższych tematach:</span><span class="sxs-lookup"><span data-stu-id="82d7a-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="82d7a-107">Integracja Power Platform — włącz podczas wdrażania środowiska</span><span class="sxs-lookup"><span data-stu-id="82d7a-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="82d7a-108">Integracja Power Platform — włącz po wdrażaniu środowiska</span><span class="sxs-lookup"><span data-stu-id="82d7a-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="82d7a-109">Wskazówki dotyczące konfigurowania podwójnego zapisu w środowiskach Dataverse</span><span class="sxs-lookup"><span data-stu-id="82d7a-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="82d7a-110">Aby skonfigurować podwójny zapis ze strony **Szczegóły środowiska** usługi LCS, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="82d7a-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="82d7a-111">Na stronie **Szczegóły środowiska** rozwiń sekcję **Integracja Power Platform**.</span><span class="sxs-lookup"><span data-stu-id="82d7a-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="82d7a-112">Wybierz przycisk **Aplikacji podwójnego zapisu**.</span><span class="sxs-lookup"><span data-stu-id="82d7a-112">Select the **Dual-write application** button.</span></span>

    ![Integracja z programem Power Platform](media/powerplat_integration_step2.png)

3. <span data-ttu-id="82d7a-114">Przejrzyj warunki, a następnie zaznacz pole wyboru **Konfiguruj**.</span><span class="sxs-lookup"><span data-stu-id="82d7a-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="82d7a-115">Wybierz przycisk **OK**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="82d7a-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="82d7a-116">Postęp można monitorować, okresowo odświeżając stronę szczegółów środowiska.</span><span class="sxs-lookup"><span data-stu-id="82d7a-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="82d7a-117">Konfiguracja zwykle trwa 30 minut lub dłużej.</span><span class="sxs-lookup"><span data-stu-id="82d7a-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="82d7a-118">Po zakończeniu konfigurowania pojawi się komunikat informujący o pomyślnym zakończeniu procesu lub niepowodzeniu jego wykonania.</span><span class="sxs-lookup"><span data-stu-id="82d7a-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="82d7a-119">Jeśli konfiguracja nie powiodła się, wyświetlany jest powiązany komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="82d7a-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="82d7a-120">Przed przejściem do następnego kroku należy poprawić wszystkie błędy.</span><span class="sxs-lookup"><span data-stu-id="82d7a-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="82d7a-121">Wybierz **Łącze do środowiska Power Platform**, aby utworzyć łącze między Dataverse a bazami danych bieżącego środowiska.</span><span class="sxs-lookup"><span data-stu-id="82d7a-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="82d7a-122">Ta konfiguracja zwykle trwa 5 minut lub mniej.</span><span class="sxs-lookup"><span data-stu-id="82d7a-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Łącze do środowiska Power Platform":::

8. <span data-ttu-id="82d7a-124">Po zakończeniu łączenia jest wyświetlane hiperłącze.</span><span class="sxs-lookup"><span data-stu-id="82d7a-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="82d7a-125">Użyj łącza, aby zalogować się do obszaru administracji podwójnego zapisu w środowisku Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="82d7a-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="82d7a-126">Istnieje możliwość skonfigurowania mapowań encji.</span><span class="sxs-lookup"><span data-stu-id="82d7a-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="82d7a-127">Wskazówki dotyczące konfigurowania podwójnego zapisu dla istniejącego środowiska Dataverse</span><span class="sxs-lookup"><span data-stu-id="82d7a-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="82d7a-128">Aby skonfigurować podwójny zapis dla istniejącego środowiska Dataverse, musisz utworzyć [zgłoszenie](../../lifecycle-services/lcs-support.md) do pomocy technicznej firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="82d7a-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="82d7a-129">Zgłoszenie musi zawierać następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="82d7a-129">The ticket must include:</span></span>

+ <span data-ttu-id="82d7a-130">Identyfikator środowiska Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="82d7a-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="82d7a-131">Twoja nazwa środowiska z usługi Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="82d7a-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="82d7a-132">Identyfikator organizacji Dataverse lub identyfikator środowiska Power Platform z centrum administracyjnego Power Platform.</span><span class="sxs-lookup"><span data-stu-id="82d7a-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="82d7a-133">W zgłoszeniu poproś, aby identyfikator był wystąpieniem używanym do integracji Power Platform.</span><span class="sxs-lookup"><span data-stu-id="82d7a-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="82d7a-134">Nie można odłączyć środowisk za pomocą usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="82d7a-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="82d7a-135">Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.</span><span class="sxs-lookup"><span data-stu-id="82d7a-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
