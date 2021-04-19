---
title: Tworzenie szablonu BOM
description: Szablon BOM można utworzyć przy użyciu różnych metod.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 781df7611ec1e3ee9d3013f971232700df38ada0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836309"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="439df-103">Tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="439df-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="439df-104">Szablon BOM można utworzyć przy użyciu dowolnej z niżej opisanych metod.</span><span class="sxs-lookup"><span data-stu-id="439df-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="439df-105">W przypadku wszystkich metod pola **Od dnia** i **Do dnia** są opcjonalne i mają wyłącznie charakter informacyjny.</span><span class="sxs-lookup"><span data-stu-id="439df-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="439df-106">Ręczne tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="439df-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="439df-107">Przejdź do **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-107">Go to **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="439df-108">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-108">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="439df-109">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="439df-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="439df-110">W polu **Numer pozycji** wprowadź towar o typie **BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="439df-111">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="439df-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="439df-112">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="439df-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="439df-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="439df-113">Select **OK**.</span></span>

<span data-ttu-id="439df-114">Zostanie utworzony nowy, pusty szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="439df-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="439df-115">Tworzenie szablonu BOM na podstawie innego szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="439df-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="439df-116">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-116">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="439df-117">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-117">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="439df-118">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="439df-119">W polu **Numer odwołania** wybierz istniejący szablon BOM, który ma zostać skopiowany do nowego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="439df-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="439df-120">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="439df-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="439df-121">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="439df-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="439df-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="439df-122">Select **OK**.</span></span>

<span data-ttu-id="439df-123">Zostanie utworzony nowy szablon BOM przy użyciu wierszy odpowiadających wierszom pierwotnego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="439df-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="439df-124">Tworzenie szablonu BOM na podstawie towaru BOM</span><span class="sxs-lookup"><span data-stu-id="439df-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="439df-125">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-125">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="439df-126">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-126">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="439df-127">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="439df-128">W polu **Numer odwołania** wybierz wersję BOM.</span><span class="sxs-lookup"><span data-stu-id="439df-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="439df-129">Towar typu BOM zostanie skopiowany do pola **Numer pozycji**.</span><span class="sxs-lookup"><span data-stu-id="439df-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="439df-130">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="439df-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="439df-131">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="439df-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="439df-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="439df-132">Select **OK**.</span></span>

<span data-ttu-id="439df-133">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **Listy składowe (BOM)**.</span><span class="sxs-lookup"><span data-stu-id="439df-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="439df-134">Tworzenie szablonu BOM na podstawie BOM produkcji</span><span class="sxs-lookup"><span data-stu-id="439df-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="439df-135">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-135">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="439df-136">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-136">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="439df-137">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="439df-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="439df-138">W polu **Numer odwołania** wybierz BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="439df-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="439df-139">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="439df-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="439df-140">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="439df-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="439df-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="439df-141">Select **OK**.</span></span>

<span data-ttu-id="439df-142">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **BOM**.</span><span class="sxs-lookup"><span data-stu-id="439df-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="439df-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="439df-143">See also</span></span>

[<span data-ttu-id="439df-144">Szablony BOM </span><span class="sxs-lookup"><span data-stu-id="439df-144">Template BOMs</span></span>](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]