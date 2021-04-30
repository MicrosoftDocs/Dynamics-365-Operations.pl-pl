---
title: Podwójne raportowanie
description: W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86f42f8db707f3b8c62b9ec4c39ad6464f080748
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881163"
---
# <a name="dual-reporting"></a><span data-ttu-id="008a1-103">Podwójne raportowanie</span><span class="sxs-lookup"><span data-stu-id="008a1-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="008a1-104">W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="008a1-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="008a1-105">Wymagane jest zapoznanie się z warstwami księgowania w Microsoft Dynamics 365 Finance, dzięki czemu przykład będzie łatwiejszy do zrozumienia.</span><span class="sxs-lookup"><span data-stu-id="008a1-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="008a1-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="008a1-106">Example</span></span>

<span data-ttu-id="008a1-107">W poniższym przykładzie przedstawiono wynajem podlegający ustawowej włoskiej sprawozdawczości przy użyciu metody kasowej i metody sprawozdawczości MSSF.</span><span class="sxs-lookup"><span data-stu-id="008a1-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="008a1-108">Firma musi utworzyć trzy księgi, aby uwzględnić zarówno włoskie wymagania ustawowe, jak i wymagania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="008a1-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="008a1-109">Jedna księga jest przeznaczona na MSSF 16, jedna na wymagania ustawowe i jedna do automatycznego wycofywania księgowań ustawowych.</span><span class="sxs-lookup"><span data-stu-id="008a1-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="008a1-110">Księgi są skonfigurowane zgodnie z poniższymi tabelami.</span><span class="sxs-lookup"><span data-stu-id="008a1-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="008a1-111">**Księga MSSF 16**</span><span class="sxs-lookup"><span data-stu-id="008a1-111">**IFRS 16 book**</span></span>

<span data-ttu-id="008a1-112">Księga MSSF 16 jest skonfigurowana w taki sposób, aby była zgodna ze standardem księgowania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="008a1-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="008a1-113">Wszystkie zapisy zaksięgowane w tej księdze będą księgowane w warstwie niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="008a1-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="008a1-114">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="008a1-114">Name</span></span>                                    | <span data-ttu-id="008a1-115">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="008a1-116">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-116">Book type</span></span>                               | <span data-ttu-id="008a1-117">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="008a1-117">IFRS 16</span></span>        |
| <span data-ttu-id="008a1-118">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-118">Book description</span></span>                        | <span data-ttu-id="008a1-119">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="008a1-119">IFRS 16</span></span>        |
| <span data-ttu-id="008a1-120">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-120">Posting Layer</span></span>                           | <span data-ttu-id="008a1-121">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="008a1-121">Custom layer 1</span></span> |
| <span data-ttu-id="008a1-122">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-122">Lease Type</span></span>                              | <span data-ttu-id="008a1-123">Finance</span><span class="sxs-lookup"><span data-stu-id="008a1-123">Finance</span></span>        |
| <span data-ttu-id="008a1-124">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-124">Accounting Framework</span></span>                    | <span data-ttu-id="008a1-125">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="008a1-125">IFRS 16</span></span>        |
| <span data-ttu-id="008a1-126">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="008a1-127">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-127">0.00</span></span>           |
| <span data-ttu-id="008a1-128">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="008a1-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="008a1-129">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-129">0.00</span></span>           |
| <span data-ttu-id="008a1-130">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="008a1-130">Short-term threshold</span></span>                    | <span data-ttu-id="008a1-131">12</span><span class="sxs-lookup"><span data-stu-id="008a1-131">12</span></span>             |
| <span data-ttu-id="008a1-132">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="008a1-132">Low Value Threshold</span></span>                     | <span data-ttu-id="008a1-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-133">5,000.00</span></span>       |
| <span data-ttu-id="008a1-134">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="008a1-134">Pay to Vendor</span></span>                           | <span data-ttu-id="008a1-135">Nr</span><span class="sxs-lookup"><span data-stu-id="008a1-135">No</span></span>             |

<span data-ttu-id="008a1-136">**Księga ustawowa**</span><span class="sxs-lookup"><span data-stu-id="008a1-136">**Statutory book**</span></span>

<span data-ttu-id="008a1-137">Księga ustawowa to księga metody kasowej, w której firma będzie księgować wydatki z tytułu wynajmu jako kwotę gotówki płaconej w każdym miesiącu za wynajem.</span><span class="sxs-lookup"><span data-stu-id="008a1-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="008a1-138">Ta księga nie będzie generować składnika majątku z prawem do użytkowania ani zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="008a1-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="008a1-139">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="008a1-139">Name</span></span>                                    | <span data-ttu-id="008a1-140">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="008a1-141">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-141">Book type</span></span>                               | <span data-ttu-id="008a1-142">Ustawowa</span><span class="sxs-lookup"><span data-stu-id="008a1-142">Statutory</span></span>   |
| <span data-ttu-id="008a1-143">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-143">Book description</span></span>                        | <span data-ttu-id="008a1-144">Lokalna GAAP</span><span class="sxs-lookup"><span data-stu-id="008a1-144">Local GAAP</span></span>  |
| <span data-ttu-id="008a1-145">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-145">Posting Layer</span></span>                           | <span data-ttu-id="008a1-146">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-146">Current</span></span>     |
| <span data-ttu-id="008a1-147">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-147">Lease Type</span></span>                              | <span data-ttu-id="008a1-148">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="008a1-148">Automatic</span></span>   |
| <span data-ttu-id="008a1-149">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-149">Accounting Framework</span></span>                    | <span data-ttu-id="008a1-150">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="008a1-150">Cash basis</span></span>  |
| <span data-ttu-id="008a1-151">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="008a1-152">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-152">0.00</span></span>        |
| <span data-ttu-id="008a1-153">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="008a1-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="008a1-154">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-154">0.00</span></span>        |
| <span data-ttu-id="008a1-155">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="008a1-155">Short-term threshold</span></span>                    | <span data-ttu-id="008a1-156">0</span><span class="sxs-lookup"><span data-stu-id="008a1-156">0</span></span>           |
| <span data-ttu-id="008a1-157">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="008a1-157">Low Value Threshold</span></span>                     | <span data-ttu-id="008a1-158">0</span><span class="sxs-lookup"><span data-stu-id="008a1-158">0</span></span>           |
| <span data-ttu-id="008a1-159">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="008a1-159">Pay to Vendor</span></span>                           | <span data-ttu-id="008a1-160">Nr</span><span class="sxs-lookup"><span data-stu-id="008a1-160">No</span></span>          |

<span data-ttu-id="008a1-161">**Księga wycofania ustawowego**</span><span class="sxs-lookup"><span data-stu-id="008a1-161">**Statutory reversal book**</span></span>

<span data-ttu-id="008a1-162">Księga wycofania ustawowego jest konfigurowana w taki sam sposób, jak księga ustawowa.</span><span class="sxs-lookup"><span data-stu-id="008a1-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="008a1-163">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="008a1-163">Name</span></span>                                    | <span data-ttu-id="008a1-164">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="008a1-165">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-165">Book type</span></span>                               | <span data-ttu-id="008a1-166">Ustawowe — wycofanie</span><span class="sxs-lookup"><span data-stu-id="008a1-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="008a1-167">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="008a1-167">Book description</span></span>                        | <span data-ttu-id="008a1-168">Księga do cofania księgi ustawowej</span><span class="sxs-lookup"><span data-stu-id="008a1-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="008a1-169">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-169">Posting Layer</span></span>                           | <span data-ttu-id="008a1-170">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="008a1-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="008a1-171">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-171">Lease Type</span></span>                              | <span data-ttu-id="008a1-172">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="008a1-172">Automatic</span></span>                      |
| <span data-ttu-id="008a1-173">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="008a1-173">Accounting Framework</span></span>                    | <span data-ttu-id="008a1-174">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="008a1-174">Cash basis</span></span>                     |
| <span data-ttu-id="008a1-175">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="008a1-176">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-176">0.00</span></span>                           |
| <span data-ttu-id="008a1-177">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="008a1-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="008a1-178">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-178">0.00</span></span>                           |
| <span data-ttu-id="008a1-179">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="008a1-179">Short-term threshold</span></span>                    | <span data-ttu-id="008a1-180">0</span><span class="sxs-lookup"><span data-stu-id="008a1-180">0</span></span>                              |
| <span data-ttu-id="008a1-181">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="008a1-181">Low Value Threshold</span></span>                     | <span data-ttu-id="008a1-182">0</span><span class="sxs-lookup"><span data-stu-id="008a1-182">0</span></span>                              |
| <span data-ttu-id="008a1-183">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="008a1-183">Pay to Vendor</span></span>                           | <span data-ttu-id="008a1-184">Nr</span><span class="sxs-lookup"><span data-stu-id="008a1-184">No</span></span>                             |

<span data-ttu-id="008a1-185">W tym przykładzie utworzono wynajem, który ma następujące ustawienia na kartach **Ogólne** i **Wiersze harmonogramu płatności**.</span><span class="sxs-lookup"><span data-stu-id="008a1-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="008a1-186">**Karta Ogólne**</span><span class="sxs-lookup"><span data-stu-id="008a1-186">**General tab**</span></span>

| <span data-ttu-id="008a1-187">Pole</span><span class="sxs-lookup"><span data-stu-id="008a1-187">Field</span></span>                      | <span data-ttu-id="008a1-188">Wartość</span><span class="sxs-lookup"><span data-stu-id="008a1-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="008a1-189">Krańcowa stopa procentowa</span><span class="sxs-lookup"><span data-stu-id="008a1-189">Incremental borrowing rate</span></span> | <span data-ttu-id="008a1-190">5%</span><span class="sxs-lookup"><span data-stu-id="008a1-190">5%</span></span>               |
| <span data-ttu-id="008a1-191">Data rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="008a1-191">Commencement date</span></span>          | <span data-ttu-id="008a1-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="008a1-192">1/1/2020</span></span>         |
| <span data-ttu-id="008a1-193">Grupa wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-193">Lease group</span></span>                | <span data-ttu-id="008a1-194">Budynki</span><span class="sxs-lookup"><span data-stu-id="008a1-194">Buildings</span></span>        |
| <span data-ttu-id="008a1-195">Dostawca</span><span class="sxs-lookup"><span data-stu-id="008a1-195">Vendor</span></span>                     | <span data-ttu-id="008a1-196">1001</span><span class="sxs-lookup"><span data-stu-id="008a1-196">1001</span></span>             |
| <span data-ttu-id="008a1-197">Wartość godziwa składnika majątku</span><span class="sxs-lookup"><span data-stu-id="008a1-197">Fair value of the asset</span></span>    | <span data-ttu-id="008a1-198">245,000</span><span class="sxs-lookup"><span data-stu-id="008a1-198">245,000</span></span>          |
| <span data-ttu-id="008a1-199">Okres użyteczności składnika majątku</span><span class="sxs-lookup"><span data-stu-id="008a1-199">Asset useful life</span></span>          | <span data-ttu-id="008a1-200">120</span><span class="sxs-lookup"><span data-stu-id="008a1-200">120</span></span>              |
| <span data-ttu-id="008a1-201">Typ annuity</span><span class="sxs-lookup"><span data-stu-id="008a1-201">Annuity type</span></span>               | <span data-ttu-id="008a1-202">Zwykła annuita</span><span class="sxs-lookup"><span data-stu-id="008a1-202">Ordinary annuity</span></span> |
| <span data-ttu-id="008a1-203">Interwał łączenia</span><span class="sxs-lookup"><span data-stu-id="008a1-203">Compounding interval</span></span>       | <span data-ttu-id="008a1-204">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="008a1-204">Monthly</span></span>          |

<span data-ttu-id="008a1-205">**Karta Wiersze harmonogramu płatności**</span><span class="sxs-lookup"><span data-stu-id="008a1-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="008a1-206">Pole</span><span class="sxs-lookup"><span data-stu-id="008a1-206">Field</span></span>             | <span data-ttu-id="008a1-207">Wartość</span><span class="sxs-lookup"><span data-stu-id="008a1-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="008a1-208">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="008a1-208">Start date</span></span>        | <span data-ttu-id="008a1-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="008a1-209">1/1/2020</span></span>   |
| <span data-ttu-id="008a1-210">Zakres czasowy</span><span class="sxs-lookup"><span data-stu-id="008a1-210">Period interval</span></span>   | <span data-ttu-id="008a1-211">Miesiące</span><span class="sxs-lookup"><span data-stu-id="008a1-211">Months</span></span>     |
| <span data-ttu-id="008a1-212">Okresy</span><span class="sxs-lookup"><span data-stu-id="008a1-212">Periods</span></span>           | <span data-ttu-id="008a1-213">24</span><span class="sxs-lookup"><span data-stu-id="008a1-213">24</span></span>         |
| <span data-ttu-id="008a1-214">Data końcowa</span><span class="sxs-lookup"><span data-stu-id="008a1-214">End date</span></span>          | <span data-ttu-id="008a1-215">12/31/2020</span><span class="sxs-lookup"><span data-stu-id="008a1-215">12/31/2020</span></span> |
| <span data-ttu-id="008a1-216">Częstość płatności</span><span class="sxs-lookup"><span data-stu-id="008a1-216">Payment frequency</span></span> | <span data-ttu-id="008a1-217">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="008a1-217">Monthly</span></span>    |
| <span data-ttu-id="008a1-218">Kwota płatności</span><span class="sxs-lookup"><span data-stu-id="008a1-218">Payment amount</span></span>    | <span data-ttu-id="008a1-219">1 000</span><span class="sxs-lookup"><span data-stu-id="008a1-219">1,000</span></span>      |

<span data-ttu-id="008a1-220">Aby ten wynajem był rozliczany w dwóch strukturach, należy skorzystać z bieżącej warstwy księgowania i niestandardowej warstwy księgowania.</span><span class="sxs-lookup"><span data-stu-id="008a1-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="008a1-221">W poniższej tabeli przedstawiono przykład każdego wpisu w arkuszu wymaganego do rzetelnego reprezentowania finansów w poszczególnych standardach sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="008a1-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="008a1-222">Szczegółowy opis każdego wpisu w arkuszu za pierwszy miesiąc wynajmu znajduje się dalej.</span><span class="sxs-lookup"><span data-stu-id="008a1-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="008a1-223">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="008a1-224">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="008a1-225">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="008a1-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="008a1-226">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="008a1-226">Current layer total</span></span></th>
<th><span data-ttu-id="008a1-227">Księga wycofania (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="008a1-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="008a1-228">Księga MSSF 16 (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="008a1-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="008a1-229">Suma Bieżąca warstwa + Niestandardowa warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="008a1-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="008a1-230">JE-100</span></span></th>
<th><span data-ttu-id="008a1-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="008a1-231">JE-110</span></span></th>
<th><span data-ttu-id="008a1-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="008a1-232">JE-120</span></span></th>
<th><span data-ttu-id="008a1-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="008a1-233">JE-130</span></span></th>
<th><span data-ttu-id="008a1-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="008a1-234">JE-140</span></span></th>
<th><span data-ttu-id="008a1-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="008a1-235">JE-150</span></span></th>
<th><span data-ttu-id="008a1-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="008a1-236">JE-160</span></span></th>
<th><span data-ttu-id="008a1-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="008a1-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="008a1-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="008a1-246">1</span><span class="sxs-lookup"><span data-stu-id="008a1-246">1</span></span></td>
<td><span data-ttu-id="008a1-247">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-247">Lease expense</span></span></td>
<td><span data-ttu-id="008a1-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-249">1,000.00</span></span></td>
<td><span data-ttu-id="008a1-250">-1000,00</span><span class="sxs-lookup"><span data-stu-id="008a1-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-251">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-252">2</span><span class="sxs-lookup"><span data-stu-id="008a1-252">2</span></span></td>
<td><span data-ttu-id="008a1-253">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="008a1-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-254">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-255">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-256">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-257">3</span><span class="sxs-lookup"><span data-stu-id="008a1-257">3</span></span></td>
<td><span data-ttu-id="008a1-258">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="008a1-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-259">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-260">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-261">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-262">4</span><span class="sxs-lookup"><span data-stu-id="008a1-262">4</span></span></td>
<td><span data-ttu-id="008a1-263">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-263">Clearing account</span></span></td>
<td><span data-ttu-id="008a1-264">-1000,00</span><span class="sxs-lookup"><span data-stu-id="008a1-264">-1,000.00</span></span></td>
<td><span data-ttu-id="008a1-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-266">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-266">0.00</span></span></td>
<td><span data-ttu-id="008a1-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-268">-1000,00</span><span class="sxs-lookup"><span data-stu-id="008a1-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-269">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-270">5</span><span class="sxs-lookup"><span data-stu-id="008a1-270">5</span></span></td>
<td><span data-ttu-id="008a1-271">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="008a1-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-272">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-272">-1,008.00</span></span></td>
<td><span data-ttu-id="008a1-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="008a1-273">1,008.00</span></span></td>
<td><span data-ttu-id="008a1-274">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-275">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-276">6</span><span class="sxs-lookup"><span data-stu-id="008a1-276">6</span></span></td>
<td><span data-ttu-id="008a1-277">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="008a1-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-278">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="008a1-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="008a1-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-281">7</span><span class="sxs-lookup"><span data-stu-id="008a1-281">7</span></span></td>
<td><span data-ttu-id="008a1-282">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-283">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="008a1-284">-22,794.00</span></span></td>
<td><span data-ttu-id="008a1-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-285">1,000.00</span></span></td>
<td><span data-ttu-id="008a1-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="008a1-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="008a1-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-288">8</span><span class="sxs-lookup"><span data-stu-id="008a1-288">8</span></span></td>
<td><span data-ttu-id="008a1-289">Odsetki</span><span class="sxs-lookup"><span data-stu-id="008a1-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-290">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-291">94.97</span><span class="sxs-lookup"><span data-stu-id="008a1-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-292">94.97</span><span class="sxs-lookup"><span data-stu-id="008a1-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-293">9</span><span class="sxs-lookup"><span data-stu-id="008a1-293">9</span></span></td>
<td><span data-ttu-id="008a1-294">Kasa</span><span class="sxs-lookup"><span data-stu-id="008a1-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-295">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-295">-1,008.00</span></span></td>
<td><span data-ttu-id="008a1-296">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-297">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-298">10</span><span class="sxs-lookup"><span data-stu-id="008a1-298">10</span></span></td>
<td><span data-ttu-id="008a1-299">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="008a1-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-300">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-301">949.75</span><span class="sxs-lookup"><span data-stu-id="008a1-301">949.75</span></span></td>
<td><span data-ttu-id="008a1-302">949.75</span><span class="sxs-lookup"><span data-stu-id="008a1-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-303">11</span><span class="sxs-lookup"><span data-stu-id="008a1-303">11</span></span></td>
<td><span data-ttu-id="008a1-304">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="008a1-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-305">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="008a1-306">-949.75</span></span></td>
<td><span data-ttu-id="008a1-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="008a1-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="008a1-308">Jak widać w powyższych tabelach, wymagane są trzy księgi do raportowania według sprawozdawczości ustawowej i MSSF.</span><span class="sxs-lookup"><span data-stu-id="008a1-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="008a1-309">W księdze ustawowej jest rejestrowana opłata z tytułu wynajmu zgodnie z regułami księgowania w metodzie kasowej w bieżącej warstwie.</span><span class="sxs-lookup"><span data-stu-id="008a1-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="008a1-310">Księga wycofania ustawowego wycofuje ustawowe wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="008a1-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="008a1-311">Księga MSSF 16 tworzy wpisy w arkuszu wymagane na mocy MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="008a1-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="008a1-312">Wynajem musi zostać wprowadzony tylko raz.</span><span class="sxs-lookup"><span data-stu-id="008a1-312">You must enter a lease only one time.</span></span> <span data-ttu-id="008a1-313">Następnie można otworzyć stronę **Księgi** w celu wyświetlenia wszystkich ksiąg skojarzonych z wynajmem.</span><span class="sxs-lookup"><span data-stu-id="008a1-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="008a1-314">Po utworzeniu ksiąg wszystkie trzy z nich muszą być skojarzone z tym samym rekordem wynajmu.</span><span class="sxs-lookup"><span data-stu-id="008a1-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="008a1-315">Pierwszy wpis w arkuszu rejestruje wydatek z tytułu wynajmu w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="008a1-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="008a1-316">Płatności można tworzyć w ramach partii lub wybierając harmonogram płatności w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="008a1-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="008a1-317">W tym przykładzie dla księgi ustawowej jest tworzony następujący wpis w arkuszu z harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="008a1-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="008a1-318">Opłata z tytułu wynajmu — 1/31/2020 — JE 100</span><span class="sxs-lookup"><span data-stu-id="008a1-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="008a1-319">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-319">Account type</span></span> | <span data-ttu-id="008a1-320">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-320">Account number</span></span> | <span data-ttu-id="008a1-321">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-321">Layer</span></span>   | <span data-ttu-id="008a1-322">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-322">Account description</span></span> | <span data-ttu-id="008a1-323">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-323">Debit</span></span>    | <span data-ttu-id="008a1-324">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="008a1-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-325">Ledger</span></span>       | <span data-ttu-id="008a1-326">1</span><span class="sxs-lookup"><span data-stu-id="008a1-326">1</span></span>              | <span data-ttu-id="008a1-327">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-327">Current</span></span> | <span data-ttu-id="008a1-328">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-328">Lease expense</span></span>       | <span data-ttu-id="008a1-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-329">1,000.00</span></span> |          |
| <span data-ttu-id="008a1-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-330">Ledger</span></span>       | <span data-ttu-id="008a1-331">4</span><span class="sxs-lookup"><span data-stu-id="008a1-331">4</span></span>              | <span data-ttu-id="008a1-332">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-332">Current</span></span> | <span data-ttu-id="008a1-333">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-333">Clearing account</span></span>    |          | <span data-ttu-id="008a1-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-334">1,000.00</span></span> |

<span data-ttu-id="008a1-335">Pracownik ds. rozrachunków z dostawcami korzysta ze standardowych funkcji systemu Dynamics 365, aby utworzyć fakturę do zapłacenia za wynajem poza wynajmem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="008a1-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="008a1-336">Jednak zamiast wybierania **Wydatek z tytułu wynajmu** jako konta debetowego pracownik ds. rozrachunków z dostawcami wybiera konto rozliczeniowe w celu wygenerowania poniższego wpisu.</span><span class="sxs-lookup"><span data-stu-id="008a1-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="008a1-337">Proces AP — 1/31/2020 — JE 110</span><span class="sxs-lookup"><span data-stu-id="008a1-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="008a1-338">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-338">Account type</span></span> | <span data-ttu-id="008a1-339">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-339">Account number</span></span> | <span data-ttu-id="008a1-340">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-340">Layer</span></span>   | <span data-ttu-id="008a1-341">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-341">Account description</span></span> | <span data-ttu-id="008a1-342">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-342">Debit</span></span>    | <span data-ttu-id="008a1-343">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="008a1-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-344">Ledger</span></span>       | <span data-ttu-id="008a1-345">4</span><span class="sxs-lookup"><span data-stu-id="008a1-345">4</span></span>              | <span data-ttu-id="008a1-346">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-346">Current</span></span> | <span data-ttu-id="008a1-347">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-347">Clearing account</span></span>    | <span data-ttu-id="008a1-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-348">1,000.00</span></span> |          |
| <span data-ttu-id="008a1-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-349">Ledger</span></span>       | <span data-ttu-id="008a1-350">2</span><span class="sxs-lookup"><span data-stu-id="008a1-350">2</span></span>              | <span data-ttu-id="008a1-351">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-351">Current</span></span> | <span data-ttu-id="008a1-352">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="008a1-352">Bank fee</span></span>            | <span data-ttu-id="008a1-353">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-353">3.00</span></span>     |          |
| <span data-ttu-id="008a1-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-354">Ledger</span></span>       | <span data-ttu-id="008a1-355">3</span><span class="sxs-lookup"><span data-stu-id="008a1-355">3</span></span>              | <span data-ttu-id="008a1-356">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-356">Current</span></span> | <span data-ttu-id="008a1-357">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="008a1-357">VAT expense</span></span>         | <span data-ttu-id="008a1-358">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-358">5.00</span></span>     |          |
| <span data-ttu-id="008a1-359">Dostawca</span><span class="sxs-lookup"><span data-stu-id="008a1-359">Vendor</span></span>       | <span data-ttu-id="008a1-360">5</span><span class="sxs-lookup"><span data-stu-id="008a1-360">5</span></span>              | <span data-ttu-id="008a1-361">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-361">Current</span></span> | <span data-ttu-id="008a1-362">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="008a1-362">Accounts payable</span></span>    |          | <span data-ttu-id="008a1-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="008a1-363">1,008.00</span></span> |

<span data-ttu-id="008a1-364">Gdy dostawcy jest udzielana instrukcja, należy postępować zgodnie z regularnym procesem płatności.</span><span class="sxs-lookup"><span data-stu-id="008a1-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="008a1-365">Podczas tego procesu jest generowany następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="008a1-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="008a1-366">Płatność gotówkowa — 1/31/2020 — JE 120</span><span class="sxs-lookup"><span data-stu-id="008a1-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="008a1-367">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-367">Account type</span></span> | <span data-ttu-id="008a1-368">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-368">Account number</span></span> | <span data-ttu-id="008a1-369">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-369">Layer</span></span>   | <span data-ttu-id="008a1-370">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-370">Account description</span></span> | <span data-ttu-id="008a1-371">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-371">Debit</span></span>    | <span data-ttu-id="008a1-372">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="008a1-373">Dostawca</span><span class="sxs-lookup"><span data-stu-id="008a1-373">Vendor</span></span>       | <span data-ttu-id="008a1-374">5</span><span class="sxs-lookup"><span data-stu-id="008a1-374">5</span></span>              | <span data-ttu-id="008a1-375">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-375">Current</span></span> | <span data-ttu-id="008a1-376">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="008a1-376">Accounts Payable</span></span>    | <span data-ttu-id="008a1-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="008a1-377">1,008.00</span></span> |          |
| <span data-ttu-id="008a1-378">Bank</span><span class="sxs-lookup"><span data-stu-id="008a1-378">Bank</span></span>         | <span data-ttu-id="008a1-379">9</span><span class="sxs-lookup"><span data-stu-id="008a1-379">9</span></span>              | <span data-ttu-id="008a1-380">Bieżące</span><span class="sxs-lookup"><span data-stu-id="008a1-380">Current</span></span> | <span data-ttu-id="008a1-381">Kasa</span><span class="sxs-lookup"><span data-stu-id="008a1-381">Cash</span></span>                |          | <span data-ttu-id="008a1-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="008a1-382">1,008.00</span></span> |

<span data-ttu-id="008a1-383">Na tym etapie wynajem jest w pełni zaksięgowany zgodnie z ustawowymi wymogami sprawozdawczości i można wygenerować bilans próbny, korzystając z bieżącej warstwy.</span><span class="sxs-lookup"><span data-stu-id="008a1-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="008a1-384">System zwraca bilans próbny o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="008a1-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="008a1-385">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="008a1-386">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="008a1-387">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="008a1-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="008a1-388">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="008a1-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="008a1-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="008a1-389">JE-100</span></span></th>
<th><span data-ttu-id="008a1-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="008a1-390">JE-110</span></span></th>
<th><span data-ttu-id="008a1-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="008a1-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="008a1-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="008a1-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="008a1-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="008a1-395">1</span><span class="sxs-lookup"><span data-stu-id="008a1-395">1</span></span></td>
<td><span data-ttu-id="008a1-396">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-396">Lease expense</span></span></td>
<td><span data-ttu-id="008a1-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-399">2</span><span class="sxs-lookup"><span data-stu-id="008a1-399">2</span></span></td>
<td><span data-ttu-id="008a1-400">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="008a1-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-401">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-402">3.00</span><span class="sxs-lookup"><span data-stu-id="008a1-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-403">3</span><span class="sxs-lookup"><span data-stu-id="008a1-403">3</span></span></td>
<td><span data-ttu-id="008a1-404">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="008a1-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-405">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-406">5.00</span><span class="sxs-lookup"><span data-stu-id="008a1-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-407">4</span><span class="sxs-lookup"><span data-stu-id="008a1-407">4</span></span></td>
<td><span data-ttu-id="008a1-408">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-408">Clearing account</span></span></td>
<td><span data-ttu-id="008a1-409">-1000,00</span><span class="sxs-lookup"><span data-stu-id="008a1-409">-1,000.00</span></span></td>
<td><span data-ttu-id="008a1-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-411">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-412">5</span><span class="sxs-lookup"><span data-stu-id="008a1-412">5</span></span></td>
<td><span data-ttu-id="008a1-413">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="008a1-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="008a1-414">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-414">-1,008.00</span></span></td>
<td><span data-ttu-id="008a1-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="008a1-415">1,008.00</span></span></td>
<td><span data-ttu-id="008a1-416">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-417">6</span><span class="sxs-lookup"><span data-stu-id="008a1-417">6</span></span></td>
<td><span data-ttu-id="008a1-418">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="008a1-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-419">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-420">7</span><span class="sxs-lookup"><span data-stu-id="008a1-420">7</span></span></td>
<td><span data-ttu-id="008a1-421">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-422">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-423">8</span><span class="sxs-lookup"><span data-stu-id="008a1-423">8</span></span></td>
<td><span data-ttu-id="008a1-424">Odsetki</span><span class="sxs-lookup"><span data-stu-id="008a1-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-425">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-426">9</span><span class="sxs-lookup"><span data-stu-id="008a1-426">9</span></span></td>
<td><span data-ttu-id="008a1-427">Kasa</span><span class="sxs-lookup"><span data-stu-id="008a1-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-428">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-428">-1,008.00</span></span></td>
<td><span data-ttu-id="008a1-429">-1008,00</span><span class="sxs-lookup"><span data-stu-id="008a1-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-430">10</span><span class="sxs-lookup"><span data-stu-id="008a1-430">10</span></span></td>
<td><span data-ttu-id="008a1-431">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="008a1-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-432">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="008a1-433">11</span><span class="sxs-lookup"><span data-stu-id="008a1-433">11</span></span></td>
<td><span data-ttu-id="008a1-434">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="008a1-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="008a1-435">0,00</span><span class="sxs-lookup"><span data-stu-id="008a1-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="008a1-436">Jeśli ten sam bilans próbny ma zostać wykonany na wartościach MSSF 16, należy wycofać wpisy w arkuszu księgowania ustawowego i zaksięgować wpisy w arkuszu MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="008a1-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="008a1-437">Aby wycofać ustawowe wpisy w arkuszu, w tym przykładzie jest zawarta księga wycofania ustawowego, która ma taką samą konfigurację jak księga ustawowa, ale przeciwny profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="008a1-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="008a1-438">Na przykład księga ustawowa *obciąża* konto wydatku z tytułu wynajmu, a księga wycofania *uznaje* to konto.</span><span class="sxs-lookup"><span data-stu-id="008a1-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="008a1-439">Relacje te są łatwe do zdefiniowania na kontach księgowania wynajmu składników majątku na stronie **Parametry wynajmu składników majątku** (**Wynajem składników majątku \> Ustawienia \> Parametry wynajmu składników majątku**).</span><span class="sxs-lookup"><span data-stu-id="008a1-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="008a1-440">Jeśli ten sam proces, który był używany dla księgi ustawowej, zostanie użyty w księdze wycofania, tworzony jest następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="008a1-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="008a1-441">Różnica polega na tym, że księga wycofania księguje zapisy wycofania z księgi ustawowej.</span><span class="sxs-lookup"><span data-stu-id="008a1-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="008a1-442">Wpisy wycofania są również wprowadzane do niestandardowej warstwy.</span><span class="sxs-lookup"><span data-stu-id="008a1-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="008a1-443">Jeśli bilans próbny zostanie wykonany na bieżącej warstwie, wycofujące wpisy w arkuszu nie będą uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="008a1-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="008a1-444">Opłata z tytułu wynajmu — 1/31/2020 — JE 130</span><span class="sxs-lookup"><span data-stu-id="008a1-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="008a1-445">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-445">Account type</span></span> | <span data-ttu-id="008a1-446">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-446">Account number</span></span> | <span data-ttu-id="008a1-447">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-447">Layer</span></span>  | <span data-ttu-id="008a1-448">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-448">Account description</span></span> | <span data-ttu-id="008a1-449">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-449">Debit</span></span>    | <span data-ttu-id="008a1-450">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="008a1-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-451">Ledger</span></span>       | <span data-ttu-id="008a1-452">4</span><span class="sxs-lookup"><span data-stu-id="008a1-452">4</span></span>              | <span data-ttu-id="008a1-453">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-453">Custom</span></span> | <span data-ttu-id="008a1-454">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-454">Clearing account</span></span>    | <span data-ttu-id="008a1-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-455">1,000.00</span></span> |          |
| <span data-ttu-id="008a1-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-456">Ledger</span></span>       | <span data-ttu-id="008a1-457">1</span><span class="sxs-lookup"><span data-stu-id="008a1-457">1</span></span>              | <span data-ttu-id="008a1-458">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-458">Custom</span></span> | <span data-ttu-id="008a1-459">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-459">Lease expense</span></span>       |          | <span data-ttu-id="008a1-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-460">1,000.00</span></span> |

<span data-ttu-id="008a1-461">Po usunięciu ustawowych wpisów w arkuszu księgujesz w księdze MSSF 16 wszystkie wpisy w dzienniku, których wymaga MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="008a1-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="008a1-462">Do tych wpisów należą początkowe uznanie składnika majątku z PDU i zobowiązanie, a także rekord odsetek i amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="008a1-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="008a1-463">Początkowe uznanie — 1/1/2020 — JE 140</span><span class="sxs-lookup"><span data-stu-id="008a1-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="008a1-464">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-464">Account type</span></span> | <span data-ttu-id="008a1-465">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-465">Account number</span></span> | <span data-ttu-id="008a1-466">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-466">Layer</span></span>  | <span data-ttu-id="008a1-467">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-467">Account description</span></span>      | <span data-ttu-id="008a1-468">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-468">Debit</span></span>     | <span data-ttu-id="008a1-469">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="008a1-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-470">Ledger</span></span>       | <span data-ttu-id="008a1-471">6</span><span class="sxs-lookup"><span data-stu-id="008a1-471">6</span></span>              | <span data-ttu-id="008a1-472">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-472">Custom</span></span> | <span data-ttu-id="008a1-473">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="008a1-473">ROU Asset</span></span>                | <span data-ttu-id="008a1-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="008a1-474">22,793.90</span></span> |           |
| <span data-ttu-id="008a1-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-475">Ledger</span></span>       | <span data-ttu-id="008a1-476">7</span><span class="sxs-lookup"><span data-stu-id="008a1-476">7</span></span>              | <span data-ttu-id="008a1-477">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-477">Custom</span></span> | <span data-ttu-id="008a1-478">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-478">Finance lease obligation</span></span> |           | <span data-ttu-id="008a1-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="008a1-479">22,793.90</span></span> |

<span data-ttu-id="008a1-480">Opłata z tytułu wynajmu jest księgowana jak inne opłaty z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="008a1-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="008a1-481">Przyczyną użycia konta rozliczeniowego jest zapewnienie, aby gotówka była uznawana tylko jeden raz.</span><span class="sxs-lookup"><span data-stu-id="008a1-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="008a1-482">Opłata z tytułu wynajmu — 1/31/2020 — JE 150</span><span class="sxs-lookup"><span data-stu-id="008a1-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="008a1-483">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-483">Account type</span></span> | <span data-ttu-id="008a1-484">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-484">Account number</span></span> | <span data-ttu-id="008a1-485">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-485">Layer</span></span>  | <span data-ttu-id="008a1-486">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-486">Account description</span></span>      | <span data-ttu-id="008a1-487">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-487">Debit</span></span>    | <span data-ttu-id="008a1-488">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="008a1-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-489">Ledger</span></span>       | <span data-ttu-id="008a1-490">7</span><span class="sxs-lookup"><span data-stu-id="008a1-490">7</span></span>              | <span data-ttu-id="008a1-491">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-491">Custom</span></span> | <span data-ttu-id="008a1-492">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-492">Finance lease obligation</span></span> | <span data-ttu-id="008a1-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-493">1,000.00</span></span> |          |
| <span data-ttu-id="008a1-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-494">Ledger</span></span>       | <span data-ttu-id="008a1-495">4</span><span class="sxs-lookup"><span data-stu-id="008a1-495">4</span></span>              | <span data-ttu-id="008a1-496">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-496">Custom</span></span> | <span data-ttu-id="008a1-497">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-497">Clearing account</span></span>         |          | <span data-ttu-id="008a1-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="008a1-498">1,000.00</span></span> |

<span data-ttu-id="008a1-499">Wpis w arkuszu kosztu odsetek jest generowany na podstawie harmonogramu amortyzacji zobowiązań.</span><span class="sxs-lookup"><span data-stu-id="008a1-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="008a1-500">Koszt odsetek — 1/31/2020 — JE 160</span><span class="sxs-lookup"><span data-stu-id="008a1-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="008a1-501">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-501">Account type</span></span> | <span data-ttu-id="008a1-502">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-502">Account number</span></span> | <span data-ttu-id="008a1-503">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-503">Layer</span></span>  | <span data-ttu-id="008a1-504">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-504">Account description</span></span>      | <span data-ttu-id="008a1-505">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-505">Debit</span></span> | <span data-ttu-id="008a1-506">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="008a1-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-507">Ledger</span></span>       | <span data-ttu-id="008a1-508">8</span><span class="sxs-lookup"><span data-stu-id="008a1-508">8</span></span>              | <span data-ttu-id="008a1-509">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-509">Custom</span></span> | <span data-ttu-id="008a1-510">Odsetki</span><span class="sxs-lookup"><span data-stu-id="008a1-510">Interest expense</span></span>         | <span data-ttu-id="008a1-511">94.97</span><span class="sxs-lookup"><span data-stu-id="008a1-511">94.97</span></span> |        |
| <span data-ttu-id="008a1-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-512">Ledger</span></span>       | <span data-ttu-id="008a1-513">7</span><span class="sxs-lookup"><span data-stu-id="008a1-513">7</span></span>              | <span data-ttu-id="008a1-514">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-514">Custom</span></span> | <span data-ttu-id="008a1-515">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-515">Finance lease obligation</span></span> |       | <span data-ttu-id="008a1-516">94.97</span><span class="sxs-lookup"><span data-stu-id="008a1-516">94.97</span></span>  |

<span data-ttu-id="008a1-517">Wpis w arkuszu kosztu amortyzacji jest generowany na podstawie harmonogramu amortyzacji składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="008a1-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="008a1-518">Wydatek amortyzacji — 1/31/2020 — JE 170</span><span class="sxs-lookup"><span data-stu-id="008a1-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="008a1-519">Typ konta</span><span class="sxs-lookup"><span data-stu-id="008a1-519">Account type</span></span> | <span data-ttu-id="008a1-520">Numer konta</span><span class="sxs-lookup"><span data-stu-id="008a1-520">Account number</span></span> | <span data-ttu-id="008a1-521">Warstwa</span><span class="sxs-lookup"><span data-stu-id="008a1-521">Layer</span></span>  | <span data-ttu-id="008a1-522">Opis konta</span><span class="sxs-lookup"><span data-stu-id="008a1-522">Account description</span></span>      | <span data-ttu-id="008a1-523">Uznanie</span><span class="sxs-lookup"><span data-stu-id="008a1-523">Debit</span></span>  | <span data-ttu-id="008a1-524">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="008a1-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="008a1-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-525">Ledger</span></span>       | <span data-ttu-id="008a1-526">10</span><span class="sxs-lookup"><span data-stu-id="008a1-526">10</span></span>             | <span data-ttu-id="008a1-527">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-527">Custom</span></span> | <span data-ttu-id="008a1-528">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="008a1-528">Depreciation expense</span></span>     | <span data-ttu-id="008a1-529">949.75</span><span class="sxs-lookup"><span data-stu-id="008a1-529">949.75</span></span> |        |
| <span data-ttu-id="008a1-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="008a1-530">Ledger</span></span>       | <span data-ttu-id="008a1-531">11</span><span class="sxs-lookup"><span data-stu-id="008a1-531">11</span></span>             | <span data-ttu-id="008a1-532">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="008a1-532">Custom</span></span> | <span data-ttu-id="008a1-533">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="008a1-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="008a1-534">949.75</span><span class="sxs-lookup"><span data-stu-id="008a1-534">949.75</span></span> |

<span data-ttu-id="008a1-535">Po utworzeniu i zaksięgowaniu wszystkich tych wpisów w arkuszu będą widoczne następujące wartości „niestandardowej warstwy 1”.</span><span class="sxs-lookup"><span data-stu-id="008a1-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="008a1-536">Należy zauważyć, że ostatnia kolumna zawiera opłatę bankową, koszt VAT oraz zmniejszenie ilości gotówki z poprzedniej warstwy, ale nie zawiera wpisów w arkuszu sprawozdawczości ustawowej.</span><span class="sxs-lookup"><span data-stu-id="008a1-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="008a1-537">Pozwala to na osiągnięcie prawdziwych możliwości podwójnego raportowania.</span><span class="sxs-lookup"><span data-stu-id="008a1-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="008a1-538">W tym momencie firma ma możliwość uruchomienia bilansu próbnego i połączenia bieżącej warstwy z niestandardową warstwą w celu utworzenia bilansu próbnego według MSSF.</span><span class="sxs-lookup"><span data-stu-id="008a1-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="008a1-539">Nr konta</span><span class="sxs-lookup"><span data-stu-id="008a1-539">Account No</span></span> | <span data-ttu-id="008a1-540">opis</span><span class="sxs-lookup"><span data-stu-id="008a1-540">Description</span></span>              | <span data-ttu-id="008a1-541">Księga ustawowa\-bieżąca warstwa\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-542">Księga ustawowa\-bieżąca warstwa\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-543">Księga ustawowa\-bieżąca warstwa\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-544">Bieżąca warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="008a1-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="008a1-545">Księga wycofania\-niestandardowa warstwa\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-546">Księga MSSF 16\-niestandardowa warstwa\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-547">Księga MSSF 16\-niestandardowa warstwa\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-548">Księga MSSF 16\-niestandardowa warstwa\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-549">Księga MSSF 16\-niestandardowa warstwa\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="008a1-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="008a1-550">Bieżąca warstwa \+ niestandardowa warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="008a1-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="008a1-551">1</span><span class="sxs-lookup"><span data-stu-id="008a1-551">1</span></span>          | <span data-ttu-id="008a1-552">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="008a1-552">Lease expense</span></span>            | <span data-ttu-id="008a1-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="008a1-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-554">1,000\.00</span></span>               |   | <span data-ttu-id="008a1-555">\-1000</span><span class="sxs-lookup"><span data-stu-id="008a1-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="008a1-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-556">0\.00</span></span>                                   |
| <span data-ttu-id="008a1-557">2</span><span class="sxs-lookup"><span data-stu-id="008a1-557">2</span></span>          | <span data-ttu-id="008a1-558">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="008a1-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="008a1-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="008a1-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="008a1-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-561">3\.00</span></span>                                   |
| <span data-ttu-id="008a1-562">3</span><span class="sxs-lookup"><span data-stu-id="008a1-562">3</span></span>          | <span data-ttu-id="008a1-563">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="008a1-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="008a1-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="008a1-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="008a1-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-566">5\.00</span></span>                                   |
| <span data-ttu-id="008a1-567">4</span><span class="sxs-lookup"><span data-stu-id="008a1-567">4</span></span>          | <span data-ttu-id="008a1-568">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="008a1-568">Clearing account</span></span>         | <span data-ttu-id="008a1-569">\-1000\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="008a1-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="008a1-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-571">0\.00</span></span>                   |   | <span data-ttu-id="008a1-572">1 000</span><span class="sxs-lookup"><span data-stu-id="008a1-572">1,000</span></span>                                           |                                                | <span data-ttu-id="008a1-573">\-1000</span><span class="sxs-lookup"><span data-stu-id="008a1-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="008a1-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-574">0\.00</span></span>                                   |
| <span data-ttu-id="008a1-575">5</span><span class="sxs-lookup"><span data-stu-id="008a1-575">5</span></span>          | <span data-ttu-id="008a1-576">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="008a1-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="008a1-577">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="008a1-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-578">1,008\.00</span></span>                                         | <span data-ttu-id="008a1-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="008a1-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-580">0\.00</span></span>                                   |
| <span data-ttu-id="008a1-581">6</span><span class="sxs-lookup"><span data-stu-id="008a1-581">6</span></span>          | <span data-ttu-id="008a1-582">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="008a1-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="008a1-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="008a1-584">22,794</span><span class="sxs-lookup"><span data-stu-id="008a1-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="008a1-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="008a1-585">22,793\.90</span></span>                              |
| <span data-ttu-id="008a1-586">7</span><span class="sxs-lookup"><span data-stu-id="008a1-586">7</span></span>          | <span data-ttu-id="008a1-587">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="008a1-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="008a1-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="008a1-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="008a1-589">\-22,794</span></span>                                       | <span data-ttu-id="008a1-590">1 000</span><span class="sxs-lookup"><span data-stu-id="008a1-590">1,000</span></span>                                          | <span data-ttu-id="008a1-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="008a1-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="008a1-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="008a1-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="008a1-593">8</span><span class="sxs-lookup"><span data-stu-id="008a1-593">8</span></span>          | <span data-ttu-id="008a1-594">Odsetki</span><span class="sxs-lookup"><span data-stu-id="008a1-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="008a1-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="008a1-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="008a1-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="008a1-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="008a1-597">94\.97</span></span>                                  |
| <span data-ttu-id="008a1-598">9</span><span class="sxs-lookup"><span data-stu-id="008a1-598">9</span></span>          | <span data-ttu-id="008a1-599">Kasa</span><span class="sxs-lookup"><span data-stu-id="008a1-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="008a1-600">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="008a1-601">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="008a1-602">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="008a1-603">10</span><span class="sxs-lookup"><span data-stu-id="008a1-603">10</span></span>         | <span data-ttu-id="008a1-604">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="008a1-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="008a1-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="008a1-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="008a1-606">949\.75</span></span>                                        | <span data-ttu-id="008a1-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="008a1-607">949\.75</span></span>                                 |
| <span data-ttu-id="008a1-608">11</span><span class="sxs-lookup"><span data-stu-id="008a1-608">11</span></span>         | <span data-ttu-id="008a1-609">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="008a1-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="008a1-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="008a1-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="008a1-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="008a1-611">\-949\.75</span></span>                                      | <span data-ttu-id="008a1-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="008a1-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
