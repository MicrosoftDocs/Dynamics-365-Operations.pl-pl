---
title: Warunki przepływu pracy arkusza magazynowego mają zastosowanie na poziomie arkusza, a nie na poziomie wiersza
description: Warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477307"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Warunki przepływu pracy arkusza magazynowego mają zastosowanie na poziomie arkusza, a nie na poziomie wiersza

## <a name="symptoms"></a>Objawy

Ten problem może wystąpić na przykład w przypadku próby skonfigurowania warunku przepływu pracy arkusza magazynowego dla kwoty kosztu. Warunek jest ustawiany w taki sposób, aby krok 1 był uruchamiany tylko wtedy, gdy kwota kosztu jest mniejsza niż 100. Następnie inny warunek jest ustawiany w taki sposób, aby krok 2 był uruchamiany tylko wtedy, gdy kwota kosztu jest większa lub równa 100. Potem podczas uruchamiania przepływu pracy historia przepływu pracy pokazuje tylko jeden wiersz, a pierwszy warunek jest zawsze obliczany jako *prawdziwy*, niezależnie od przesłanej wartości.

## <a name="workaround"></a>Obejście

W aktualnym wydaniu warunki przepływu pracy arkusza magazynowego mają zastosowanie tylko na poziomie arkusza, a nie na poziomie wiersza. Jest to celowe. Zaleca się, aby kryteria warunku ustawić tylko dla atrybutów na poziomie arkusza.
