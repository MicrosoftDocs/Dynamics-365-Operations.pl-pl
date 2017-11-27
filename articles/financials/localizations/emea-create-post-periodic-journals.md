---
title: "Okresy podziału w arkuszach okresowych"
description: "Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza. Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące. Można także określić liczbę okresów, dla których arkusz będzie księgowany."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 73ccfc906e8d7a91e7bae5ae21d9ddad9d58f109
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="split-periods-in-periodic-journals"></a><span data-ttu-id="21658-105">Okresy podziału w arkuszach okresowych</span><span class="sxs-lookup"><span data-stu-id="21658-105">Split periods in periodic journals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="21658-106">Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="21658-106">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the journal is posted.</span></span> <span data-ttu-id="21658-107">Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące.</span><span class="sxs-lookup"><span data-stu-id="21658-107">When you create the journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="21658-108">Można także określić liczbę okresów, dla których arkusz będzie księgowany.</span><span class="sxs-lookup"><span data-stu-id="21658-108">You also specify the number of periods for which the journal will be posted.</span></span>

<span data-ttu-id="21658-109">Aby wielokrotnie pobierać i księgować wiersze transakcji, można użyć strony **Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="21658-109">To repeatedly retrieve and post transaction lines, you can use the **Periodic journals** page.</span></span> <span data-ttu-id="21658-110">Dla firm w Czechach, Estonii, na Węgrzech, Łotwie, Litwie, w Polsce i Rosji strona **Arkusze okresowe** została rozszerzona o funkcjonalność podziału na okresy.</span><span class="sxs-lookup"><span data-stu-id="21658-110">For legal entities in Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, and Russia, the **Periodic journals** page is extended by the split for periods functionality.</span></span> <span data-ttu-id="21658-111">Aby uzyskać więcej informacji, zobacz [Księgowanie arkusza okresowego](../general-ledger/tasks/post-periodic-journals.md)</span><span class="sxs-lookup"><span data-stu-id="21658-111">For more information, see [Post a periodic journal](../general-ledger/tasks/post-periodic-journals.md)</span></span>

### <a name="example-split-for-periods-in-periodic-journals"></a><span data-ttu-id="21658-112">Przykład: Podział na okresy w arkuszach okresowych</span><span class="sxs-lookup"><span data-stu-id="21658-112">Example: Split for periods in periodic journals</span></span>

<span data-ttu-id="21658-113">Firma ubezpieczeniowa oferuje organizacji rabat na przedpłatę polisy ubezpieczeniowej na cały rok.</span><span class="sxs-lookup"><span data-stu-id="21658-113">An insurance company offers your organization a discount for prepaying the insurance policy for an entire year.</span></span> <span data-ttu-id="21658-114">Płatność jest zaksięgowana na koncie aktywów, takich jak przedpłaty na ubezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="21658-114">The payment is posted to an asset account such as prepaid insurance.</span></span> <span data-ttu-id="21658-115">Następnie miesięczny koszt ubezpieczenia jest amortyzowany w ciągu roku przez utworzenie arkusza okresowego, który zawiera kredyt na koncie przedpłat na ubezpieczenia i debet na koncie kosztów ubezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="21658-115">You then amortize your monthly insurance expense throughout the year by creating a periodic journal that contains a credit to the prepaid insurance account and a debit to an insurance expense account.</span></span> <span data-ttu-id="21658-116">W takim przypadku można użyć funkcji podziału na okresy.</span><span class="sxs-lookup"><span data-stu-id="21658-116">In this case, you can use the split for periods functionality.</span></span> <span data-ttu-id="21658-117">Kliknij przycisk **Podziel na okresy** znajdujący się w okienku akcji na stronie **Wiersze arkusza** **okresowego**, a następnie wypełnij następujące pola.</span><span class="sxs-lookup"><span data-stu-id="21658-117">Click the **Split for periods** button on the Action Pane on the **Periodic journal** **lines** page, and then specify the following fields.</span></span>

|                       |                                                                                                                                                                                                             |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="21658-118">**Pole**</span><span class="sxs-lookup"><span data-stu-id="21658-118">**Field**</span></span>             | <span data-ttu-id="21658-119">**Opis**</span><span class="sxs-lookup"><span data-stu-id="21658-119">**Description**</span></span>                                                                                                                                                                                             |
| <span data-ttu-id="21658-120">**Data rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="21658-120">**Start date**</span></span>        | <span data-ttu-id="21658-121">Wybierz datę dla pierwszego wiersza arkusza okresowego.</span><span class="sxs-lookup"><span data-stu-id="21658-121">Select the date for the first periodic journal line.</span></span>                                                                                                                                                        |
| <span data-ttu-id="21658-122">**Liczba okresów**</span><span class="sxs-lookup"><span data-stu-id="21658-122">**Number of periods**</span></span> | <span data-ttu-id="21658-123">Wprowadź liczbę okresów, na które zostanie podzielony wiersz dziennika.</span><span class="sxs-lookup"><span data-stu-id="21658-123">Enter the number of periods across which to split the journal line.</span></span> <span data-ttu-id="21658-124">Ta wartość określa liczbę nowych transakcji, które zostaną wygenerowane.</span><span class="sxs-lookup"><span data-stu-id="21658-124">This value determines how many new transactions are generated.</span></span> <span data-ttu-id="21658-125">Kwota transakcji jest równo dzielona między nowymi transakcjami.</span><span class="sxs-lookup"><span data-stu-id="21658-125">The transaction amount is distributed evenly among the new transactions.</span></span> |
| <span data-ttu-id="21658-126">**Jednostka**</span><span class="sxs-lookup"><span data-stu-id="21658-126">**Unit**</span></span>              | <span data-ttu-id="21658-127">Wybierz jednostkę miary okresu.</span><span class="sxs-lookup"><span data-stu-id="21658-127">Select the unit of measure for the period.</span></span>                                                                                                                                                                  |
| <span data-ttu-id="21658-128">**Zakres czasowy**</span><span class="sxs-lookup"><span data-stu-id="21658-128">**Period interval**</span></span>   | <span data-ttu-id="21658-129">Określ interwał (odstęp czasu) między okresami księgowania.</span><span class="sxs-lookup"><span data-stu-id="21658-129">Determine an interval between posting periods.</span></span>                                                                                                                                                              |

<span data-ttu-id="21658-130">Na przykład aby wygenerować kwartalne księgowania, wprowadź **4** w polu **Liczba okresów**, zaznacz opcję **Miesiące** w polu **Jednostka** i wprowadź **3** w polu **Zakres czasowy**.</span><span class="sxs-lookup"><span data-stu-id="21658-130">For example, to generate quarterly postings, enter **4** in the **Number of periods** field, select **Months** in the **Unit** field, and enter **3** in the **Period interval** field.</span></span> <span data-ttu-id="21658-131">System generuje cztery wiersze arkusza, każdy dla jednej czwartej wprowadzonej kwoty wiersza arkusza, w 3-miesięcznych interwałach.</span><span class="sxs-lookup"><span data-stu-id="21658-131">The system generates four journal lines, each for one fourth of the journal line amount that you entered, at 3-month intervals.</span></span> <span data-ttu-id="21658-132">Podobna funkcjonalność jest również dostępna dla arkusza finansowego.</span><span class="sxs-lookup"><span data-stu-id="21658-132">Similar functionality is also available for the general journal.</span></span> <span data-ttu-id="21658-133">Podczas wyświetlania wierszy arkusza finansowego wybierz kolejno opcje **Arkusz okresowy** &gt; **Zapisz arkusz**.</span><span class="sxs-lookup"><span data-stu-id="21658-133">When viewing general journal lines, select **Period journal** &gt; **Save journal**.</span></span>




