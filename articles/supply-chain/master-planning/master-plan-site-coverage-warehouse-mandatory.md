---
title: Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”. Magazyn jest wymiarem obowiązkowym.
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72240e7db8ec914220cb8f8f1185a91a304ff66b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977970"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="b11c1-104">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="b11c1-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b11c1-105">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”.</span><span class="sxs-lookup"><span data-stu-id="b11c1-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="b11c1-106">Magazyn jest wymiarem obowiązkowym.</span><span class="sxs-lookup"><span data-stu-id="b11c1-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="b11c1-107">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="b11c1-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="b11c1-108">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="b11c1-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="b11c1-109">Tego ustawienia nie można zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="b11c1-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="b11c1-110">Wymiar magazynu jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="b11c1-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="b11c1-111">Wymiar oddziału jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b11c1-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="b11c1-112">Również inne wymiary mogą być ustawione dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b11c1-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="b11c1-113">Jednak funkcja wielooddziałowości nie ma na nie wpływu.</span><span class="sxs-lookup"><span data-stu-id="b11c1-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="b11c1-114">Wymiar magazynu nie jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b11c1-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="b11c1-115">Dlatego podaż i popyt są agregowane według oddziałów oraz ewentualnie według innych wymiarów z planowaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="b11c1-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="b11c1-116">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="b11c1-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="b11c1-117">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="b11c1-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="b11c1-118">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="b11c1-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="b11c1-119">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="b11c1-120">Zaznacz towar i kliknij kolejno opcje **Plan &gt; Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="b11c1-121">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="b11c1-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="b11c1-122">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="b11c1-123">Na karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="b11c1-124">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="b11c1-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="b11c1-125">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="b11c1-126">Wybierz odpowiedni towar i kliknij kolejno opcje **Plan &gt; Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="b11c1-127">W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="b11c1-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Popyt dla zapotrzebowania oddziału, magazyn wymagany](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="b11c1-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b11c1-129">Additional resources</span></span>
--------

[<span data-ttu-id="b11c1-130">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="b11c1-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="b11c1-131">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="b11c1-131">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b11c1-132">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="b11c1-132">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b11c1-133">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="b11c1-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b11c1-134">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="b11c1-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



