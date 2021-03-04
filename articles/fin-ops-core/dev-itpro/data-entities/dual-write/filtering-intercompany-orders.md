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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizowania rekordów Orders i OrderLines

[!include [banner](../../includes/banner.md)]

Zamówienia międzyfirmowe można wyfiltrować, aby uniknąć synchronizowania jednostek **Orders** i **OrderLines**. W niektórych scenariuszach szczegóły zamówienia międzyfirmowego nie są konieczne w aplikacji do zakontraktowania odbiorcy.

Każda ze standardowych jednostek w usłudze Common Data Service jest rozszerzana o odwołania do pola **IntercompanyOrder**, a mapowania podwójnego zapisu są zmodyfikowane w celu odwoływania się do dodatkowych pól w filtrach. W efekcie zamówienia międzyfirmowe nie są już synchronizowane. Ten proces pozwala uniknąć niepotrzebnych danych w aplikacji do zakontraktowania odbiorcy.

1. Dodaj odwołanie do pola **IntercompanyOrder** do jednostki **Nagłówki zamówień sprzedaży CDS**. Jest ono wypełniane tylko w zamówieniach międzyfirmowych. Pole **IntercompanyOrder** jest dostępne w obszarze **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, SalesOrderHeader":::
    
2. Po rozszerzeniu jednostki **Nagłówki zamówień sprzedaży CDS** pole **IntercompanyOrder** jest dostępne w mapowaniu. Zastosuj filtr z `INTERCOMPANYORDER == ""` jako ciągiem zapytania.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Nagłówki zamówień sprzedaży, edytowanie zapytania":::

3. Dodaj odwołanie do pola **IntercompanyInventTransId** do jednostki **Wiersze zamówienia sprzedaży CDS**.  Jest ono wypełniane tylko w zamówieniach międzyfirmowych. Pole **InterCompanyInventTransID** jest dostępne w obszarze **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, SalesOrderLine":::

4. Po rozszerzeniu jednostki **Wiersze zamówienia sprzedaży CDS** pole **IntercompanyInventTransId** jest dostępne w mapowaniu. Zastosuj filtr z `INTERCOMPANYINVENTTRANSID == ""` jako ciągiem zapytania.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Wiersze zamówienia sprzedaży, edytowanie zapytania":::

5. Rozszerz jednostki **Nagłówki faktur sprzedaży wer. 2** i **Wiersze faktur sprzedaży wer. 2** w ten sam sposób, w jaki rozszerzono jednostki usługi Common Data Service w krokach 1 i 2. Następnie dodaj zapytania filtrujące. Ciągiem filtru dla jednostki **Nagłówki faktur sprzedaży wer. 2** jest `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. Ciągiem filtru dla jednostki **Wiersze faktur sprzedaży wer. 2** jest `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapowanie danych pośrednich do docelowych, Nagłówki faktur sprzedaży":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Nagłówki faktur sprzedaży, edytowanie zapytania":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Wiersze faktur sprzedaży, edytowanie zapytania":::

6. Jednostka **Oferty** nie ma relacji międzyfirmowej. Jeśli ktoś utworzy ofertę dla jednego z odbiorców międzyfirmowych, można umieścić wszystkich tych odbiorców w jednej grupie odbiorców, korzystając z pola **CustGroup**.  Nagłówek i wiersze można rozszerzyć, dodając do nich pole **CustGroup**, a następnie wykonać filtrowanie, aby nie dołączać tej grupy.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapowanie danych pośrednich do docelowych, Nagłówek oferty sprzedaży":::

7. Po rozszerzeniu jednostki **Oferty** zastosuj filtr z `CUSTGROUP !=  "<company>"` jako ciągiem zapytania.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Nagłówek oferty sprzedaży, edytowanie zapytania":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]