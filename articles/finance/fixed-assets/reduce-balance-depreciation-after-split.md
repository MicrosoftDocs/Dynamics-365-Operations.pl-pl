---
title: Amortyzacja degresywna po podzieleniu
description: W tym temacie opisano metodę używaną w module Środki trwałe do obliczania amortyzacji po podzieleniu składnika majątku przy użyciu metody amortyzacji degresywnej.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f276f49e5b1bc2814dc851f1ad4204a151d86c43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222390"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Amortyzacja degresywna po podzieleniu

[!include [banner](../includes/banner.md)]

W tym temacie opisano metodę używaną w module Środki trwałe do obliczania amortyzacji po podzieleniu składnika majątku na inny składnik majątku przy użyciu metody amortyzacji degresywnej. Rok amortyzacji skonfigurowany w księdze składników majątku jest rokiem obrachunkowym. Aby uzyskać więcej informacji, zobacz [Amortyzacja degresywna](reduce-balance-depreciation.md) i [Rozbicie środka trwałego](tasks/split-fixed-asset.md).

Jeśli środek trwały zostanie podzielony w okresie obrachunkowym późniejszym niż okres, w którym składnik majątku został nabyty, amortyzacja degresywna uwzględni wartość księgową netto (NBV) składnika majątku za poprzedni rok. Ponadto uwzględni transakcje korekty wartości początkowej i amortyzacji wygenerowane przez transakcję, która podzieliła składnik majątku. To zachowanie zakłada, że składnik majątku został nabyty w jednym roku obrachunkowym i podzielony w późniejszym roku obrachunkowym. Kwota, o którą należy zamortyzować pierwotny składnik majątku po podzieleniu, odzwierciedla NBV składnika sprzed podziału oraz transakcję korekty wartości początkowej i amortyzacji zaksięgowaną wskutek podziału.

Na przykład istnieją następujące okoliczności:

- Okres obrachunkowy wypada od 30 czerwca do 1 lipca.
- Wartość procentowa amortyzacji degresywnej wynosi 18 procent, a składnik majątku został kupiony w czerwcu 2019 roku w cenie nabycia 10 000 zł.
- Amortyzacja w pierwszym roku obrachunkowym wynosi 18 000 zł, amortyzacja miesięczna wynosi 150 zł, a składnik majątku jest następnie amortyzowany do listopada 2019 r. na kwotę 738,75 zł.
- W listopadzie 2019 r. 80 procent składnika majątku zostało podzielone na inny składnik majątku.

[![Amortyzacja degresywna po podzieleniu](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

Kwota amortyzacji pierwotnego składnika majątku wynosi 1822,25 zł. Ta kwota jest równa NBV przed zaksięgowaniem transakcji podziału (9111,25 zł) powiększonej o korektę wartości początkowej wygenerowaną podczas księgowania transakcji podziału (-8000 zł) oraz korektę amortyzacji wygenerowaną w trakcie transakcji podziału (711 zł). W efekcie amortyzacja za drugi rok wynosi (1822,25 × 18 procent) ÷ 12 = 27,33 zł.

Kwota amortyzacji dla nowego środka trwałego w pierwszym roku wynosi (8000 × 18 procent) ÷ 12 = 120 zł.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]