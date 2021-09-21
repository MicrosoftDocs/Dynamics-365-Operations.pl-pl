---
title: Przyjęcie zamówienia zakupu nie obejmuje wszystkich opłat
description: Przyjęcie zamówienia zakupu nie obejmuje wszystkich opłat
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477266"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Przyjęcie zamówienia zakupu nie obejmuje wszystkich opłat

## <a name="symptoms"></a>Objawy

Po otrzymaniu zamówienia zakupu nie wszystkie opłaty są uwzględnione w paragonie.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Na stronie **Parametry modułu Zaopatrzenie i sourcing** na karcie **Dostawa** upewnij się, że opcja **Generuj opłaty przy odbiorze produktu** jest ustawiona na wartość *Tak*.
1. Tworzenie zamówienia zakupu, które zawiera zmiany.
1. Potwierdź zamówienie zakupu.
1. Odbiór zamówienia zakupu.
1. Spójrz na sumę przychodu i porównaj ją z oczekiwaną sumą.
1. Zauważ, że nie wszystkie opłaty są uwzględniane w przyjęciu zamówienia zakupu.

## <a name="resolution"></a>Rozwiązanie

Rozwiązanie to zależy od sposobu, w jaki skonfigurowano opłaty dodatkowe. Aby uzyskać informacje o tym, jak skonfigurować różne opłaty, aby spełnić Twoje wymagania, zobacz następujący wpis na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
