---
title: Reguły płatności podatkowych i zaokrąglania
description: W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e1c1bb1c792eb79888a1df209f2eebaf14a38dd
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1531864"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="3cbc8-103">Reguły płatności podatkowych i zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="3cbc8-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cbc8-104">W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="3cbc8-105">Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="3cbc8-106">Można to zrobić, uruchamiając proces rozliczenia i księgowania podatku na stronie Podatek.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="3cbc8-107">Podatek od sprzedaży w danym okresie zostanie rozliczony dla kont podatku, a saldo podatku zostanie zaksięgowane na koncie rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="3cbc8-108">Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="3cbc8-109">Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="3cbc8-110">Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="3cbc8-111">Przykłady</span><span class="sxs-lookup"><span data-stu-id="3cbc8-111">Examples</span></span>

<span data-ttu-id="3cbc8-112">Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="3cbc8-113">Podmiot prawny zebrał więcej podatku, niż zapłacił.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="3cbc8-114">Z tego względu firma jest winna pieniądze urzędowi skarbowemu.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="3cbc8-115">Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="3cbc8-116">Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="3cbc8-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="3cbc8-117">Wybierz kolejno opcje Podatek &gt; Podatki pośrednie &gt; Podatek &gt; Urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="3cbc8-118">Na skróconej karcie Ogólne zaznacz opcję Normalne w polu Metoda zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="3cbc8-119">W polu Zaokrąglenie wpisz 1,00.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="3cbc8-120">Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, otwórz stronę Rozlicz i zaksięguj podatek.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="3cbc8-121">(Wybierz kolejno opcje Podatek &gt; Deklaracje &gt; Podatek &gt; Rozlicz i zaksięguj podatek).</span><span class="sxs-lookup"><span data-stu-id="3cbc8-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="3cbc8-122">Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku 98 765,43 jest zaokrąglana do 98 765.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="3cbc8-123">W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu Metoda zaokrąglania na stronie urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="3cbc8-124">Zaokrąglanie z opcji</span><span class="sxs-lookup"><span data-stu-id="3cbc8-124">Rounding form option</span></span>                | <span data-ttu-id="3cbc8-125">Wartość zaokrąglenia = 0,01</span><span class="sxs-lookup"><span data-stu-id="3cbc8-125">Round-off value = 0.01</span></span> | <span data-ttu-id="3cbc8-126">Wartość zaokrąglenia = 0,10</span><span class="sxs-lookup"><span data-stu-id="3cbc8-126">Round-off value = 0.10</span></span> | <span data-ttu-id="3cbc8-127">Wartość zaokrąglenia = 1,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-127">Round-off value = 1.00</span></span> | <span data-ttu-id="3cbc8-128">Wartość zaokrąglenia = 100,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="3cbc8-129">Normalna</span><span class="sxs-lookup"><span data-stu-id="3cbc8-129">Normal</span></span>                              | <span data-ttu-id="3cbc8-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="3cbc8-130">98,765.43</span></span>              | <span data-ttu-id="3cbc8-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="3cbc8-131">98,765.40</span></span>              | <span data-ttu-id="3cbc8-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-132">98,765.00</span></span>              | <span data-ttu-id="3cbc8-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-133">98,800.00</span></span>                |
| <span data-ttu-id="3cbc8-134">W dół</span><span class="sxs-lookup"><span data-stu-id="3cbc8-134">Downward</span></span>                            | <span data-ttu-id="3cbc8-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="3cbc8-135">98,765.43</span></span>              | <span data-ttu-id="3cbc8-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="3cbc8-136">98,765.40</span></span>              | <span data-ttu-id="3cbc8-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-137">98,765.00</span></span>              | <span data-ttu-id="3cbc8-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-138">98,700.00</span></span>                |
| <span data-ttu-id="3cbc8-139">Zaokrąglenie w górę</span><span class="sxs-lookup"><span data-stu-id="3cbc8-139">Rounding-up</span></span>                         | <span data-ttu-id="3cbc8-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="3cbc8-140">98,765.43</span></span>              | <span data-ttu-id="3cbc8-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="3cbc8-141">98,765.50</span></span>              | <span data-ttu-id="3cbc8-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-142">98,766.00</span></span>              | <span data-ttu-id="3cbc8-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-143">98,800.00</span></span>                |
| <span data-ttu-id="3cbc8-144">Na korzyść firmy, salda kredytowe</span><span class="sxs-lookup"><span data-stu-id="3cbc8-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="3cbc8-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="3cbc8-145">98,765.43</span></span>              | <span data-ttu-id="3cbc8-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="3cbc8-146">98,765.40</span></span>              | <span data-ttu-id="3cbc8-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-147">98,765.00</span></span>              | <span data-ttu-id="3cbc8-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-148">98,700.00</span></span>                |
| <span data-ttu-id="3cbc8-149">Na korzyść firmy, salda debetowe</span><span class="sxs-lookup"><span data-stu-id="3cbc8-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="3cbc8-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3cbc8-150">98,765.43</span></span>              | <span data-ttu-id="3cbc8-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="3cbc8-151">98,765.50</span></span>              | <span data-ttu-id="3cbc8-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-152">98,766.00</span></span>              | <span data-ttu-id="3cbc8-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="3cbc8-154">Brak zaokrąglania, ponieważ zaokrąglenie wynosi 0,00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="3cbc8-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span><span class="sxs-lookup"><span data-stu-id="3cbc8-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="3cbc8-156">Normalne zaokrąglenie i normalna dokładność wynoszą 0,01</span><span class="sxs-lookup"><span data-stu-id="3cbc8-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="3cbc8-157">Zaokrąglanie</span><span class="sxs-lookup"><span data-stu-id="3cbc8-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="3cbc8-158">Procedury obliczania</span><span class="sxs-lookup"><span data-stu-id="3cbc8-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3cbc8-159">round(1.015, 0.01) = 1.02</span><span class="sxs-lookup"><span data-stu-id="3cbc8-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="3cbc8-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="3cbc8-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="3cbc8-161">102 \* 0.01 = 1.02</span><span class="sxs-lookup"><span data-stu-id="3cbc8-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3cbc8-162">round(1.014, 0.01) = 1.01</span><span class="sxs-lookup"><span data-stu-id="3cbc8-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3cbc8-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="3cbc8-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="3cbc8-164">101 \* 0.01 = 1.01</span><span class="sxs-lookup"><span data-stu-id="3cbc8-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3cbc8-165">round(1.011, 0.02) = 1.02</span><span class="sxs-lookup"><span data-stu-id="3cbc8-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3cbc8-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="3cbc8-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="3cbc8-167">51 \* 0.02 = 1.02</span><span class="sxs-lookup"><span data-stu-id="3cbc8-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3cbc8-168">round(1.009, 0.02) = 1.00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3cbc8-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="3cbc8-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="3cbc8-170">50 \* 0.02 = 1.00</span><span class="sxs-lookup"><span data-stu-id="3cbc8-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="3cbc8-171">Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="3cbc8-172">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="3cbc8-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="3cbc8-173">Omówienie podatku</span><span class="sxs-lookup"><span data-stu-id="3cbc8-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="3cbc8-174">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="3cbc8-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="3cbc8-175">Tworzenie transakcji sprzedaży w dokumentach</span><span class="sxs-lookup"><span data-stu-id="3cbc8-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="3cbc8-176">Wyświetlanie zaksięgowanych transakcji podatkowych</span><span class="sxs-lookup"><span data-stu-id="3cbc8-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="3cbc8-177">Funkcja zaokrąglanie</span><span class="sxs-lookup"><span data-stu-id="3cbc8-177">round Function</span></span>](https://msdn.microsoft.com/en-us/library/aa850656.aspx)


