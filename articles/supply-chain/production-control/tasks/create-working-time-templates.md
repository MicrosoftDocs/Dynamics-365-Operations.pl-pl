---
title: Tworzenie szablonów czasu pracy
description: Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920936"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="fbc87-103">Tworzenie szablonów czasu pracy</span><span class="sxs-lookup"><span data-stu-id="fbc87-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fbc87-104">Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.</span><span class="sxs-lookup"><span data-stu-id="fbc87-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="fbc87-105">W tej procedurze pokazano sposób definiowania szablonu czasu pracy za pomocą właściwości planowania czasu pracy w celu kategoryzowania zakresów czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="fbc87-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="fbc87-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="fbc87-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="fbc87-107">Wybierz kolejno opcje **Obszary robocze > Zarządzanie cyklem życia zasobu**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="fbc87-108">Wybierz opcję **Szablony czasu pracy**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="fbc87-109">Tworzenie szablonu czasu pracy</span><span class="sxs-lookup"><span data-stu-id="fbc87-109">Create working time template</span></span>

1. <span data-ttu-id="fbc87-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-110">Select **New**.</span></span>
1. <span data-ttu-id="fbc87-111">W polu **Szablon czasu pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="fbc87-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="fbc87-112">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="fbc87-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="fbc87-113">Rozwiń sekcję **Poniedziałek**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="fbc87-114">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-114">Select **Add**.</span></span>
1. <span data-ttu-id="fbc87-115">W polu **Od** wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="fbc87-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="fbc87-116">Określ godzinę rozpoczynania pracy rano.</span><span class="sxs-lookup"><span data-stu-id="fbc87-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="fbc87-117">W polu **Do** wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="fbc87-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="fbc87-118">Określ godzinę, kiedy pracownicy zaczynają przerwę na obiad.</span><span class="sxs-lookup"><span data-stu-id="fbc87-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="fbc87-119">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-119">Select **Add**.</span></span>
1. <span data-ttu-id="fbc87-120">W polu **Od** wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="fbc87-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="fbc87-121">Określ godzinę, kiedy pracownicy wznawiają pracę po obiedzie.</span><span class="sxs-lookup"><span data-stu-id="fbc87-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="fbc87-122">W polu **Do** wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="fbc87-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="fbc87-123">Określ godzinę zakończenia dnia pracy.</span><span class="sxs-lookup"><span data-stu-id="fbc87-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="fbc87-124">Replikowanie czasów pracy do wszystkich dni tygodnia</span><span class="sxs-lookup"><span data-stu-id="fbc87-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="fbc87-125">Wybierz opcję **Kopiuj dzień**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="fbc87-126">Skopiuj definicje czasu pracy z poniedziałku do wtorku.</span><span class="sxs-lookup"><span data-stu-id="fbc87-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="fbc87-127">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-127">Select **OK**.</span></span>
1. <span data-ttu-id="fbc87-128">Wybierz opcję **Kopiuj dzień**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="fbc87-129">Skopiuj definicje czasu pracy z poniedziałku do środy.</span><span class="sxs-lookup"><span data-stu-id="fbc87-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="fbc87-130">W polu **Do dnia roboczego** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="fbc87-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="fbc87-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-131">Select **OK**.</span></span>
1. <span data-ttu-id="fbc87-132">Wybierz opcję **Kopiuj dzień**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="fbc87-133">Skopiuj definicje czasu pracy z poniedziałku do czwartku.</span><span class="sxs-lookup"><span data-stu-id="fbc87-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="fbc87-134">W polu **Do dnia roboczego** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="fbc87-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="fbc87-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-135">Select **OK**.</span></span>
1. <span data-ttu-id="fbc87-136">Wybierz opcję **Kopiuj dzień**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="fbc87-137">Skopiuj definicje czasu pracy z poniedziałku do piątku.</span><span class="sxs-lookup"><span data-stu-id="fbc87-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="fbc87-138">W polu **Do dnia roboczego** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="fbc87-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="fbc87-139">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="fbc87-140">Definiowanie przedziałów czasu dla operacji specjalnych</span><span class="sxs-lookup"><span data-stu-id="fbc87-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="fbc87-141">Rozwiń sekcję **Piątek**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="fbc87-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="fbc87-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="fbc87-143">W polu **Właściwość** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fbc87-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="fbc87-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="fbc87-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="fbc87-145">W polu **Właściwość** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fbc87-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="fbc87-146">Oznaczanie dni weekendowych jako zamkniętych dla pobierania</span><span class="sxs-lookup"><span data-stu-id="fbc87-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="fbc87-147">Rozwiń sekcję **Sobota**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="fbc87-148">W polu **Zamknięte dla pobrania** wybierz opcję *Tak*.</span><span class="sxs-lookup"><span data-stu-id="fbc87-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="fbc87-149">Rozwiń sekcję **Niedziela**.</span><span class="sxs-lookup"><span data-stu-id="fbc87-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="fbc87-150">W polu **Zamknięte dla pobrania** wybierz opcję *Tak*.</span><span class="sxs-lookup"><span data-stu-id="fbc87-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]