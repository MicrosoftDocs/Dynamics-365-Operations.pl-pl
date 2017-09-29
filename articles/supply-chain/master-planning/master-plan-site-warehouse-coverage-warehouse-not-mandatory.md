---
title: "Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany"
description: "W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9c7b13a7a018ce584c877fed6212abc3c2913903
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="a0a18-104">Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="a0a18-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a0a18-105">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="a0a18-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="a0a18-106">Wymiar magazynu nie jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="a0a18-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="a0a18-107">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="a0a18-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="a0a18-108">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="a0a18-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="a0a18-109">Tego ustawienia nie można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="a0a18-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="a0a18-110">Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="a0a18-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="a0a18-111">Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="a0a18-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="a0a18-112">Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="a0a18-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="a0a18-113">Również inne wymiary mogą być ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="a0a18-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="a0a18-114">Jednak funkcja wielooddziałowości nie ma na nie wpływu.</span><span class="sxs-lookup"><span data-stu-id="a0a18-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="a0a18-115">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="a0a18-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="a0a18-116">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="a0a18-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="a0a18-117">Magazyn ma ustawienie Ręcznie.</span><span class="sxs-lookup"><span data-stu-id="a0a18-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="a0a18-118">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="a0a18-119">Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="a0a18-120">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="a0a18-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="a0a18-121">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="a0a18-122">Wybierz towar, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="a0a18-123">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="a0a18-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="a0a18-124">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="a0a18-125">Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="a0a18-126">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="a0a18-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="a0a18-127">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="a0a18-128">Wybierz towar, a następnie w okienku akcji na karcie **Plan** kliknij **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="a0a18-129">W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="a0a18-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Popyt dla oddziału i magazynu, magazyn niewymagany](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a><span data-ttu-id="a0a18-131">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="a0a18-131">See also</span></span>
--------

[<span data-ttu-id="a0a18-132">Planowanie główne a funkcjonalność wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="a0a18-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="a0a18-133">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="a0a18-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="a0a18-134">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="a0a18-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="a0a18-135">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="a0a18-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="a0a18-136">Planowanie główne — jak określa się wersję BOM</span><span class="sxs-lookup"><span data-stu-id="a0a18-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




