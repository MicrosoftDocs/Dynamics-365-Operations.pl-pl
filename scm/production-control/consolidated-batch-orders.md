---
title: "Skonsolidowane szarże produkcyjne"
description: "W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3359f1cd5c3f1ecf25c3f28a366c022826cf895e
ms.lasthandoff: 03/31/2017


---

# <a name="consolidated-batch-orders"></a>Skonsolidowane szarże produkcyjne

[!include[banner](../includes/banner.md)]


W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych.

Wytwarzany produkt masowy jest uznawany za element nadrzędny, natomiast produkt zapakowany jest uznawany za element podrzędny. Relacja między produktem masowym a produktem zapakowanym jest wyrażona jako konwersja produktu masowego. Konwersja produktu masowego jest definiowana względem produktu masowego.  

Zapakowane produkty mogą być pakowane w kontenery tej samej wielkości lub różnej wielkości, które są uznawane za pojedynczą jednostkę. Dzięki konsolidacji zamówień dla produktu masowego można wyświetlić wszystkie pokrewne szarże produkcyjne w jednym widoku, by lepiej określić wszelkie pozostałe prace, które muszą zostać wykonane.  

Skonsolidowana szarża produkcyjna może zawierać dowolną kombinację następujących zamówień:

-   Pojedyncze zamówienie produktu zbiorczego i wiele zamówień produktu zapakowanego
-   Wiele zamówień produktu zbiorczego i wiele zamówień produktu zapakowanego
-   Wiele zamówień produktu zbiorczego i jedno zamówienie produktu zapakowanego
-   Tylko zamówienia produktów zapakowanych





