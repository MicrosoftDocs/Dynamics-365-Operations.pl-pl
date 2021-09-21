---
title: Zadanie aktualizacji dokumentów przyjęcia produktów potwierdza niepotwierdzone zamówienia
description: Po uruchomieniu aktualizacji dokumentów przyjęcia produktów system potwierdza niepotwierdzone zamówienia, które mają stan Zarejestrowane. Zapoznaj się z funkcją, która usuwa ten problem.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477273"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>Niepotwierdzone zamówienia zakupu są potwierdzane po uruchomieniu aktualizacji dokumentów przyjęcia produktów

## <a name="symptoms"></a>Objawy

Po uruchomieniuzadania okresowego *Aktualizowanie dokumentów przyjęcia produktów* system automatycznie potwierdza niepotwierdzone zamówienia zakupu ze stanem transakcji magazynowej *Zarejestrowane*.

## <a name="resolution"></a>Rozwiązanie

Nowa funkcja obsługi ładunków przychodzących *Przekroczenie przyjmowania ilości ładunku* rozwiązuje ten problem. Aby włączyć tę funkcję, przejdź do obszaru roboczego [Zarządzanie funkcjami](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) i włącz następujące funkcje (w kolejności, w jakiej są wymienione):

1. Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem
2. Przyjęcie nadmiernej ilości obciążenia pracą

Aby uzyskać więcej informacji, zajrzyj do [Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu](/dynamics365/supply-chain/warehousing/inbound-load-handling).
