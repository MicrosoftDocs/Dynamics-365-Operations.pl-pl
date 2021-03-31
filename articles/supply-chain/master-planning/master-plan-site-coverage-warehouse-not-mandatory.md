---
title: Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”.
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fce7737688f34469a0355acd4c7279d006cae1b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222904"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="529e5-103">Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="529e5-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="529e5-104">W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”.</span><span class="sxs-lookup"><span data-stu-id="529e5-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="529e5-105">Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="529e5-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="529e5-106">Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="529e5-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="529e5-107">Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy.</span><span class="sxs-lookup"><span data-stu-id="529e5-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="529e5-108">Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="529e5-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="529e5-109">Wymiar oddziału jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="529e5-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="529e5-110">Wymiar magazynu nie jest ustawiony dla planowania zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="529e5-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="529e5-111">Dlatego podaż i popyt są agregowane według oddziałów oraz ewentualnie według innych wymiarów z planowaniem zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="529e5-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="529e5-112">Na poniższej ilustracji przedstawiono przebieg planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="529e5-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="529e5-113">Parametry wymienione na ilustracji i ich lokalizacje są następujące:</span><span class="sxs-lookup"><span data-stu-id="529e5-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="529e5-114">Jest zdefiniowane zapotrzebowanie na dany towar.</span><span class="sxs-lookup"><span data-stu-id="529e5-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="529e5-115">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="529e5-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="529e5-116">Zaznacz towar i kliknij kolejno opcje **Plan &gt; Zapotrzebowanie na towary**.</span><span class="sxs-lookup"><span data-stu-id="529e5-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="529e5-117">Dla magazynu są zdefiniowane relacje uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="529e5-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="529e5-118">Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="529e5-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="529e5-119">Na karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.</span><span class="sxs-lookup"><span data-stu-id="529e5-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="529e5-120">Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban.</span><span class="sxs-lookup"><span data-stu-id="529e5-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="529e5-121">Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="529e5-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="529e5-122">Wybierz odpowiedni towar i kliknij kolejno opcje **Plan &gt; Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="529e5-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="529e5-123">W formularzu **Ustawienia domyślne zamówień** zobacz pole **Domyślny typ zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="529e5-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Popyt dla zapotrzebowania oddziału, magazyn niewymagany    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="529e5-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="529e5-125">Additional resources</span></span>
--------

[<span data-ttu-id="529e5-126">Omówienie planowania głównego i funkcjonalności wielooddziałowości</span><span class="sxs-lookup"><span data-stu-id="529e5-126">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="529e5-127">Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="529e5-127">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="529e5-128">Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany</span><span class="sxs-lookup"><span data-stu-id="529e5-128">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="529e5-129">Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany</span><span class="sxs-lookup"><span data-stu-id="529e5-129">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="529e5-130">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="529e5-130">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]