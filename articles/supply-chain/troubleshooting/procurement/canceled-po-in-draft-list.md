---
title: Anulowane zamówienia zakupu są wyświetlane na liście w wersji roboczej w obszarze roboczym
description: Anulowane zamówienia zakupu są wyświetlane na liście wersji roboczych w obszarze roboczym Przygotowywania zamówień zakupu
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
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477330"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>Anulowane zamówienia zakupu są wyświetlane na liście w wersji roboczej w obszarze roboczym

## <a name="symptoms"></a>Objawy

Po anulowaniu zamówień zakupu, które były w stanie *Potwierdzone*, anulowane zamówienia zakupu nadal są wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowanie zamówienia zakupu**.

## <a name="resolution"></a>Rozwiązanie

Ten problem występuje tylko w przypadku zamówień zakupu, które podlegają zarządzaniu zmianami. Dzieje się tak, ponieważ anulowanie jest uznawane za zmianę, która musi zostać zatwierdzona. Zatwierdzenie może być wykonane automatycznie przez system. Dlatego procesowi jest przesłanie anulowanego zamówienia zakupu do przepływu pracy zatwierdzania, aby można było przejść do stanu *Zatwierdzone*. W tym momencie zamówienie zakupu nie będzie już wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowywania zamówienia zakupu**.
