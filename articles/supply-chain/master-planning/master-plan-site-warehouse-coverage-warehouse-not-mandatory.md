---
title: Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e47531c75e54b23054464a5e1b1841eb2d82e093
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986727"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="f5350-104">Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="f5350-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5350-105">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="f5350-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="f5350-106">Wymiar magazynu nie jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="f5350-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="f5350-107">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="f5350-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f5350-108">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="f5350-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="f5350-109">Tego ustawienia nie można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="f5350-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="f5350-110">Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="f5350-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="f5350-111">Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="f5350-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="f5350-112">Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="f5350-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="f5350-113">Również inne wymiary mogą być ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="f5350-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="f5350-114">Jednak funkcja wielooddziałowości nie ma na nie wpływu.</span><span class="sxs-lookup"><span data-stu-id="f5350-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="f5350-115">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="f5350-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="f5350-116">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="f5350-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="f5350-117">Magazyn ma ustawienie Ręcznie.</span><span class="sxs-lookup"><span data-stu-id="f5350-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="f5350-118">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="f5350-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f5350-119">Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="f5350-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="f5350-120">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="f5350-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="f5350-121">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="f5350-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f5350-122">Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na pozycje**.</span><span class="sxs-lookup"><span data-stu-id="f5350-122">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="f5350-123">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="f5350-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="f5350-124">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="f5350-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f5350-125">Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="f5350-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="f5350-126">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="f5350-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="f5350-127">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="f5350-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f5350-128">Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij pozycję **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="f5350-128">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="f5350-129">W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="f5350-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Popyt dla oddziału i magazynu, magazyn niewymagany](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="f5350-131">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f5350-131">Additional resources</span></span>
--------

[<span data-ttu-id="f5350-132">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="f5350-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="f5350-133">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="f5350-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f5350-134">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="f5350-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f5350-135">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="f5350-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f5350-136">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="f5350-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



