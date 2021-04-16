---
title: Przetwarzanie zmian sytuacji życiowej
description: W trakcie cyklu życia pracownika w module Microsoft Dynamics 365 Human Resources każdy pracownik może przechodzić różne zmiany sytuacji życiowej.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 461f90c3da8fa5b2db14b6dd67a0c19f7eabe867
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793808"
---
# <a name="process-life-events"></a><span data-ttu-id="484ac-103">Przetwarzanie zmian sytuacji życiowej</span><span class="sxs-lookup"><span data-stu-id="484ac-103">Process life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="484ac-104">W trakcie cyklu życia pracownika w module Microsoft Dynamics 365 Human Resources każdy pracownik może przechodzić różne zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="484ac-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="484ac-105">Na przykład zawarcie małżeństwa, zmiana w zatrudnieniu lub zmiana osoby na utrzymaniu/beneficjenta.</span><span class="sxs-lookup"><span data-stu-id="484ac-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="484ac-106">Aby można było wprowadzać zmiany sytuacji życiowej, należy włączyć funkcję zmian sytuacji życiowej w formularzu Parametry świadczeń, skonfigurować typy zmian sytuacji życiowej oraz skonfigurować opcje zmian sytuacji życiowej dla typów planów.</span><span class="sxs-lookup"><span data-stu-id="484ac-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="484ac-107">Aby można było przetwarzać zmiany sytuacji życiowej, należy wcześniej uruchomić otwartą rejestrację co najmniej raz w trakcie okresie zatrudniania.</span><span class="sxs-lookup"><span data-stu-id="484ac-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="484ac-108">W Stanach Zjednoczonych otwarta rejestracja zazwyczaj odbywa się raz na rok.</span><span class="sxs-lookup"><span data-stu-id="484ac-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="484ac-109">Poza Stanami Zjednoczonymi otwarta rejestracja może być wykonywana w momencie zatrudniania.</span><span class="sxs-lookup"><span data-stu-id="484ac-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="484ac-110">Pracownik nie musi wybrać planu świadczeń, aby zmiany sytuacji życiowej były przetwarzane, ale musi być uwzględniony w przetwarzaniu otwartej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="484ac-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="484ac-111">Przetwarzanie zmian sytuacji życiowej należy stosować w przypadku, gdy w organizacji istnieją pracownicy ze zmianami sytuacji życiowej przypadającymi w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="484ac-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="484ac-112">To zdarzenie spowoduje przetwarzanie wszystkich zmian sytuacji życiowej, które nie zostały przetworzone (takich jak przyszłe zmiany sytuacji życiowej czy dodane zmiany sytuacji życiowej, które nie są specyficzne dla żadnego pracownika, takie jak wprowadzenie nowego świadczenia).</span><span class="sxs-lookup"><span data-stu-id="484ac-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="484ac-113">Zmiany sytuacji życiowej zachodzące w czasie rzeczywistym są ukryte.</span><span class="sxs-lookup"><span data-stu-id="484ac-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="484ac-114">Na przykład jeśli dzisiejsza data to 1 lutego, a 14 lutego pracownik Jan Kowalski ma zmienić zatrudniającą go firmę, to po uruchomieniu przetwarzania zmian sytuacji życiowej w dniu 15 lutego system przetworzy wszystkie zmiany do dnia 15 lutego włącznie.</span><span class="sxs-lookup"><span data-stu-id="484ac-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="484ac-115">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie zdarzenia zmiany sytuacji życiowej**.</span><span class="sxs-lookup"><span data-stu-id="484ac-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="484ac-116">W oknie dialogowym **Uruchom proces zdarzenia zmiany sytuacji życiowej** określ wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="484ac-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="484ac-117">Pole</span><span class="sxs-lookup"><span data-stu-id="484ac-117">Field</span></span> | <span data-ttu-id="484ac-118">Opis</span><span class="sxs-lookup"><span data-stu-id="484ac-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="484ac-119">**Okres rejestracji**</span><span class="sxs-lookup"><span data-stu-id="484ac-119">**Enrollment period**</span></span> | <span data-ttu-id="484ac-120">Okres rejestracji, dla którego mają być przetwarzane zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="484ac-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="484ac-121">**Firma**</span><span class="sxs-lookup"><span data-stu-id="484ac-121">**Legal entity**</span></span> | <span data-ttu-id="484ac-122">Firma, dla której mają być przetwarzane zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="484ac-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="484ac-123">**Data zdarzenia zmiany sytuacji życiowej**</span><span class="sxs-lookup"><span data-stu-id="484ac-123">**Life event date**</span></span> | <span data-ttu-id="484ac-124">System przetwarza wszystkie zdarzenia w okresie rejestracji, który nastąpiły do tej daty.</span><span class="sxs-lookup"><span data-stu-id="484ac-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="484ac-125">**Pracownik**</span><span class="sxs-lookup"><span data-stu-id="484ac-125">**Worker**</span></span> | <span data-ttu-id="484ac-126">Pracownik, dla którego mają być przetwarzane zmiany sytuacji życiowej.</span><span class="sxs-lookup"><span data-stu-id="484ac-126">The worker to process life events for.</span></span> <span data-ttu-id="484ac-127">Jeśli to pole pozostanie puste, zmiany sytuacji życiowej będą przetwarzane dla wszystkich pracowników.</span><span class="sxs-lookup"><span data-stu-id="484ac-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="484ac-128">Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="484ac-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="484ac-129">Umożliwia wprowadzanie informacji o przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="484ac-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="484ac-130">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="484ac-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="484ac-131">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="484ac-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="484ac-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="484ac-132">Select **OK**.</span></span> <span data-ttu-id="484ac-133">Proces będzie uruchamiany z parametrami określonymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="484ac-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="484ac-134">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="484ac-134">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]