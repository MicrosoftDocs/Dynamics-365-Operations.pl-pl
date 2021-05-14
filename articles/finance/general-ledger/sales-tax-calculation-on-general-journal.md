---
title: Obliczony podatek dla ogólnych wierszy arkuszy finansowych
description: W tym temacie objaśniono, w jaki sposób podatki są obliczane dla różnych typów kont (dostawca, odbiorca, Księga i projekt) w wierszach arkusza finansowego.
author: EricWang
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: EricWang
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: d0cb4b282fe2bd5c68af17c741787c4caca98003
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937313"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="b4065-103">Obliczony podatek dla ogólnych wierszy arkuszy finansowych</span><span class="sxs-lookup"><span data-stu-id="b4065-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4065-104">W tym temacie objaśniono, w jaki sposób podatki są obliczane dla różnych typów kont (dostawca, odbiorca, Księga i projekt) w wierszach arkusza finansowego.</span><span class="sxs-lookup"><span data-stu-id="b4065-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="b4065-105">Ten proces można podzielić na trzy etapy:</span><span class="sxs-lookup"><span data-stu-id="b4065-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="b4065-106">Określ kierunek podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="b4065-107">Umożliwia określenie kwoty podatku, która będzie przechowywaną tymczasową tabelą podatku od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b4065-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="b4065-108">Umożliwia określenie kwoty i konta podatku w załączniku.</span><span class="sxs-lookup"><span data-stu-id="b4065-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="b4065-109">Określ kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-109">Determine the sales tax direction</span></span>

<span data-ttu-id="b4065-110">Sposób ustalania kierunku podatku zależy od typu konta w załączniku.</span><span class="sxs-lookup"><span data-stu-id="b4065-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="b4065-111">Kierunek podatku jest określony przez kombinację typu konta i kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="b4065-112">Bardziej szczegółowe informacje podano w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="b4065-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="b4065-113">Konto typu Projekt</span><span class="sxs-lookup"><span data-stu-id="b4065-113">Account type is Project</span></span>

<span data-ttu-id="b4065-114">Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Projekt**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku.</span><span class="sxs-lookup"><span data-stu-id="b4065-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="b4065-115">Na ilustracji poniżej widać regułę.</span><span class="sxs-lookup"><span data-stu-id="b4065-115">The following illustration shows the rule.</span></span> <span data-ttu-id="b4065-116">W poniższych punktach przedstawiono możliwe kierunki podatku dla kont projektów.</span><span class="sxs-lookup"><span data-stu-id="b4065-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="b4065-117">• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.</span><span class="sxs-lookup"><span data-stu-id="b4065-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="b4065-118">• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="b4065-119">• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek należny.</span><span class="sxs-lookup"><span data-stu-id="b4065-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-120">• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek należny.</span><span class="sxs-lookup"><span data-stu-id="b4065-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-121">W przeciwnym razie kierunek podatku jest naliczony od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b4065-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="b4065-122">Na poniższym diagramie przedstawiono regułę graficznie.</span><span class="sxs-lookup"><span data-stu-id="b4065-122">The following diagram illustrates the rule graphically.</span></span>

![Możliwości podatkowe dla kont projektu](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="b4065-124">Konto typu Dostawca</span><span class="sxs-lookup"><span data-stu-id="b4065-124">Account type is Vendor</span></span>

<span data-ttu-id="b4065-125">Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Dostawca**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku.</span><span class="sxs-lookup"><span data-stu-id="b4065-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="b4065-126">W poniższych punktach przedstawiono możliwe kierunki podatku dla kont dostawców.</span><span class="sxs-lookup"><span data-stu-id="b4065-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="b4065-127">• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.</span><span class="sxs-lookup"><span data-stu-id="b4065-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="b4065-128">• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="b4065-129">• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek należny.</span><span class="sxs-lookup"><span data-stu-id="b4065-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-130">• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek należny.</span><span class="sxs-lookup"><span data-stu-id="b4065-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-131">W przeciwnym razie kierunek podatku jest naliczony od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b4065-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="b4065-132">Na poniższym diagramie przedstawiono regułę graficznie.</span><span class="sxs-lookup"><span data-stu-id="b4065-132">The following diagram illustrates the rule graphically.</span></span>

![Możliwości podatkowe dla kont dostawców](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="b4065-134">Konto typu Odbiorca</span><span class="sxs-lookup"><span data-stu-id="b4065-134">Account type is Customer</span></span>

<span data-ttu-id="b4065-135">Jeśli załącznik ma wiersz arkusza, w którym typem konta jest **Odbiorca**, to ten sam kierunek podatku jest stosowany w odniesieniu do wszystkich wierszy arkusza w załączniku.</span><span class="sxs-lookup"><span data-stu-id="b4065-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="b4065-136">W poniższych punktach przedstawiono możliwe kierunki podatku dla kont odbiorców.</span><span class="sxs-lookup"><span data-stu-id="b4065-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="b4065-137">• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="b4065-138">• Jeśli kod podatku jest używany jako VAT między firmami, kierunek podatku jest używany jako Podatek naliczony.</span><span class="sxs-lookup"><span data-stu-id="b4065-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="b4065-139">• Jeśli kod podatku jest używany jako odwrotne obciążenie, kierunek podatku jest używany jako Podatek naliczony.</span><span class="sxs-lookup"><span data-stu-id="b4065-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="b4065-140">W przeciwnym razie kierunek podatku jest podatek naliczony.</span><span class="sxs-lookup"><span data-stu-id="b4065-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-141">Na poniższym diagramie przedstawiono regułę graficznie.</span><span class="sxs-lookup"><span data-stu-id="b4065-141">The following diagram illustrates the rule graphically.</span></span>

![Możliwości podatkowe dla kont odbiorców](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="b4065-143">Konto typu Księga</span><span class="sxs-lookup"><span data-stu-id="b4065-143">Account type is Ledger</span></span>

<span data-ttu-id="b4065-144">Na poniższej ilustracji przedstawiono regułę, która ma zastosowanie, gdy załącznik ma tylko wiersze arkusza, w których typem konta jest **Księga**.</span><span class="sxs-lookup"><span data-stu-id="b4065-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="b4065-145">W poniższych punktach przedstawiono możliwe kierunki podatku dla kont księgi.</span><span class="sxs-lookup"><span data-stu-id="b4065-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="b4065-146">• Jeśli kod podatku jest używany jako podatek, kierunek podatku jest używany jako podatek.</span><span class="sxs-lookup"><span data-stu-id="b4065-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="b4065-147">• Jeśli kod podatku jest używany jako wyjatek podatkowy, kierunek podatku jest używany jako zakup bez podatku.</span><span class="sxs-lookup"><span data-stu-id="b4065-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="b4065-148">W przeciwnym razie, jeśli kwota arkusza ma wartość debet (dodatnia), kierunek podatku jest podatek naliczony; jeśli kwota arkusza to kredyt (ujemny), kierunek podatku jest naliczony.</span><span class="sxs-lookup"><span data-stu-id="b4065-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="b4065-149">Na poniższym diagramie przedstawiono regułę graficznie.</span><span class="sxs-lookup"><span data-stu-id="b4065-149">The following diagram illustrates the rule graphically.</span></span>

![Możliwości podatkowe dla kont księgi](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="b4065-151">Zastąp kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-151">Override the sales tax direction</span></span>

<span data-ttu-id="b4065-152">Kierunek podatku można zastąpić, jeśli załącznik zawiera tylko wiersze, dla których typem konta jest **Księga.**</span><span class="sxs-lookup"><span data-stu-id="b4065-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="b4065-153">Umożliwia przejście **Księga główna \> Plan kont \> Konta \> Główne konta** i na karcie skróconej wybierz **Firma zastępuje**.</span><span class="sxs-lookup"><span data-stu-id="b4065-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="b4065-154">Określ kwotę podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-154">Determine the sales tax amount</span></span>

<span data-ttu-id="b4065-155">W tej sekcji opisano sposób obliczania znaku kwoty podatku od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b4065-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Strona transakcji podatku](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="b4065-157">W poniższej tabeli przedstawiono regułę rodzajową służącą do określania kierunku podatku i znaku kwot podatku w tabeli tymczasowych podatków od sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="b4065-157">The following table shows the generic rule for determining the sales tax direction and sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="b4065-158">Liczba wierszy w arkuszu</span><span class="sxs-lookup"><span data-stu-id="b4065-158">Journal line amount</span></span> | <span data-ttu-id="b4065-159">Kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-159">Sales tax direction</span></span>  | <span data-ttu-id="b4065-160">Kwota podatku — podpisz</span><span class="sxs-lookup"><span data-stu-id="b4065-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="b4065-161">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-161">Positive</span></span>            | <span data-ttu-id="b4065-162">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-162">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-163">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-163">Positive</span></span>              |
| <span data-ttu-id="b4065-164">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-164">Positive</span></span>            | <span data-ttu-id="b4065-165">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="b4065-165">Sales Tax Payable</span></span>    | <span data-ttu-id="b4065-166">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-166">Negative</span></span>              |
| <span data-ttu-id="b4065-167">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-167">Negative</span></span>            | <span data-ttu-id="b4065-168">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-168">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-169">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-169">Negative</span></span>              |
| <span data-ttu-id="b4065-170">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-170">Negative</span></span>            | <span data-ttu-id="b4065-171">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="b4065-171">Sales Tax Payable</span></span>    | <span data-ttu-id="b4065-172">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-172">Positive</span></span>              |

<span data-ttu-id="b4065-173">Istnieje specjalna reguła dla załączników, które mają tylko wiersze **projektu** lub **księgi**, jeśli w wierszu **księgi** wybrano grupę podatków lub grupę podatków dla danego towaru.</span><span class="sxs-lookup"><span data-stu-id="b4065-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="b4065-174">Ta reguła jest kontrolowana przez funkcję **Włączenie funkcji niezależnego obliczania podatku dla arkuszy finansowych**.</span><span class="sxs-lookup"><span data-stu-id="b4065-174">This rule is controlled by the feature, **Enable independent sales tax calculation feature for general journals**.</span></span> <span data-ttu-id="b4065-175">Gdy ta funkcja jest wyłączona, kwota podatku w wierszu **Księgi** używa kierunku debetu/kredytu wiersza **Projektu**.</span><span class="sxs-lookup"><span data-stu-id="b4065-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="b4065-176">Gdy ta funkcja jest wyłączona, kwota podatku w wierszu **księgi** używa kierunku debetu/kredytu wiersza projektu.</span><span class="sxs-lookup"><span data-stu-id="b4065-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="b4065-177">W poniższych tabelach przedstawiono reguły dla każdego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="b4065-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="b4065-178">**Reguła, gdy funkcja jest włączona.**</span><span class="sxs-lookup"><span data-stu-id="b4065-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="b4065-179">Kwota wiersza arkusza dla projektu</span><span class="sxs-lookup"><span data-stu-id="b4065-179">Journal line amount of project</span></span> | <span data-ttu-id="b4065-180">Kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-180">Sales tax direction</span></span>  | <span data-ttu-id="b4065-181">Kwota podatku — podpisz</span><span class="sxs-lookup"><span data-stu-id="b4065-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="b4065-182">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-182">Positive</span></span>                       | <span data-ttu-id="b4065-183">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-183">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-184">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-184">Positive</span></span>              |
| <span data-ttu-id="b4065-185">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-185">Negative</span></span>                       | <span data-ttu-id="b4065-186">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-186">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-187">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-187">Negative</span></span>              |

<span data-ttu-id="b4065-188">**Reguła, gdy funkcja jest wyłączona**</span><span class="sxs-lookup"><span data-stu-id="b4065-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="b4065-189">Kwota wiersza arkusza dla księgi</span><span class="sxs-lookup"><span data-stu-id="b4065-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="b4065-190">Kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-190">Sales tax direction</span></span>  | <span data-ttu-id="b4065-191">Kwota podatku — podpisz</span><span class="sxs-lookup"><span data-stu-id="b4065-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="b4065-192">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-192">Positive</span></span>                       | <span data-ttu-id="b4065-193">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-193">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-194">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-194">Positive</span></span>              |
| <span data-ttu-id="b4065-195">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-195">Negative</span></span>                       | <span data-ttu-id="b4065-196">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-196">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-197">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="b4065-198">Umożliwia określenie kwoty i konta podatku w załączniku</span><span class="sxs-lookup"><span data-stu-id="b4065-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="b4065-199">Podczas księgowania podatków konto główne jest pobierane z profilu grupy księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="b4065-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="b4065-200">W przypadku podatku należnego system używa konta podatku należnego określonego w profilu.</span><span class="sxs-lookup"><span data-stu-id="b4065-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="b4065-201">W przypadku podatku należnego system używa konta podatku należnego określonego w profilu.</span><span class="sxs-lookup"><span data-stu-id="b4065-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="b4065-202">Poniższa tabela przedstawia ogólną regułę.</span><span class="sxs-lookup"><span data-stu-id="b4065-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="b4065-203">Kierunek podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-203">Sales tax direction</span></span>  | <span data-ttu-id="b4065-204">Kwota podatku — podpisz</span><span class="sxs-lookup"><span data-stu-id="b4065-204">Sales tax amount sign</span></span> | <span data-ttu-id="b4065-205">Konto podatku</span><span class="sxs-lookup"><span data-stu-id="b4065-205">Sales tax account</span></span>      | <span data-ttu-id="b4065-206">Kwota w załączniku</span><span class="sxs-lookup"><span data-stu-id="b4065-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="b4065-207">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-207">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-208">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-208">Positive</span></span>              | <span data-ttu-id="b4065-209">Konto podatku naliczonego</span><span class="sxs-lookup"><span data-stu-id="b4065-209">Tax Receivable Account</span></span> | <span data-ttu-id="b4065-210">Dodatnie (Debet)</span><span class="sxs-lookup"><span data-stu-id="b4065-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="b4065-211">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="b4065-211">Sales Tax Receivable</span></span> | <span data-ttu-id="b4065-212">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-212">Negative</span></span>              | <span data-ttu-id="b4065-213">Konto podatku naliczonego</span><span class="sxs-lookup"><span data-stu-id="b4065-213">Tax Receivable Account</span></span> | <span data-ttu-id="b4065-214">Ujemne (kredyt)</span><span class="sxs-lookup"><span data-stu-id="b4065-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="b4065-215">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="b4065-215">Sales Tax Payable</span></span>    | <span data-ttu-id="b4065-216">Dodatni</span><span class="sxs-lookup"><span data-stu-id="b4065-216">Positive</span></span>              | <span data-ttu-id="b4065-217">Konto podatku należnego</span><span class="sxs-lookup"><span data-stu-id="b4065-217">Tax Payable Account</span></span>    | <span data-ttu-id="b4065-218">Ujemne (kredyt)</span><span class="sxs-lookup"><span data-stu-id="b4065-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="b4065-219">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="b4065-219">Sales Tax Payable</span></span>    | <span data-ttu-id="b4065-220">Ujemny</span><span class="sxs-lookup"><span data-stu-id="b4065-220">Negative</span></span>              | <span data-ttu-id="b4065-221">Konto podatku należnego</span><span class="sxs-lookup"><span data-stu-id="b4065-221">Tax Payable Account</span></span>    | <span data-ttu-id="b4065-222">Dodatnie (Debet)</span><span class="sxs-lookup"><span data-stu-id="b4065-222">Positive (Debit)</span></span>  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
