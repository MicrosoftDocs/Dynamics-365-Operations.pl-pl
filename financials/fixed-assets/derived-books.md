---
title: "Księgi pochodne"
description: "Ten artykuł zawiera omówienie funkcji ksiąg pochodnych."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 9319fe95a25b38ca12cbc8633763b042e4086aea
ms.lasthandoff: 03/31/2017


---

# <a name="derived-books"></a>Księgi pochodne

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie funkcji ksiąg pochodnych.

Księgi pochodne upraszczają księgowanie transakcji księgi środków trwałych, które są planowane w regularnych interwałach.  Jedną księgę wskazuje się jako podstawową. Jest to zazwyczaj księga używana do amortyzacji księgowej. Następnie dołączasz tę księgę do innych ksiąg, które służą do księgowania transakcji w takich samych interwałach, jak w księdze podstawowej. Księgi amortyzacji podatkowej są często konfigurowane jako księgi pochodne. 

Najczęstszymi transakcjami księgowanymi w księgach pochodnych są transakcje nabycia, korekty wartości początkowej i likwidacje. 

## <a name="example"></a>Przykład

Księgi B i C są skonfigurowane jako księgi pochodne księgi A dla typu transakcji Nabycie. W księdze A wprowadzasz transakcję nabycia środka 123 o wartości 1500,00. 

Podczas księgowania transakcji jest generowana i księgowana transakcja nabycia o wartości 1500,00 dla składnika aktywów 123 w księdze B i składnika aktywów 123 w księdze C. W czasie przygotowywania transakcji księgi podstawowej do zaksięgowania w arkuszu środków trwałych możliwe jest również przeglądanie i modyfikowanie transakcji ksiąg pochodnych. W czasie przygotowywania transakcji księgi podstawowej w innym arkuszu nie są wyświetlane transakcje ksiąg pochodnych. Jednak są one księgowane na odpowiednich kontach i w warstwach księgowania podczas księgowania transakcji w księdze podstawowej.

> [!NOTE]                                                                                                                               
> Księgi skonfigurowane tak, aby transakcje były księgowane w interwałach innych niż interwały księgi podstawowej, należy dołączyć do środka trwałego jako oddzielne księgi, a nie jako księgi pochodne.  

Aby uzyskać więcej informacji, zobacz [Księgowanie za pomocą ksiąg pochodnych](post-derived-value-models.md).




