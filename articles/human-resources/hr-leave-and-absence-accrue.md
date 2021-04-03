---
title: Nalicz plany urlopów i nieobecności
description: W programie Dynamics 365 Human Resources urlopy i nieobecności można naliczać dla wielu pracowników lub dla jednej osoby.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 348c8e5336854eb2a1c04a1f98a97a2c9dba7176
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464917"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="664ad-103">Nalicz plany urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="664ad-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="664ad-104">W programie Dynamics 365 Human Resources urlopy i nieobecności można naliczać dla wielu pracowników lub dla jednej osoby.</span><span class="sxs-lookup"><span data-stu-id="664ad-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="664ad-105">Naliczanie urlopów i nieobecności dla wielu pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="664ad-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="664ad-106">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="664ad-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="664ad-107">W obszarze **Zarządzaj urlopami** wybierz opcję **Nalicz do planów urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="664ad-108">Zostanie wyświetlone okno dialogowe **Naliczanie planów urlopu i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="664ad-109">W polu **Naliczanie na dzień** wybierz **Datę dzisiejszą** lub wybierz **Datę niestandardową** i wprowadź datę niestandardową.</span><span class="sxs-lookup"><span data-stu-id="664ad-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="664ad-110">Aby uruchomić naliczenia dla wszystkich firm, należy wybrać opcję **Wszystkie firmy**.</span><span class="sxs-lookup"><span data-stu-id="664ad-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="664ad-111">Jeśli chcesz przetwarzać naliczenia dla planu jednego urlopu, wybierz opcję **Nie** dla **Wszystkich planów**, a następnie wybierz **Plan urlopu**.</span><span class="sxs-lookup"><span data-stu-id="664ad-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="664ad-112">W przypadku wybrania wszystkich firm nie można wybrać jednego planu urlopu.</span><span class="sxs-lookup"><span data-stu-id="664ad-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="664ad-113">Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="664ad-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="664ad-114">Wprowadź informacje o procesie naliczania.</span><span class="sxs-lookup"><span data-stu-id="664ad-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="664ad-115">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="664ad-116">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="664ad-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-117">Select **OK**.</span></span> <span data-ttu-id="664ad-118">Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="664ad-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="664ad-119">Naliczanie urlopów i nieobecności dla pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="664ad-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="664ad-120">W rekordzie pracownika wybierz pozycję **Urlop**.</span><span class="sxs-lookup"><span data-stu-id="664ad-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="664ad-121">Wybierz opcję **Nalicz do planów urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="664ad-122">Zostanie wyświetlone okno dialogowe **Naliczanie planów urlopu i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="664ad-123">W polu **Naliczanie na dzień** wybierz **Datę dzisiejszą** lub wybierz **Datę niestandardową** i wprowadź datę niestandardową.</span><span class="sxs-lookup"><span data-stu-id="664ad-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="664ad-124">Aby uruchomić naliczenia dla wszystkich firm, należy wybrać opcję **Wszystkie firmy**.</span><span class="sxs-lookup"><span data-stu-id="664ad-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="664ad-125">Jeśli chcesz przetwarzać naliczenia dla planu jednego urlopu, wybierz opcję **Nie** dla **Wszystkich planów**, a następnie wybierz **Plan urlopu**.</span><span class="sxs-lookup"><span data-stu-id="664ad-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="664ad-126">W przypadku wybrania wszystkich firm nie można wybrać jednego planu urlopu.</span><span class="sxs-lookup"><span data-stu-id="664ad-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="664ad-127">Jeśli chcesz uruchomić proces naliczania w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="664ad-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="664ad-128">Wprowadź informacje o procesie naliczania.</span><span class="sxs-lookup"><span data-stu-id="664ad-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="664ad-129">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="664ad-130">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="664ad-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-131">Select **OK**.</span></span> <span data-ttu-id="664ad-132">Proces naliczania zostanie uruchomiony z parametrami określonymi przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="664ad-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="664ad-133">Usuwanie naliczeń urlopów i nieobecności dla wielu pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="664ad-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="664ad-134">Usuwanie rekordów naliczeń dla określonego planu i zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="664ad-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="664ad-135">Daty naliczania muszą przypadać w dniu dzisiejszym lub w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="664ad-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="664ad-136">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="664ad-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="664ad-137">W obszarze **Zarządzaj urlopami** wybierz opcję **Usuń naliczanie planów urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="664ad-138">W oknie dialogowym **Usuń naliczanie planów urlopów i nieobecności** wybierz **Plan urlopów**.</span><span class="sxs-lookup"><span data-stu-id="664ad-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="664ad-139">W razie potrzeby wybierz polecenie **Usuń korekty salda**.</span><span class="sxs-lookup"><span data-stu-id="664ad-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="664ad-140">Wprowadź lub wybierz **Datę naliczania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="664ad-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="664ad-141">Ta data musi być datą dzisiejszą lub w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="664ad-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="664ad-142">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-142">Select **OK**.</span></span> <span data-ttu-id="664ad-143">Proces naliczania usunie naliczenia z parametrami określonymi przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="664ad-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="664ad-144">Usuwanie naliczeń urlopów i nieobecności dla jednego pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="664ad-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="664ad-145">W rekordzie pracownika wybierz pozycję **Urlop**.</span><span class="sxs-lookup"><span data-stu-id="664ad-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="664ad-146">Wybierz **Usuń naliczenia planów urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="664ad-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="664ad-147">W oknie dialogowym **Usuń naliczanie planów urlopów i nieobecności** wybierz **Plan urlopów**.</span><span class="sxs-lookup"><span data-stu-id="664ad-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="664ad-148">W razie potrzeby wybierz polecenie **Usuń korekty salda**.</span><span class="sxs-lookup"><span data-stu-id="664ad-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="664ad-149">Wprowadź lub wybierz **Datę naliczania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="664ad-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="664ad-150">Ta data musi być datą dzisiejszą lub w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="664ad-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="664ad-151">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="664ad-151">Select **OK**.</span></span> <span data-ttu-id="664ad-152">Proces naliczania usunie naliczenia z parametrami określonymi przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="664ad-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="664ad-153">Przeglądanie procesów naliczania i usuwania urlopu</span><span class="sxs-lookup"><span data-stu-id="664ad-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="664ad-154">**Inspekcja naliczania urlopów** wyświetla się przy każdym uruchomieniu lub usunięciu naliczenia dla jednego lub wszystkich pracowników.</span><span class="sxs-lookup"><span data-stu-id="664ad-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="664ad-155">Zostanie wyświetlona data i osoba, która wykonała akcję.</span><span class="sxs-lookup"><span data-stu-id="664ad-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="664ad-156">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="664ad-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="664ad-157">W obszarze **Zarządzaj urlopami** wybierz opcję **Usuń inspekcję naliczania planów**.</span><span class="sxs-lookup"><span data-stu-id="664ad-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="664ad-158">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="664ad-158">See also</span></span>

[<span data-ttu-id="664ad-159">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="664ad-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="664ad-160">Tworzenie planu urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="664ad-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]