---
title: Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizowania rekordów Orders i OrderLines
description: W tym temacie opisano, jak filtrować zamówienia międzyfirmowe w celu uniknięcia synchronizowania rekordów Orders i OrderLines.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701040"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="a4356-103">Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizowania rekordów Orders i OrderLines</span><span class="sxs-lookup"><span data-stu-id="a4356-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4356-104">Zamówienia międzyfirmowe można wyfiltrować, aby uniknąć synchronizowania jednostek **Orders** i **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="a4356-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="a4356-105">W niektórych scenariuszach szczegóły zamówienia międzyfirmowego nie są konieczne w aplikacji do zakontraktowania odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a4356-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="a4356-106">Każda ze standardowych jednostek w usłudze Common Data Service jest rozszerzana o odwołania do pola **IntercompanyOrder**, a mapowania podwójnego zapisu są zmodyfikowane w celu odwoływania się do dodatkowych pól w filtrach.</span><span class="sxs-lookup"><span data-stu-id="a4356-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="a4356-107">W efekcie zamówienia międzyfirmowe nie są już synchronizowane.</span><span class="sxs-lookup"><span data-stu-id="a4356-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="a4356-108">Ten proces pozwala uniknąć niepotrzebnych danych w aplikacji do zakontraktowania odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a4356-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="a4356-109">Dodaj odwołanie do pola **IntercompanyOrder** do jednostki **Nagłówki zamówień sprzedaży CDS**.</span><span class="sxs-lookup"><span data-stu-id="a4356-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="a4356-110">Jest ono wypełniane tylko w zamówieniach międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="a4356-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="a4356-111">Pole **IntercompanyOrder** jest dostępne w obszarze **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="a4356-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, SalesOrderHeader":::
    
2. <span data-ttu-id="a4356-113">Po rozszerzeniu jednostki **Nagłówki zamówień sprzedaży CDS** pole **IntercompanyOrder** jest dostępne w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="a4356-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="a4356-114">Zastosuj filtr z `INTERCOMPANYORDER == ""` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="a4356-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Nagłówki zamówień sprzedaży, edytowanie zapytania":::

3. <span data-ttu-id="a4356-116">Dodaj odwołanie do pola **IntercompanyInventTransId** do jednostki **Wiersze zamówienia sprzedaży CDS**.</span><span class="sxs-lookup"><span data-stu-id="a4356-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="a4356-117">Jest ono wypełniane tylko w zamówieniach międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="a4356-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="a4356-118">Pole **InterCompanyInventTransID** jest dostępne w obszarze **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="a4356-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, SalesOrderLine":::

4. <span data-ttu-id="a4356-120">Po rozszerzeniu jednostki **Wiersze zamówienia sprzedaży CDS** pole **IntercompanyInventTransId** jest dostępne w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="a4356-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="a4356-121">Zastosuj filtr z `INTERCOMPANYINVENTTRANSID == ""` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="a4356-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Wiersze zamówienia sprzedaży, edytowanie zapytania":::

5. <span data-ttu-id="a4356-123">Rozszerz jednostki **Nagłówki faktur sprzedaży wer. 2** i **Wiersze faktur sprzedaży wer. 2** w ten sam sposób, w jaki rozszerzono jednostki usługi Common Data Service w krokach 1 i 2.</span><span class="sxs-lookup"><span data-stu-id="a4356-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="a4356-124">Następnie dodaj zapytania filtrujące.</span><span class="sxs-lookup"><span data-stu-id="a4356-124">Then add the filter queries.</span></span> <span data-ttu-id="a4356-125">Ciągiem filtru dla jednostki **Nagłówki faktur sprzedaży wer. 2** jest `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="a4356-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="a4356-126">Ciągiem filtru dla jednostki **Wiersze faktur sprzedaży wer. 2** jest `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="a4356-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, Nagłówki faktur sprzedaży":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Nagłówki faktur sprzedaży, edytowanie zapytania":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Wiersze faktur sprzedaży, edytowanie zapytania":::

6. <span data-ttu-id="a4356-130">Jednostka **Oferty** nie ma relacji międzyfirmowej.</span><span class="sxs-lookup"><span data-stu-id="a4356-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="a4356-131">Jeśli ktoś utworzy ofertę dla jednego z odbiorców międzyfirmowych, można umieścić wszystkich tych odbiorców w jednej grupie odbiorców, korzystając z pola **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="a4356-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="a4356-132">Nagłówek i wiersze można rozszerzyć, dodając do nich pole **CustGroup**, a następnie wykonać filtrowanie, aby nie dołączać tej grupy.</span><span class="sxs-lookup"><span data-stu-id="a4356-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapowanie danych pośrednich do docelowych, Nagłówek oferty sprzedaży":::

7. <span data-ttu-id="a4356-134">Po rozszerzeniu jednostki **Oferty** zastosuj filtr z `CUSTGROUP !=  "<company>"` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="a4356-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Nagłówek oferty sprzedaży, edytowanie zapytania":::
