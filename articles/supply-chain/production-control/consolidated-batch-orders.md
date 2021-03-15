---
title: Skonsolidowane szarże produkcyjne
description: W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2098cb458821146f6d1bf029591493ac745626f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966462"
---
# <a name="consolidated-batch-orders"></a>Skonsolidowane szarże produkcyjne

[!include [banner](../includes/banner.md)]

W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych.

Wytwarzany produkt masowy jest uznawany za element nadrzędny, natomiast produkt zapakowany jest uznawany za element podrzędny. Relacja między produktem masowym a produktem zapakowanym jest wyrażona jako konwersja produktu masowego. Konwersja produktu masowego jest definiowana względem produktu masowego.  

Zapakowane produkty mogą być pakowane w kontenery tej samej wielkości lub różnej wielkości, które są uznawane za pojedynczą jednostkę. Dzięki konsolidacji zamówień dla produktu masowego można wyświetlić wszystkie pokrewne szarże produkcyjne w jednym widoku, by lepiej określić wszelkie pozostałe prace, które muszą zostać wykonane.  

Skonsolidowana szarża produkcyjna może zawierać dowolną kombinację następujących zamówień:

-   Pojedyncze zamówienie produktu zbiorczego i wiele zamówień produktu zapakowanego
-   Wiele zamówień produktu zbiorczego i wiele zamówień produktu zapakowanego
-   Wiele zamówień produktu zbiorczego i jedno zamówienie produktu zapakowanego
-   Tylko zamówienia produktów zapakowanych






[!INCLUDE[footer-include](../../includes/footer-banner.md)]