---
title: Typy księgowania wynajmu
description: W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841148"
---
# <a name="lease-posting-types"></a><span data-ttu-id="09c9b-103">Typy księgowania wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09c9b-104">W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="09c9b-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="09c9b-105">Składnik majątku wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-105">Lease asset</span></span>

<span data-ttu-id="09c9b-106">Konto jest skojarzone ze składnikiem majątku z prawem do użytkowania (PDU).</span><span class="sxs-lookup"><span data-stu-id="09c9b-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="09c9b-107">To konto jest obciążane, gdy wynajem jest początkowo ujmowany zgodnie z nowymi standardami księgowania wynajmu — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).</span><span class="sxs-lookup"><span data-stu-id="09c9b-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="09c9b-108">W zmodyfikowanym wynajmie to konto może być obciążane lub uznawane w zależności od tego, czy modyfikacja powoduje zwiększenie, czy zmniejszenie zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="09c9b-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="09c9b-109">**Przykładowe wpisy w arkuszu:** Początkowe ujęcie</span><span class="sxs-lookup"><span data-stu-id="09c9b-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="09c9b-110">**Strona Winien:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="09c9b-111">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="09c9b-112">Zobowiązanie z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-112">Lease liability</span></span>

<span data-ttu-id="09c9b-113">Konto jest skojarzone ze zobowiązaniem z tytułu wynajmu, które występuje, gdy płatności są dyskontowane w ramach nowych standardów MSSF 16 i ASC 842.</span><span class="sxs-lookup"><span data-stu-id="09c9b-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="09c9b-114">Konto jest uznawane, gdy wynajem jest początkowo ujmowany według nowych standardów.</span><span class="sxs-lookup"><span data-stu-id="09c9b-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="09c9b-115">Jest obciążane opłatami z tytułu wynajmu, a uznawane naliczonymi odsetkami.</span><span class="sxs-lookup"><span data-stu-id="09c9b-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="09c9b-116">**Przykładowe wpisy w arkuszu:** Początkowe ujęcie</span><span class="sxs-lookup"><span data-stu-id="09c9b-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="09c9b-117">**Strona Winien:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="09c9b-118">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="09c9b-119">**Przykładowe wpisy w arkuszu:** Naliczanie odsetek</span><span class="sxs-lookup"><span data-stu-id="09c9b-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="09c9b-120">**Strona Winien:** Koszt odsetek XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="09c9b-121">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="09c9b-122">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="09c9b-123">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-124">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="09c9b-125">Krótkoterminowe zobowiązanie z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-125">Short-term lease liability</span></span>

<span data-ttu-id="09c9b-126">Konto jest łączone z krótkoterminowym zobowiązaniem z tytułu wynajmu, gdy jest księgowany wpis w arkuszu dotyczący przeklasyfikowania krótkoterminowego zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="09c9b-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="09c9b-127">Konto jest uznawane krótkoterminowym zobowiązaniem według harmonogramu amortyzacji w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="09c9b-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="09c9b-128">Jednak ta sama kwota jest księgowana po stronie debetowej pierwszego dnia następnego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="09c9b-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="09c9b-129">**Przykładowe wpisy w arkuszu:** Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="09c9b-130">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-131">**Strona Ma:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-132">**Strona Winien:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-133">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="09c9b-134">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="09c9b-134">Depreciation expense</span></span>

<span data-ttu-id="09c9b-135">Konto jest łączone z wydatkiem związanym z amortyzacją składnika majątku z PDU zgodnie z MSSF 16, ASC 842 i zasadami leasingu finansowego określonymi w MSR 17 i ASC 840.</span><span class="sxs-lookup"><span data-stu-id="09c9b-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="09c9b-136">Konto jest obciążane, gdy składnik majątku z PDU jest amortyzowany w każdym miesiącu.</span><span class="sxs-lookup"><span data-stu-id="09c9b-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="09c9b-137">**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="09c9b-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="09c9b-138">**Strona Winien:** Wydatek amortyzacji XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="09c9b-139">**Strona Ma:** Umorzenie XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="09c9b-140">Zysk/strata z modyfikacji wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="09c9b-141">Konto jest łączone ze wszystkimi zyskami lub stratami powstającymi w wyniku modyfikacji wynajmu.</span><span class="sxs-lookup"><span data-stu-id="09c9b-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="09c9b-142">Zysk może powstać podczas modyfikacji wynajmu, jeśli modyfikacja zmniejsza zobowiązanie z tytułu wynajmu o kwotę przekraczającą wartość bilansową składnika majątku z PDU.</span><span class="sxs-lookup"><span data-stu-id="09c9b-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="09c9b-143">Na przykład wynajmowany składnik ma bieżącą wartość bilansową zobowiązania z tytułu wynajmu wynoszącą 150 000 zł i wartość bilansową składnika majątku z PDU wynoszącą 100 000 zł.</span><span class="sxs-lookup"><span data-stu-id="09c9b-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="09c9b-144">Wynajem jest modyfikowany, a modyfikacja powoduje utworzenie nowej wartości bieżącej przyszłych opłat z tytułu wynajmu (PVFMLP) wynoszącej 40 000 zł.</span><span class="sxs-lookup"><span data-stu-id="09c9b-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="09c9b-145">Z tego względu zobowiązanie z tytułu wynajmu zostanie zaksięgowane po stronie debetowej na kwotę 110 000 zł (150 000 zł – 40 000 zł).</span><span class="sxs-lookup"><span data-stu-id="09c9b-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="09c9b-146">Ponieważ składnik majątku z PDU ma wartość tylko 100 000 zł, spadek o 110 000 zł zmniejszy wartość składnika majątku poniżej 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="09c9b-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="09c9b-147">Dlatego też wytyczne dotyczące księgowania stanowią, że reszta powinna zostać zaksięgowana na koncie zysków.</span><span class="sxs-lookup"><span data-stu-id="09c9b-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="09c9b-148">W tym przypadku ostatecznym wpisem w arkuszu będzie obciążenie zobowiązaniem z tytułu wynajmu na kwotę 110 000 zł, uznanie należnością z tytułu wynajmu na kwotę 100 000 zł oraz uznanie konta zysków na kwotę 10 000 zł.</span><span class="sxs-lookup"><span data-stu-id="09c9b-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="09c9b-149">**Przykładowe wpisy w arkuszu:** Modyfikacja wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="09c9b-150">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-151">**Strona Ma:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="09c9b-152">**Strona Ma:** Zysk XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="09c9b-153">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="09c9b-153">Accumulated depreciation</span></span>

<span data-ttu-id="09c9b-154">Konto jest łączone z kontem przeciwstawnym składnika majątku z PDU.</span><span class="sxs-lookup"><span data-stu-id="09c9b-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="09c9b-155">Konto jest uznawane podczas księgowania wydatku amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="09c9b-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="09c9b-156">**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="09c9b-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="09c9b-157">**Strona Winien:** Wydatek amortyzacji XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="09c9b-158">**Strona Ma:** Umorzenie XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="09c9b-159">Zmienna płatność</span><span class="sxs-lookup"><span data-stu-id="09c9b-159">Variable payment</span></span>

<span data-ttu-id="09c9b-160">Konto jest łączone ze zmiennymi opłatami z tytułu wynajmu, które są generowane poprzez przeszacowanie indeksu w leasingu według standardów ASC 842, ASC 840 i MSR 17.</span><span class="sxs-lookup"><span data-stu-id="09c9b-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="09c9b-161">W harmonogramie opłat z tytułu wynajmu zmienne płatności są uwzględniane w kolumnie **Opłaty zmienne**.</span><span class="sxs-lookup"><span data-stu-id="09c9b-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="09c9b-162">Konto jest obciążane podczas tworzenia faktury dla wiersza harmonogramu płatności zawierającego zmienną opłatę.</span><span class="sxs-lookup"><span data-stu-id="09c9b-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="09c9b-163">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="09c9b-164">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-165">**Strona Winien:** Opłata zmienna XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="09c9b-166">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="09c9b-167">Odroczony czynsz składnika majątku (zobowiązanie)</span><span class="sxs-lookup"><span data-stu-id="09c9b-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="09c9b-168">Konto jest łączone z należnością lub zobowiązaniem z tytułu odroczonego czynszu powstającego w wynajmie z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="09c9b-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="09c9b-169">Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem, jeśli kwota opłaty z tytułu wynajmu jest wyższa niż koszt wynajmu liczony metodą liniową za ten okres.</span><span class="sxs-lookup"><span data-stu-id="09c9b-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="09c9b-170">Jest uznawane, gdy opłata z tytułu wynajmu jest niższa niż koszt wynajmu liczony metodą liniową za ten okres.</span><span class="sxs-lookup"><span data-stu-id="09c9b-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="09c9b-171">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)</span><span class="sxs-lookup"><span data-stu-id="09c9b-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="09c9b-172">**Strona Winien:** Wydatek z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="09c9b-173">**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="09c9b-174">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="09c9b-175">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-175">Lease expense</span></span>

<span data-ttu-id="09c9b-176">Konto jest łączone z wydatkiem z tytułu wynajmu, jeśli wynajem jest klasyfikowany jako wynajem z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="09c9b-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="09c9b-177">Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="09c9b-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="09c9b-178">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)</span><span class="sxs-lookup"><span data-stu-id="09c9b-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="09c9b-179">**Strona Winien:** Wydatek z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="09c9b-180">**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="09c9b-181">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="09c9b-182">Wydatek utraty wartości</span><span class="sxs-lookup"><span data-stu-id="09c9b-182">Impairment expense</span></span>

<span data-ttu-id="09c9b-183">Spadek wartości wynajmowanego składnika powoduje odpowiednie księgowanie na koncie.</span><span class="sxs-lookup"><span data-stu-id="09c9b-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="09c9b-184">Konto jest obciążane, natomiast konto składnika majątku z PDU jest bezpośrednio uznawane.</span><span class="sxs-lookup"><span data-stu-id="09c9b-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="09c9b-185">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="09c9b-186">**Strona Winien:** Wydatek utraty wartości XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="09c9b-187">**Strona Ma:** Składnik majątku z PDU XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="09c9b-188">Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-188">Lease payment</span></span>

<span data-ttu-id="09c9b-189">Na koncie następuje księgowanie, gdy parametr **Płatność dla dostawcy** jest wyłączony.</span><span class="sxs-lookup"><span data-stu-id="09c9b-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="09c9b-190">Kiedy parametr jest wyłączony, jest uznawane to konto, a nie konto zobowiązań wobec dostawcy.</span><span class="sxs-lookup"><span data-stu-id="09c9b-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="09c9b-191">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="09c9b-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="09c9b-192">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="09c9b-193">**Strona Ma:** Opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="09c9b-194">Księgowania typów wydatków</span><span class="sxs-lookup"><span data-stu-id="09c9b-194">Expense type postings</span></span>

<span data-ttu-id="09c9b-195">Konto wybrane dla każdego typu wydatków jest obciążane po wygenerowaniu płatności dla danego typu wydatków.</span><span class="sxs-lookup"><span data-stu-id="09c9b-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="09c9b-196">Na przykład konto określone dla typu wydatków **Ubezpieczenia** jest obciążane, ilekroć jest tworzona faktura lub wpis w arkuszu płatności na podstawie harmonogramu kosztów wykonawczych dla wydatków ubezpieczeniowych.</span><span class="sxs-lookup"><span data-stu-id="09c9b-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="09c9b-197">**Przykładowe wpisy w arkuszu:** Płatność z tytułu ubezpieczenia</span><span class="sxs-lookup"><span data-stu-id="09c9b-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="09c9b-198">**Strona Winien:** Konto wydatków ubezpieczeniowych XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="09c9b-199">**Strona Ma:** Konto przeciwstawne XXX</span><span class="sxs-lookup"><span data-stu-id="09c9b-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="09c9b-200">Konto przeciwstawne jest wybierane na poziomie wynajmu w wierszach harmonogramu płatności kosztów wykonawczych.</span><span class="sxs-lookup"><span data-stu-id="09c9b-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="09c9b-201">Konto przeciwstawne może być powiązane z dostawcą lub z kontem księgowym.</span><span class="sxs-lookup"><span data-stu-id="09c9b-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
