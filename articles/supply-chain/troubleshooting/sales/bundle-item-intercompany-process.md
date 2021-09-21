---
title: Element pakietu nieobsługiwany w procesie międzyfirmowym
description: Element pakietu nie jest dostępny do zakupu. W zamówieniu sprzedaży są kupowane tylko składniki elementu pakietu, a nie sam element pakietu.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477310"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Element pakietu nie jest obsługiwany w procesie międzyfirmowym

## <a name="symptoms"></a>Objawy

Pozycja pakietu jest niedostępna dla zamówienia zakupu, ponieważ w przypadku zbadania wierszy zamówienia sprzedaży dla towaru pakietu można zauważyć, że ilość wynosi *0* (zero), a stan jest *Anulowany*.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Zamówienie sprzedaży kupuje tylko składniki towaru pakietu. Nie powoduje to nabycia samego towaru w pakiecie. Jeśli trzeba kupić pakiet, należy rozważyć, czy należy go oznaczyć jako element pakietu, ponieważ jest on przeznaczony do scenariuszy rozpoznawania przychodów. Aby uzyskać więcej informacji o elementach pakietów, zobacz temat [Pakiety](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
