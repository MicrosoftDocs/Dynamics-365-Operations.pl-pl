---
title: Przetwórz uprawnienia do świadczeń
description: W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfb7f13dce48f33c111af491918702763f7e3b8a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420021"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="1b06d-103">Przetwórz uprawnienia do świadczeń</span><span class="sxs-lookup"><span data-stu-id="1b06d-103">Process enrollment eligibility</span></span>

<span data-ttu-id="1b06d-104">W tym artykule opisano sposób uruchamiania procesu uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="1b06d-105">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie uprawnień do świadczeń**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="1b06d-106">W oknie dialogowym **Uruchamianie procesu uprawnień do rejestracji świadczenia** określ wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="1b06d-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="1b06d-107">Pole</span><span class="sxs-lookup"><span data-stu-id="1b06d-107">Field</span></span> | <span data-ttu-id="1b06d-108">Opis</span><span class="sxs-lookup"><span data-stu-id="1b06d-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="1b06d-109">**Okres rejestracji**</span><span class="sxs-lookup"><span data-stu-id="1b06d-109">**Enrollment period**</span></span> | <span data-ttu-id="1b06d-110">Okres rejestracji służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="1b06d-111">**Firma**</span><span class="sxs-lookup"><span data-stu-id="1b06d-111">**Legal entity**</span></span> | <span data-ttu-id="1b06d-112">Jednostka prawna służąca do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="1b06d-113">**Pracownik**</span><span class="sxs-lookup"><span data-stu-id="1b06d-113">**Worker**</span></span> | <span data-ttu-id="1b06d-114">Pracownik służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="1b06d-115">Jeśli to pole pozostanie puste, uprawnienia do rejestracji będą przetwarzane dla wszystkich pracowników.</span><span class="sxs-lookup"><span data-stu-id="1b06d-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="1b06d-116">**Plan świadczeń**</span><span class="sxs-lookup"><span data-stu-id="1b06d-116">**Benefit plan**</span></span> | <span data-ttu-id="1b06d-117">Plan świadczeń służący do przetworzenia uprawnień do rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="1b06d-118">Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="1b06d-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="1b06d-119">Umożliwia wprowadzanie informacji o przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="1b06d-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="1b06d-120">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="1b06d-121">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="1b06d-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-122">Select **OK**.</span></span> <span data-ttu-id="1b06d-123">Proces będzie uruchamiany z parametrami określonymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1b06d-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="1b06d-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="1b06d-125">Wyświetlanie wyników procesu</span><span class="sxs-lookup"><span data-stu-id="1b06d-125">View Process Results</span></span>

<span data-ttu-id="1b06d-126">W tym artykule opisano sposób wyświetlania wyników procesu.</span><span class="sxs-lookup"><span data-stu-id="1b06d-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="1b06d-127">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Wyniki procesu**.</span><span class="sxs-lookup"><span data-stu-id="1b06d-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="1b06d-128">W formularzu **Wyniki procesu** są określone następujące pola:</span><span class="sxs-lookup"><span data-stu-id="1b06d-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="1b06d-129">Pole</span><span class="sxs-lookup"><span data-stu-id="1b06d-129">Field</span></span> | <span data-ttu-id="1b06d-130">opis</span><span class="sxs-lookup"><span data-stu-id="1b06d-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="1b06d-131">**Identyfikator procesu**</span><span class="sxs-lookup"><span data-stu-id="1b06d-131">**Process ID**</span></span> | <span data-ttu-id="1b06d-132">Unikatowy identyfikator połączony Pracownika, Firmy i przebiegu procesu.</span><span class="sxs-lookup"><span data-stu-id="1b06d-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="1b06d-133">**Typ procesu**</span><span class="sxs-lookup"><span data-stu-id="1b06d-133">**Process type**</span></span> | <span data-ttu-id="1b06d-134">Identyfikuje proces, który został uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="1b06d-134">This identifies the process that was run.</span></span> <span data-ttu-id="1b06d-135">Na przykład:  Rejestracja.</span><span class="sxs-lookup"><span data-stu-id="1b06d-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="1b06d-136">**Sygnatura czasowa**</span><span class="sxs-lookup"><span data-stu-id="1b06d-136">**Time stamp**</span></span> | <span data-ttu-id="1b06d-137">Godzina, o której ma być uruchomiony proces kwalifikowania.</span><span class="sxs-lookup"><span data-stu-id="1b06d-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="1b06d-138">**Firma**</span><span class="sxs-lookup"><span data-stu-id="1b06d-138">**Legal entity**</span></span> | <span data-ttu-id="1b06d-139">Firma określona w procesie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="1b06d-140">**Pracownik**</span><span class="sxs-lookup"><span data-stu-id="1b06d-140">**Worker**</span></span> | <span data-ttu-id="1b06d-141">Pracownik, który został przetworzony.</span><span class="sxs-lookup"><span data-stu-id="1b06d-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="1b06d-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="1b06d-142">\*\*Plan</span></span> | <span data-ttu-id="1b06d-143">Plan świadczeń, dla którego podjęto próbę rejestracji.</span><span class="sxs-lookup"><span data-stu-id="1b06d-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="1b06d-144">**Reguła uprawnienia**</span><span class="sxs-lookup"><span data-stu-id="1b06d-144">**Eligibility rule**</span></span> | <span data-ttu-id="1b06d-145">Przetworzona reguła uprawnień.</span><span class="sxs-lookup"><span data-stu-id="1b06d-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="1b06d-146">Jeśli wystąpił błąd przed uruchomieniem uprawnień, to pole będzie puste.</span><span class="sxs-lookup"><span data-stu-id="1b06d-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="1b06d-147">Na przykład: Jeśli wynagrodzenie nie zostało zdefiniowane dla pracownika, proces kwalifikowania nie zostanie uruchomiony, a to pole zostanie pozostawione puste.</span><span class="sxs-lookup"><span data-stu-id="1b06d-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="1b06d-148">**Stan wyniku**</span><span class="sxs-lookup"><span data-stu-id="1b06d-148">**Result status**</span></span> | <span data-ttu-id="1b06d-149">Ta opcja będzie Uprawniona lub Niekwalifikująca się.</span><span class="sxs-lookup"><span data-stu-id="1b06d-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="1b06d-150">Stan wyniku jest nieuprawniony, jeśli pracownik nie spełnił kryteriów reguły uprawnień, jeśli pracownik nie dostarczył wymaganych informacji, takich jak częstotliwość płac lub stałe wynagrodzenie, lub jeśli w planie świadczeń brakuje informacji, co uniemożliwia zarejestrowanie się pracowników.</span><span class="sxs-lookup"><span data-stu-id="1b06d-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="1b06d-151">**Komunikat wyniku**</span><span class="sxs-lookup"><span data-stu-id="1b06d-151">**Result message**</span></span> | <span data-ttu-id="1b06d-152">Wskazuje, dlaczego pracownik nie kwalifikuje się do planu świadczeń lub jeśli została przekazana reguła uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="1b06d-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |

