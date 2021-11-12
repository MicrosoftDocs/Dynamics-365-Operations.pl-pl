---
title: Kwota zaokrąglenia do obliczenia amortyzacji
description: W tym temacie omówiono pole Zaokrąglenie amortyzacji, które znajduje się na stronach konfiguracji ksiąg.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3df48fc7bb092b0257c4652a8c67d1d740dbcfe
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674340"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Kwota zaokrąglenia do obliczenia amortyzacji

[!include [banner](../includes/banner.md)]

W tym temacie omówiono pole **Zaokrąglenie amortyzacji**, które znajduje się na stronach **konfiguracji ksiąg**.

Kwoty zaokrąglenia amortyzacji są ustawiane dla każdej księgi. Kwoty zaokrąglenia amortyzacji są używane w profilu amortyzacji środka trwałego, który pokazuje przyszłą amortyzację i wartość środka trwałego, a także w propozycjach amortyzacji. Wprowadź najniższą kwotę amortyzacji dozwoloną dla danej księgi. 

Niezależnie od ustawionego zaokrąglenia kwota amortyzacji w ostatnim okresie amortyzacji nie jest zaokrąglana. Na końcu ostatniego okresu amortyzacji wartość środków trwałych musi wynosić 0 (zero) lub być równa wartości likwidacji, jeśli likwidacja jest stosowana.

### <a name="example"></a>Przykład

Amortyzacja bez żadnego zaokrąglania została obliczona jako 2444,44. Jak pokazano w poniższej tabeli sugerowane kwoty różnią się w zależności od ustawienia zaokrąglania.

| Metoda zaokrąglania | Kwota amortyzacji |
|-----------------|---------------------|
| Zaokrąglanie 0,1    | 2444,40            |
| Zaokrąglanie 1,00   | 2,444.00            |
| Zaokrąglanie 10,00  | 2,440.00            |
| Zaokrąglanie 100,00 | 2,400.00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
