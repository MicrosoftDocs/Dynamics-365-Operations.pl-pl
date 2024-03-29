---
title: Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizacji rekordów Orders i OrderLines
description: W tym artykule wyjaśniono sposób filtrowania zamówień międzyfirmowych w celu uniknięcia synchronizowania jednostek Orders i OrderLines.
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f5b7831e103aaa219394099b79537bf0842d9be8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289289"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrowanie zamówień międzyfirmowych w celu uniknięcia synchronizacji rekordów Orders i OrderLines

[!include [banner](../../includes/banner.md)]

Zamówienia międzyfirmowe można odfiltrować, aby uniknąć synchronizowania tabel **Orders** i **OrderLines**. W niektórych scenariuszach szczegóły zamówienia międzyfirmowego nie są konieczne w aplikacji Customer Engagement.

Każda ze standardowych tabel w usłudze Dataverse jest rozszerzana za pośrednictwem odwołań do kolumny **IntercompanyOrder**, a mapowania podwójnego zapisu są zmodyfikowane w celu odwoływania się do dodatkowych kolumn w filtrach. W związku z tym zamówienia międzyfirmowe nie są już synchronizowane. Ten proces pozwala uniknąć niepotrzebnych danych w aplikacji Customer Engagement.

1. Rozszerz tabelę **Nagłówki zamówień sprzedaży CDS**, dodając odwołanie do kolumny **IntercompanyOrder**. Ta kolumna jest wypełniana tylko w zamówieniach międzyfirmowych. Kolumna **IntercompanyOrder** jest dostępna w tabeli **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówków zamówień sprzedaży usługi CDS.":::

2. Po rozszerzeniu tabeli **Nagłówki zamówień sprzedaży CDS** kolumna **IntercompanyOrder** jest dostępna w mapowaniu. Zastosuj filtr z `INTERCOMPANYORDER == ""` jako ciągiem zapytania.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówków zamówień sprzedaży usługi CDS.":::

3. Rozszerz tabelę **Wiersze zamówień sprzedaży CDS**, dodając odwołanie do kolumny **IntercompanyInventTransId**. Ta kolumna jest wypełniana tylko w zamówieniach międzyfirmowych. Kolumna **IntercompanyInventTransId** jest dostępna w tabeli **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla wierszy zamówień sprzedaży usługi CDS.":::

4. Po rozszerzeniu tabeli **Wiersze zamówienia sprzedaży CDS** kolumna **IntercompanyInventTransId** jest dostępna w mapowaniu. Zastosuj filtr z `INTERCOMPANYINVENTTRANSID == ""` jako ciągiem zapytania.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Okno dialogowe edytowania zapytania dla wierszy zamówień sprzedaży usługi CDS.":::

5. Powtórz kroki 1 i 2, aby rozszerzyć tabelę **Nagłówek faktury sprzedaży (wersja 2)** i dodać zapytanie filtru. W takim przypadku należy użyć `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` jako ciągu zapytania dla filtru.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówka faktury sprzedaży (wersja 2).":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówka faktury sprzedaży (wersja 2).":::

6. Powtórz kroki 3 i 4, aby rozszerzyć tabelę **Wiersze faktury sprzedaży (wersja 2)** i dodać zapytanie filtru. W takim przypadku należy użyć `INTERCOMPANYINVENTTRANSID == ""` jako ciągu zapytania dla filtru.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Okno dialogowe edytowania zapytania dla wierszy faktury sprzedaży (wersja 2).":::

7. Tabela **Oferty** nie ma relacji międzyfirmowej. Jeśli ktoś utworzy ofertę dla jednego z odbiorców międzyfirmowych, można użyć kolumny **CustGroup**, aby umieścić tych dostawców w jednej grupie dostawców. Nagłówek i wiersze można rozszerzać, dodając kolumnę **CustGroup**, a następnie filtrując dane tak, aby grupa nie była uwzględniana.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Strona mapowania danych pośrednich do docelowych dla nagłówka oferty sprzedaży usługi CDS.":::

8. Po rozszerzeniu tabeli **Oferty** zastosuj filtr z `CUSTGROUP != "<company>"` jako ciągiem zapytania.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Okno dialogowe edytowania zapytania dla nagłówka oferty sprzedaży usługi CDS.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
