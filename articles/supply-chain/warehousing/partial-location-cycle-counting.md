---
title: Częściowa inwentaryzacja ciągła w lokalizacji
description: Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji. Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f07c7754dbe36334e8972d49edf9fb84a78f5d0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215684"
---
# <a name="partial-location-cycle-counting"></a><span data-ttu-id="bb698-104">Częściowa inwentaryzacja ciągła w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="bb698-104">Partial location cycle counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb698-105">Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="bb698-106">Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="bb698-107">Tworząc pracę inwentaryzacji za pomocą planów inwentaryzacji ciągłej, można decydować o faktycznym przebiegu operacji inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="bb698-108">Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="bb698-109">Wyfiltrowując określone produkty, kierownik magazynu może zmniejszyć pracochłonność przeglądu, uniknąć błędów konsolidacji i zaoszczędzić czas.</span><span class="sxs-lookup"><span data-stu-id="bb698-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="bb698-110">Jak skonfigurować częściową inwentaryzację ciągłą w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="bb698-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="bb698-111">Jeśli do operacji inwentaryzacji wykorzystujesz proces pracy magazynowej, dla każdej lokalizacji jest tworzony nagłówek pracy.</span><span class="sxs-lookup"><span data-stu-id="bb698-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="bb698-112">Podczas definiowaniu planu inwentaryzacji ciągłej można użyć zapytania **Wybierz lokalizacje**, aby ograniczyć tworzoną pracę inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="bb698-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="bb698-113">Po wybraniu produktów do planu inwentaryzacji ciągłej można użyć zapytań o produkty i wariantu produktów w celu doprecyzowania zakresu inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="bb698-114">Można skojarzyć **szablon pracy** z planem inwentaryzacji ciągłej w celu zdefiniowania sposobu tworzenia pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="bb698-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="bb698-115">Szablon pracy operacji inwentaryzacji wywoływany bezpośrednio z planu inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="bb698-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="bb698-116">Definiując szczegóły szablonu pracy, można użyć opcji **Podziały wierszy pracy** i określić, czy wiersze pracy inwentaryzacji mają być grupowane według numeru towaru, czy numeru wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="bb698-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="bb698-117">Ta konfiguracja jest wymagana, jeśli mają być inwentaryzowane dostępne zapasy tylko dla określonych produktów w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="bb698-118">Tworzone wiersze pracy inwentaryzacji ciągłej będą miały poziom informacji zdefiniowany w tym miejscu i sterowane operacje inwentaryzacji będą obsługiwane na podstawie tego poziomu.</span><span class="sxs-lookup"><span data-stu-id="bb698-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="bb698-119">Jeśli skojarzysz plany inwentaryzacji ciągłej z szablonami pracy za pomocą opcji **Podziały wierszy pracy**, dla tworzonej pracy inwentaryzacji ciągłej zostanie zaznaczone pole **Częściowa inwentaryzacja ciągła** oraz zostanie utworzonych wiele wierszy pracy inwentaryzacji, zgodnie z definicją szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="bb698-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="bb698-120">Aby można było wykonywać pracę częściowej inwentaryzacji ciągłej, należy co najmniej zaznaczyć w menu urządzenia komórkowego opcję **Wyświetl kod pozycji** w konfiguracji inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="bb698-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="bb698-121">Operator magazynu będzie musiał rejestrować tylko dane inwentaryzacji powiązane z wierszami inwentaryzacji (numerami towarów i wymiarami produktów).</span><span class="sxs-lookup"><span data-stu-id="bb698-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="bb698-122">W tym procesie inwentaryzacji wszystkie pozostałe dostępne zapasy będą ignorowane.</span><span class="sxs-lookup"><span data-stu-id="bb698-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="bb698-123">W procesie częściowej inwentaryzacji ciągłej pole daty/godziny **Ostatnie obliczenie cyklu** nie będzie aktualizowane dla lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bb698-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="bb698-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb698-124">Example</span></span>
<span data-ttu-id="bb698-125">W tym przykładzie musi być inwentaryzowany tylko towar o numerze A0001 w magazynie 61.</span><span class="sxs-lookup"><span data-stu-id="bb698-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="bb698-126">Zostanie utworzony nowy szablon pracy inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="bb698-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="bb698-127">Opcja **Podziały wierszy pracy** służy do grupowania wierszy pracy inwentaryzacji według numerów towarów.</span><span class="sxs-lookup"><span data-stu-id="bb698-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="bb698-128">W związku z tym tworzona praca inwentaryzacji ciągłej będzie miała wiersze dla każdego numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="bb698-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="bb698-129">Można również grupować wiersze według numeru wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="bb698-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="bb698-130">Tworzony jest nowy plan inwentaryzacji ciągłej, który odwołuje się do nowo utworzonego szablonu pracy.</span><span class="sxs-lookup"><span data-stu-id="bb698-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="bb698-131">Plan inwentaryzacji ciągłej zawiera wszystkie lokalizacje w magazynie 61 (zapytanie **Wybierz lokalizacje**) przechowujące zapasy towaru o kodzie A0001.</span><span class="sxs-lookup"><span data-stu-id="bb698-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="bb698-132">Wybór określonych produktów jest definiowany w sekcji **Wybory produktów do inwentaryzacji ciągłej**.</span><span class="sxs-lookup"><span data-stu-id="bb698-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="bb698-133">Produkty do planów inwentaryzacji ciągłej można wybrać, ustawiając w polu **Puste lokalizacje** wartość **Wyklucz puste**.</span><span class="sxs-lookup"><span data-stu-id="bb698-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.</span></span> <span data-ttu-id="bb698-134">Podczas przetwarzania planu inwentaryzacji ciągłej tworzona jest praca inwentaryzacji częściowej dla numeru pozycji A0001.</span><span class="sxs-lookup"><span data-stu-id="bb698-134">When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="bb698-135">Faktyczny proces inwentaryzacji można przeprowadzić przy użyciu elementu menu wspomaganej inwentaryzacji ciągłej na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="bb698-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="additional-resources"></a><span data-ttu-id="bb698-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bb698-136">Additional resources</span></span>
--------

[<span data-ttu-id="bb698-137">Inwentaryzacja ciągła</span><span class="sxs-lookup"><span data-stu-id="bb698-137">Cycle counting</span></span>](cycle-counting.md)

