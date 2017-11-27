---
title: "Skonsolidowane szarże produkcyjne"
description: "W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d6ee4ea9c8af06c493d906887f5ed6f7874e703e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="consolidated-batch-orders"></a><span data-ttu-id="e87b7-103">Skonsolidowane szarże produkcyjne</span><span class="sxs-lookup"><span data-stu-id="e87b7-103">Consolidated batch orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e87b7-104">W tym artykule opisano koncepcję skonsolidowanych szarż produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="e87b7-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="e87b7-105">Wytwarzany produkt masowy jest uznawany za element nadrzędny, natomiast produkt zapakowany jest uznawany za element podrzędny.</span><span class="sxs-lookup"><span data-stu-id="e87b7-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="e87b7-106">Relacja między produktem masowym a produktem zapakowanym jest wyrażona jako konwersja produktu masowego.</span><span class="sxs-lookup"><span data-stu-id="e87b7-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="e87b7-107">Konwersja produktu masowego jest definiowana względem produktu masowego.</span><span class="sxs-lookup"><span data-stu-id="e87b7-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="e87b7-108">Zapakowane produkty mogą być pakowane w kontenery tej samej wielkości lub różnej wielkości, które są uznawane za pojedynczą jednostkę.</span><span class="sxs-lookup"><span data-stu-id="e87b7-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="e87b7-109">Dzięki konsolidacji zamówień dla produktu masowego można wyświetlić wszystkie pokrewne szarże produkcyjne w jednym widoku, by lepiej określić wszelkie pozostałe prace, które muszą zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="e87b7-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="e87b7-110">Skonsolidowana szarża produkcyjna może zawierać dowolną kombinację następujących zamówień:</span><span class="sxs-lookup"><span data-stu-id="e87b7-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="e87b7-111">Pojedyncze zamówienie produktu zbiorczego i wiele zamówień produktu zapakowanego</span><span class="sxs-lookup"><span data-stu-id="e87b7-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="e87b7-112">Wiele zamówień produktu zbiorczego i wiele zamówień produktu zapakowanego</span><span class="sxs-lookup"><span data-stu-id="e87b7-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="e87b7-113">Wiele zamówień produktu zbiorczego i jedno zamówienie produktu zapakowanego</span><span class="sxs-lookup"><span data-stu-id="e87b7-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="e87b7-114">Tylko zamówienia produktów zapakowanych</span><span class="sxs-lookup"><span data-stu-id="e87b7-114">Only packed orders</span></span>





