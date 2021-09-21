---
title: Nie można przetworzyć dostawy bezpośredniej dla magazynu z obsługą WMS
description: Jeśli magazyn ma włączoną funkcję WMS, nie obsługuje dostawy bezpośredniej. Aby można było skorzystać z dostawy bezpośredniej, należy wybrać pozycję i magazyn spoza WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477360"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>Nie można przetworzyć dostawy bezpośredniej dla magazynu z obsługą WMS

## <a name="symptoms"></a>Objawy

Jeśli pozycja zostanie dodana do wiersza sprzedaży w celu bezpośredniej dostawy z magazynu, który jest włączony dla zarządzania magazynem (WMS), podczas aktualizacji wiersza sprzedaży wyświetlany jest następujący komunikat o błędzie:

> Nie można przetworzyć dostawy bezpośredniej dla magazynu 1%, ponieważ ma włączone zarządzanie magazynem. Określ inny magazyn, który nie obsługuje zarządzania magazynem.

## <a name="resolution"></a>Rozwiązanie

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie usługa WMS nie obsługuje dostawy bezpośredniej. Dlatego też, aby można było skorzystać z dostawy bezpośredniej, należy wybrać pozycję i magazyn spoza WMS.
