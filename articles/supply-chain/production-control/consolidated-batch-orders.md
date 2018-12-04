---
title: "Skonsolidowane szarże produkcyjne"
description: "W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d6ee4ea9c8af06c493d906887f5ed6f7874e703e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

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





