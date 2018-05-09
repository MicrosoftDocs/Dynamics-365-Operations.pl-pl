---
title: "Podwyższenie amortyzacji"
description: "Ten artykuł zawiera omówienie funkcji podwyższania amortyzacji."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 89814bf54f09b91d7c23904c2f1ac31d5b284824
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="bonus-depreciation"></a><span data-ttu-id="53cf1-103">Podwyższenie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="53cf1-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53cf1-104">Ten artykuł zawiera omówienie funkcji podwyższania amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="53cf1-105">Podwyższenie amortyzacji umożliwia uzyskanie większych lub dodatkowych kwot amortyzacji w pierwszym roku użytkowania i amortyzacji środków.</span><span class="sxs-lookup"><span data-stu-id="53cf1-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="53cf1-106">Podwyższenie amortyzacji należy wykonać przed wszelkimi innymi obliczeniami amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="53cf1-107">Z tego względu najlepiej używać podwyższenia amortyzacji z księgami, w których wyłączono funkcję księgowania w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="53cf1-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="53cf1-108">Można użyć opcji **Usuwanie transakcji, które nie zostały zaksięgowane w księdze głównej**, aby usunąć historyczne transakcje dla ksiąg, które nie powodują księgowania w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="53cf1-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="53cf1-109">Następnie można uwzględnić podwyższenie amortyzacji na dalszych etapach cyklu życia środka trwałego poprzez usunięcie transakcji amortyzacji, które zostały wcześniej zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="53cf1-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="53cf1-110">Podwyższenie amortyzacji można obliczyć za pomocą propozycji lub tworząc ręczne transakcje podwyższenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="53cf1-111">Jeżeli w księdze środków trwałych istnieją transakcje podwyższenia lub transakcje korekty amortyzacji, nie można tworzyć transakcji podwyższenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="53cf1-112">Jeżeli do obliczenia podwyższenia amortyzacji jest stosowany proces propozycji, w obliczeniu podstawy zostaną uwzględnione wszystkie istniejące transakcje podwyższenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="53cf1-113">Obliczenie uwzględni również wszystkie poprzednie podwyższenia amortyzacji wprowadzone ręcznie dla składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="53cf1-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="53cf1-114">Jeżeli dla danego środka trwałego istnieje więcej niż jedno podwyższenie amortyzacji, jest uwzględniany priorytet.</span><span class="sxs-lookup"><span data-stu-id="53cf1-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="53cf1-115">Każde podwyższenie zmniejsza podstawę amortyzacji dla kolejnego podwyższenia.</span><span class="sxs-lookup"><span data-stu-id="53cf1-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="53cf1-116">Wartość odzyskana nie jest uwzględniana w podstawie składnika aktywów dla obliczeń podwyższenia amortyzacji, a konwencja amortyzacji nie jest stosowana do podwyższenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="53cf1-117">Obecnie w Stanach Zjednoczonych niektóre środki trwałe podlegają amortyzacji wg rozdziału 179.</span><span class="sxs-lookup"><span data-stu-id="53cf1-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="53cf1-118">Za pomocą potrącenia wg rozdziału 179 można przywrócić całość lub część kosztu niektórych środków do określonego limitu.</span><span class="sxs-lookup"><span data-stu-id="53cf1-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="53cf1-119">Można odzyskać koszt, odliczając go w roku, w którym składnik został włączony do eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="53cf1-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="53cf1-120">Example</span></span>
<span data-ttu-id="53cf1-121">Następujące podwyższenia amortyzacji są skojarzone z księgą środków trwałych:</span><span class="sxs-lookup"><span data-stu-id="53cf1-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="53cf1-122">**Rozdział 179:** 1000,00, priorytet 1</span><span class="sxs-lookup"><span data-stu-id="53cf1-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="53cf1-123">**Ulga podatkowa:** 30%, priorytet 2</span><span class="sxs-lookup"><span data-stu-id="53cf1-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="53cf1-124">Koszt nabycia składnika aktywów wynosi 5000,00.</span><span class="sxs-lookup"><span data-stu-id="53cf1-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="53cf1-125">Po obliczeniu podwyższenia amortyzacji pierwsza kwota podwyższenia amortyzacji będzie wynosiła 1000,00 zgodnie z amortyzacją wg rozdziału 179.</span><span class="sxs-lookup"><span data-stu-id="53cf1-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="53cf1-126">Kolejna kwota podwyższenia amortyzacji, zgodnie ze stawką amortyzacji po zastosowaniu ulgi, będzie obliczana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="53cf1-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="53cf1-127">Koszt nabycia – 1000 (amortyzacja wg rozdziału 179) x 30% = 1200</span><span class="sxs-lookup"><span data-stu-id="53cf1-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="53cf1-128">Jeżeli kwota podwyższenia amortyzacji jest wyższa niż pozostały koszt nabycia, kwota podwyższenia amortyzacji będzie równa obliczonej wartości podwyższenia lub wartości pozostałego kosztu nabycia — w zależności od tego, która kwota jest niższa.</span><span class="sxs-lookup"><span data-stu-id="53cf1-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="53cf1-129">Jeżeli pozostały koszt nabycia wynosi zero (0) lub mniej, transakcje podwyższenia amortyzacji nie zostaną wygenerowane.</span><span class="sxs-lookup"><span data-stu-id="53cf1-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="53cf1-130">Jeżeli podwyższenie amortyzacji jest obliczane za pomocą propozycji, zostanie utworzona transakcja podwyższenia dla wszystkich rekordów podwyższenia skojarzonych z księgą środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="53cf1-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="53cf1-131">Można utworzyć nieograniczoną liczbę rekordów podwyższenia amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="53cf1-132">Po przypisaniu tych rekordów do księgi grupy środków trwałych zostaną one zastosowane do księgi środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="53cf1-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="53cf1-133">Podwyższenie amortyzacji jest wprowadzane jako wartość procentowa lub jako kwota stała.</span><span class="sxs-lookup"><span data-stu-id="53cf1-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="53cf1-134">Po zaksięgowaniu propozycji amortyzacji transakcje podwyższenia amortyzacji są księgowane w księdze jako osobne transakcje obok transakcji amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="53cf1-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>




