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
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742035"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości

Numer artykułu z bazy wiedzy: 4612803

## <a name="symptoms"></a>Objawy

Pole **Data ostatniego testu** nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Data ostatniego testowego nie jest powiązana ze zleceniami kontroli jakości. Przechowuje datę, kiedy ukończone towary zostały zakupione lub wytworzone. Data ta jest używana do obliczania terminu przydatności.
