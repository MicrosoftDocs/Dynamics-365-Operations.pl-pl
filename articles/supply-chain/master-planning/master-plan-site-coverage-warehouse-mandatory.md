---
title: "Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany"
description: "W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”. Magazyn jest wymiarem obowiązkowym."
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
ms.search.scope: Core, Operations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fcfdbf8cdc6aae7f82ba308d450b754d652ac699
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="4ecdd-104">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="4ecdd-104">Master planning for site coverage, mandatory warehouse</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="4ecdd-105">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="4ecdd-106">Magazyn jest wymiarem obowiązkowym.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="4ecdd-107">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="4ecdd-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="4ecdd-108">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="4ecdd-109">Tego ustawienia nie można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="4ecdd-110">Wymiar magazynu jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="4ecdd-111">Wymiar oddziału jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="4ecdd-112">Również inne wymiary mogą być ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="4ecdd-113">Jednak funkcja wielooddziałowości nie ma na nie wpływu.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="4ecdd-114">Wymiar magazynu nie jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="4ecdd-115">Dlatego podaż i popyt są agregowane według oddziałów oraz ewentualnie według innych wymiarów z planowaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="4ecdd-116">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="4ecdd-117">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="4ecdd-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="4ecdd-118">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="4ecdd-119">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="4ecdd-120">Zaznacz towar i kliknij kolejno opcje **Plan &gt; Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="4ecdd-121">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="4ecdd-122">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="4ecdd-123">Na karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="4ecdd-124">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="4ecdd-125">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="4ecdd-126">Wybierz odpowiedni towar i kliknij kolejno opcje **Plan &gt; Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="4ecdd-127">W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="4ecdd-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Popyt dla zapotrzebowania oddziału, magazyn wymagany](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="4ecdd-129">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4ecdd-129">See also</span></span>
--------

[<span data-ttu-id="4ecdd-130">Planowanie główne a funkcjonalność wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="4ecdd-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="4ecdd-131">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="4ecdd-131">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="4ecdd-132">Planowanie główne — zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="4ecdd-132">Master planning - site coverage. warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="4ecdd-133">Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="4ecdd-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="4ecdd-134">Planowanie główne — jak określa się wersję BOM</span><span class="sxs-lookup"><span data-stu-id="4ecdd-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




