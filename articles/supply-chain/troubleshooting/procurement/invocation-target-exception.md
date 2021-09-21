---
title: Podczas księgowania faktury od dostawcy wystąpił wyjątek
description: Podczas księgowania faktury od dostawcy wystąpił wyjątek „Wyjątek zgłoszony dla obiektu docelowego wywołania”.
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
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477304"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Podczas księgowania faktury od dostawcy wystąpił wyjątek


## <a name="symptoms"></a>Objawy

Podczas księgowania faktury od dostawcy występuje następujący wyjątek:

> Wyjątek zgłoszony dla obiektu docelowego wywołania

## <a name="cause"></a>Powód

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

## <a name="resolution"></a>Rozwiązanie

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
