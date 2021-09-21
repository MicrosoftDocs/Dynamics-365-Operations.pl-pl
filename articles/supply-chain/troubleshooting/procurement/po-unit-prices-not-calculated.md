---
title: Ceny jednostkowe w zamówieniach zakupu nie są obliczane na podstawie konwersji jednostek
description: Ceny jednostkowe w zamówieniach zakupu nie są obliczane na podstawie konwersji jednostek
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
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477303"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Ceny jednostkowe w zamówieniach zakupu nie są obliczane na podstawie konwersji jednostek

## <a name="symptoms"></a>Objawy

Po zmianie jednostki w zamówieniu zakupu ceny umowy handlowej nie są ponownie obliczane zgodnie z definicjami konwersji jednostek.

## <a name="cause"></a>Powód

Ceny są zawsze uzyskiwane z umów handlowych (lub innych ustawień cen w systemie, takich jak umowy sprzedaży lub ceny towarów) i są ustalane dla jednostki.

Jeśli jednostka została zmieniona w wierszu zamówienia, system wyszukuje cenę nowej jednostki i stosuje tę cenę. Jeśli dla jednostki nie zostanie znaleziona żadna cena, system nie zastosuje ceny. Konwersji jednostek nie można użyć do przeliczenia ceny na inną jednostkę. Teoretycznie cena jednego pola o wartości 10 może nie być równa dziesięć razy więcej niż cena jednego pola.

## <a name="workaround"></a>Obejście

Jednym ze sposobów obejścia tego problemu jest zagwarantowanie, że istnieją umowy handlowe dla oczekiwanych jednostek, które będą używane w wierszach zamówień dla towaru.
