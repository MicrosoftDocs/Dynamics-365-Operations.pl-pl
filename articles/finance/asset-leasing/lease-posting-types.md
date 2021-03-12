---
title: Typy księgowania wynajmu
description: W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: b79b02f7e241783d19a315ccff5bb6874a238c38
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995425"
---
# <a name="lease-posting-types"></a><span data-ttu-id="ef90d-103">Typy księgowania wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef90d-104">W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ef90d-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="ef90d-105">Składnik majątku wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-105">Lease asset</span></span>

<span data-ttu-id="ef90d-106">Konto jest skojarzone ze składnikiem majątku z prawem do użytkowania (PDU).</span><span class="sxs-lookup"><span data-stu-id="ef90d-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="ef90d-107">To konto jest obciążane, gdy wynajem jest początkowo ujmowany zgodnie z nowymi standardami księgowania wynajmu — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16).</span><span class="sxs-lookup"><span data-stu-id="ef90d-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="ef90d-108">W zmodyfikowanym wynajmie to konto może być obciążane lub uznawane w zależności od tego, czy modyfikacja powoduje zwiększenie, czy zmniejszenie zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="ef90d-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="ef90d-109">**Przykładowe wpisy w arkuszu:** Początkowe ujęcie</span><span class="sxs-lookup"><span data-stu-id="ef90d-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="ef90d-110">**Strona Winien:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="ef90d-111">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="ef90d-112">Zobowiązanie z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-112">Lease liability</span></span>

<span data-ttu-id="ef90d-113">Konto jest skojarzone ze zobowiązaniem z tytułu wynajmu, które występuje, gdy płatności są dyskontowane w ramach nowych standardów MSSF 16 i ASC 842.</span><span class="sxs-lookup"><span data-stu-id="ef90d-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="ef90d-114">Konto jest uznawane, gdy wynajem jest początkowo ujmowany według nowych standardów.</span><span class="sxs-lookup"><span data-stu-id="ef90d-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="ef90d-115">Jest obciążane opłatami z tytułu wynajmu, a uznawane naliczonymi odsetkami.</span><span class="sxs-lookup"><span data-stu-id="ef90d-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="ef90d-116">**Przykładowe wpisy w arkuszu:** Początkowe ujęcie</span><span class="sxs-lookup"><span data-stu-id="ef90d-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="ef90d-117">**Strona Winien:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="ef90d-118">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="ef90d-119">**Przykładowe wpisy w arkuszu:** Naliczanie odsetek</span><span class="sxs-lookup"><span data-stu-id="ef90d-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="ef90d-120">**Strona Winien:** Koszt odsetek XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="ef90d-121">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="ef90d-122">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ef90d-123">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-124">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="ef90d-125">Krótkoterminowe zobowiązanie z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-125">Short-term lease liability</span></span>

<span data-ttu-id="ef90d-126">Konto jest łączone z krótkoterminowym zobowiązaniem z tytułu wynajmu, gdy jest księgowany wpis w arkuszu dotyczący przeklasyfikowania krótkoterminowego zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="ef90d-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="ef90d-127">Konto jest uznawane krótkoterminowym zobowiązaniem według harmonogramu amortyzacji w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="ef90d-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="ef90d-128">Jednak ta sama kwota jest księgowana po stronie debetowej pierwszego dnia następnego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="ef90d-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="ef90d-129">**Przykładowe wpisy w arkuszu:** Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="ef90d-130">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-131">**Strona Ma:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-132">**Strona Winien:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-133">**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="ef90d-134">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="ef90d-134">Depreciation expense</span></span>

<span data-ttu-id="ef90d-135">Konto jest łączone z wydatkiem związanym z amortyzacją składnika majątku z PDU zgodnie z MSSF 16, ASC 842 i zasadami leasingu finansowego określonymi w MSR 17 i ASC 840.</span><span class="sxs-lookup"><span data-stu-id="ef90d-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="ef90d-136">Konto jest obciążane, gdy składnik majątku z PDU jest amortyzowany w każdym miesiącu.</span><span class="sxs-lookup"><span data-stu-id="ef90d-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="ef90d-137">**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="ef90d-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="ef90d-138">**Strona Winien:** Wydatek amortyzacji XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="ef90d-139">**Strona Ma:** Umorzenie XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="ef90d-140">Zysk/strata z modyfikacji wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="ef90d-141">Konto jest łączone ze wszystkimi zyskami lub stratami powstającymi w wyniku modyfikacji wynajmu.</span><span class="sxs-lookup"><span data-stu-id="ef90d-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="ef90d-142">Zysk może powstać podczas modyfikacji wynajmu, jeśli modyfikacja zmniejsza zobowiązanie z tytułu wynajmu o kwotę przekraczającą wartość bilansową składnika majątku z PDU.</span><span class="sxs-lookup"><span data-stu-id="ef90d-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="ef90d-143">Na przykład wynajmowany składnik ma bieżącą wartość bilansową zobowiązania z tytułu wynajmu wynoszącą 150 000 zł i wartość bilansową składnika majątku z PDU wynoszącą 100 000 zł.</span><span class="sxs-lookup"><span data-stu-id="ef90d-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="ef90d-144">Wynajem jest modyfikowany, a modyfikacja powoduje utworzenie nowej wartości bieżącej przyszłych opłat z tytułu wynajmu (PVFMLP) wynoszącej 40 000 zł.</span><span class="sxs-lookup"><span data-stu-id="ef90d-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="ef90d-145">Z tego względu zobowiązanie z tytułu wynajmu zostanie zaksięgowane po stronie debetowej na kwotę 110 000 zł (150 000 zł – 40 000 zł).</span><span class="sxs-lookup"><span data-stu-id="ef90d-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="ef90d-146">Ponieważ składnik majątku z PDU ma wartość tylko 100 000 zł, spadek o 110 000 zł zmniejszy wartość składnika majątku poniżej 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="ef90d-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="ef90d-147">Dlatego też wytyczne dotyczące księgowania stanowią, że reszta powinna zostać zaksięgowana na koncie zysków.</span><span class="sxs-lookup"><span data-stu-id="ef90d-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="ef90d-148">W tym przypadku ostatecznym wpisem w arkuszu będzie obciążenie zobowiązaniem z tytułu wynajmu na kwotę 110 000 zł, uznanie należnością z tytułu wynajmu na kwotę 100 000 zł oraz uznanie konta zysków na kwotę 10 000 zł.</span><span class="sxs-lookup"><span data-stu-id="ef90d-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="ef90d-149">**Przykładowe wpisy w arkuszu:** Modyfikacja wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="ef90d-150">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-151">**Strona Ma:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="ef90d-152">**Strona Ma:** Zysk XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="ef90d-153">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="ef90d-153">Accumulated depreciation</span></span>

<span data-ttu-id="ef90d-154">Konto jest łączone z kontem przeciwstawnym składnika majątku z PDU.</span><span class="sxs-lookup"><span data-stu-id="ef90d-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="ef90d-155">Konto jest uznawane podczas księgowania wydatku amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="ef90d-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="ef90d-156">**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji</span><span class="sxs-lookup"><span data-stu-id="ef90d-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="ef90d-157">**Strona Winien:** Wydatek amortyzacji XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="ef90d-158">**Strona Ma:** Umorzenie XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="retained-earnings"></a><span data-ttu-id="ef90d-159">Wstrzymane dochody</span><span class="sxs-lookup"><span data-stu-id="ef90d-159">Retained earnings</span></span>

<span data-ttu-id="ef90d-160">Konto jest łączone z zyskami zatrzymanymi.</span><span class="sxs-lookup"><span data-stu-id="ef90d-160">The account is associated with retained earnings.</span></span> <span data-ttu-id="ef90d-161">Konto może być obciążane lub uznawane we wpisie w arkuszu dotyczącym korekty przejścia przy użyciu metody pełnej retrospekcji lub metody aktualizacji skumulowanej typu A.</span><span class="sxs-lookup"><span data-stu-id="ef90d-161">This account might be either debited or credited in a transition adjustment journal entry by using the full retrospective method or the cumulative catch-up option A method.</span></span> <span data-ttu-id="ef90d-162">Różnica między początkową wartością składnika majątku z PDU a zobowiązaniem z tytułu wynajmu jest księgowana w zyskach zatrzymanych.</span><span class="sxs-lookup"><span data-stu-id="ef90d-162">The difference between the initial ROU asset and lease liability is booked to retained earnings.</span></span> <span data-ttu-id="ef90d-163">Sporadycznie modyfikacja wynajmu może również wpłynąć na zyski zatrzymane, jeśli klasyfikacja wynajmu zmieni się z leasingu finansowego na operacyjny i w ten sposób spowoduje zwiększenie lub zmniejszenie wartości składnika majątku z PDU, tak aby była ona równa wartości zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="ef90d-163">In rare cases, the retained earnings might also be affected during lease modification, if the classification of a lease is changed from finance to operating to write the ROU asset up or down so that it equals the lease liability.</span></span>

<span data-ttu-id="ef90d-164">**Przykładowe wpisy w arkuszu:** Korekta przejścia (metoda pełnej retrospekcji lub aktualizacji skumulowanej typu A)</span><span class="sxs-lookup"><span data-stu-id="ef90d-164">**Example journal entries:** Transition adjustment (full retrospective or cumulative catch-up option A method)</span></span><br>
<span data-ttu-id="ef90d-165">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-165">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-166">**Strona Ma:** Należność z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-166">**Credit:** Lease asset XXX</span></span><br>
<span data-ttu-id="ef90d-167">**Strona Ma:** Zyski zatrzymane XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-167">**Credit:** Retained earnings XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="ef90d-168">Zmienna płatność</span><span class="sxs-lookup"><span data-stu-id="ef90d-168">Variable payment</span></span>

<span data-ttu-id="ef90d-169">Konto jest łączone ze zmiennymi opłatami z tytułu wynajmu, które są generowane poprzez przeszacowanie indeksu w leasingu według standardów ASC 842, ASC 840 i MSR 17.</span><span class="sxs-lookup"><span data-stu-id="ef90d-169">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="ef90d-170">W harmonogramie opłat z tytułu wynajmu zmienne płatności są uwzględniane w kolumnie **Opłaty zmienne**.</span><span class="sxs-lookup"><span data-stu-id="ef90d-170">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="ef90d-171">Konto jest obciążane podczas tworzenia faktury dla wiersza harmonogramu płatności zawierającego zmienną opłatę.</span><span class="sxs-lookup"><span data-stu-id="ef90d-171">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="ef90d-172">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-172">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ef90d-173">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-173">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-174">**Strona Winien:** Opłata zmienna XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-174">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="ef90d-175">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-175">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="ef90d-176">Odroczony czynsz składnika majątku (zobowiązanie)</span><span class="sxs-lookup"><span data-stu-id="ef90d-176">Deferred rent asset (liability)</span></span>

<span data-ttu-id="ef90d-177">Konto jest łączone z należnością lub zobowiązaniem z tytułu odroczonego czynszu powstającego w wynajmie z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="ef90d-177">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="ef90d-178">Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem, jeśli kwota opłaty z tytułu wynajmu jest wyższa niż koszt wynajmu liczony metodą liniową za ten okres.</span><span class="sxs-lookup"><span data-stu-id="ef90d-178">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="ef90d-179">Jest uznawane, gdy opłata z tytułu wynajmu jest niższa niż koszt wynajmu liczony metodą liniową za ten okres.</span><span class="sxs-lookup"><span data-stu-id="ef90d-179">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="ef90d-180">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)</span><span class="sxs-lookup"><span data-stu-id="ef90d-180">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="ef90d-181">**Strona Winien:** Wydatek z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-181">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="ef90d-182">**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-182">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="ef90d-183">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-183">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="ef90d-184">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-184">Lease expense</span></span>

<span data-ttu-id="ef90d-185">Konto jest łączone z wydatkiem z tytułu wynajmu, jeśli wynajem jest klasyfikowany jako wynajem z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="ef90d-185">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="ef90d-186">Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem.</span><span class="sxs-lookup"><span data-stu-id="ef90d-186">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="ef90d-187">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)</span><span class="sxs-lookup"><span data-stu-id="ef90d-187">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="ef90d-188">**Strona Winien:** Wydatek z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-188">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="ef90d-189">**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-189">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="ef90d-190">**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-190">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="ef90d-191">Wydatek utraty wartości</span><span class="sxs-lookup"><span data-stu-id="ef90d-191">Impairment expense</span></span>

<span data-ttu-id="ef90d-192">Spadek wartości wynajmowanego składnika powoduje odpowiednie księgowanie na koncie.</span><span class="sxs-lookup"><span data-stu-id="ef90d-192">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="ef90d-193">Konto jest obciążane, natomiast konto składnika majątku z PDU jest bezpośrednio uznawane.</span><span class="sxs-lookup"><span data-stu-id="ef90d-193">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="ef90d-194">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-194">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ef90d-195">**Strona Winien:** Wydatek utraty wartości XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-195">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="ef90d-196">**Strona Ma:** Składnik majątku z PDU XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-196">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="ef90d-197">Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-197">Lease payment</span></span>

<span data-ttu-id="ef90d-198">Na koncie następuje księgowanie, gdy parametr **Płatność dla dostawcy** jest wyłączony.</span><span class="sxs-lookup"><span data-stu-id="ef90d-198">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="ef90d-199">Kiedy parametr jest wyłączony, jest uznawane to konto, a nie konto zobowiązań wobec dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ef90d-199">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="ef90d-200">**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="ef90d-200">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="ef90d-201">**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-201">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="ef90d-202">**Strona Ma:** Opłata z tytułu wynajmu XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-202">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="ef90d-203">Księgowania typów wydatków</span><span class="sxs-lookup"><span data-stu-id="ef90d-203">Expense type postings</span></span>

<span data-ttu-id="ef90d-204">Konto wybrane dla każdego typu wydatków jest obciążane po wygenerowaniu płatności dla danego typu wydatków.</span><span class="sxs-lookup"><span data-stu-id="ef90d-204">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="ef90d-205">Na przykład konto określone dla typu wydatków **Ubezpieczenia** jest obciążane, ilekroć jest tworzona faktura lub wpis w arkuszu płatności na podstawie harmonogramu kosztów wykonawczych dla wydatków ubezpieczeniowych.</span><span class="sxs-lookup"><span data-stu-id="ef90d-205">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="ef90d-206">**Przykładowe wpisy w arkuszu:** Płatność z tytułu ubezpieczenia</span><span class="sxs-lookup"><span data-stu-id="ef90d-206">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="ef90d-207">**Strona Winien:** Konto wydatków ubezpieczeniowych XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-207">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="ef90d-208">**Strona Ma:** Konto przeciwstawne XXX</span><span class="sxs-lookup"><span data-stu-id="ef90d-208">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="ef90d-209">Konto przeciwstawne jest wybierane na poziomie wynajmu w wierszach harmonogramu płatności kosztów wykonawczych.</span><span class="sxs-lookup"><span data-stu-id="ef90d-209">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="ef90d-210">Konto przeciwstawne może być powiązane z dostawcą lub z kontem księgowym.</span><span class="sxs-lookup"><span data-stu-id="ef90d-210">This offset account can associated with the vendor, or with a ledger account.</span></span>
