---
title: Numer załącznika dokumentu przyjęcia produktów jest zużywany nawet wtedy, gdy nie generuje załącznika
description: Numer kuponu przyjęcia produktu jest używany, nawet jeśli podczas przyjęcia produktu nie jest generowany żaden dowód finansowy
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
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477302"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Numer załącznika dokumentu przyjęcia produktów jest zużywany nawet wtedy, gdy nie generuje załącznika

## <a name="symptoms"></a>Objawy

Numer kuponu przyjęcia produktu jest używany, nawet jeśli podczas przyjęcia produktu nie jest generowany żaden dowód finansowy.

## <a name="resolution"></a>Rozwiązanie

Jeśli dla grupy modeli towaru dla opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** jest ustawiona wartość *Nie*, księgowanie nie będzie wykonywane w księdze głównej. Jednak zdarzenie fizyczne zostanie zarejestrowane do celów księgowania w księdze podrzędnej, a to zdarzenie wymaga numeru załącznika. Ten numer załącznika jest numerem załącznika, do którego istnieje odwołanie w transakcjach magazynowych.

Zaleca się ustawienie opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** na wartość *Tak*, jak to opisano w następującym wpisie na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
