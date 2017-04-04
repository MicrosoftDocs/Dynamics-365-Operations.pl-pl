---
title: "Kwota zaokrąglenia do obliczenia amortyzacji"
description: "W tym artykule omówiono pole Zaokrąglenie amortyzacji, które znajduje się na stronach konfiguracji ksiąg."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 0cb514dfb8c37b8c027ab895cb970af1b0135bf0
ms.lasthandoff: 03/31/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>Kwota zaokrąglenia do obliczenia amortyzacji

W tym artykule omówiono pole Zaokrąglenie amortyzacji, które znajduje się na stronach konfiguracji ksiąg.

Zaokrąglenie amortyzacji kwot są ustawiane dla każdej księgi. Zaokrąglenie amortyzacji kwot są używane w profilu amortyzacji środka trwałego, który pokazuje przyszła amortyzacja i wartość środka trwałego, a także w propozycji amortyzacji. Wprowadź najniższą kwotę amortyzacji dozwoloną dla danej księgi. 

Niezależnie od ustawionego zaokrąglenia kwota amortyzacji w ostatnim okresie amortyzacji nie jest zaokrąglana. Na końcu ostatniego okresu amortyzacji wartość środków trwałych musi wynosić 0 (zero) lub być równa wartości likwidacji, jeśli likwidacja jest stosowana.

### <a name="example"></a>Przykład

Amortyzacja bez żadnego zaokrąglania została obliczona jako 2444,44. Jak pokazano w poniższej tabeli sugerowane kwoty różnią się w zależności od ustawienia zaokrąglania.

| Metoda zaokrąglania | Kwota amortyzacji |
|-----------------|---------------------|
| Zaokrąglanie 0,1    | 2444,40            |
| Zaokrąglanie 1,00   | 2444,00            |
| Zaokrąglanie 10,00  | 2440,00            |
| Zaokrąglanie 100,00 | 2400,00            |




