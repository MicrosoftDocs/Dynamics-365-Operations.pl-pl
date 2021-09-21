---
title: Tekst jest zastępowany, gdy towar jest konfigurowany w wierszu zamówienia sprzedaży
description: Gdy produkt jest konfigurowany w wierszu zamówienia sprzedaży, zmodyfikowany tekst jest zastępowany tekstem standardowym. Zmień tekst po skonfigurowaniu wiersza, a nie przed.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477262"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>Tekst pozycji jest zastępowany, gdy produkt jest konfigurowany w wierszu zamówienia sprzedaży

## <a name="symptoms"></a>Objawy

Ten problem występuje podczas tworzenia wiersza zamówienia sprzedaży dla towaru konfigurowalnego, a następnie modyfikowania tekstu towaru. Po skonfigurowaniu towaru i wybraniu opcji **OK** tekst jest zastępowany tekstem standardowym.

## <a name="resolution"></a>Rozwiązanie

To zachowanie jest oczekiwane. Pole tekstowe zawiera nazwę wariantu, która jest wypełniana tylko po skonfigurowaniu wiersza. Dlatego należy zmienić tekst po skonfigurowaniu wiersza, a nie przed.
