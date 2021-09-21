---
title: Informacje podatkowe nie są aktualizowane, jeśli lokalizacja zamówienia sprzedaży została zmieniona
description: Jeśli oddział, magazyn lub adres dostawy został zmieniony w nagłówku zamówienia sprzedaży, informacje o podatku w tych wierszach nie są aktualizowane. Należy to zrobić ręcznie.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477312"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>Informacje podatkowe nie są aktualizowane, jeśli lokalizacja w nagłówku zamówienia sprzedaży została zmieniona

## <a name="symptoms"></a>Objawy

Jeśli oddział, magazyn lub adres dostawy został zmieniony w nagłówku zamówienia sprzedaży, informacje o podatku w tych wierszach nie są aktualizowane.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Ten problem występuje, ponieważ adres dostawy, oddział i magazyn nie są automatycznie zmieniane na poziomie wiersza. Musisz zaktualizować je ręcznie.
