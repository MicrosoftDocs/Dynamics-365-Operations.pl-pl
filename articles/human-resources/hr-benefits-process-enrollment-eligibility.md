---
title: Przetwórz uprawnienia do świadczeń
description: W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010149"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="98eb2-103">Przetwórz uprawnienia do świadczeń</span><span class="sxs-lookup"><span data-stu-id="98eb2-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="98eb2-104">W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98eb2-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="98eb2-105">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie uprawnień do świadczeń**.</span><span class="sxs-lookup"><span data-stu-id="98eb2-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="98eb2-106">W oknie dialogowym **Uruchamianie procesu uprawnień do rejestracji świadczenia** określ wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="98eb2-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="98eb2-107">Pole</span><span class="sxs-lookup"><span data-stu-id="98eb2-107">Field</span></span> | <span data-ttu-id="98eb2-108">Opis</span><span class="sxs-lookup"><span data-stu-id="98eb2-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="98eb2-109">Okres rejestracji</span><span class="sxs-lookup"><span data-stu-id="98eb2-109">Enrollment period</span></span> | <span data-ttu-id="98eb2-110">Okres rejestracji służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98eb2-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="98eb2-111">Firma</span><span class="sxs-lookup"><span data-stu-id="98eb2-111">Legal entity</span></span> | <span data-ttu-id="98eb2-112">Jednostka prawna służąca do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98eb2-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="98eb2-113">Pracownik</span><span class="sxs-lookup"><span data-stu-id="98eb2-113">Worker</span></span> | <span data-ttu-id="98eb2-114">Pracownik służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98eb2-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="98eb2-115">Jeśli to pole pozostanie puste, uprawnienia do rejestracji będą przetwarzane dla wszystkich pracowników.</span><span class="sxs-lookup"><span data-stu-id="98eb2-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="98eb2-116">Plan świadczeń</span><span class="sxs-lookup"><span data-stu-id="98eb2-116">Benefit plan</span></span> | <span data-ttu-id="98eb2-117">Plan świadczeń służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="98eb2-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="98eb2-118">Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="98eb2-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="98eb2-119">Umożliwia wprowadzanie informacji o przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="98eb2-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="98eb2-120">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="98eb2-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="98eb2-121">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="98eb2-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="98eb2-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="98eb2-122">Select **OK**.</span></span> <span data-ttu-id="98eb2-123">Proces będzie uruchamiany z parametrami określonymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="98eb2-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="98eb2-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="98eb2-124">Select **OK**.</span></span>
