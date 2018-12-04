---
title: "Księgi pochodne"
description: "Ten artykuł zawiera omówienie funkcji ksiąg pochodnych."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e43dcc15212ae90a33d59fa32692aabcba7a19cb
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="derived-books"></a>Księgi pochodne

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie funkcji ksiąg pochodnych.

Księgi pochodne upraszczają księgowanie transakcji księgi środków trwałych, które są planowane w regularnych interwałach.  Jedną księgę wskazuje się jako podstawową. Jest to zazwyczaj księga używana do amortyzacji księgowej. Następnie dołączasz tę księgę do innych ksiąg, które służą do księgowania transakcji w takich samych interwałach, jak w księdze podstawowej. Księgi amortyzacji podatkowej są często konfigurowane jako księgi pochodne. 

Najczęstszymi transakcjami księgowanymi w księgach pochodnych są transakcje nabycia, korekty wartości początkowej i likwidacje. 

## <a name="example"></a>Przykład

Księgi B i C są skonfigurowane jako księgi pochodne księgi A dla typu transakcji Nabycie. W księdze A wprowadzasz transakcję nabycia środka 123 o wartości 1500,00. 

Podczas księgowania transakcji jest generowana i księgowana transakcja nabycia o wartości 1500,00 dla składnika aktywów 123 w księdze B i składnika aktywów 123 w księdze C. W czasie przygotowywania transakcji księgi podstawowej do zaksięgowania w arkuszu środków trwałych możliwe jest również przeglądanie i modyfikowanie transakcji ksiąg pochodnych. W czasie przygotowywania transakcji księgi podstawowej w innym arkuszu nie są wyświetlane transakcje ksiąg pochodnych. Jednak są one księgowane na odpowiednich kontach i w warstwach księgowania podczas księgowania transakcji w księdze podstawowej.

> [!NOTE]                                                                                                                               
> Księgi skonfigurowane tak, aby transakcje były księgowane w interwałach innych niż interwały księgi podstawowej, należy dołączyć do środka trwałego jako oddzielne księgi, a nie jako księgi pochodne.  

Aby uzyskać więcej informacji, zobacz [Księgowanie za pomocą ksiąg pochodnych](post-derived-value-models.md).




