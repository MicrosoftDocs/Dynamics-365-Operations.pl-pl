---
title: Planowane zamówienia są generowane dla zapasów wraz ze zleceniami produkcyjnymi
description: Zamówienia planowane są generowane nawet wtedy, gdy masz towary w magazynie i istnieją już dla nich zlecenia produkcyjne
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477357"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>Planowane zamówienia są generowane dla zapasów wraz ze zleceniami produkcyjnymi

## <a name="symptoms"></a>Objawy

Zamówienia planowane są generowane nawet wtedy, gdy masz towary w magazynie i istnieją już dla nich zlecenia produkcyjne.

## <a name="resolution"></a>Rozwiązanie

Można rozwiązać ten problem, zwiększając wartość **Ilość dni z dodatnim stanem magazynu** dla odpowiednich grup na stronie **Grupa zapotrzebowania**. Ta zmiana spowoduje, że system określi, czy dla popytu można używać dostępnych zapasów. Wtedy nowe zamówienie planowane nie zostanie wygenerowane dla towarów znajdujących się w magazynie.
