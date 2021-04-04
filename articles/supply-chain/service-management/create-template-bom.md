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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5afcb8171b674281faf8100d5c01fdff8d6ff764
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470792"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="f91ed-103">Tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="f91ed-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f91ed-104">Szablon BOM można utworzyć przy użyciu dowolnej z niżej opisanych metod.</span><span class="sxs-lookup"><span data-stu-id="f91ed-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="f91ed-105">W przypadku wszystkich metod pola **Od dnia** i **Do dnia** są opcjonalne i mają wyłącznie charakter informacyjny.</span><span class="sxs-lookup"><span data-stu-id="f91ed-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="f91ed-106">Ręczne tworzenie szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="f91ed-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="f91ed-107">Przejdź do **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-107">Go to **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f91ed-108">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-108">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f91ed-109">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="f91ed-110">W polu **Numer pozycji** wprowadź towar o typie **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="f91ed-111">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="f91ed-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f91ed-112">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="f91ed-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f91ed-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-113">Select **OK**.</span></span>

<span data-ttu-id="f91ed-114">Zostanie utworzony nowy, pusty szablon BOM.</span><span class="sxs-lookup"><span data-stu-id="f91ed-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="f91ed-115">Tworzenie szablonu BOM na podstawie innego szablonu BOM</span><span class="sxs-lookup"><span data-stu-id="f91ed-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="f91ed-116">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-116">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f91ed-117">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-117">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f91ed-118">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="f91ed-119">W polu **Numer odwołania** wybierz istniejący szablon BOM, który ma zostać skopiowany do nowego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="f91ed-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="f91ed-120">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="f91ed-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f91ed-121">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="f91ed-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f91ed-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-122">Select **OK**.</span></span>

<span data-ttu-id="f91ed-123">Zostanie utworzony nowy szablon BOM przy użyciu wierszy odpowiadających wierszom pierwotnego szablonu BOM.</span><span class="sxs-lookup"><span data-stu-id="f91ed-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="f91ed-124">Tworzenie szablonu BOM na podstawie towaru BOM</span><span class="sxs-lookup"><span data-stu-id="f91ed-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="f91ed-125">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-125">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f91ed-126">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-126">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f91ed-127">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="f91ed-128">W polu **Numer odwołania** wybierz wersję BOM.</span><span class="sxs-lookup"><span data-stu-id="f91ed-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="f91ed-129">Towar typu BOM zostanie skopiowany do pola **Numer pozycji**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="f91ed-130">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="f91ed-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f91ed-131">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="f91ed-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f91ed-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-132">Select **OK**.</span></span>

<span data-ttu-id="f91ed-133">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **Listy składowe (BOM)**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="f91ed-134">Tworzenie szablonu BOM na podstawie BOM produkcji</span><span class="sxs-lookup"><span data-stu-id="f91ed-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="f91ed-135">Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-135">Select **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="f91ed-136">Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-136">Select **New** to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="f91ed-137">W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Produkcja**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="f91ed-138">W polu **Numer odwołania** wybierz BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="f91ed-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="f91ed-139">W polu **Nazwa** nadaj nazwę szablonowi.</span><span class="sxs-lookup"><span data-stu-id="f91ed-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="f91ed-140">Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.</span><span class="sxs-lookup"><span data-stu-id="f91ed-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="f91ed-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-141">Select **OK**.</span></span>

<span data-ttu-id="f91ed-142">Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **BOM**.</span><span class="sxs-lookup"><span data-stu-id="f91ed-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f91ed-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f91ed-143">See also</span></span>

[<span data-ttu-id="f91ed-144">Szablony BOM </span><span class="sxs-lookup"><span data-stu-id="f91ed-144">Template BOMs</span></span>](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]