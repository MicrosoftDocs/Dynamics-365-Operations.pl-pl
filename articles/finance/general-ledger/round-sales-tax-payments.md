---
title: Reguły płatności podatkowych i zaokrąglania
description: W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adc48d1841903670577684b1c3d773d323c19ea1
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275681"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="0e53d-103">Reguły płatności podatkowych i zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="0e53d-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e53d-104">W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.</span><span class="sxs-lookup"><span data-stu-id="0e53d-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="0e53d-105">Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym.</span><span class="sxs-lookup"><span data-stu-id="0e53d-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="0e53d-106">Można to zrobić, uruchamiając proces rozliczenia i księgowania podatku na stronie Podatek.</span><span class="sxs-lookup"><span data-stu-id="0e53d-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="0e53d-107">Podatek od sprzedaży w danym okresie zostanie rozliczony dla kont podatku, a saldo podatku zostanie zaksięgowane na koncie rozliczenia podatku.</span><span class="sxs-lookup"><span data-stu-id="0e53d-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="0e53d-108">Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0e53d-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="0e53d-109">Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="0e53d-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="0e53d-110">Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="0e53d-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="0e53d-111">Przykłady</span><span class="sxs-lookup"><span data-stu-id="0e53d-111">Examples</span></span>

<span data-ttu-id="0e53d-112">Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="0e53d-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="0e53d-113">Podmiot prawny zebrał więcej podatku, niż zapłacił.</span><span class="sxs-lookup"><span data-stu-id="0e53d-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="0e53d-114">Z tego względu firma jest winna pieniądze urzędowi skarbowemu.</span><span class="sxs-lookup"><span data-stu-id="0e53d-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="0e53d-115">Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="0e53d-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="0e53d-116">Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="0e53d-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="0e53d-117">Wybierz kolejno opcje **Podatek** > **Podatki pośrednie** > **Podatek** > **Urzędy skarbowe**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="0e53d-118">Na skróconej karcie **Ogólne** w polu **Metoda zaokrąglenia** zaznacz opcję **Normalne**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="0e53d-119">W polu **Zaokrąglenie** wpisz 1,00.</span><span class="sxs-lookup"><span data-stu-id="0e53d-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="0e53d-120">Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, przejdź do **Podatek** > **Deklaracje** > **Podatek** > **Rozlicz i zaksięguj podatek**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="0e53d-121">Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku **98,765.43** jest zaokrąglana do **98,765**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="0e53d-122">W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu **Metoda zaokrąglania** na stronie **Urząd skarbowy**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="0e53d-123">Jeśli wartość zaokrąglenia jest ustawiona jako 0,00, to:</span><span class="sxs-lookup"><span data-stu-id="0e53d-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="0e53d-124">W przypadku zwykłego zaokrąglania zachowanie zaokrąglania jest takie samo, jak dla **Zaokrąglenie = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="0e53d-125">W przypadku **Opcji formularza zaokrąglania** w **Dół**, **W górę** i **Na korzyść firmy**, zachowanie jest takie samo, jak dla **Zaokrąglenie = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="0e53d-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="0e53d-126">Zaokrąglanie z opcji</span><span class="sxs-lookup"><span data-stu-id="0e53d-126">Rounding form option</span></span>                | <span data-ttu-id="0e53d-127">Wartość zaokrąglenia = 0,01</span><span class="sxs-lookup"><span data-stu-id="0e53d-127">Round-off value = 0.01</span></span> | <span data-ttu-id="0e53d-128">Wartość zaokrąglenia = 0,10</span><span class="sxs-lookup"><span data-stu-id="0e53d-128">Round-off value = 0.10</span></span> | <span data-ttu-id="0e53d-129">Wartość zaokrąglenia = 1,00</span><span class="sxs-lookup"><span data-stu-id="0e53d-129">Round-off value = 1.00</span></span> | <span data-ttu-id="0e53d-130">Wartość zaokrąglenia = 100,00</span><span class="sxs-lookup"><span data-stu-id="0e53d-130">Round-off value = 100.00</span></span> | <span data-ttu-id="0e53d-131">Wartość zaokrąglenia = 0,00</span><span class="sxs-lookup"><span data-stu-id="0e53d-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="0e53d-132">Normalnie</span><span class="sxs-lookup"><span data-stu-id="0e53d-132">Normal</span></span>                              | <span data-ttu-id="0e53d-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-133">98,765.43</span></span>              | <span data-ttu-id="0e53d-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="0e53d-134">98,765.40</span></span>              | <span data-ttu-id="0e53d-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-135">98,765.00</span></span>              | <span data-ttu-id="0e53d-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-136">98,800.00</span></span>                | <span data-ttu-id="0e53d-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-137">98,765.43</span></span>                |
| <span data-ttu-id="0e53d-138">W dół</span><span class="sxs-lookup"><span data-stu-id="0e53d-138">Downward</span></span>                            | <span data-ttu-id="0e53d-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-139">98,765.43</span></span>              | <span data-ttu-id="0e53d-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="0e53d-140">98,765.40</span></span>              | <span data-ttu-id="0e53d-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-141">98,765.00</span></span>              | <span data-ttu-id="0e53d-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-142">98,700.00</span></span>                | <span data-ttu-id="0e53d-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-143">98,765.00</span></span>                |
| <span data-ttu-id="0e53d-144">Zaokrąglenie w górę</span><span class="sxs-lookup"><span data-stu-id="0e53d-144">Rounding-up</span></span>                         | <span data-ttu-id="0e53d-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-145">98,765.43</span></span>              | <span data-ttu-id="0e53d-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="0e53d-146">98,765.50</span></span>              | <span data-ttu-id="0e53d-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-147">98,766.00</span></span>              | <span data-ttu-id="0e53d-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-148">98,800.00</span></span>                | <span data-ttu-id="0e53d-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-149">98,766.00</span></span>                |
| <span data-ttu-id="0e53d-150">Na korzyść firmy, salda kredytowe</span><span class="sxs-lookup"><span data-stu-id="0e53d-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="0e53d-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-151">98,765.43</span></span>              | <span data-ttu-id="0e53d-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="0e53d-152">98,765.40</span></span>              | <span data-ttu-id="0e53d-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-153">98,765.00</span></span>              | <span data-ttu-id="0e53d-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-154">98,700.00</span></span>                | <span data-ttu-id="0e53d-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-155">98,765.00</span></span>                |
| <span data-ttu-id="0e53d-156">Na korzyść firmy, salda debetowe</span><span class="sxs-lookup"><span data-stu-id="0e53d-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="0e53d-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0e53d-157">98,765.43</span></span>              | <span data-ttu-id="0e53d-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="0e53d-158">98,765.50</span></span>              | <span data-ttu-id="0e53d-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-159">98,766.00</span></span>              | <span data-ttu-id="0e53d-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-160">98,800.00</span></span>                | <span data-ttu-id="0e53d-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="0e53d-162">Normalne zaokrąglenie i normalna dokładność wynoszą 0,01</span><span class="sxs-lookup"><span data-stu-id="0e53d-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="0e53d-163">Zaokrąglanie</span><span class="sxs-lookup"><span data-stu-id="0e53d-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="0e53d-164">Procedury obliczania</span><span class="sxs-lookup"><span data-stu-id="0e53d-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0e53d-165">round(1.015, 0.01) = 1.02</span><span class="sxs-lookup"><span data-stu-id="0e53d-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="0e53d-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="0e53d-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="0e53d-167">102 \* 0.01 = 1.02</span><span class="sxs-lookup"><span data-stu-id="0e53d-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0e53d-168">round(1.014, 0.01) = 1.01</span><span class="sxs-lookup"><span data-stu-id="0e53d-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0e53d-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="0e53d-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="0e53d-170">101 \* 0.01 = 1.01</span><span class="sxs-lookup"><span data-stu-id="0e53d-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0e53d-171">round(1.011, 0.02) = 1.02</span><span class="sxs-lookup"><span data-stu-id="0e53d-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0e53d-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="0e53d-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="0e53d-173">51 \* 0.02 = 1.02</span><span class="sxs-lookup"><span data-stu-id="0e53d-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0e53d-174">round(1.009, 0.02) = 1.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0e53d-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="0e53d-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="0e53d-176">50 \* 0.02 = 1.00</span><span class="sxs-lookup"><span data-stu-id="0e53d-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="0e53d-177">Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy.</span><span class="sxs-lookup"><span data-stu-id="0e53d-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="0e53d-178">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="0e53d-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="0e53d-179">Omówienie podatku</span><span class="sxs-lookup"><span data-stu-id="0e53d-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="0e53d-180">Tworzenie płatności podatku</span><span class="sxs-lookup"><span data-stu-id="0e53d-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="0e53d-181">Tworzenie transakcji podatku w dokumentach</span><span class="sxs-lookup"><span data-stu-id="0e53d-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="0e53d-182">Wyświetlanie zaksięgowanych transakcji podatkowych</span><span class="sxs-lookup"><span data-stu-id="0e53d-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="0e53d-183">Funkcja zaokrąglanie</span><span class="sxs-lookup"><span data-stu-id="0e53d-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


