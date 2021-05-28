---
title: Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości
description: Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026824"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości

Numer artykułu z bazy wiedzy: 4612803

## <a name="symptoms"></a>Objawy

Pole **Data ostatniego testu** nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Data ostatniego testowego nie jest powiązana ze zleceniami kontroli jakości. Przechowuje datę, kiedy ukończone towary zostały zakupione lub wytworzone. Data ta jest używana do obliczania terminu przydatności.
