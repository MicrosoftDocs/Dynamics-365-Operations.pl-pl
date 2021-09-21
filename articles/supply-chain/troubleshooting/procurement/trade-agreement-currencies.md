---
title: Problemy z konwersją waluty umowy handlowej
description: Ceny w umowach handlowych nie są przeliczane zgodnie z walutą, jeśli waluta jest inna w zamówieniu zakupu
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
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477272"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problemy z konwersją waluty umowy handlowej

## <a name="symptoms"></a>Objawy

Ceny w umowach handlowych nie są przeliczane zgodnie z walutą, jeśli waluta jest inna w zamówieniu zakupu.

## <a name="resolution"></a>Rozwiązanie

Funkcja *Waluty ogólnej* umożliwia definiowanie cen i rabatów tylko w jednej walucie. Następnie można dokonać konwersji na inne waluty w razie konieczności. Ponadto po zakończeniu konwersji funkcja może automatycznie stosować przyjazne zaokrąglanie.
