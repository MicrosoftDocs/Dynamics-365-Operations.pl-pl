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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5bd1b384fe66dd7d59b776bdf1154cc5b8262ce
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434930"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="8f071-103">Tworzenie szablonów czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8f071-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8f071-104">Szablony czasu pracy określają godziny pracy w tygodniu i są używane do generowania czasów pracy w wybranych okresach.</span><span class="sxs-lookup"><span data-stu-id="8f071-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="8f071-105">W tej procedurze pokazano sposób definiowania szablonu czasu pracy za pomocą właściwości planowania czasu pracy w celu kategoryzowania zakresów czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="8f071-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="8f071-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="8f071-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="8f071-107">Wybierz kolejno opcje Wszystkie obszary robocze > Zarządzanie cyklem życia zasobu.</span><span class="sxs-lookup"><span data-stu-id="8f071-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="8f071-108">Kliknij opcję Szablony czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="8f071-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="8f071-109">Tworzenie szablonu czasu pracy</span><span class="sxs-lookup"><span data-stu-id="8f071-109">Create working time template</span></span>
1. <span data-ttu-id="8f071-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8f071-110">Click New.</span></span>
2. <span data-ttu-id="8f071-111">W polu Szablon czasu pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f071-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="8f071-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f071-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8f071-113">Rozwiń sekcję Poniedziałek.</span><span class="sxs-lookup"><span data-stu-id="8f071-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="8f071-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8f071-114">Click Add.</span></span>
6. <span data-ttu-id="8f071-115">W polu Od wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="8f071-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="8f071-116">Określ godzinę rozpoczynania pracy rano.</span><span class="sxs-lookup"><span data-stu-id="8f071-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="8f071-117">W polu Do wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="8f071-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="8f071-118">Określ godzinę, kiedy pracownicy zaczynają przerwę na obiad.</span><span class="sxs-lookup"><span data-stu-id="8f071-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="8f071-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="8f071-119">Click Add.</span></span>
9. <span data-ttu-id="8f071-120">W polu Od wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="8f071-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="8f071-121">Określ godzinę, kiedy pracownicy wznawiają pracę po obiedzie.</span><span class="sxs-lookup"><span data-stu-id="8f071-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="8f071-122">W polu Do wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="8f071-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="8f071-123">Określ godzinę zakończenia dnia pracy.</span><span class="sxs-lookup"><span data-stu-id="8f071-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="8f071-124">Replikowanie czasów pracy do wszystkich dni tygodnia</span><span class="sxs-lookup"><span data-stu-id="8f071-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="8f071-125">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="8f071-125">Click Copy day.</span></span>
    * <span data-ttu-id="8f071-126">Skopiuj definicje czasu pracy z poniedziałku do wtorku.</span><span class="sxs-lookup"><span data-stu-id="8f071-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="8f071-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f071-127">Click OK.</span></span>
3. <span data-ttu-id="8f071-128">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="8f071-128">Click Copy day.</span></span>
    * <span data-ttu-id="8f071-129">Skopiuj definicje czasu pracy z poniedziałku do środy.</span><span class="sxs-lookup"><span data-stu-id="8f071-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="8f071-130">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="8f071-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="8f071-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f071-131">Click OK.</span></span>
6. <span data-ttu-id="8f071-132">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="8f071-132">Click Copy day.</span></span>
    * <span data-ttu-id="8f071-133">Skopiuj definicje czasu pracy z poniedziałku do czwartku.</span><span class="sxs-lookup"><span data-stu-id="8f071-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="8f071-134">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="8f071-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="8f071-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f071-135">Click OK.</span></span>
9. <span data-ttu-id="8f071-136">Kliknij opcję Kopiuj dzień.</span><span class="sxs-lookup"><span data-stu-id="8f071-136">Click Copy day.</span></span>
    * <span data-ttu-id="8f071-137">Skopiuj definicje czasu pracy z poniedziałku do piątku.</span><span class="sxs-lookup"><span data-stu-id="8f071-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="8f071-138">W polu Do dnia roboczego wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="8f071-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="8f071-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8f071-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="8f071-140">Definiowanie przedziałów czasu dla operacji specjalnych</span><span class="sxs-lookup"><span data-stu-id="8f071-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="8f071-141">Rozwiń sekcję Piątek.</span><span class="sxs-lookup"><span data-stu-id="8f071-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="8f071-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8f071-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8f071-143">W polu Właściwość wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f071-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="8f071-144">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8f071-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8f071-145">W polu Właściwość wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="8f071-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="8f071-146">Oznaczanie dni weekendowych jako zamkniętych dla pobierania</span><span class="sxs-lookup"><span data-stu-id="8f071-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="8f071-147">Rozwiń sekcję Sobota.</span><span class="sxs-lookup"><span data-stu-id="8f071-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="8f071-148">W polu Zamknięte dla pobrania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8f071-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="8f071-149">Rozwiń sekcję Niedziela.</span><span class="sxs-lookup"><span data-stu-id="8f071-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="8f071-150">W polu Zamknięte dla pobrania wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="8f071-150">Select Yes in the Closed for pickup field.</span></span>

