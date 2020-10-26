---
title: Tworzenie szablonu BOM
description: Szablon BOM można utworzyć przy użyciu różnych metod.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2e06283f3b95c5ff6b4376bba63cf5a42d5feeb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981824"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="d8f21-103">Tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="d8f21-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d8f21-104">Szablon BOM można utworzyć przy użyciu dowolnej z niżej opisanych metod.</span><span class="sxs-lookup"><span data-stu-id="d8f21-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="d8f21-105">W przypadku wszystkich metod pola **Od dnia** i **Do dnia** są opcjonalne i mają wyłącznie charakter informacyjny.</span><span class="sxs-lookup"><span data-stu-id="d8f21-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="d8f21-106">Ręczne tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="d8f21-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="d8f21-107">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="d8f21-108">Naciśnij kombinację klawiszy CTRL+N, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="d8f21-109">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="d8f21-110">W polu **Numer pozycji** wprowadź towar o typie **BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="d8f21-111">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="d8f21-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="d8f21-112">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="d8f21-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="d8f21-113">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="d8f21-113">Click **OK**.</span></span>

<span data-ttu-id="d8f21-114">Zostanie utworzony nowy, pusty szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="d8f21-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="d8f21-115">Tworzenie szablonu BOM na podstawie innego szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="d8f21-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="d8f21-116">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="d8f21-117">Naciśnij kombinację klawiszy CTRL+N, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="d8f21-118">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="d8f21-119">W polu **Numer odwołania** wybierz istniejący szablon BOM, który ma zostać skopiowany do nowego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="d8f21-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="d8f21-120">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="d8f21-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="d8f21-121">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="d8f21-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="d8f21-122">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="d8f21-122">Click **OK**.</span></span>

<span data-ttu-id="d8f21-123">Zostanie utworzony nowy szablon BOM przy użyciu wierszy odpowiadających wierszom pierwotnego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="d8f21-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="d8f21-124">Tworzenie szablonu BOM na podstawie towaru BOM</span><span class="sxs-lookup"><span data-stu-id="d8f21-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="d8f21-125">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="d8f21-126">Naciśnij kombinację klawiszy CTRL+N, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="d8f21-127">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="d8f21-128">W polu **Numer odwołania** wybierz wersję BOM.</span><span class="sxs-lookup"><span data-stu-id="d8f21-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="d8f21-129">Towar typu BOM zostanie skopiowany do pola **Numer pozycji**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="d8f21-130">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="d8f21-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="d8f21-131">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="d8f21-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="d8f21-132">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="d8f21-132">Click **OK**.</span></span>

<span data-ttu-id="d8f21-133">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **Listy składowe (BOM)**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="d8f21-134">Tworzenie szablonu BOM na podstawie BOM produkcji</span><span class="sxs-lookup"><span data-stu-id="d8f21-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="d8f21-135">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="d8f21-136">Naciśnij kombinację klawiszy CTRL+N, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="d8f21-137">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="d8f21-138">W polu **Numer odwołania** wybierz BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="d8f21-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="d8f21-139">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="d8f21-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="d8f21-140">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="d8f21-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="d8f21-141">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="d8f21-141">Click **OK**.</span></span>

<span data-ttu-id="d8f21-142">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **BOM**.</span><span class="sxs-lookup"><span data-stu-id="d8f21-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8f21-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d8f21-143">See also</span></span>

[<span data-ttu-id="d8f21-144">Szablony BOM </span><span class="sxs-lookup"><span data-stu-id="d8f21-144">Template BOMs</span></span>](template-boms.md)

  


