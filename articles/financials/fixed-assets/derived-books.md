---
title: "Księgi pochodne"
description: "Ten artykuł zawiera omówienie funkcji ksiąg pochodnych."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: twheeloc
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

# <a name="derived-books"></a><span data-ttu-id="5a519-103">Księgi pochodne</span><span class="sxs-lookup"><span data-stu-id="5a519-103">Derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5a519-104">Ten artykuł zawiera omówienie funkcji ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="5a519-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="5a519-105">Księgi pochodne upraszczają księgowanie transakcji księgi środków trwałych, które są planowane w regularnych interwałach.</span><span class="sxs-lookup"><span data-stu-id="5a519-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="5a519-106">Jedną księgę wskazuje się jako podstawową.</span><span class="sxs-lookup"><span data-stu-id="5a519-106">You choose one book as the primary book.</span></span> <span data-ttu-id="5a519-107">Jest to zazwyczaj księga używana do amortyzacji księgowej.</span><span class="sxs-lookup"><span data-stu-id="5a519-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="5a519-108">Następnie dołączasz tę księgę do innych ksiąg, które służą do księgowania transakcji w takich samych interwałach, jak w księdze podstawowej.</span><span class="sxs-lookup"><span data-stu-id="5a519-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="5a519-109">Księgi amortyzacji podatkowej są często konfigurowane jako księgi pochodne.</span><span class="sxs-lookup"><span data-stu-id="5a519-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="5a519-110">Najczęstszymi transakcjami księgowanymi w księgach pochodnych są transakcje nabycia, korekty wartości początkowej i likwidacje.</span><span class="sxs-lookup"><span data-stu-id="5a519-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="5a519-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="5a519-111">Example</span></span>

<span data-ttu-id="5a519-112">Księgi B i C są skonfigurowane jako księgi pochodne księgi A dla typu transakcji Nabycie.</span><span class="sxs-lookup"><span data-stu-id="5a519-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="5a519-113">W księdze A wprowadzasz transakcję nabycia środka 123 o wartości 1500,00.</span><span class="sxs-lookup"><span data-stu-id="5a519-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="5a519-114">Podczas księgowania transakcji jest generowana i księgowana transakcja nabycia o wartości 1500,00 dla składnika aktywów 123 w księdze B i składnika aktywów 123 w księdze C.</span><span class="sxs-lookup"><span data-stu-id="5a519-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="5a519-115">W czasie przygotowywania transakcji księgi podstawowej do zaksięgowania w arkuszu środków trwałych możliwe jest również przeglądanie i modyfikowanie transakcji ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="5a519-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="5a519-116">W czasie przygotowywania transakcji księgi podstawowej w innym arkuszu nie są wyświetlane transakcje ksiąg pochodnych.</span><span class="sxs-lookup"><span data-stu-id="5a519-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="5a519-117">Jednak są one księgowane na odpowiednich kontach i w warstwach księgowania podczas księgowania transakcji w księdze podstawowej.</span><span class="sxs-lookup"><span data-stu-id="5a519-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="5a519-118">Księgi skonfigurowane tak, aby transakcje były księgowane w interwałach innych niż interwały księgi podstawowej, należy dołączyć do środka trwałego jako oddzielne księgi, a nie jako księgi pochodne.</span><span class="sxs-lookup"><span data-stu-id="5a519-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="5a519-119">Aby uzyskać więcej informacji, zobacz [Księgowanie za pomocą ksiąg pochodnych](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="5a519-119">For more information, see [Posting with derived books](post-derived-value-models.md).</span></span>




