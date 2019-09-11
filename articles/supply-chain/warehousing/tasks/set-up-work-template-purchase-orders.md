---
title: Konfigurowanie szablonu pracy dla zamówień zakupu
description: W tym temacie opisano konfigurowanie prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227a6865df826caf8ce154f9c44ebe082acd76a5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916750"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="37532-103">Konfigurowanie szablonu pracy dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="37532-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="37532-104">W tym temacie opisano konfigurowanie prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów.</span><span class="sxs-lookup"><span data-stu-id="37532-104">This topic describes how to set up a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="37532-105">Szablony pracy decydują o zbiorze instrukcji przedstawianych pracownikowi magazynu na urządzeniu przenośnym w trakcie przenoszenia towarów w obszarze przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="37532-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="37532-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="37532-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="37532-107">Przed rozpoczęciem tego przewodnika należy utworzyć identyfikator puli pracy.</span><span class="sxs-lookup"><span data-stu-id="37532-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="37532-108">W tym przykładzie jest używany identyfikator puli pracy o nazwie w Przychodzące.</span><span class="sxs-lookup"><span data-stu-id="37532-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="37532-109">Ta procedura jest przeznaczona dla kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="37532-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="37532-110">W okienku nawigacji przejdź do **Moduły > Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy**.</span><span class="sxs-lookup"><span data-stu-id="37532-110">In the navigation pane, go to **Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="37532-111">W polu **Typ zlecenia pracy** zaznacz opcję **Zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="37532-111">In the **Work order type** field, select **Purchase orders**.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="37532-112">Tworzenie nagłówka szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="37532-112">Create a work template header</span></span>
1. <span data-ttu-id="37532-113">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="37532-113">Select **New**.</span></span>
2. <span data-ttu-id="37532-114">W polu **Numer sekwencyjny** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="37532-114">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="37532-115">Jest to kolejność, w jakiej są sprawdzane szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="37532-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="37532-116">Można zmienić taką sekwencję, jeśli trzeba.</span><span class="sxs-lookup"><span data-stu-id="37532-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="37532-117">W polu **Szablon pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="37532-117">In the **Work template** field, type a value.</span></span> <span data-ttu-id="37532-118">Jest to unikatowy identyfikator tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="37532-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="37532-119">W polu **Opis szablonu pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="37532-119">In the **Work template description** field, type a value.</span></span>
    - <span data-ttu-id="37532-120">Opcja **Ważne** zostanie zaznaczona dopiero wtedy, gdy wprowadzisz wszystkie informacje wymagane przez szablon, a następnie klikniesz przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37532-120">The **Valid** option will not be checked until you’ve completed all the information that's needed by the template and have then selected **Save**.</span></span>  
    - <span data-ttu-id="37532-121">Zlecenie typu **Zamówienie zakupu** nie może być przetwarzane automatycznie, więc pozostaw w opcji **Przetwarzanie automatyczne** wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="37532-121">A work order of type **Purchase order** cannot be automatically processed, so leave the **Automatically process** option set to **No**.</span></span>  
5. <span data-ttu-id="37532-122">W polu **Identyfikator puli pracy** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="37532-122">In the **Work pool ID** field, type a value.</span></span> <span data-ttu-id="37532-123">Identyfikatory pul pracy umożliwiają organizowanie prac w grupy.</span><span class="sxs-lookup"><span data-stu-id="37532-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="37532-124">Wartość ustawiona w tym polu będzie domyślną wartością dla każdej pracy utworzonej na podstawie tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="37532-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="37532-125">W polu **Priorytet pracy** wpisz `1`.</span><span class="sxs-lookup"><span data-stu-id="37532-125">In the **Work priority** field, enter `1`.</span></span> <span data-ttu-id="37532-126">To wskazuje istotność pracy, a wartość ustawiona w tym polu będzie domyślna dla każdej pracy utworzonej za pomocą tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="37532-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="37532-127">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37532-127">Select **Save**.</span></span> <span data-ttu-id="37532-128">Zanim przycisk **Edytuj zapytanie** zostanie uaktywniony, należy zapisać nagłówek szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="37532-128">You must save the work template header before the **Edit Query** button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="37532-129">Konfigurowanie zapytania dla szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="37532-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="37532-130">Wybierz **Edytuj zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="37532-130">Select **Edit query**.</span></span> <span data-ttu-id="37532-131">Ustawimy ograniczenie, że szablon może być używany tylko w ramach określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="37532-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="37532-132">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="37532-132">Select **Add**.</span></span>
3. <span data-ttu-id="37532-133">W polu **Dziedzina** w nowym wierszu wpisz `warehouse`.</span><span class="sxs-lookup"><span data-stu-id="37532-133">In the **Field** field of the new row, type `warehouse`.</span></span>
4. <span data-ttu-id="37532-134">W polu **Kryteria** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="37532-134">In the **Criteria** field, type a value.</span></span>
5. <span data-ttu-id="37532-135">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="37532-135">Select **OK**.</span></span>
6. <span data-ttu-id="37532-136">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="37532-136">Select **Yes**.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="37532-137">Konfigurowanie szczegółów szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="37532-137">Set work template details</span></span>
1. <span data-ttu-id="37532-138">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="37532-138">Select **New**.</span></span>
2. <span data-ttu-id="37532-139">W polu **Typ pracy** zaznacz opcję **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="37532-139">In the **Work type** field, select **Pick**.</span></span>
3. <span data-ttu-id="37532-140">W polu **Identyfikator klasy roboczej** wpisz `purchase`.</span><span class="sxs-lookup"><span data-stu-id="37532-140">In the **Work class ID** field, type `purchase`.</span></span> <span data-ttu-id="37532-141">Klasa pracy ustawiona w tym miejscu będzie domyślna we wszystkich wierszach pracy typu Pobranie, które są tworzone za pomocą tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="37532-141">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="37532-142">Klasy pracy nie można zastąpić z poziomu wierszy zamówienia.</span><span class="sxs-lookup"><span data-stu-id="37532-142">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="37532-143">Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownik magazynu może przetwarzać na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="37532-143">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="37532-144">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="37532-144">Select **New**.</span></span>
5. <span data-ttu-id="37532-145">W polu **Typ pracy** zaznacz opcję **Odłożenie**.</span><span class="sxs-lookup"><span data-stu-id="37532-145">In the **Work type** field, select **Put**.</span></span>
6. <span data-ttu-id="37532-146">W polu **Identyfikator klasy roboczej** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="37532-146">In the **Work class ID** field, type a value.</span></span> <span data-ttu-id="37532-147">Instrukcje pobierania i odkładania są zestawem.</span><span class="sxs-lookup"><span data-stu-id="37532-147">The pick and put instructions are a set.</span></span> <span data-ttu-id="37532-148">Każdy zestaw pobrania/odłożenia musi mieć tę samą klasę pracy.</span><span class="sxs-lookup"><span data-stu-id="37532-148">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="37532-149">Użyj tej samej klasy pracy, jak podana w instrukcji pobrania.</span><span class="sxs-lookup"><span data-stu-id="37532-149">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="37532-150">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="37532-150">Select **Save**.</span></span> <span data-ttu-id="37532-151">Należy zwrócić uwagę, że pole wyboru **Ważne** jest teraz zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="37532-151">Note that the **Valid** checkbox is now checked.</span></span>  

