---
title: "Śledzenie dynamicznych średnich kosztów własnych dla wymiaru magazynowego"
description: "Każda pozycja magazynowa ma przypisaną grupę wymiarów magazynowych. Dlatego dynamiczny średni koszt własny dla towaru jest obliczany na podstawie wyboru wymiarów magazynowych, które są śledzone pod względem finansowym."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bb2a3a193585944810c5dfac1eb3c019e074008f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="7083c-104">Śledzenie dynamicznych średnich kosztów własnych dla wymiaru magazynowego</span><span class="sxs-lookup"><span data-stu-id="7083c-104">Tracking running average cost per inventory dimension</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="7083c-105">Każda pozycja magazynowa ma przypisaną grupę wymiarów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="7083c-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="7083c-106">Dlatego dynamiczny średni koszt własny dla towaru jest obliczany na podstawie wyboru wymiarów magazynowych, które są śledzone pod względem finansowym.</span><span class="sxs-lookup"><span data-stu-id="7083c-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="7083c-107">Istnieją trzy typy wymiarów magazynowych: produkt, magazyn i śledzenie.</span><span class="sxs-lookup"><span data-stu-id="7083c-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="7083c-108">Wymiary produktów obejmują konfigurację, rozmiar i kolor.</span><span class="sxs-lookup"><span data-stu-id="7083c-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="7083c-109">Wymiary produktów są zawsze śledzone pod względem finansowym.</span><span class="sxs-lookup"><span data-stu-id="7083c-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="7083c-110">Wymiary magazynowania i śledzenia obejmują oddział, magazyn, lokalizację, stan zapasów, numer identyfikacyjny, numer partii i numer seryjny.</span><span class="sxs-lookup"><span data-stu-id="7083c-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="7083c-111">Można określić, które wymiary magazynowania i śledzenia są śledzone pod względem finansowym.</span><span class="sxs-lookup"><span data-stu-id="7083c-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="7083c-112">**Przykład 1**</span><span class="sxs-lookup"><span data-stu-id="7083c-112">**Example 1**</span></span> 

<span data-ttu-id="7083c-113">Jeśli grupa wymiarów magazynowania przypisana do towaru jest śledzona pod względem finansowym według magazynów, dynamiczne średnie koszty własne będą obliczane dla każdego magazynu.</span><span class="sxs-lookup"><span data-stu-id="7083c-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="7083c-114">Zafakturowano następujące zamówienia zakupu:</span><span class="sxs-lookup"><span data-stu-id="7083c-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="7083c-115">Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 10,00 zł zostało zafakturowane dla magazynu GW.</span><span class="sxs-lookup"><span data-stu-id="7083c-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="7083c-116">Zamówienie zakupu dotyczące ilości równej 3 i kosztu własnego równego 12,00 zł zostało zafakturowane dla magazynu GW.</span><span class="sxs-lookup"><span data-stu-id="7083c-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="7083c-117">Zamówienie zakupu dotyczące ilości równej 5 i kosztu własnego równego 15,00 zł zostało zafakturowane dla magazynu MW.</span><span class="sxs-lookup"><span data-stu-id="7083c-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="7083c-118">Dynamiczny średni koszt własny dla magazynu GW wynosi 11,20 zł., a dynamiczny średni koszt własny dla magazynu MW wynosi 15,00 zł.</span><span class="sxs-lookup"><span data-stu-id="7083c-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="7083c-119">Dla magazynu GW zaksięgowano fakturę zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7083c-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="7083c-120">Wartość zapasów i koszt własny sprzedaży (przed uruchomieniem zamknięcia magazynu i bez zaznaczania) to 11,20 zł.</span><span class="sxs-lookup"><span data-stu-id="7083c-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="7083c-121">Dla magazynu MW zaksięgowano inne zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7083c-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="7083c-122">Wartość zapasów i koszt własny sprzedaży (przed uruchomieniem zamknięcia magazynu i bez zaznaczania) to 15,00 zł.</span><span class="sxs-lookup"><span data-stu-id="7083c-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="7083c-123">**Przykład 2** Jeśli grupa wymiarów magazynowania, która jest przypisana do towaru, jest śledzona pod względem według magazynu, a grupa wymiarów śledzenia jest śledzona pod względem finansowym wg numeru partii, dynamiczny średni koszt własny jest obliczany dla każdej partii.</span><span class="sxs-lookup"><span data-stu-id="7083c-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="7083c-124">**Uwaga:** Zaleca się, aby koszt własny zawsze wyświetlać razem ze wszystkimi śledzonymi wymiarami finansowymi.</span><span class="sxs-lookup"><span data-stu-id="7083c-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="7083c-125">Zafakturowano następujące zamówienia zakupu:</span><span class="sxs-lookup"><span data-stu-id="7083c-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="7083c-126">Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 10,00 zł zostało zafakturowane dla magazynu GW i partii AAA.</span><span class="sxs-lookup"><span data-stu-id="7083c-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="7083c-127">Zamówienie zakupu dotyczące ilości równej 3 i kosztu własnego równego 12,00 zł zostało zafakturowane dla magazynu GW i partii AAA.</span><span class="sxs-lookup"><span data-stu-id="7083c-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="7083c-128">Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 15,00 zł zostało zafakturowane dla magazynu GW i partii BBB.</span><span class="sxs-lookup"><span data-stu-id="7083c-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="7083c-129">Dynamiczny średni koszt własny dla magazynu GW i partii AAA wynosi 11,20 zł., a dynamiczny średni koszt własny dla magazynu GW i partii BBB wynosi 15,00 zł.</span><span class="sxs-lookup"><span data-stu-id="7083c-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>




