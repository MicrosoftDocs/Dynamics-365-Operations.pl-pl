---
title: Dostępność zapasów w podwójnym zapisie
description: Ten temat zawiera informacje o sposobie sprawdzania dostępności zapasów w trybie podwójnego zapisu.
author: yijialuan
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 9d9b7970720218fbcf2f512345ade672810440b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748572"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="c12cc-103">Dostępność zapasów w podwójnym zapisie</span><span class="sxs-lookup"><span data-stu-id="c12cc-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c12cc-104">Korzystając z dostępności zapasów, można sprawdzić stan zapasów przed dodaniem produktu do stron **Oferty**, **Zamówienia** lub **Faktury** w Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c12cc-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="c12cc-105">Na przykład sprawdzenie zapasów i określenie daty realizacji jest jednym z kluczowych zadań w procesie [od prospektu do gotówki](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="c12cc-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="c12cc-106">Jeśli nie ma wystarczającej ilości zapasów, można oszacować datę dostawy na podstawie przewidywanych przyjęć i problemów z zapasami.</span><span class="sxs-lookup"><span data-stu-id="c12cc-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="c12cc-107">Można również sprawdzić informacje o dostępności zapasów (ATP), w której można znaleźć ilość ATP w wstępnie zdefiniowanym horyzoncie czasowym.</span><span class="sxs-lookup"><span data-stu-id="c12cc-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="c12cc-108">Dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="c12cc-108">On-hand inventory</span></span>

<span data-ttu-id="c12cc-109">W Dynamics 365 Sales jest dodany nowy przycisk **Dostępne zapasy** do nagłówka stron **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="c12cc-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="c12cc-110">Wybranie tego przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę i produkt, dla którego mają zostać sprawdzone dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="c12cc-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="c12cc-111">W tym oknie dialogowym są wyświetlane takie same informacje jak [Dostępne zapasy](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="c12cc-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="c12cc-112">W oknie dialogowym są zwracane informacje o zapasach z Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c12cc-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c12cc-113">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="c12cc-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="c12cc-114">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="c12cc-114">On-hand quantity</span></span>
- <span data-ttu-id="c12cc-115">Zarezerowowana dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="c12cc-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="c12cc-116">Dostępna ilość na stanie</span><span class="sxs-lookup"><span data-stu-id="c12cc-116">Available on-hand quantity</span></span>
- <span data-ttu-id="c12cc-117">Ilość zamówiona</span><span class="sxs-lookup"><span data-stu-id="c12cc-117">Ordered quantity</span></span>
- <span data-ttu-id="c12cc-118">Ilość na zamówienie</span><span class="sxs-lookup"><span data-stu-id="c12cc-118">On-order quantity</span></span>
- <span data-ttu-id="c12cc-119">Zarezerwowana zamówiona ilość</span><span class="sxs-lookup"><span data-stu-id="c12cc-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="c12cc-120">Łączna dostępna ilość</span><span class="sxs-lookup"><span data-stu-id="c12cc-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="c12cc-121">Informacje ATP</span><span class="sxs-lookup"><span data-stu-id="c12cc-121">ATP information</span></span>

<span data-ttu-id="c12cc-122">W Sales nowy przyscisk **Informacje ATP** został dodany do wiersza pozycji na stronach **Oferty**, **Zamówienia** i **Faktury**.</span><span class="sxs-lookup"><span data-stu-id="c12cc-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="c12cc-123">Wybranie przycisku powoduje wyświetlenie okna dialogowego, w którym można określić firmę, produkt, oddział zapasów, magazyn zapasów i ilośc zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c12cc-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="c12cc-124">To okno dialogowe ma takie same ustawienia, które są opisane w obszarze [Zobowiązanie do zamówienia](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="c12cc-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="c12cc-125">Okno dialogowe zwraca informacje o ATP z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c12cc-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="c12cc-126">Informacje te obejmują następujące ilości:</span><span class="sxs-lookup"><span data-stu-id="c12cc-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="c12cc-127">Ilość ATP</span><span class="sxs-lookup"><span data-stu-id="c12cc-127">ATP quantity</span></span>
- <span data-ttu-id="c12cc-128">Ilość przychodu</span><span class="sxs-lookup"><span data-stu-id="c12cc-128">Receipt quantity</span></span>
- <span data-ttu-id="c12cc-129">Ilość rozchodu</span><span class="sxs-lookup"><span data-stu-id="c12cc-129">Issue quantity</span></span>
- <span data-ttu-id="c12cc-130">Ilość dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="c12cc-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="c12cc-131">Jak działa</span><span class="sxs-lookup"><span data-stu-id="c12cc-131">How it works</span></span>

<span data-ttu-id="c12cc-132">Po wybraniu przycisku **Dostępne zapasy** na stronie **Oferty**, **Zamówienia** lub **Faktury** zostanie wykonane na żywo wywołanie podwójnego zapisu dla interfejsu API **dostępnych zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c12cc-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="c12cc-133">Interfejs API oblicza stan dostępnych zapasów danego produktu.</span><span class="sxs-lookup"><span data-stu-id="c12cc-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="c12cc-134">Wynik jest przechowywany w tabelach **InventCDSInventoryOnHandRequestEntity** i **InventCDSInventoryOnHandEntryEntity**, a następnie zapisywany w tabeli w trybie podwójnego zapisu usługi Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c12cc-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="c12cc-135">Aby korzystać z tej funkcji, należy uruchomić następujące mapy podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="c12cc-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="c12cc-136">Pomiń wstępną synchronizację podczas uruchamiania map.</span><span class="sxs-lookup"><span data-stu-id="c12cc-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="c12cc-137">Wpisy dostępnych zapasów CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="c12cc-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="c12cc-138">Żądania dostępnych zapasów CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="c12cc-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="c12cc-139">Szablony</span><span class="sxs-lookup"><span data-stu-id="c12cc-139">Templates</span></span>
<span data-ttu-id="c12cc-140">Dla danych dotyczących dostępnych zapasów są dostępne następujące szablony.</span><span class="sxs-lookup"><span data-stu-id="c12cc-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="c12cc-141">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c12cc-141">Finance and Operations apps</span></span> | <span data-ttu-id="c12cc-142">Aplikacja Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c12cc-142">Customer engagement app</span></span> | <span data-ttu-id="c12cc-143">opis</span><span class="sxs-lookup"><span data-stu-id="c12cc-143">Description</span></span> 
---|---|---
[<span data-ttu-id="c12cc-144">Dostępne wpisy zapasów CDS</span><span class="sxs-lookup"><span data-stu-id="c12cc-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="c12cc-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="c12cc-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="c12cc-146">Żądania dostępnych zapasów CDS</span><span class="sxs-lookup"><span data-stu-id="c12cc-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="c12cc-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="c12cc-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="c12cc-148">Wpisy dostępnych zapasów CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="c12cc-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="c12cc-149">Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c12cc-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="c12cc-150">Pole aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c12cc-150">Finance and Operations field</span></span> | <span data-ttu-id="c12cc-151">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="c12cc-151">Map type</span></span> | <span data-ttu-id="c12cc-152">Pole Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c12cc-152">Customer engagement field</span></span> | <span data-ttu-id="c12cc-153">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="c12cc-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="c12cc-154">Żądania dostępnych zapasów CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="c12cc-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="c12cc-155">Ten szablon synchronizuje dane między aplikacjami Finance and Operations i usługami Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c12cc-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="c12cc-156">Pole aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c12cc-156">Finance and Operations field</span></span> | <span data-ttu-id="c12cc-157">Typ mapy</span><span class="sxs-lookup"><span data-stu-id="c12cc-157">Map type</span></span> | <span data-ttu-id="c12cc-158">Pole Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="c12cc-158">Customer engagement field</span></span> | <span data-ttu-id="c12cc-159">Wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="c12cc-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]