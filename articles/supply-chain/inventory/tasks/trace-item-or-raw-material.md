---
title: Śledzenie elementu lub surowca
description: Ta procedura przedstawia wykorzystanie funkcji śledzenia towarów w celu identyfikacji miejsc, gdzie towary lub surowce zostały użyte albo są używane.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c39d34773a2b36cbf9477e4bdda8e45491d9c03
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213913"
---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="bbe5f-103">Śledzenie elementu lub surowca</span><span class="sxs-lookup"><span data-stu-id="bbe5f-103">Trace an item or raw material</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bbe5f-104">Ta procedura przedstawia wykorzystanie funkcji śledzenia towarów w celu identyfikacji miejsc, gdzie towary lub surowce zostały użyte albo są używane.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="bbe5f-105">Za pomocą tej procedury można zidentyfikować towar, śledzić go z powrotem do źródła, a następnie śledzić w przód aż do produkcji i sprzedaży produktu gotowego.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="bbe5f-106">Proces może służyć do analizowania odbiorców, zamówień sprzedaży i innych obiektów objętych oddziaływaniem.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="bbe5f-107">Procedura wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="bbe5f-108">Śledzenie towaru wstecz za pomocą znanego numeru partii</span><span class="sxs-lookup"><span data-stu-id="bbe5f-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="bbe5f-109">W **okienku nawigacji** otwórz **Moduły > Zarządzanie zapasami > Zapytania i raporty > Wymiary śledzenia > Śledzenie towaru**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-109">In the **Navigation pane**, go to **Modules > Inventory management > Inquiries and reports > Tracking dimensions > Item tracing**.</span></span>
2. <span data-ttu-id="bbe5f-110">W polu **Numer pozycji** wybierz wartość „P9100”.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-110">In the **Item number** field, select 'P9100'.</span></span>
3. <span data-ttu-id="bbe5f-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bbe5f-112">W polu **W przód lub w tył** wybierz opcję „Wstecz”.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-112">In the **Forward or backward** field, select 'Backward'.</span></span>
5. <span data-ttu-id="bbe5f-113">W polu **Numer partii** wybierz wartość „as-12-344-01”.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-113">In the **Batch number** field, select 'as-12-344-01'.</span></span>
6. <span data-ttu-id="bbe5f-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="bbe5f-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-115">Click **OK**.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="bbe5f-116">Identyfikacja towaru, śledzenie go w przód i analiza</span><span class="sxs-lookup"><span data-stu-id="bbe5f-116">Identify an item, trace it forward, and make an analysis</span></span>

<span data-ttu-id="bbe5f-117">Najwyższy węzeł drzewa odpowiada dostępnej ilości wybranego towaru oraz partii.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="bbe5f-118">Należy rozwinąć węzły drzewa, aby znaleźć towar, do którego należy zastosować śledzenie w przód.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="bbe5f-119">W drzewie rozwiń węzły opisane poniżej, a następnie zaznacz ostatni węzeł.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    
    <span data-ttu-id="bbe5f-120">Rozwiń węzeł „P9100 / 1 / 10 / as-12-344-01 ● 2 kegi ● 7,00 gal  \P9100 ● Pobrane ● Zamówienie sprzedaży 000072 ● 12/22/2015 ● -1 kega ● -4,00 gal ● Oddział=1, Magazyn=10, Numer partii=as-12-344-01  \P9100 ● Produkcja B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Oddział=1,Magazyn=10,Numer partii=as-12-344-01 ● Produkty towarzyszące: P9101”, a następnie go zaznacz.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="bbe5f-121">W drzewie rozwiń węzeł opisany poniżej, a następnie go zaznacz.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    
    <span data-ttu-id="bbe5f-122">Zaczynając od węzła, który właśnie został zaznaczony, rozwiń węzeł „M9103 ● Linia produkcyjna B-000050 ● 12/9/2015 ● -160,00 lb ● Rozmiar=70, Kolor=OK, Oddział=1, Magazyn=10, Numer partii=App01”, a następnie go zaznacz.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-122">Starting from the node that you've just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="bbe5f-123">Kliknij opcję **Śledź od węzła**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-123">Click **Trace from node**.</span></span>
4. <span data-ttu-id="bbe5f-124">Kliknij opcję **W przód**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-124">Click **Forward**.</span></span>
5. <span data-ttu-id="bbe5f-125">W **okienku akcji** kliknij pozycję **Śledzenie**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-125">On the **Action Pane**, click **Tracing**.</span></span>
    
    <span data-ttu-id="bbe5f-126">Dostępnych jest kilka opcji śledzenia, które dostarczają informacji o odbiorcach wykorzystujących śledzony towar oraz o zamówieniach sprzedaży związanych z towarem, dla których towar został wysłany lub nie.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-126">There are several tracing options which provide information about the customers impacted by the item that you're tracing, and the sales orders related to the item which have and haven't been shipped.</span></span>   
6. <span data-ttu-id="bbe5f-127">Kliknij opcję **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-127">Click **Customers**.</span></span>
7. <span data-ttu-id="bbe5f-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-128">Close the page.</span></span>
8. <span data-ttu-id="bbe5f-129">W **okienku akcji** kliknij pozycję **Śledzenie**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-129">On the **Action Pane**, click **Tracing**.</span></span>
9. <span data-ttu-id="bbe5f-130">Kliknij opcję **Zamówienia sprzedaży, towary wysłane**.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-130">Click **Shipped sales orders**.</span></span>
10. <span data-ttu-id="bbe5f-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bbe5f-131">Close the page.</span></span>

