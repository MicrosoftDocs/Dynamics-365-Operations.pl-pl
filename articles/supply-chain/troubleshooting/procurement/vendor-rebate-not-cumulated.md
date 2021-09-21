---
title: Rabat dostawcy nie jest kumulowany na podstawie faktur
description: Rabat dostawcy nie jest kumulowany na podstawie faktur
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
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477351"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Rabat dostawcy nie jest kumulowany na podstawie faktur

## <a name="symptoms"></a>Objawy

Jeśli faktury, które zostały zaksięgowane, mają różne terminy płatności, te faktury nie są uwzględniane w wygenerowanych rabatach dostawców.

## <a name="resolution"></a>Rozwiązanie

Termin płatności nie jest brany pod uwagę przy obliczaniu rabatu dla dostawcy. Rozważ dostosowanie systemu, tak aby termin płatności i związek z fakturą były bardziej widoczne w odniesieniu do faktycznego rabatu dostawcy.
