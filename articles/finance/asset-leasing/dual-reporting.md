---
title: Podwójne raportowanie
description: W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.
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
ms.openlocfilehash: a7d9b3ea3d4f1d48b8a7326bd5a01d3119310c62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003188"
---
# <a name="dual-reporting"></a><span data-ttu-id="d63fa-103">Podwójne raportowanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d63fa-104">W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="d63fa-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="d63fa-105">Wymagane jest zapoznanie się z warstwami księgowania w Microsoft Dynamics 365 Finance, dzięki czemu przykład będzie łatwiejszy do zrozumienia.</span><span class="sxs-lookup"><span data-stu-id="d63fa-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="d63fa-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="d63fa-106">Example</span></span>

<span data-ttu-id="d63fa-107">W poniższym przykładzie przedstawiono wynajem podlegający ustawowej włoskiej sprawozdawczości przy użyciu metody kasowej i metody sprawozdawczości MSSF.</span><span class="sxs-lookup"><span data-stu-id="d63fa-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="d63fa-108">Firma musi utworzyć trzy księgi, aby uwzględnić zarówno włoskie wymagania ustawowe, jak i wymagania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="d63fa-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="d63fa-109">Jedna księga jest przeznaczona na MSSF 16, jedna na wymagania ustawowe i jedna do automatycznego wycofywania księgowań ustawowych.</span><span class="sxs-lookup"><span data-stu-id="d63fa-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="d63fa-110">Księgi są skonfigurowane zgodnie z poniższymi tabelami.</span><span class="sxs-lookup"><span data-stu-id="d63fa-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="d63fa-111">**Księga MSSF 16**</span><span class="sxs-lookup"><span data-stu-id="d63fa-111">**IFRS 16 book**</span></span>

<span data-ttu-id="d63fa-112">Księga MSSF 16 jest skonfigurowana w taki sposób, aby była zgodna ze standardem księgowania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="d63fa-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="d63fa-113">Wszystkie zapisy zaksięgowane w tej księdze będą księgowane w warstwie niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="d63fa-114">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="d63fa-114">Name</span></span>                                    | <span data-ttu-id="d63fa-115">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="d63fa-116">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-116">Book type</span></span>                               | <span data-ttu-id="d63fa-117">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="d63fa-117">IFRS 16</span></span>        |
| <span data-ttu-id="d63fa-118">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-118">Book description</span></span>                        | <span data-ttu-id="d63fa-119">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="d63fa-119">IFRS 16</span></span>        |
| <span data-ttu-id="d63fa-120">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-120">Posting Layer</span></span>                           | <span data-ttu-id="d63fa-121">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="d63fa-121">Custom layer 1</span></span> |
| <span data-ttu-id="d63fa-122">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-122">Lease Type</span></span>                              | <span data-ttu-id="d63fa-123">Finance</span><span class="sxs-lookup"><span data-stu-id="d63fa-123">Finance</span></span>        |
| <span data-ttu-id="d63fa-124">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-124">Accounting Framework</span></span>                    | <span data-ttu-id="d63fa-125">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="d63fa-125">IFRS 16</span></span>        |
| <span data-ttu-id="d63fa-126">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="d63fa-127">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-127">0.00</span></span>           |
| <span data-ttu-id="d63fa-128">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="d63fa-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="d63fa-129">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-129">0.00</span></span>           |
| <span data-ttu-id="d63fa-130">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="d63fa-130">Short-term threshold</span></span>                    | <span data-ttu-id="d63fa-131">12</span><span class="sxs-lookup"><span data-stu-id="d63fa-131">12</span></span>             |
| <span data-ttu-id="d63fa-132">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="d63fa-132">Low Value Threshold</span></span>                     | <span data-ttu-id="d63fa-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-133">5,000.00</span></span>       |
| <span data-ttu-id="d63fa-134">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="d63fa-134">Pay to Vendor</span></span>                           | <span data-ttu-id="d63fa-135">Nr</span><span class="sxs-lookup"><span data-stu-id="d63fa-135">No</span></span>             |

<span data-ttu-id="d63fa-136">**Księga ustawowa**</span><span class="sxs-lookup"><span data-stu-id="d63fa-136">**Statutory book**</span></span>

<span data-ttu-id="d63fa-137">Księga ustawowa to księga metody kasowej, w której firma będzie księgować wydatki z tytułu wynajmu jako kwotę gotówki płaconej w każdym miesiącu za wynajem.</span><span class="sxs-lookup"><span data-stu-id="d63fa-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="d63fa-138">Ta księga nie będzie generować składnika majątku z prawem do użytkowania ani zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="d63fa-139">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="d63fa-139">Name</span></span>                                    | <span data-ttu-id="d63fa-140">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="d63fa-141">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-141">Book type</span></span>                               | <span data-ttu-id="d63fa-142">Ustawowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-142">Statutory</span></span>   |
| <span data-ttu-id="d63fa-143">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-143">Book description</span></span>                        | <span data-ttu-id="d63fa-144">Lokalna GAAP</span><span class="sxs-lookup"><span data-stu-id="d63fa-144">Local GAAP</span></span>  |
| <span data-ttu-id="d63fa-145">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-145">Posting Layer</span></span>                           | <span data-ttu-id="d63fa-146">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-146">Current</span></span>     |
| <span data-ttu-id="d63fa-147">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-147">Lease Type</span></span>                              | <span data-ttu-id="d63fa-148">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="d63fa-148">Automatic</span></span>   |
| <span data-ttu-id="d63fa-149">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-149">Accounting Framework</span></span>                    | <span data-ttu-id="d63fa-150">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="d63fa-150">Cash basis</span></span>  |
| <span data-ttu-id="d63fa-151">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="d63fa-152">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-152">0.00</span></span>        |
| <span data-ttu-id="d63fa-153">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="d63fa-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="d63fa-154">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-154">0.00</span></span>        |
| <span data-ttu-id="d63fa-155">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="d63fa-155">Short-term threshold</span></span>                    | <span data-ttu-id="d63fa-156">0</span><span class="sxs-lookup"><span data-stu-id="d63fa-156">0</span></span>           |
| <span data-ttu-id="d63fa-157">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="d63fa-157">Low Value Threshold</span></span>                     | <span data-ttu-id="d63fa-158">0</span><span class="sxs-lookup"><span data-stu-id="d63fa-158">0</span></span>           |
| <span data-ttu-id="d63fa-159">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="d63fa-159">Pay to Vendor</span></span>                           | <span data-ttu-id="d63fa-160">Nr</span><span class="sxs-lookup"><span data-stu-id="d63fa-160">No</span></span>          |

<span data-ttu-id="d63fa-161">**Księga wycofania ustawowego**</span><span class="sxs-lookup"><span data-stu-id="d63fa-161">**Statutory reversal book**</span></span>

<span data-ttu-id="d63fa-162">Księga wycofania ustawowego jest konfigurowana w taki sam sposób, jak księga ustawowa.</span><span class="sxs-lookup"><span data-stu-id="d63fa-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="d63fa-163">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="d63fa-163">Name</span></span>                                    | <span data-ttu-id="d63fa-164">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="d63fa-165">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-165">Book type</span></span>                               | <span data-ttu-id="d63fa-166">Ustawowe — wycofanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="d63fa-167">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="d63fa-167">Book description</span></span>                        | <span data-ttu-id="d63fa-168">Księga do cofania księgi ustawowej</span><span class="sxs-lookup"><span data-stu-id="d63fa-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="d63fa-169">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-169">Posting Layer</span></span>                           | <span data-ttu-id="d63fa-170">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="d63fa-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="d63fa-171">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-171">Lease Type</span></span>                              | <span data-ttu-id="d63fa-172">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="d63fa-172">Automatic</span></span>                      |
| <span data-ttu-id="d63fa-173">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="d63fa-173">Accounting Framework</span></span>                    | <span data-ttu-id="d63fa-174">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="d63fa-174">Cash basis</span></span>                     |
| <span data-ttu-id="d63fa-175">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="d63fa-176">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-176">0.00</span></span>                           |
| <span data-ttu-id="d63fa-177">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="d63fa-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="d63fa-178">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-178">0.00</span></span>                           |
| <span data-ttu-id="d63fa-179">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="d63fa-179">Short-term threshold</span></span>                    | <span data-ttu-id="d63fa-180">0</span><span class="sxs-lookup"><span data-stu-id="d63fa-180">0</span></span>                              |
| <span data-ttu-id="d63fa-181">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="d63fa-181">Low Value Threshold</span></span>                     | <span data-ttu-id="d63fa-182">0</span><span class="sxs-lookup"><span data-stu-id="d63fa-182">0</span></span>                              |
| <span data-ttu-id="d63fa-183">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="d63fa-183">Pay to Vendor</span></span>                           | <span data-ttu-id="d63fa-184">Nr</span><span class="sxs-lookup"><span data-stu-id="d63fa-184">No</span></span>                             |

<span data-ttu-id="d63fa-185">W tym przykładzie utworzono wynajem, który ma następujące ustawienia na kartach **Ogólne** i **Wiersze harmonogramu płatności**.</span><span class="sxs-lookup"><span data-stu-id="d63fa-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="d63fa-186">**Karta Ogólne**</span><span class="sxs-lookup"><span data-stu-id="d63fa-186">**General tab**</span></span>

| <span data-ttu-id="d63fa-187">Pole</span><span class="sxs-lookup"><span data-stu-id="d63fa-187">Field</span></span>                      | <span data-ttu-id="d63fa-188">Wartość</span><span class="sxs-lookup"><span data-stu-id="d63fa-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="d63fa-189">Krańcowa stopa procentowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-189">Incremental borrowing rate</span></span> | <span data-ttu-id="d63fa-190">5%</span><span class="sxs-lookup"><span data-stu-id="d63fa-190">5%</span></span>               |
| <span data-ttu-id="d63fa-191">Data rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="d63fa-191">Commencement date</span></span>          | <span data-ttu-id="d63fa-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="d63fa-192">1/1/2020</span></span>         |
| <span data-ttu-id="d63fa-193">Grupa wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-193">Lease group</span></span>                | <span data-ttu-id="d63fa-194">Budynki</span><span class="sxs-lookup"><span data-stu-id="d63fa-194">Buildings</span></span>        |
| <span data-ttu-id="d63fa-195">Dostawca</span><span class="sxs-lookup"><span data-stu-id="d63fa-195">Vendor</span></span>                     | <span data-ttu-id="d63fa-196">1001</span><span class="sxs-lookup"><span data-stu-id="d63fa-196">1001</span></span>             |
| <span data-ttu-id="d63fa-197">Wartość godziwa składnika majątku</span><span class="sxs-lookup"><span data-stu-id="d63fa-197">Fair value of the asset</span></span>    | <span data-ttu-id="d63fa-198">245,000</span><span class="sxs-lookup"><span data-stu-id="d63fa-198">245,000</span></span>          |
| <span data-ttu-id="d63fa-199">Okres użyteczności składnika majątku</span><span class="sxs-lookup"><span data-stu-id="d63fa-199">Asset useful life</span></span>          | <span data-ttu-id="d63fa-200">120</span><span class="sxs-lookup"><span data-stu-id="d63fa-200">120</span></span>              |
| <span data-ttu-id="d63fa-201">Typ annuity</span><span class="sxs-lookup"><span data-stu-id="d63fa-201">Annuity type</span></span>               | <span data-ttu-id="d63fa-202">Zwykła annuita</span><span class="sxs-lookup"><span data-stu-id="d63fa-202">Ordinary annuity</span></span> |
| <span data-ttu-id="d63fa-203">Interwał łączenia</span><span class="sxs-lookup"><span data-stu-id="d63fa-203">Compounding interval</span></span>       | <span data-ttu-id="d63fa-204">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="d63fa-204">Monthly</span></span>          |

<span data-ttu-id="d63fa-205">**Karta Wiersze harmonogramu płatności**</span><span class="sxs-lookup"><span data-stu-id="d63fa-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="d63fa-206">Pole</span><span class="sxs-lookup"><span data-stu-id="d63fa-206">Field</span></span>             | <span data-ttu-id="d63fa-207">Wartość</span><span class="sxs-lookup"><span data-stu-id="d63fa-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="d63fa-208">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="d63fa-208">Start date</span></span>        | <span data-ttu-id="d63fa-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="d63fa-209">1/1/2020</span></span>   |
| <span data-ttu-id="d63fa-210">Zakres czasowy</span><span class="sxs-lookup"><span data-stu-id="d63fa-210">Period interval</span></span>   | <span data-ttu-id="d63fa-211">Miesiące</span><span class="sxs-lookup"><span data-stu-id="d63fa-211">Months</span></span>     |
| <span data-ttu-id="d63fa-212">Okresy</span><span class="sxs-lookup"><span data-stu-id="d63fa-212">Periods</span></span>           | <span data-ttu-id="d63fa-213">24</span><span class="sxs-lookup"><span data-stu-id="d63fa-213">24</span></span>         |
| <span data-ttu-id="d63fa-214">Data końcowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-214">End date</span></span>          | <span data-ttu-id="d63fa-215">12/31/2020</span><span class="sxs-lookup"><span data-stu-id="d63fa-215">12/31/2020</span></span> |
| <span data-ttu-id="d63fa-216">Częstość płatności</span><span class="sxs-lookup"><span data-stu-id="d63fa-216">Payment frequency</span></span> | <span data-ttu-id="d63fa-217">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="d63fa-217">Monthly</span></span>    |
| <span data-ttu-id="d63fa-218">Kwota płatności</span><span class="sxs-lookup"><span data-stu-id="d63fa-218">Payment amount</span></span>    | <span data-ttu-id="d63fa-219">1 000</span><span class="sxs-lookup"><span data-stu-id="d63fa-219">1,000</span></span>      |

<span data-ttu-id="d63fa-220">Aby ten wynajem był rozliczany w dwóch strukturach, należy skorzystać z bieżącej warstwy księgowania i niestandardowej warstwy księgowania.</span><span class="sxs-lookup"><span data-stu-id="d63fa-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="d63fa-221">W poniższej tabeli przedstawiono przykład każdego wpisu w arkuszu wymaganego do rzetelnego reprezentowania finansów w poszczególnych standardach sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="d63fa-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="d63fa-222">Szczegółowy opis każdego wpisu w arkuszu za pierwszy miesiąc wynajmu znajduje się dalej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="d63fa-223">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="d63fa-224">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="d63fa-225">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="d63fa-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="d63fa-226">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="d63fa-226">Current layer total</span></span></th>
<th><span data-ttu-id="d63fa-227">Księga wycofania (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="d63fa-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="d63fa-228">Księga MSSF 16 (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="d63fa-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="d63fa-229">Suma Bieżąca warstwa + Niestandardowa warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d63fa-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="d63fa-230">JE-100</span></span></th>
<th><span data-ttu-id="d63fa-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="d63fa-231">JE-110</span></span></th>
<th><span data-ttu-id="d63fa-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="d63fa-232">JE-120</span></span></th>
<th><span data-ttu-id="d63fa-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="d63fa-233">JE-130</span></span></th>
<th><span data-ttu-id="d63fa-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="d63fa-234">JE-140</span></span></th>
<th><span data-ttu-id="d63fa-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="d63fa-235">JE-150</span></span></th>
<th><span data-ttu-id="d63fa-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="d63fa-236">JE-160</span></span></th>
<th><span data-ttu-id="d63fa-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="d63fa-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d63fa-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d63fa-246">1</span><span class="sxs-lookup"><span data-stu-id="d63fa-246">1</span></span></td>
<td><span data-ttu-id="d63fa-247">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-247">Lease expense</span></span></td>
<td><span data-ttu-id="d63fa-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-249">1,000.00</span></span></td>
<td><span data-ttu-id="d63fa-250">-1000,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-251">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-252">2</span><span class="sxs-lookup"><span data-stu-id="d63fa-252">2</span></span></td>
<td><span data-ttu-id="d63fa-253">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-254">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-255">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-256">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-257">3</span><span class="sxs-lookup"><span data-stu-id="d63fa-257">3</span></span></td>
<td><span data-ttu-id="d63fa-258">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="d63fa-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-259">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-260">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-261">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-262">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-262">4</span></span></td>
<td><span data-ttu-id="d63fa-263">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-263">Clearing account</span></span></td>
<td><span data-ttu-id="d63fa-264">-1000,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-264">-1,000.00</span></span></td>
<td><span data-ttu-id="d63fa-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-266">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-266">0.00</span></span></td>
<td><span data-ttu-id="d63fa-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-268">-1000,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-269">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-270">5</span><span class="sxs-lookup"><span data-stu-id="d63fa-270">5</span></span></td>
<td><span data-ttu-id="d63fa-271">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="d63fa-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-272">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-272">-1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-273">1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-274">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-275">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-276">6</span><span class="sxs-lookup"><span data-stu-id="d63fa-276">6</span></span></td>
<td><span data-ttu-id="d63fa-277">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="d63fa-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-278">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="d63fa-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-281">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-281">7</span></span></td>
<td><span data-ttu-id="d63fa-282">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-283">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-284">-22,794.00</span></span></td>
<td><span data-ttu-id="d63fa-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-285">1,000.00</span></span></td>
<td><span data-ttu-id="d63fa-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="d63fa-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="d63fa-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-288">8</span><span class="sxs-lookup"><span data-stu-id="d63fa-288">8</span></span></td>
<td><span data-ttu-id="d63fa-289">Odsetki</span><span class="sxs-lookup"><span data-stu-id="d63fa-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-290">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-291">94.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-292">94.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-293">9</span><span class="sxs-lookup"><span data-stu-id="d63fa-293">9</span></span></td>
<td><span data-ttu-id="d63fa-294">Kasa</span><span class="sxs-lookup"><span data-stu-id="d63fa-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-295">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-295">-1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-296">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-297">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-298">10</span><span class="sxs-lookup"><span data-stu-id="d63fa-298">10</span></span></td>
<td><span data-ttu-id="d63fa-299">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d63fa-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-300">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-301">949.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-301">949.75</span></span></td>
<td><span data-ttu-id="d63fa-302">949.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-303">11</span><span class="sxs-lookup"><span data-stu-id="d63fa-303">11</span></span></td>
<td><span data-ttu-id="d63fa-304">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="d63fa-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-305">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="d63fa-306">-949.75</span></span></td>
<td><span data-ttu-id="d63fa-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="d63fa-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d63fa-308">Jak widać w powyższych tabelach, wymagane są trzy księgi do raportowania według sprawozdawczości ustawowej i MSSF.</span><span class="sxs-lookup"><span data-stu-id="d63fa-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="d63fa-309">W księdze ustawowej jest rejestrowana opłata z tytułu wynajmu zgodnie z regułami księgowania w metodzie kasowej w bieżącej warstwie.</span><span class="sxs-lookup"><span data-stu-id="d63fa-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="d63fa-310">Księga wycofania ustawowego wycofuje ustawowe wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="d63fa-311">Księga MSSF 16 tworzy wpisy w arkuszu wymagane na mocy MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="d63fa-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="d63fa-312">Wynajem musi zostać wprowadzony tylko raz.</span><span class="sxs-lookup"><span data-stu-id="d63fa-312">You must enter a lease only one time.</span></span> <span data-ttu-id="d63fa-313">Następnie można otworzyć stronę **Księgi** w celu wyświetlenia wszystkich ksiąg skojarzonych z wynajmem.</span><span class="sxs-lookup"><span data-stu-id="d63fa-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="d63fa-314">Po utworzeniu ksiąg wszystkie trzy z nich muszą być skojarzone z tym samym rekordem wynajmu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="d63fa-315">Pierwszy wpis w arkuszu rejestruje wydatek z tytułu wynajmu w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="d63fa-316">Płatności można tworzyć w ramach partii lub wybierając harmonogram płatności w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="d63fa-317">W tym przykładzie dla księgi ustawowej jest tworzony następujący wpis w arkuszu z harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="d63fa-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="d63fa-318">Opłata z tytułu wynajmu — 1/31/2020 — JE 100</span><span class="sxs-lookup"><span data-stu-id="d63fa-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="d63fa-319">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-319">Account type</span></span> | <span data-ttu-id="d63fa-320">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-320">Account number</span></span> | <span data-ttu-id="d63fa-321">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-321">Layer</span></span>   | <span data-ttu-id="d63fa-322">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-322">Account description</span></span> | <span data-ttu-id="d63fa-323">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-323">Debit</span></span>    | <span data-ttu-id="d63fa-324">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="d63fa-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-325">Ledger</span></span>       | <span data-ttu-id="d63fa-326">1</span><span class="sxs-lookup"><span data-stu-id="d63fa-326">1</span></span>              | <span data-ttu-id="d63fa-327">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-327">Current</span></span> | <span data-ttu-id="d63fa-328">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-328">Lease expense</span></span>       | <span data-ttu-id="d63fa-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-329">1,000.00</span></span> |          |
| <span data-ttu-id="d63fa-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-330">Ledger</span></span>       | <span data-ttu-id="d63fa-331">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-331">4</span></span>              | <span data-ttu-id="d63fa-332">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-332">Current</span></span> | <span data-ttu-id="d63fa-333">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-333">Clearing account</span></span>    |          | <span data-ttu-id="d63fa-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-334">1,000.00</span></span> |

<span data-ttu-id="d63fa-335">Pracownik ds. rozrachunków z dostawcami korzysta ze standardowych funkcji systemu Dynamics 365, aby utworzyć fakturę do zapłacenia za wynajem poza wynajmem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="d63fa-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="d63fa-336">Jednak zamiast wybierania **Wydatek z tytułu wynajmu** jako konta debetowego pracownik ds. rozrachunków z dostawcami wybiera konto rozliczeniowe w celu wygenerowania poniższego wpisu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="d63fa-337">Proces AP — 1/31/2020 — JE 110</span><span class="sxs-lookup"><span data-stu-id="d63fa-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="d63fa-338">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-338">Account type</span></span> | <span data-ttu-id="d63fa-339">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-339">Account number</span></span> | <span data-ttu-id="d63fa-340">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-340">Layer</span></span>   | <span data-ttu-id="d63fa-341">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-341">Account description</span></span> | <span data-ttu-id="d63fa-342">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-342">Debit</span></span>    | <span data-ttu-id="d63fa-343">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="d63fa-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-344">Ledger</span></span>       | <span data-ttu-id="d63fa-345">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-345">4</span></span>              | <span data-ttu-id="d63fa-346">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-346">Current</span></span> | <span data-ttu-id="d63fa-347">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-347">Clearing account</span></span>    | <span data-ttu-id="d63fa-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-348">1,000.00</span></span> |          |
| <span data-ttu-id="d63fa-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-349">Ledger</span></span>       | <span data-ttu-id="d63fa-350">2</span><span class="sxs-lookup"><span data-stu-id="d63fa-350">2</span></span>              | <span data-ttu-id="d63fa-351">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-351">Current</span></span> | <span data-ttu-id="d63fa-352">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-352">Bank fee</span></span>            | <span data-ttu-id="d63fa-353">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-353">3.00</span></span>     |          |
| <span data-ttu-id="d63fa-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-354">Ledger</span></span>       | <span data-ttu-id="d63fa-355">3</span><span class="sxs-lookup"><span data-stu-id="d63fa-355">3</span></span>              | <span data-ttu-id="d63fa-356">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-356">Current</span></span> | <span data-ttu-id="d63fa-357">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="d63fa-357">VAT expense</span></span>         | <span data-ttu-id="d63fa-358">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-358">5.00</span></span>     |          |
| <span data-ttu-id="d63fa-359">Dostawca</span><span class="sxs-lookup"><span data-stu-id="d63fa-359">Vendor</span></span>       | <span data-ttu-id="d63fa-360">5</span><span class="sxs-lookup"><span data-stu-id="d63fa-360">5</span></span>              | <span data-ttu-id="d63fa-361">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-361">Current</span></span> | <span data-ttu-id="d63fa-362">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="d63fa-362">Accounts payable</span></span>    |          | <span data-ttu-id="d63fa-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-363">1,008.00</span></span> |

<span data-ttu-id="d63fa-364">Gdy dostawcy jest udzielana instrukcja, należy postępować zgodnie z regularnym procesem płatności.</span><span class="sxs-lookup"><span data-stu-id="d63fa-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="d63fa-365">Podczas tego procesu jest generowany następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="d63fa-366">Płatność gotówkowa — 1/31/2020 — JE 120</span><span class="sxs-lookup"><span data-stu-id="d63fa-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="d63fa-367">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-367">Account type</span></span> | <span data-ttu-id="d63fa-368">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-368">Account number</span></span> | <span data-ttu-id="d63fa-369">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-369">Layer</span></span>   | <span data-ttu-id="d63fa-370">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-370">Account description</span></span> | <span data-ttu-id="d63fa-371">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-371">Debit</span></span>    | <span data-ttu-id="d63fa-372">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="d63fa-373">Dostawca</span><span class="sxs-lookup"><span data-stu-id="d63fa-373">Vendor</span></span>       | <span data-ttu-id="d63fa-374">5</span><span class="sxs-lookup"><span data-stu-id="d63fa-374">5</span></span>              | <span data-ttu-id="d63fa-375">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-375">Current</span></span> | <span data-ttu-id="d63fa-376">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="d63fa-376">Accounts Payable</span></span>    | <span data-ttu-id="d63fa-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-377">1,008.00</span></span> |          |
| <span data-ttu-id="d63fa-378">Bank</span><span class="sxs-lookup"><span data-stu-id="d63fa-378">Bank</span></span>         | <span data-ttu-id="d63fa-379">9</span><span class="sxs-lookup"><span data-stu-id="d63fa-379">9</span></span>              | <span data-ttu-id="d63fa-380">Bieżące</span><span class="sxs-lookup"><span data-stu-id="d63fa-380">Current</span></span> | <span data-ttu-id="d63fa-381">Kasa</span><span class="sxs-lookup"><span data-stu-id="d63fa-381">Cash</span></span>                |          | <span data-ttu-id="d63fa-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-382">1,008.00</span></span> |

<span data-ttu-id="d63fa-383">Na tym etapie wynajem jest w pełni zaksięgowany zgodnie z ustawowymi wymogami sprawozdawczości i można wygenerować bilans próbny, korzystając z bieżącej warstwy.</span><span class="sxs-lookup"><span data-stu-id="d63fa-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="d63fa-384">System zwraca bilans próbny o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="d63fa-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="d63fa-385">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="d63fa-386">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="d63fa-387">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="d63fa-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="d63fa-388">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="d63fa-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d63fa-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="d63fa-389">JE-100</span></span></th>
<th><span data-ttu-id="d63fa-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="d63fa-390">JE-110</span></span></th>
<th><span data-ttu-id="d63fa-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="d63fa-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d63fa-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="d63fa-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="d63fa-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d63fa-395">1</span><span class="sxs-lookup"><span data-stu-id="d63fa-395">1</span></span></td>
<td><span data-ttu-id="d63fa-396">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-396">Lease expense</span></span></td>
<td><span data-ttu-id="d63fa-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-399">2</span><span class="sxs-lookup"><span data-stu-id="d63fa-399">2</span></span></td>
<td><span data-ttu-id="d63fa-400">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-401">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-402">3.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-403">3</span><span class="sxs-lookup"><span data-stu-id="d63fa-403">3</span></span></td>
<td><span data-ttu-id="d63fa-404">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="d63fa-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-405">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-406">5.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-407">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-407">4</span></span></td>
<td><span data-ttu-id="d63fa-408">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-408">Clearing account</span></span></td>
<td><span data-ttu-id="d63fa-409">-1000,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-409">-1,000.00</span></span></td>
<td><span data-ttu-id="d63fa-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-411">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-412">5</span><span class="sxs-lookup"><span data-stu-id="d63fa-412">5</span></span></td>
<td><span data-ttu-id="d63fa-413">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="d63fa-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="d63fa-414">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-414">-1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-415">1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-416">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-417">6</span><span class="sxs-lookup"><span data-stu-id="d63fa-417">6</span></span></td>
<td><span data-ttu-id="d63fa-418">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="d63fa-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-419">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-420">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-420">7</span></span></td>
<td><span data-ttu-id="d63fa-421">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-422">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-423">8</span><span class="sxs-lookup"><span data-stu-id="d63fa-423">8</span></span></td>
<td><span data-ttu-id="d63fa-424">Odsetki</span><span class="sxs-lookup"><span data-stu-id="d63fa-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-425">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-426">9</span><span class="sxs-lookup"><span data-stu-id="d63fa-426">9</span></span></td>
<td><span data-ttu-id="d63fa-427">Kasa</span><span class="sxs-lookup"><span data-stu-id="d63fa-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-428">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-428">-1,008.00</span></span></td>
<td><span data-ttu-id="d63fa-429">-1008,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-430">10</span><span class="sxs-lookup"><span data-stu-id="d63fa-430">10</span></span></td>
<td><span data-ttu-id="d63fa-431">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d63fa-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-432">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d63fa-433">11</span><span class="sxs-lookup"><span data-stu-id="d63fa-433">11</span></span></td>
<td><span data-ttu-id="d63fa-434">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="d63fa-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="d63fa-435">0,00</span><span class="sxs-lookup"><span data-stu-id="d63fa-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d63fa-436">Jeśli ten sam bilans próbny ma zostać wykonany na wartościach MSSF 16, należy wycofać wpisy w arkuszu księgowania ustawowego i zaksięgować wpisy w arkuszu MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="d63fa-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="d63fa-437">Aby wycofać ustawowe wpisy w arkuszu, w tym przykładzie jest zawarta księga wycofania ustawowego, która ma taką samą konfigurację jak księga ustawowa, ale przeciwny profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="d63fa-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="d63fa-438">Na przykład księga ustawowa *obciąża* konto wydatku z tytułu wynajmu, a księga wycofania *uznaje* to konto.</span><span class="sxs-lookup"><span data-stu-id="d63fa-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="d63fa-439">Relacje te są łatwe do zdefiniowania na kontach księgowania wynajmu składników majątku na stronie **Parametry wynajmu składników majątku** (**Wynajem składników majątku \> Ustawienia \> Parametry wynajmu składników majątku**).</span><span class="sxs-lookup"><span data-stu-id="d63fa-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="d63fa-440">Jeśli ten sam proces, który był używany dla księgi ustawowej, zostanie użyty w księdze wycofania, tworzony jest następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="d63fa-441">Różnica polega na tym, że księga wycofania księguje zapisy wycofania z księgi ustawowej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="d63fa-442">Wpisy wycofania są również wprowadzane do niestandardowej warstwy.</span><span class="sxs-lookup"><span data-stu-id="d63fa-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="d63fa-443">Jeśli bilans próbny zostanie wykonany na bieżącej warstwie, wycofujące wpisy w arkuszu nie będą uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="d63fa-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="d63fa-444">Opłata z tytułu wynajmu — 1/31/2020 — JE 130</span><span class="sxs-lookup"><span data-stu-id="d63fa-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="d63fa-445">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-445">Account type</span></span> | <span data-ttu-id="d63fa-446">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-446">Account number</span></span> | <span data-ttu-id="d63fa-447">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-447">Layer</span></span>  | <span data-ttu-id="d63fa-448">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-448">Account description</span></span> | <span data-ttu-id="d63fa-449">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-449">Debit</span></span>    | <span data-ttu-id="d63fa-450">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="d63fa-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-451">Ledger</span></span>       | <span data-ttu-id="d63fa-452">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-452">4</span></span>              | <span data-ttu-id="d63fa-453">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-453">Custom</span></span> | <span data-ttu-id="d63fa-454">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-454">Clearing account</span></span>    | <span data-ttu-id="d63fa-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-455">1,000.00</span></span> |          |
| <span data-ttu-id="d63fa-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-456">Ledger</span></span>       | <span data-ttu-id="d63fa-457">1</span><span class="sxs-lookup"><span data-stu-id="d63fa-457">1</span></span>              | <span data-ttu-id="d63fa-458">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-458">Custom</span></span> | <span data-ttu-id="d63fa-459">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-459">Lease expense</span></span>       |          | <span data-ttu-id="d63fa-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-460">1,000.00</span></span> |

<span data-ttu-id="d63fa-461">Po usunięciu ustawowych wpisów w arkuszu księgujesz w księdze MSSF 16 wszystkie wpisy w dzienniku, których wymaga MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="d63fa-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="d63fa-462">Do tych wpisów należą początkowe uznanie składnika majątku z PDU i zobowiązanie, a także rekord odsetek i amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="d63fa-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="d63fa-463">Początkowe uznanie — 1/1/2020 — JE 140</span><span class="sxs-lookup"><span data-stu-id="d63fa-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="d63fa-464">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-464">Account type</span></span> | <span data-ttu-id="d63fa-465">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-465">Account number</span></span> | <span data-ttu-id="d63fa-466">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-466">Layer</span></span>  | <span data-ttu-id="d63fa-467">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-467">Account description</span></span>      | <span data-ttu-id="d63fa-468">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-468">Debit</span></span>     | <span data-ttu-id="d63fa-469">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="d63fa-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-470">Ledger</span></span>       | <span data-ttu-id="d63fa-471">6</span><span class="sxs-lookup"><span data-stu-id="d63fa-471">6</span></span>              | <span data-ttu-id="d63fa-472">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-472">Custom</span></span> | <span data-ttu-id="d63fa-473">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="d63fa-473">ROU Asset</span></span>                | <span data-ttu-id="d63fa-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="d63fa-474">22,793.90</span></span> |           |
| <span data-ttu-id="d63fa-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-475">Ledger</span></span>       | <span data-ttu-id="d63fa-476">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-476">7</span></span>              | <span data-ttu-id="d63fa-477">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-477">Custom</span></span> | <span data-ttu-id="d63fa-478">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-478">Finance lease obligation</span></span> |           | <span data-ttu-id="d63fa-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="d63fa-479">22,793.90</span></span> |

<span data-ttu-id="d63fa-480">Opłata z tytułu wynajmu jest księgowana jak inne opłaty z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="d63fa-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="d63fa-481">Przyczyną użycia konta rozliczeniowego jest zapewnienie, aby gotówka była uznawana tylko jeden raz.</span><span class="sxs-lookup"><span data-stu-id="d63fa-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="d63fa-482">Opłata z tytułu wynajmu — 1/31/2020 — JE 150</span><span class="sxs-lookup"><span data-stu-id="d63fa-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="d63fa-483">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-483">Account type</span></span> | <span data-ttu-id="d63fa-484">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-484">Account number</span></span> | <span data-ttu-id="d63fa-485">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-485">Layer</span></span>  | <span data-ttu-id="d63fa-486">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-486">Account description</span></span>      | <span data-ttu-id="d63fa-487">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-487">Debit</span></span>    | <span data-ttu-id="d63fa-488">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="d63fa-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-489">Ledger</span></span>       | <span data-ttu-id="d63fa-490">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-490">7</span></span>              | <span data-ttu-id="d63fa-491">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-491">Custom</span></span> | <span data-ttu-id="d63fa-492">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-492">Finance lease obligation</span></span> | <span data-ttu-id="d63fa-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-493">1,000.00</span></span> |          |
| <span data-ttu-id="d63fa-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-494">Ledger</span></span>       | <span data-ttu-id="d63fa-495">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-495">4</span></span>              | <span data-ttu-id="d63fa-496">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-496">Custom</span></span> | <span data-ttu-id="d63fa-497">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-497">Clearing account</span></span>         |          | <span data-ttu-id="d63fa-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-498">1,000.00</span></span> |

<span data-ttu-id="d63fa-499">Wpis w arkuszu kosztu odsetek jest generowany na podstawie harmonogramu amortyzacji zobowiązań.</span><span class="sxs-lookup"><span data-stu-id="d63fa-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="d63fa-500">Koszt odsetek — 1/31/2020 — JE 160</span><span class="sxs-lookup"><span data-stu-id="d63fa-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="d63fa-501">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-501">Account type</span></span> | <span data-ttu-id="d63fa-502">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-502">Account number</span></span> | <span data-ttu-id="d63fa-503">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-503">Layer</span></span>  | <span data-ttu-id="d63fa-504">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-504">Account description</span></span>      | <span data-ttu-id="d63fa-505">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-505">Debit</span></span> | <span data-ttu-id="d63fa-506">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="d63fa-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-507">Ledger</span></span>       | <span data-ttu-id="d63fa-508">8</span><span class="sxs-lookup"><span data-stu-id="d63fa-508">8</span></span>              | <span data-ttu-id="d63fa-509">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-509">Custom</span></span> | <span data-ttu-id="d63fa-510">Odsetki</span><span class="sxs-lookup"><span data-stu-id="d63fa-510">Interest expense</span></span>         | <span data-ttu-id="d63fa-511">94.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-511">94.97</span></span> |        |
| <span data-ttu-id="d63fa-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-512">Ledger</span></span>       | <span data-ttu-id="d63fa-513">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-513">7</span></span>              | <span data-ttu-id="d63fa-514">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-514">Custom</span></span> | <span data-ttu-id="d63fa-515">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-515">Finance lease obligation</span></span> |       | <span data-ttu-id="d63fa-516">94.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-516">94.97</span></span>  |

<span data-ttu-id="d63fa-517">Wpis w arkuszu kosztu amortyzacji jest generowany na podstawie harmonogramu amortyzacji składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="d63fa-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="d63fa-518">Wydatek amortyzacji — 1/31/2020 — JE 170</span><span class="sxs-lookup"><span data-stu-id="d63fa-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="d63fa-519">Typ konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-519">Account type</span></span> | <span data-ttu-id="d63fa-520">Numer konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-520">Account number</span></span> | <span data-ttu-id="d63fa-521">Warstwa</span><span class="sxs-lookup"><span data-stu-id="d63fa-521">Layer</span></span>  | <span data-ttu-id="d63fa-522">Opis konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-522">Account description</span></span>      | <span data-ttu-id="d63fa-523">Uznanie</span><span class="sxs-lookup"><span data-stu-id="d63fa-523">Debit</span></span>  | <span data-ttu-id="d63fa-524">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="d63fa-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-525">Ledger</span></span>       | <span data-ttu-id="d63fa-526">10</span><span class="sxs-lookup"><span data-stu-id="d63fa-526">10</span></span>             | <span data-ttu-id="d63fa-527">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-527">Custom</span></span> | <span data-ttu-id="d63fa-528">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d63fa-528">Depreciation expense</span></span>     | <span data-ttu-id="d63fa-529">949.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-529">949.75</span></span> |        |
| <span data-ttu-id="d63fa-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="d63fa-530">Ledger</span></span>       | <span data-ttu-id="d63fa-531">11</span><span class="sxs-lookup"><span data-stu-id="d63fa-531">11</span></span>             | <span data-ttu-id="d63fa-532">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-532">Custom</span></span> | <span data-ttu-id="d63fa-533">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="d63fa-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="d63fa-534">949.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-534">949.75</span></span> |

<span data-ttu-id="d63fa-535">Po utworzeniu i zaksięgowaniu wszystkich tych wpisów w arkuszu będą widoczne następujące wartości „niestandardowej warstwy 1”.</span><span class="sxs-lookup"><span data-stu-id="d63fa-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="d63fa-536">Należy zauważyć, że ostatnia kolumna zawiera opłatę bankową, koszt VAT oraz zmniejszenie ilości gotówki z poprzedniej warstwy, ale nie zawiera wpisów w arkuszu sprawozdawczości ustawowej.</span><span class="sxs-lookup"><span data-stu-id="d63fa-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="d63fa-537">Pozwala to na osiągnięcie prawdziwych możliwości podwójnego raportowania.</span><span class="sxs-lookup"><span data-stu-id="d63fa-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="d63fa-538">W tym momencie firma ma możliwość uruchomienia bilansu próbnego i połączenia bieżącej warstwy z niestandardową warstwą w celu utworzenia bilansu próbnego według MSSF.</span><span class="sxs-lookup"><span data-stu-id="d63fa-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="d63fa-539">Nr konta</span><span class="sxs-lookup"><span data-stu-id="d63fa-539">Account No</span></span> | <span data-ttu-id="d63fa-540">opis</span><span class="sxs-lookup"><span data-stu-id="d63fa-540">Description</span></span>              | <span data-ttu-id="d63fa-541">Księga ustawowa\-bieżąca warstwa\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-542">Księga ustawowa\-bieżąca warstwa\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-543">Księga ustawowa\-bieżąca warstwa\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-544">Bieżąca warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="d63fa-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="d63fa-545">Księga wycofania\-niestandardowa warstwa\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-546">Księga MSSF 16\-niestandardowa warstwa\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-547">Księga MSSF 16\-niestandardowa warstwa\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-548">Księga MSSF 16\-niestandardowa warstwa\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-549">Księga MSSF 16\-niestandardowa warstwa\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="d63fa-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="d63fa-550">Bieżąca warstwa \+ niestandardowa warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="d63fa-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="d63fa-551">1</span><span class="sxs-lookup"><span data-stu-id="d63fa-551">1</span></span>          | <span data-ttu-id="d63fa-552">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="d63fa-552">Lease expense</span></span>            | <span data-ttu-id="d63fa-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="d63fa-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-554">1,000\.00</span></span>               |   | <span data-ttu-id="d63fa-555">\-1000</span><span class="sxs-lookup"><span data-stu-id="d63fa-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="d63fa-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-556">0\.00</span></span>                                   |
| <span data-ttu-id="d63fa-557">2</span><span class="sxs-lookup"><span data-stu-id="d63fa-557">2</span></span>          | <span data-ttu-id="d63fa-558">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="d63fa-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="d63fa-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="d63fa-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="d63fa-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-561">3\.00</span></span>                                   |
| <span data-ttu-id="d63fa-562">3</span><span class="sxs-lookup"><span data-stu-id="d63fa-562">3</span></span>          | <span data-ttu-id="d63fa-563">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="d63fa-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="d63fa-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="d63fa-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="d63fa-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-566">5\.00</span></span>                                   |
| <span data-ttu-id="d63fa-567">4</span><span class="sxs-lookup"><span data-stu-id="d63fa-567">4</span></span>          | <span data-ttu-id="d63fa-568">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="d63fa-568">Clearing account</span></span>         | <span data-ttu-id="d63fa-569">\-1000\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="d63fa-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="d63fa-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-571">0\.00</span></span>                   |   | <span data-ttu-id="d63fa-572">1 000</span><span class="sxs-lookup"><span data-stu-id="d63fa-572">1,000</span></span>                                           |                                                | <span data-ttu-id="d63fa-573">\-1000</span><span class="sxs-lookup"><span data-stu-id="d63fa-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="d63fa-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-574">0\.00</span></span>                                   |
| <span data-ttu-id="d63fa-575">5</span><span class="sxs-lookup"><span data-stu-id="d63fa-575">5</span></span>          | <span data-ttu-id="d63fa-576">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="d63fa-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="d63fa-577">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="d63fa-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-578">1,008\.00</span></span>                                         | <span data-ttu-id="d63fa-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="d63fa-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-580">0\.00</span></span>                                   |
| <span data-ttu-id="d63fa-581">6</span><span class="sxs-lookup"><span data-stu-id="d63fa-581">6</span></span>          | <span data-ttu-id="d63fa-582">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="d63fa-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="d63fa-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="d63fa-584">22,794</span><span class="sxs-lookup"><span data-stu-id="d63fa-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="d63fa-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="d63fa-585">22,793\.90</span></span>                              |
| <span data-ttu-id="d63fa-586">7</span><span class="sxs-lookup"><span data-stu-id="d63fa-586">7</span></span>          | <span data-ttu-id="d63fa-587">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="d63fa-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="d63fa-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="d63fa-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="d63fa-589">\-22,794</span></span>                                       | <span data-ttu-id="d63fa-590">1 000</span><span class="sxs-lookup"><span data-stu-id="d63fa-590">1,000</span></span>                                          | <span data-ttu-id="d63fa-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="d63fa-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="d63fa-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="d63fa-593">8</span><span class="sxs-lookup"><span data-stu-id="d63fa-593">8</span></span>          | <span data-ttu-id="d63fa-594">Odsetki</span><span class="sxs-lookup"><span data-stu-id="d63fa-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="d63fa-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="d63fa-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="d63fa-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="d63fa-597">94\.97</span></span>                                  |
| <span data-ttu-id="d63fa-598">9</span><span class="sxs-lookup"><span data-stu-id="d63fa-598">9</span></span>          | <span data-ttu-id="d63fa-599">Kasa</span><span class="sxs-lookup"><span data-stu-id="d63fa-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="d63fa-600">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="d63fa-601">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="d63fa-602">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="d63fa-603">10</span><span class="sxs-lookup"><span data-stu-id="d63fa-603">10</span></span>         | <span data-ttu-id="d63fa-604">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="d63fa-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="d63fa-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="d63fa-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-606">949\.75</span></span>                                        | <span data-ttu-id="d63fa-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-607">949\.75</span></span>                                 |
| <span data-ttu-id="d63fa-608">11</span><span class="sxs-lookup"><span data-stu-id="d63fa-608">11</span></span>         | <span data-ttu-id="d63fa-609">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="d63fa-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="d63fa-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="d63fa-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="d63fa-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-611">\-949\.75</span></span>                                      | <span data-ttu-id="d63fa-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="d63fa-612">\-949\.75</span></span>                               |


