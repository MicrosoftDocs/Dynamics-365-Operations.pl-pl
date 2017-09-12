---
title: "Częściowa inwentaryzacja ciągła w lokalizacji"
description: "Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji. Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2ee4de8eabc55271e272ca3026746787353f5fc3
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="45461-105">Częściowa inwentaryzacja ciągła w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="45461-105">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="45461-106">Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="45461-106">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="45461-107">Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="45461-107">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="45461-108">Tworząc pracę inwentaryzacji za pomocą planów inwentaryzacji ciągłej, można decydować o faktycznym przebiegu operacji inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="45461-108">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="45461-109">Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="45461-109">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="45461-110">Wyfiltrowując określone produkty, kierownik magazynu może zmniejszyć pracochłonność przeglądu, uniknąć błędów konsolidacji i zaoszczędzić czas.</span><span class="sxs-lookup"><span data-stu-id="45461-110">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="45461-111">Jak skonfigurować częściową inwentaryzację ciągłą w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="45461-111">How to configure partial location cycle counting</span></span>
<span data-ttu-id="45461-112">Jeśli do operacji inwentaryzacji wykorzystujesz proces pracy magazynowej, dla każdej lokalizacji jest tworzony nagłówek pracy.</span><span class="sxs-lookup"><span data-stu-id="45461-112">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="45461-113">Podczas definiowaniu planu inwentaryzacji ciągłej można użyć zapytania **Wybierz lokalizacje**, aby ograniczyć tworzoną pracę inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="45461-113">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="45461-114">Po wybraniu produktów do planu inwentaryzacji ciągłej można użyć zapytań o produkty i wariantu produktów w celu doprecyzowania zakresu inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="45461-114">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="45461-115">Można skojarzyć **szablon pracy** z planem inwentaryzacji ciągłej w celu zdefiniowania sposobu tworzenia pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="45461-115">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="45461-116">Szablon pracy operacji inwentaryzacji wywoływany bezpośrednio z planu inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="45461-116">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="45461-117">Definiując szczegóły szablonu pracy, można użyć opcji **Podziały wierszy pracy** i określić, czy wiersze pracy inwentaryzacji mają być grupowane według numeru towaru, czy numeru wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="45461-117">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="45461-118">Ta konfiguracja jest wymagana, jeśli mają być inwentaryzowane dostępne zapasy tylko dla określonych produktów w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="45461-118">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="45461-119">Tworzone wiersze pracy inwentaryzacji ciągłej będą miały poziom informacji zdefiniowany w tym miejscu i sterowane operacje inwentaryzacji będą obsługiwane na podstawie tego poziomu.</span><span class="sxs-lookup"><span data-stu-id="45461-119">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="45461-120">Jeśli skojarzysz plany inwentaryzacji ciągłej z szablonami pracy za pomocą opcji **Podziały wierszy pracy**, dla tworzonej pracy inwentaryzacji ciągłej zostanie zaznaczone pole **Częściowa inwentaryzacja ciągła** oraz zostanie utworzonych wiele wierszy pracy inwentaryzacji, zgodnie z definicją szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="45461-120">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="45461-121">Aby można było wykonywać pracę częściowej inwentaryzacji ciągłej, należy co najmniej zaznaczyć w menu urządzenia komórkowego opcję **Wyświetl kod pozycji** w konfiguracji inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="45461-121">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="45461-122">Operator magazynu będzie musiał rejestrować tylko dane inwentaryzacji powiązane z wierszami inwentaryzacji (numerami towarów i wymiarami produktów).</span><span class="sxs-lookup"><span data-stu-id="45461-122">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="45461-123">W tym procesie inwentaryzacji wszystkie pozostałe dostępne zapasy będą ignorowane.</span><span class="sxs-lookup"><span data-stu-id="45461-123">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="45461-124">W procesie częściowej inwentaryzacji ciągłej pole daty/godziny **Ostatnie obliczenie cyklu** nie będzie aktualizowane dla lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="45461-124">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="45461-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="45461-125">Example</span></span>
<span data-ttu-id="45461-126">W tym przykładzie musi być inwentaryzowany tylko towar o numerze A0001 w magazynie 61.</span><span class="sxs-lookup"><span data-stu-id="45461-126">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="45461-127">Zostanie utworzony nowy szablon pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="45461-127">A new work template for cycle counting is created.</span></span> <span data-ttu-id="45461-128">Opcja **Podziały wierszy pracy** służy do grupowania wierszy pracy inwentaryzacji według numerów towarów.</span><span class="sxs-lookup"><span data-stu-id="45461-128">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="45461-129">W związku z tym tworzona praca inwentaryzacji ciągłej będzie miała wiersze dla każdego numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="45461-129">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="45461-130">Można również grupować wiersze według numeru wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="45461-130">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="45461-131">Tworzony jest nowy plan inwentaryzacji ciągłej, który odwołuje się do nowo utworzonego szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="45461-131">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="45461-132">Plan inwentaryzacji ciągłej zawiera wszystkie lokalizacje w magazynie 61 (zapytanie **Wybierz lokalizacje**) przechowujące zapasy towaru o kodzie A0001.</span><span class="sxs-lookup"><span data-stu-id="45461-132">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="45461-133">Wybór określonych produktów jest definiowany w sekcji **Wybory produktów do inwentaryzacji ciągłej**.</span><span class="sxs-lookup"><span data-stu-id="45461-133">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="45461-134">Można wybrać produkty do planów inwentaryzacji poprzez ustawienie w polu **Puste lokalizacje** wartości **Wyklucz puste**. W trakcie przetwarzania planu inwentaryzacji ciągłej jest tworzona praca częściowej inwentaryzacji ciągłej towaru o numerze A0001.</span><span class="sxs-lookup"><span data-stu-id="45461-134">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="45461-135">Faktyczny proces inwentaryzacji można przeprowadzić przy użyciu elementu menu wspomaganej inwentaryzacji ciągłej na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="45461-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="45461-136">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="45461-136">See also</span></span>
--------

[<span data-ttu-id="45461-137">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="45461-137">Cycle counting</span></span>](cycle-counting.md)


