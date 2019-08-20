---
title: Konfigurowanie szablonu pracy dla zamówień zakupu
description: Ta procedura skupia się na konfigurowaniu prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 16a8b2d80e6d5445d57c171ddb4456dd8db5ecde
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847046"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="88a39-103">Konfigurowanie szablonu pracy dla zamówień zakupu</span><span class="sxs-lookup"><span data-stu-id="88a39-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="88a39-104">Ta procedura skupia się na konfigurowaniu prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów.</span><span class="sxs-lookup"><span data-stu-id="88a39-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="88a39-105">Szablony pracy decydują o zbiorze instrukcji przedstawianych pracownikowi magazynu na urządzeniu przenośnym w trakcie przenoszenia towarów w obszarze przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="88a39-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="88a39-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="88a39-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="88a39-107">Przed rozpoczęciem tego przewodnika należy utworzyć identyfikator puli pracy.</span><span class="sxs-lookup"><span data-stu-id="88a39-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="88a39-108">W tym przykładzie jest używany identyfikator puli pracy o nazwie w Przychodzące.</span><span class="sxs-lookup"><span data-stu-id="88a39-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="88a39-109">Ta procedura jest przeznaczona dla kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="88a39-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="88a39-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="88a39-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="88a39-111">W polu Typ zlecenia zaznacz opcję „Zamówienia zakupu”.</span><span class="sxs-lookup"><span data-stu-id="88a39-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="88a39-112">Tworzenie nagłówka szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="88a39-112">Create a work template header</span></span>
1. <span data-ttu-id="88a39-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="88a39-113">Click New.</span></span>
2. <span data-ttu-id="88a39-114">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="88a39-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="88a39-115">Jest to kolejność, w jakiej są sprawdzane szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="88a39-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="88a39-116">Można zmienić taką sekwencję, jeśli trzeba.</span><span class="sxs-lookup"><span data-stu-id="88a39-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="88a39-117">W polu Szablon pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88a39-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="88a39-118">Jest to unikatowy identyfikator tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88a39-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="88a39-119">W polu Opis szablonu pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88a39-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="88a39-120">Opcja Prawidłowe zostanie zaznaczona dopiero wtedy, gdy wprowadzisz wszystkie informacje wymagane przez szablon, a następnie klikniesz przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88a39-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="88a39-121">Zlecenie typu Zamówienie zakupu nie może być przetwarzane automatycznie, więc pozostaw w opcji Przetwarzanie automatyczne wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="88a39-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="88a39-122">W polu Identyfikator puli pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88a39-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="88a39-123">Identyfikatory pul pracy umożliwiają organizowanie prac w grupy.</span><span class="sxs-lookup"><span data-stu-id="88a39-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="88a39-124">Wartość ustawiona w tym polu będzie domyślną wartością dla każdej pracy utworzonej na podstawie tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88a39-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="88a39-125">W polu Priorytet pracy wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="88a39-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="88a39-126">To wskazuje istotność pracy, a wartość ustawiona w tym polu będzie domyślna dla każdej pracy utworzonej za pomocą tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88a39-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="88a39-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88a39-127">Click Save.</span></span>
    * <span data-ttu-id="88a39-128">Zanim przycisk Edytuj kwerendę zostanie uaktywniony, należy zapisać nagłówek szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="88a39-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="88a39-129">Konfigurowanie zapytania dla szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="88a39-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="88a39-130">Kliknij opcję Edytuj kwerendę.</span><span class="sxs-lookup"><span data-stu-id="88a39-130">Click Edit query.</span></span>
    * <span data-ttu-id="88a39-131">Ustawimy ograniczenie, że szablon może być używany tylko w ramach określonego magazynu.</span><span class="sxs-lookup"><span data-stu-id="88a39-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="88a39-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="88a39-132">Click Add.</span></span>
3. <span data-ttu-id="88a39-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="88a39-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="88a39-134">W polu Pole wpisz wartość „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="88a39-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="88a39-135">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88a39-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="88a39-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="88a39-136">Click OK.</span></span>
7. <span data-ttu-id="88a39-137">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="88a39-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="88a39-138">Konfigurowanie szczegółów szablonu pracy</span><span class="sxs-lookup"><span data-stu-id="88a39-138">Set work template details</span></span>
1. <span data-ttu-id="88a39-139">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="88a39-139">Click New.</span></span>
2. <span data-ttu-id="88a39-140">W polu Typ pracy zaznacz opcję „Pobranie”.</span><span class="sxs-lookup"><span data-stu-id="88a39-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="88a39-141">W polu Identyfikator klasy roboczej wpisz „zakup”.</span><span class="sxs-lookup"><span data-stu-id="88a39-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="88a39-142">Klasa pracy ustawiona w tym miejscu będzie domyślna we wszystkich wierszach pracy typu Pobranie, które są tworzone za pomocą tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="88a39-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="88a39-143">Klasy pracy nie można zastąpić z poziomu wierszy zamówienia.</span><span class="sxs-lookup"><span data-stu-id="88a39-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="88a39-144">Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownik magazynu może przetwarzać na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="88a39-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="88a39-145">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="88a39-145">Click New.</span></span>
5. <span data-ttu-id="88a39-146">W polu Typ pracy zaznacz opcję „Odłożenie”.</span><span class="sxs-lookup"><span data-stu-id="88a39-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="88a39-147">W polu Identyfikator klasy roboczej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="88a39-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="88a39-148">Instrukcje pobierania i odkładania są zestawem.</span><span class="sxs-lookup"><span data-stu-id="88a39-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="88a39-149">Każdy zestaw pobrania/odłożenia musi mieć tę samą klasę pracy.</span><span class="sxs-lookup"><span data-stu-id="88a39-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="88a39-150">Użyj tej samej klasy pracy, jak podana w instrukcji pobrania.</span><span class="sxs-lookup"><span data-stu-id="88a39-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="88a39-151">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="88a39-151">Click Save.</span></span>
    * <span data-ttu-id="88a39-152">Należy zwrócić uwagę, że pole wyboru Prawidłowe jest teraz zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="88a39-152">Note that the Valid checkbox is now checked.</span></span>  

