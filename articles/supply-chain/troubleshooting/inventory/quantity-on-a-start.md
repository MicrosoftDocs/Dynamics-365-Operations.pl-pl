---
title: Ilość ze rozpoczętego zlecenia kwarantanny nie jest aktualizowana po podziale zamówienia
description: Po utworzeniu zlecenia kwarantanny i próbie jego podziału ilość zamówienia nie zostanie zaktualizowana zgodnie z pozostałą do podziału ilością.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026826"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>Ilość ze rozpoczętego zlecenia kwarantanny nie jest aktualizowana po podziale zamówienia

Numer artykułu z bazy wiedzy: 4613113

## <a name="symptoms"></a>Objawy

Po utworzeniu zlecenia kwarantanny i próbie jego podziału ilość zamówienia nie zostanie zaktualizowana zgodnie z pozostałą do podziału ilością po podziale.

## <a name="resolution"></a>Rozdzielczość

System nie zmienia oryginalnej ilości ze zlecenia kwarantanny, aby upewnić się, że można śledzić oryginalną ilość utworzoną dla tego zlecenia kwarantanny. System śledzi jednak ilość, która jest dzielona ze zlecenia kwarantanny. Do tego śledzenia jest używane pole bazy danych o nazwie `QuantityThatHasSplitIntoOtherQuarantineOrders`. Jednak to pole nie jest wyświetlane w interfejsie użytkownika (UI).
