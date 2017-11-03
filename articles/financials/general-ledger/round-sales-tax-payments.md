---
title: "Reguły płatności podatkowych i zaokrąglania"
description: "W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 13470282efc6b9135e86355cf8071b841aad3071
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="97499-103">Reguły płatności podatkowych i zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="97499-103">Sales tax payments and rounding rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="97499-104">W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.</span><span class="sxs-lookup"><span data-stu-id="97499-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="97499-105">Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym.</span><span class="sxs-lookup"><span data-stu-id="97499-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="97499-106">Można to zrobić, uruchamiając proces rozliczenia i księgowania podatku na stronie Podatek.</span><span class="sxs-lookup"><span data-stu-id="97499-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="97499-107">Podatek od sprzedaży w danym okresie zostanie rozliczony dla kont podatku, a saldo podatku zostanie zaksięgowane na koncie rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="97499-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="97499-108">Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="97499-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="97499-109">Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="97499-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="97499-110">Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="97499-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="97499-111">Przykład:</span><span class="sxs-lookup"><span data-stu-id="97499-111">Example:</span></span>

<span data-ttu-id="97499-112">Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="97499-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="97499-113">Podmiot prawny zebrał więcej podatku, niż zapłacił.</span><span class="sxs-lookup"><span data-stu-id="97499-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="97499-114">Z tego względu firma jest winna pieniądze urzędowi skarbowemu.</span><span class="sxs-lookup"><span data-stu-id="97499-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="97499-115">Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="97499-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="97499-116">Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="97499-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="97499-117">Wybierz kolejno opcje Podatek &gt; Podatki pośrednie &gt; Podatek &gt; Urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="97499-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="97499-118">Na skróconej karcie Ogólne zaznacz opcję Normalne w polu Metoda zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="97499-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="97499-119">W polu Zaokrąglenie wpisz 1,00.</span><span class="sxs-lookup"><span data-stu-id="97499-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="97499-120">Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, otwórz stronę Rozlicz i zaksięguj podatek.</span><span class="sxs-lookup"><span data-stu-id="97499-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="97499-121">(Wybierz kolejno opcje Podatek &gt; Deklaracje &gt; Podatek &gt; Rozlicz i zaksięguj podatek).</span><span class="sxs-lookup"><span data-stu-id="97499-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="97499-122">Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku 98 765,43 jest zaokrąglana do 98 765.</span><span class="sxs-lookup"><span data-stu-id="97499-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="97499-123">W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu Metoda zaokrąglania na stronie urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="97499-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="97499-124">Zaokrąglanie z opcji</span><span class="sxs-lookup"><span data-stu-id="97499-124">Rounding form option</span></span>                | <span data-ttu-id="97499-125">Wartość zaokrąglenia = 0,01</span><span class="sxs-lookup"><span data-stu-id="97499-125">Round-off value = 0.01</span></span> | <span data-ttu-id="97499-126">Wartość zaokrąglenia = 0,10</span><span class="sxs-lookup"><span data-stu-id="97499-126">Round-off value = 0.10</span></span> | <span data-ttu-id="97499-127">Wartość zaokrąglenia = 1,00</span><span class="sxs-lookup"><span data-stu-id="97499-127">Round-off value = 1.00</span></span> | <span data-ttu-id="97499-128">Wartość zaokrąglenia = 100,00</span><span class="sxs-lookup"><span data-stu-id="97499-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="97499-129">Normalna</span><span class="sxs-lookup"><span data-stu-id="97499-129">Normal</span></span>                              | <span data-ttu-id="97499-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="97499-130">98,765.43</span></span>              | <span data-ttu-id="97499-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="97499-131">98,765.40</span></span>              | <span data-ttu-id="97499-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="97499-132">98,765.00</span></span>              | <span data-ttu-id="97499-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="97499-133">98,800.00</span></span>                |
| <span data-ttu-id="97499-134">W dół</span><span class="sxs-lookup"><span data-stu-id="97499-134">Downward</span></span>                            | <span data-ttu-id="97499-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="97499-135">98,765.43</span></span>              | <span data-ttu-id="97499-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="97499-136">98,765.40</span></span>              | <span data-ttu-id="97499-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="97499-137">98,765.00</span></span>              | <span data-ttu-id="97499-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="97499-138">98,700.00</span></span>                |
| <span data-ttu-id="97499-139">Zaokrąglenie w górę</span><span class="sxs-lookup"><span data-stu-id="97499-139">Rounding-up</span></span>                         | <span data-ttu-id="97499-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="97499-140">98,765.43</span></span>              | <span data-ttu-id="97499-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="97499-141">98,765.50</span></span>              | <span data-ttu-id="97499-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="97499-142">98,766.00</span></span>              | <span data-ttu-id="97499-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="97499-143">98,800.00</span></span>                |
| <span data-ttu-id="97499-144">Na korzyść firmy, salda kredytowe</span><span class="sxs-lookup"><span data-stu-id="97499-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="97499-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="97499-145">98,765.43</span></span>              | <span data-ttu-id="97499-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="97499-146">98,765.40</span></span>              | <span data-ttu-id="97499-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="97499-147">98,765.00</span></span>              | <span data-ttu-id="97499-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="97499-148">98,700.00</span></span>                |
| <span data-ttu-id="97499-149">Na korzyść firmy, salda debetowe</span><span class="sxs-lookup"><span data-stu-id="97499-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="97499-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="97499-150">98,765.43</span></span>              | <span data-ttu-id="97499-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="97499-151">98,765.50</span></span>              | <span data-ttu-id="97499-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="97499-152">98,766.00</span></span>              | <span data-ttu-id="97499-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="97499-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="97499-154">Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy.</span><span class="sxs-lookup"><span data-stu-id="97499-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="97499-155">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="97499-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="97499-156">Omówienie podatku</span><span class="sxs-lookup"><span data-stu-id="97499-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="97499-157">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="97499-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="97499-158">Tworzenie transakcji sprzedaży w dokumentach</span><span class="sxs-lookup"><span data-stu-id="97499-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="97499-159">Wyświetlanie zaksięgowanych transakcji podatkowych</span><span class="sxs-lookup"><span data-stu-id="97499-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)



