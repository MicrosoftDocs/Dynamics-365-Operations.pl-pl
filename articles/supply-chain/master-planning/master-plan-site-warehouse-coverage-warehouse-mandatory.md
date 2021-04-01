---
title: Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn wymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu jest obowiązkowy.
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
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ffc550ff719950a603811c65cb9b790ded5c2c8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236058"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="cd428-104">Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="cd428-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd428-105">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”.</span><span class="sxs-lookup"><span data-stu-id="cd428-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="cd428-106">Wymiar magazynu jest obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="cd428-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="cd428-107">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="cd428-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="cd428-108">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="cd428-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="cd428-109">Wymiar magazynu jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="cd428-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="cd428-110">Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="cd428-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="cd428-111">Również inne wymiary mogą być ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="cd428-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="cd428-112">Jednak funkcja wielooddziałowości nie ma na nie wpływu.</span><span class="sxs-lookup"><span data-stu-id="cd428-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="cd428-113">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="cd428-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="cd428-114">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="cd428-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="cd428-115">Magazyn ma ustawienie **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="cd428-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="cd428-116">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="cd428-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cd428-117">Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="cd428-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="cd428-118">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="cd428-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="cd428-119">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="cd428-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cd428-120">Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na pozycje**.</span><span class="sxs-lookup"><span data-stu-id="cd428-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="cd428-121">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="cd428-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="cd428-122">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="cd428-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cd428-123">Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="cd428-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="cd428-124">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="cd428-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="cd428-125">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="cd428-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cd428-126">Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij pozycję **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="cd428-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="cd428-127">W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="cd428-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Popyt dla zapotrzebowania oddziału i magazynu, magazyn wymagany](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="cd428-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cd428-129">Additional resources</span></span>
--------

[<span data-ttu-id="cd428-130">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="cd428-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="cd428-131">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="cd428-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="cd428-132">Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="cd428-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="cd428-133">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="cd428-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="cd428-134">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="cd428-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]