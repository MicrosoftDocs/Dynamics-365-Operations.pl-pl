---
title: Okresy podziału w arkuszach okresowych
description: Ten temat zawiera informacje o funkcji okresów podziału w arkuszach okresowych i arkuszach cyklicznych dla firm w Czechach, Estonii, na Węgrzech, na Łotwie, na Litwie, w Polsce i w Rosji.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5ea11e94c188c04c6d3d8ab0173fcc2ba56335c3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408375"
---
# <a name="split-periods-in-periodic-journals"></a><span data-ttu-id="8f854-103">Okresy podziału w arkuszach okresowych</span><span class="sxs-lookup"><span data-stu-id="8f854-103">Split periods in periodic journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f854-104">Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="8f854-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the journal is posted.</span></span> <span data-ttu-id="8f854-105">Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące.</span><span class="sxs-lookup"><span data-stu-id="8f854-105">When you create the journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="8f854-106">Można także określić liczbę okresów, dla których arkusz będzie księgowany.</span><span class="sxs-lookup"><span data-stu-id="8f854-106">You also specify the number of periods for which the journal will be posted.</span></span>

<span data-ttu-id="8f854-107">Aby wielokrotnie pobierać i księgować wiersze transakcji, można użyć strony **Arkusze okresowe**.</span><span class="sxs-lookup"><span data-stu-id="8f854-107">To repeatedly retrieve and post transaction lines, you can use the **Periodic journals** page.</span></span> <span data-ttu-id="8f854-108">Dla firm w Czechach, Estonii, na Węgrzech, Łotwie, Litwie, w Polsce i Rosji strona **Arkusze okresowe** została rozszerzona o funkcjonalność podziału na okresy.</span><span class="sxs-lookup"><span data-stu-id="8f854-108">For legal entities in Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, and Russia, the **Periodic journals** page is extended by the split for periods functionality.</span></span> <span data-ttu-id="8f854-109">Aby uzyskać więcej informacji, zobacz [Księgowanie arkuszy okresowych](../general-ledger/tasks/post-periodic-journals.md)</span><span class="sxs-lookup"><span data-stu-id="8f854-109">For more information, see [Post periodic journals](../general-ledger/tasks/post-periodic-journals.md)</span></span>

### <a name="example-split-for-periods-in-periodic-journals"></a><span data-ttu-id="8f854-110">Przykład: Podział na okresy w arkuszach okresowych</span><span class="sxs-lookup"><span data-stu-id="8f854-110">Example: Split for periods in periodic journals</span></span>

<span data-ttu-id="8f854-111">Firma ubezpieczeniowa oferuje organizacji rabat na przedpłatę polisy ubezpieczeniowej na cały rok.</span><span class="sxs-lookup"><span data-stu-id="8f854-111">An insurance company offers your organization a discount for prepaying the insurance policy for an entire year.</span></span> <span data-ttu-id="8f854-112">Płatność jest zaksięgowana na koncie aktywów, takich jak przedpłaty na ubezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="8f854-112">The payment is posted to an asset account such as prepaid insurance.</span></span> <span data-ttu-id="8f854-113">Następnie miesięczny koszt ubezpieczenia jest amortyzowany w ciągu roku przez utworzenie arkusza okresowego, który zawiera kredyt na koncie przedpłat na ubezpieczenia i debet na koncie kosztów ubezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="8f854-113">You then amortize your monthly insurance expense throughout the year by creating a periodic journal that contains a credit to the prepaid insurance account and a debit to an insurance expense account.</span></span> <span data-ttu-id="8f854-114">W takim przypadku można użyć funkcji podziału na okresy.</span><span class="sxs-lookup"><span data-stu-id="8f854-114">In this case, you can use the split for periods functionality.</span></span> <span data-ttu-id="8f854-115">Kliknij przycisk **Podziel na okresy** znajdujący się w okienku akcji na stronie **Wiersze arkusza** **okresowego**, a następnie wypełnij następujące pola.</span><span class="sxs-lookup"><span data-stu-id="8f854-115">Click the **Split for periods** button on the Action Pane on the **Periodic journal** **lines** page, and then specify the following fields.</span></span>


| <span data-ttu-id="8f854-116">Pole</span><span class="sxs-lookup"><span data-stu-id="8f854-116">Field</span></span>            | <span data-ttu-id="8f854-117">Opis</span><span class="sxs-lookup"><span data-stu-id="8f854-117">Description</span></span>                                                                                                                                                                                             |
|-----------------------|---------------------------------------------------------------|
| <span data-ttu-id="8f854-118">**Data rozpoczęcia**</span><span class="sxs-lookup"><span data-stu-id="8f854-118">**Start date**</span></span>        | <span data-ttu-id="8f854-119">Wybierz datę dla pierwszego wiersza arkusza okresowego.</span><span class="sxs-lookup"><span data-stu-id="8f854-119">Select the date for the first periodic journal line.</span></span>                                                                                                                                                        |
| <span data-ttu-id="8f854-120">**Liczba okresów**</span><span class="sxs-lookup"><span data-stu-id="8f854-120">**Number of periods**</span></span> | <span data-ttu-id="8f854-121">Wprowadź liczbę okresów, na które zostanie podzielony wiersz dziennika.</span><span class="sxs-lookup"><span data-stu-id="8f854-121">Enter the number of periods across which to split the journal line.</span></span> <span data-ttu-id="8f854-122">Ta wartość określa liczbę nowych transakcji, które zostaną wygenerowane.</span><span class="sxs-lookup"><span data-stu-id="8f854-122">This value determines how many new transactions are generated.</span></span> <span data-ttu-id="8f854-123">Kwota transakcji jest równo dzielona między nowymi transakcjami.</span><span class="sxs-lookup"><span data-stu-id="8f854-123">The transaction amount is distributed evenly among the new transactions.</span></span> |
| <span data-ttu-id="8f854-124">**Jednostka**</span><span class="sxs-lookup"><span data-stu-id="8f854-124">**Unit**</span></span>              | <span data-ttu-id="8f854-125">Wybierz jednostkę miary okresu.</span><span class="sxs-lookup"><span data-stu-id="8f854-125">Select the unit of measure for the period.</span></span>                                                                                                                                                                  |
| <span data-ttu-id="8f854-126">**Zakres czasowy**</span><span class="sxs-lookup"><span data-stu-id="8f854-126">**Period interval**</span></span>   | <span data-ttu-id="8f854-127">Określ interwał (odstęp czasu) między okresami księgowania.</span><span class="sxs-lookup"><span data-stu-id="8f854-127">Determine an interval between posting periods.</span></span>                                                                                                                                                              |

<span data-ttu-id="8f854-128">Na przykład aby wygenerować kwartalne księgowania, wprowadź **4** w polu **Liczba okresów**, zaznacz opcję **Miesiące** w polu **Jednostka** i wprowadź **3** w polu **Zakres czasowy**.</span><span class="sxs-lookup"><span data-stu-id="8f854-128">For example, to generate quarterly postings, enter **4** in the **Number of periods** field, select **Months** in the **Unit** field, and enter **3** in the **Period interval** field.</span></span> <span data-ttu-id="8f854-129">System generuje cztery wiersze arkusza, każdy dla jednej czwartej wprowadzonej kwoty wiersza arkusza, w 3-miesięcznych interwałach.</span><span class="sxs-lookup"><span data-stu-id="8f854-129">The system generates four journal lines, each for one fourth of the journal line amount that you entered, at 3-month intervals.</span></span> <span data-ttu-id="8f854-130">Podobna funkcjonalność jest również dostępna dla arkusza finansowego.</span><span class="sxs-lookup"><span data-stu-id="8f854-130">Similar functionality is also available for the general journal.</span></span> <span data-ttu-id="8f854-131">Podczas wyświetlania wierszy arkusza finansowego wybierz kolejno opcje **Arkusz okresowy** &gt; **Zapisz arkusz**.</span><span class="sxs-lookup"><span data-stu-id="8f854-131">When viewing general journal lines, select **Period journal** &gt; **Save journal**.</span></span>



