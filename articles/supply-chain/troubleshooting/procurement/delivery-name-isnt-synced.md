---
title: Nazwa dostawy nie jest synchronizowana po zmianie adresu dostawy zamówienia zakupu
description: Po zmianie adresu dostawy w nagłówku zamówienia zakupu nazwa dostawy nie jest synchronizowana
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
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477276"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>Nazwa dostawy nie jest synchronizowana po zmianie adresu dostawy zamówienia zakupu

## <a name="symptoms"></a>Objawy

Adres w nagłówku zamówienia zakupu jest aktualizowany na adres, który nie jest adresem dostawy. Mimo że adres jest aktualizowany na zamówieniu zakupu, nazwa dostawy nie jest aktualizowana na podstawie zaktualizowanego adresu.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Wybrany adres musi być klasyfikowany jako adres dostawy. W przeciwnym razie nazwa dostawy nie zostanie zaktualizowana na podstawie wybranego adresu.
