---
title: "Księgowanie transakcji środków trwałych w warstwach księgowania"
description: "Ten artykuł zawiera omówienie funkcji warstwy księgowania dla transakcji na środkach trwałych."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe92e2f0d57a1daeb2c20da91e1b60b2308dce6a
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="1054a-103">Księgowanie transakcji środków trwałych w warstwach księgowania</span><span class="sxs-lookup"><span data-stu-id="1054a-103">Post fixed asset transactions to posting layers</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="1054a-104">Ten artykuł zawiera omówienie funkcji warstwy księgowania dla transakcji na środkach trwałych.</span><span class="sxs-lookup"><span data-stu-id="1054a-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="1054a-105">Środek trwały jest często amortyzowany na różne sposoby w zależności od konkretnego celu.</span><span class="sxs-lookup"><span data-stu-id="1054a-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="1054a-106">Amortyzacja do celów podatkowych jest obliczana na bieżących zasadach podatkowych w celu uzyskania najwyższej możliwej amortyzacji przed opodatkowaniem, natomiast amortyzacja do celów sprawozdawczych jest obliczana na podstawie zasad i norm księgowych.</span><span class="sxs-lookup"><span data-stu-id="1054a-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="1054a-107">W warstwach księgowania obliczane i rejestrowane są różne rodzaje amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="1054a-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="1054a-108">Każda księga dołączana do środka trwałego jest konfigurowany dla konkretnej warstwy księgowania mającej ogólne zamierzenie amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="1054a-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="1054a-109">Istnieje dziesięć warstw księgowania: Bieżący, Operacje, Podatek i 7 warstw niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="1054a-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="1054a-110">Można również wyłączyć księgowanie pozycji księgi w księdze głównej, ustawiając w polu Księguj w księdze głównej wartość Nie.</span><span class="sxs-lookup"><span data-stu-id="1054a-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="1054a-111">Wtedy w polu Warstwa księgowania jest automatycznie ustawiana wartość Brak.</span><span class="sxs-lookup"><span data-stu-id="1054a-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="1054a-112">Zazwyczaj księgi, które nie powodują księgowania w księdze głównej, są używane na potrzeby sprawozdawczości podatkowej.</span><span class="sxs-lookup"><span data-stu-id="1054a-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="1054a-113">Zapewnia to dodatkową elastyczność umożliwiającą usuwanie historycznych transakcji z księgi środków trwałych, ponieważ nie zostały one potwierdzone w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="1054a-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="1054a-114">Arkusze środków trwałych są zdefiniowane na stronie Nazwy arkuszy (ścieżka Księga główna > Konfiguracja arkusza > Nazwy arkuszy).</span><span class="sxs-lookup"><span data-stu-id="1054a-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="1054a-115">Każdy arkusz, w którym można zaksięgować amortyzację, zdefiniowany jest nazwą tylko dla jednej warstwy księgowania.</span><span class="sxs-lookup"><span data-stu-id="1054a-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="1054a-116">Nie można zmienić warstwy księgowania w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="1054a-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="1054a-117">To ograniczenie pozwala zagwarantować, że transakcje dla każdej warstwy księgowania są przechowywane oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="1054a-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="1054a-118">Dla każdej warstwy księgowania konieczne jest utworzenie przynajmniej jednej nazwy arkusza.</span><span class="sxs-lookup"><span data-stu-id="1054a-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="1054a-119">Jeśli używasz ksiąg, których zapisy nie są księgowanie w księdze głównej, trzeba również utworzyć arkusz z ustawioną warstwą księgowania Brak.</span><span class="sxs-lookup"><span data-stu-id="1054a-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="1054a-120">Na stronie Profile księgowania środków trwałych można wskazać konta księgowe dla transakcji na środkach trwałych.</span><span class="sxs-lookup"><span data-stu-id="1054a-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="1054a-121">Dla każdego profilu księgowania należy wybrać właściwy typ transakcji i księgę, a następnie wskazać konta księgowe.</span><span class="sxs-lookup"><span data-stu-id="1054a-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="1054a-122">Skonfiguruj rekord profilu księgowania dla każdej księgi, który będzie księgować w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="1054a-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="1054a-123">Używając ksiąg pochodnych, można księgować transakcje jednocześnie w różnych warstwach księgowania.</span><span class="sxs-lookup"><span data-stu-id="1054a-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="1054a-124">Transakcje księgi podstawowej tworzy się w arkuszu, którego warstwa księgowania odpowiada warstwie księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="1054a-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="1054a-125">Podczas księgowania transakcje księgi pochodnej są księgowane w odpowiednich warstwach księgowania.</span><span class="sxs-lookup"><span data-stu-id="1054a-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="1054a-126">Aby uzyskać więcej informacji, zobacz [Księgi pochodne](derived-books.md) i [Księgowanie za pomocą ksiąg pochodnych](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="1054a-126">For more information see, [Derived books](derived-books.md) and [Posting with derived books](post-derived-value-models.md).</span></span>




