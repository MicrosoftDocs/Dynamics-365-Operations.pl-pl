---
title: Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu
description: Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu, jeśli inne wiersze dokumentu przyjęcia produktów mają różne daty księgowania.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477277"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu

## <a name="symptoms"></a>Objawy

Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu, jeśli inne wiersze dokumentu przyjęcia produktów mają różne daty księgowania.

## <a name="resolution"></a>Rozwiązanie

W starszych wersjach rozwiązania Dynamics 365 Supply Chain Management konsolidacja była dopuszczalna w tej sytuacji. Jednak praktyka ta jest podatna na błędy. Data księgowania w tworzonych wierszach zamówienia zakupu nie powinna różnić się od daty księgowania w wierszach przyjęcia produktów, na podstawie których utworzono te wiersze zamówienia. (Data księgowania w wierszach zamówienia jest zgodna z datą księgowania w nagłówku zamówienia). Dlatego konsolidacja wielu przyjęć produktów w pojedyncze zamówienia zakupu nie jest już dozwolona.

Data księgowania jest używana na przykład w odniesieniu do rezerwacji budżetu i przyszłych zobowiązań wiążących. Dlatego należy go zachować podczas przejścia od przyjęcia produktu do zamówienia.
