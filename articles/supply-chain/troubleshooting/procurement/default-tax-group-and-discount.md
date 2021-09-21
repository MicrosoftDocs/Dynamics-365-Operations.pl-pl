---
title: Domyślna grupa podatków i rabat gotówkowy nie są wypełniane na podstawie konta faktury
description: Domyślna grupa podatków i domyślny rabat gotówkowy nie są wypełniane na podstawie konta płatnika
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
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477301"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>Domyślna grupa podatków i rabat gotówkowy nie są wypełniane na podstawie konta faktury

## <a name="symptoms"></a>Objawy

Jeśli używasz konta faktury, które różni się od konta odbiorcy, domyślna grupa podatkowa i domyślny rabat gotówkowy nie są wypełniane z konta faktury podczas tworzenia zamówienia zakupu.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Domyślne wartości grupy podatków, rabatów gotówkowych i innych informacji o cenie są oparte na koncie odbiorcy, a nie na koncie faktury.
