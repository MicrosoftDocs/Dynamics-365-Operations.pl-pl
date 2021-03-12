---
title: Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizacji rekordów Orders i OrderLines
description: W tym temacie wyjaśniono sposób filtrowania zamówień międzyfirmowych w celu uniknięcia synchronizowania jednostek Orders i OrderLines.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 342db8c1b4337145bfd61f5698ff6de25434a400
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796613"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="c6f5b-103">Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizacji rekordów Orders i OrderLines</span><span class="sxs-lookup"><span data-stu-id="c6f5b-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c6f5b-104">Zamówienia międzyfirmowe można odfiltrować, aby uniknąć synchronizowania tabel **Orders** i **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="c6f5b-105">W niektórych scenariuszach szczegóły zamówienia międzyfirmowego nie są konieczne w aplikacji Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="c6f5b-106">Każda ze standardowych tabel w usłudze Dataverse jest rozszerzana za pośrednictwem odwołań do kolumny **IntercompanyOrder**, a mapowania podwójnego zapisu są zmodyfikowane w celu odwoływania się do dodatkowych kolumn w filtrach.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="c6f5b-107">W związku z tym zamówienia międzyfirmowe nie są już synchronizowane.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="c6f5b-108">Ten proces pozwala uniknąć niepotrzebnych danych w aplikacji Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="c6f5b-109">Rozszerz tabelę **Nagłówki zamówień sprzedaży CDS**, dodając odwołanie do kolumny **IntercompanyOrder**.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="c6f5b-110">Ta kolumna jest wypełniana tylko w zamówieniach międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="c6f5b-111">Kolumna **IntercompanyOrder** jest dostępna w tabeli **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówków zamówień sprzedaży usługi CDS":::

2. <span data-ttu-id="c6f5b-113">Po rozszerzeniu tabeli **Nagłówki zamówień sprzedaży CDS** kolumna **IntercompanyOrder** jest dostępna w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="c6f5b-114">Zastosuj filtr z `INTERCOMPANYORDER == ""` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówków zamówień sprzedaży usługi CDS":::

3. <span data-ttu-id="c6f5b-116">Rozszerz tabelę **Wiersze zamówień sprzedaży CDS**, dodając odwołanie do kolumny **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="c6f5b-117">Ta kolumna jest wypełniana tylko w zamówieniach międzyfirmowych.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="c6f5b-118">Kolumna **IntercompanyInventTransId** jest dostępna w tabeli **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla wierszy zamówień sprzedaży usługi CDS":::

4. <span data-ttu-id="c6f5b-120">Po rozszerzeniu tabeli **Wiersze zamówienia sprzedaży CDS** kolumna **IntercompanyInventTransId** jest dostępna w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="c6f5b-121">Zastosuj filtr z `INTERCOMPANYINVENTTRANSID == ""` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Okno dialogowe edytowania zapytania dla wierszy zamówień sprzedaży usługi CDS":::

5. <span data-ttu-id="c6f5b-123">Powtórz kroki 1 i 2, aby rozszerzyć tabelę **Nagłówek faktury sprzedaży (wersja 2)** i dodać zapytanie filtru.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="c6f5b-124">W takim przypadku należy użyć `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` jako ciągu zapytania dla filtru.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówka faktury sprzedaży (wersja 2)":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówka faktury sprzedaży (wersja 2)":::

6. <span data-ttu-id="c6f5b-127">Powtórz kroki 3 i 4, aby rozszerzyć tabelę **Wiersze faktury sprzedaży (wersja 2)** i dodać zapytanie filtru.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="c6f5b-128">W takim przypadku należy użyć `INTERCOMPANYINVENTTRANSID == ""` jako ciągu zapytania dla filtru.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Okno dialogowe edytowania zapytania dla wierszy faktury sprzedaży (wersja 2)":::

7. <span data-ttu-id="c6f5b-130">Tabela **Oferty** nie ma relacji międzyfirmowej.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="c6f5b-131">Jeśli ktoś utworzy ofertę dla jednego z odbiorców międzyfirmowych, można użyć kolumny **CustGroup**, aby umieścić tych dostawców w jednej grupie dostawców.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="c6f5b-132">Nagłówek i wiersze można rozszerzać, dodając kolumnę **CustGroup**, a następnie filtrując dane tak, aby grupa nie była uwzględniana.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówka oferty sprzedaży usługi CDS":::

8. <span data-ttu-id="c6f5b-134">Po rozszerzeniu tabeli **Oferty** zastosuj filtr z `CUSTGROUP != "<company>"` jako ciągiem zapytania.</span><span class="sxs-lookup"><span data-stu-id="c6f5b-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówka oferty sprzedaży usługi CDS":::
