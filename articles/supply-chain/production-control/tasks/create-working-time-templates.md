---
title: Tworzenie szablonów czasu pracy
description: Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e8e43900fd25f0051124d761dc7b06d4f9313a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006823"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="24927-103">Tworzenie szablonów czasu pracy</span><span class="sxs-lookup"><span data-stu-id="24927-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="24927-104">Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.</span><span class="sxs-lookup"><span data-stu-id="24927-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="24927-105">W tej procedurze pokazano sposób definiowania szablonu czasu pracy za pomocą właściwości planowania czasu pracy w celu kategoryzowania zakresów czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="24927-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="24927-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="24927-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="24927-107">Wybierz kolejno opcje Wszystkie obszary robocze > Zarządzanie cyklem życia zasobu.</span><span class="sxs-lookup"><span data-stu-id="24927-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="24927-108">Kliknij opcję Szablony czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="24927-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="24927-109">Tworzenie szablonu czasu pracy</span><span class="sxs-lookup"><span data-stu-id="24927-109">Create working time template</span></span>
1. <span data-ttu-id="24927-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="24927-110">Click New.</span></span>
2. <span data-ttu-id="24927-111">W polu Szablon czasu pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="24927-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="24927-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="24927-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="24927-113">Rozwiń sekcję Poniedziałek.</span><span class="sxs-lookup"><span data-stu-id="24927-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="24927-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="24927-114">Click Add.</span></span>
6. <span data-ttu-id="24927-115">W polu Od wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="24927-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="24927-116">Określ godzinę rozpoczynania pracy rano.</span><span class="sxs-lookup"><span data-stu-id="24927-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="24927-117">W polu Do wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="24927-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="24927-118">Określ godzinę, kiedy pracownicy zaczynają przerwę na obiad.</span><span class="sxs-lookup"><span data-stu-id="24927-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="24927-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="24927-119">Click Add.</span></span>
9. <span data-ttu-id="24927-120">W polu Od wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="24927-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="24927-121">Określ godzinę, kiedy pracownicy wznawiają pracę po obiedzie.</span><span class="sxs-lookup"><span data-stu-id="24927-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="24927-122">W polu Do wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="24927-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="24927-123">Określ godzinę zakończenia dnia pracy.</span><span class="sxs-lookup"><span data-stu-id="24927-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="24927-124">Replikowanie czasów pracy do wszystkich dni tygodnia</span><span class="sxs-lookup"><span data-stu-id="24927-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="24927-125">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="24927-125">Click Copy day.</span></span>
    * <span data-ttu-id="24927-126">Skopiuj definicje czasu pracy z poniedziałku do wtorku.</span><span class="sxs-lookup"><span data-stu-id="24927-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="24927-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="24927-127">Click OK.</span></span>
3. <span data-ttu-id="24927-128">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="24927-128">Click Copy day.</span></span>
    * <span data-ttu-id="24927-129">Skopiuj definicje czasu pracy z poniedziałku do środy.</span><span class="sxs-lookup"><span data-stu-id="24927-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="24927-130">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="24927-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="24927-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="24927-131">Click OK.</span></span>
6. <span data-ttu-id="24927-132">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="24927-132">Click Copy day.</span></span>
    * <span data-ttu-id="24927-133">Skopiuj definicje czasu pracy z poniedziałku do czwartku.</span><span class="sxs-lookup"><span data-stu-id="24927-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="24927-134">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="24927-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="24927-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="24927-135">Click OK.</span></span>
9. <span data-ttu-id="24927-136">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="24927-136">Click Copy day.</span></span>
    * <span data-ttu-id="24927-137">Skopiuj definicje czasu pracy z poniedziałku do piątku.</span><span class="sxs-lookup"><span data-stu-id="24927-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="24927-138">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="24927-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="24927-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="24927-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="24927-140">Definiowanie przedziałów czasu dla operacji specjalnych</span><span class="sxs-lookup"><span data-stu-id="24927-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="24927-141">Rozwiń sekcję Piątek.</span><span class="sxs-lookup"><span data-stu-id="24927-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="24927-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="24927-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="24927-143">W polu Właściwość wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24927-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="24927-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="24927-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="24927-145">W polu Właściwość wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24927-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="24927-146">Oznaczanie dni weekendowych jako zamkniętych dla pobierania</span><span class="sxs-lookup"><span data-stu-id="24927-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="24927-147">Rozwiń sekcję Sobota.</span><span class="sxs-lookup"><span data-stu-id="24927-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="24927-148">W polu Zamknięte dla pobrania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24927-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="24927-149">Rozwiń sekcję Niedziela.</span><span class="sxs-lookup"><span data-stu-id="24927-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="24927-150">W polu Zamknięte dla pobrania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24927-150">Select Yes in the Closed for pickup field.</span></span>

