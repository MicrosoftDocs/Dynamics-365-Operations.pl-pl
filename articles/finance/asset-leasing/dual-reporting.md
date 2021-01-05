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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446985"
---
# <a name="dual-reporting"></a><span data-ttu-id="b4e1c-103">Podwójne raportowanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4e1c-104">W tym temacie przedstawiono przykład, w jaki sposób można spełnić wymagania zarówno Międzynarodowych Standardów Sprawozdawczości Finansowej (MSSF), jak i ustawowe dotyczące sprawozdawczości wynajmu składników majątku.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="b4e1c-105">Wymagane jest zapoznanie się z warstwami księgowania w Microsoft Dynamics 365 Finance, dzięki czemu przykład będzie łatwiejszy do zrozumienia.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="b4e1c-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="b4e1c-106">Example</span></span>

<span data-ttu-id="b4e1c-107">W poniższym przykładzie przedstawiono wynajem podlegający ustawowej włoskiej sprawozdawczości przy użyciu metody kasowej i metody sprawozdawczości MSSF.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="b4e1c-108">Firma musi utworzyć trzy księgi, aby uwzględnić zarówno włoskie wymagania ustawowe, jak i wymagania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="b4e1c-109">Jedna księga jest przeznaczona na MSSF 16, jedna na wymagania ustawowe i jedna do automatycznego wycofywania księgowań ustawowych.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="b4e1c-110">Księgi są skonfigurowane zgodnie z poniższymi tabelami.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="b4e1c-111">**Księga MSSF 16**</span><span class="sxs-lookup"><span data-stu-id="b4e1c-111">**IFRS 16 book**</span></span>

<span data-ttu-id="b4e1c-112">Księga MSSF 16 jest skonfigurowana w taki sposób, aby była zgodna ze standardem księgowania MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="b4e1c-113">Wszystkie zapisy zaksięgowane w tej księdze będą księgowane w warstwie niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="b4e1c-114">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="b4e1c-114">Name</span></span>                                    | <span data-ttu-id="b4e1c-115">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="b4e1c-116">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-116">Book type</span></span>                               | <span data-ttu-id="b4e1c-117">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="b4e1c-117">IFRS 16</span></span>        |
| <span data-ttu-id="b4e1c-118">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-118">Book description</span></span>                        | <span data-ttu-id="b4e1c-119">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="b4e1c-119">IFRS 16</span></span>        |
| <span data-ttu-id="b4e1c-120">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-120">Posting Layer</span></span>                           | <span data-ttu-id="b4e1c-121">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-121">Custom layer 1</span></span> |
| <span data-ttu-id="b4e1c-122">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-122">Lease Type</span></span>                              | <span data-ttu-id="b4e1c-123">Finance</span><span class="sxs-lookup"><span data-stu-id="b4e1c-123">Finance</span></span>        |
| <span data-ttu-id="b4e1c-124">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-124">Accounting Framework</span></span>                    | <span data-ttu-id="b4e1c-125">MSSF 16</span><span class="sxs-lookup"><span data-stu-id="b4e1c-125">IFRS 16</span></span>        |
| <span data-ttu-id="b4e1c-126">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b4e1c-127">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-127">0.00</span></span>           |
| <span data-ttu-id="b4e1c-128">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b4e1c-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b4e1c-129">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-129">0.00</span></span>           |
| <span data-ttu-id="b4e1c-130">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-130">Short-term threshold</span></span>                    | <span data-ttu-id="b4e1c-131">12</span><span class="sxs-lookup"><span data-stu-id="b4e1c-131">12</span></span>             |
| <span data-ttu-id="b4e1c-132">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="b4e1c-132">Low Value Threshold</span></span>                     | <span data-ttu-id="b4e1c-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-133">5,000.00</span></span>       |
| <span data-ttu-id="b4e1c-134">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-134">Pay to Vendor</span></span>                           | <span data-ttu-id="b4e1c-135">Nr</span><span class="sxs-lookup"><span data-stu-id="b4e1c-135">No</span></span>             |

<span data-ttu-id="b4e1c-136">**Księga ustawowa**</span><span class="sxs-lookup"><span data-stu-id="b4e1c-136">**Statutory book**</span></span>

<span data-ttu-id="b4e1c-137">Księga ustawowa to księga metody kasowej, w której firma będzie księgować wydatki z tytułu wynajmu jako kwotę gotówki płaconej w każdym miesiącu za wynajem.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="b4e1c-138">Ta księga nie będzie generować składnika majątku z prawem do użytkowania ani zobowiązania z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="b4e1c-139">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="b4e1c-139">Name</span></span>                                    | <span data-ttu-id="b4e1c-140">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="b4e1c-141">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-141">Book type</span></span>                               | <span data-ttu-id="b4e1c-142">Ustawowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-142">Statutory</span></span>   |
| <span data-ttu-id="b4e1c-143">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-143">Book description</span></span>                        | <span data-ttu-id="b4e1c-144">Lokalna GAAP</span><span class="sxs-lookup"><span data-stu-id="b4e1c-144">Local GAAP</span></span>  |
| <span data-ttu-id="b4e1c-145">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-145">Posting Layer</span></span>                           | <span data-ttu-id="b4e1c-146">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-146">Current</span></span>     |
| <span data-ttu-id="b4e1c-147">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-147">Lease Type</span></span>                              | <span data-ttu-id="b4e1c-148">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="b4e1c-148">Automatic</span></span>   |
| <span data-ttu-id="b4e1c-149">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-149">Accounting Framework</span></span>                    | <span data-ttu-id="b4e1c-150">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-150">Cash basis</span></span>  |
| <span data-ttu-id="b4e1c-151">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b4e1c-152">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-152">0.00</span></span>        |
| <span data-ttu-id="b4e1c-153">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b4e1c-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b4e1c-154">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-154">0.00</span></span>        |
| <span data-ttu-id="b4e1c-155">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-155">Short-term threshold</span></span>                    | <span data-ttu-id="b4e1c-156">0</span><span class="sxs-lookup"><span data-stu-id="b4e1c-156">0</span></span>           |
| <span data-ttu-id="b4e1c-157">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="b4e1c-157">Low Value Threshold</span></span>                     | <span data-ttu-id="b4e1c-158">0</span><span class="sxs-lookup"><span data-stu-id="b4e1c-158">0</span></span>           |
| <span data-ttu-id="b4e1c-159">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-159">Pay to Vendor</span></span>                           | <span data-ttu-id="b4e1c-160">Nr</span><span class="sxs-lookup"><span data-stu-id="b4e1c-160">No</span></span>          |

<span data-ttu-id="b4e1c-161">**Księga wycofania ustawowego**</span><span class="sxs-lookup"><span data-stu-id="b4e1c-161">**Statutory reversal book**</span></span>

<span data-ttu-id="b4e1c-162">Księga wycofania ustawowego jest konfigurowana w taki sam sposób, jak księga ustawowa.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="b4e1c-163">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="b4e1c-163">Name</span></span>                                    | <span data-ttu-id="b4e1c-164">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="b4e1c-165">Typ księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-165">Book type</span></span>                               | <span data-ttu-id="b4e1c-166">Ustawowe — wycofanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="b4e1c-167">Opis księgi</span><span class="sxs-lookup"><span data-stu-id="b4e1c-167">Book description</span></span>                        | <span data-ttu-id="b4e1c-168">Księga do cofania księgi ustawowej</span><span class="sxs-lookup"><span data-stu-id="b4e1c-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="b4e1c-169">Warstwa księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-169">Posting Layer</span></span>                           | <span data-ttu-id="b4e1c-170">Warstwa niestandardowa 1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="b4e1c-171">Typ wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-171">Lease Type</span></span>                              | <span data-ttu-id="b4e1c-172">Automatyczna</span><span class="sxs-lookup"><span data-stu-id="b4e1c-172">Automatic</span></span>                      |
| <span data-ttu-id="b4e1c-173">Struktura księgowania</span><span class="sxs-lookup"><span data-stu-id="b4e1c-173">Accounting Framework</span></span>                    | <span data-ttu-id="b4e1c-174">Podstawa gotówki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-174">Cash basis</span></span>                     |
| <span data-ttu-id="b4e1c-175">Konfiguracja okresu / okresu użyteczności wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b4e1c-176">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-176">0.00</span></span>                           |
| <span data-ttu-id="b4e1c-177">Konfiguracja wartości obecnej / wartości godziwej składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b4e1c-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b4e1c-178">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-178">0.00</span></span>                           |
| <span data-ttu-id="b4e1c-179">Próg krótkiego terminu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-179">Short-term threshold</span></span>                    | <span data-ttu-id="b4e1c-180">0</span><span class="sxs-lookup"><span data-stu-id="b4e1c-180">0</span></span>                              |
| <span data-ttu-id="b4e1c-181">Próg niskiej wartości</span><span class="sxs-lookup"><span data-stu-id="b4e1c-181">Low Value Threshold</span></span>                     | <span data-ttu-id="b4e1c-182">0</span><span class="sxs-lookup"><span data-stu-id="b4e1c-182">0</span></span>                              |
| <span data-ttu-id="b4e1c-183">Płatność dla dostawcy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-183">Pay to Vendor</span></span>                           | <span data-ttu-id="b4e1c-184">Nr</span><span class="sxs-lookup"><span data-stu-id="b4e1c-184">No</span></span>                             |

<span data-ttu-id="b4e1c-185">W tym przykładzie utworzono wynajem, który ma następujące ustawienia na kartach **Ogólne** i **Wiersze harmonogramu płatności**.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="b4e1c-186">**Karta Ogólne**</span><span class="sxs-lookup"><span data-stu-id="b4e1c-186">**General tab**</span></span>

| <span data-ttu-id="b4e1c-187">Pole</span><span class="sxs-lookup"><span data-stu-id="b4e1c-187">Field</span></span>                      | <span data-ttu-id="b4e1c-188">Wartość</span><span class="sxs-lookup"><span data-stu-id="b4e1c-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="b4e1c-189">Krańcowa stopa procentowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-189">Incremental borrowing rate</span></span> | <span data-ttu-id="b4e1c-190">5%</span><span class="sxs-lookup"><span data-stu-id="b4e1c-190">5%</span></span>               |
| <span data-ttu-id="b4e1c-191">Data rozpoczęcia</span><span class="sxs-lookup"><span data-stu-id="b4e1c-191">Commencement date</span></span>          | <span data-ttu-id="b4e1c-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="b4e1c-192">1/1/2020</span></span>         |
| <span data-ttu-id="b4e1c-193">Grupa wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-193">Lease group</span></span>                | <span data-ttu-id="b4e1c-194">Budynki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-194">Buildings</span></span>        |
| <span data-ttu-id="b4e1c-195">Dostawca</span><span class="sxs-lookup"><span data-stu-id="b4e1c-195">Vendor</span></span>                     | <span data-ttu-id="b4e1c-196">1001</span><span class="sxs-lookup"><span data-stu-id="b4e1c-196">1001</span></span>             |
| <span data-ttu-id="b4e1c-197">Wartość godziwa składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b4e1c-197">Fair value of the asset</span></span>    | <span data-ttu-id="b4e1c-198">245,000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-198">245,000</span></span>          |
| <span data-ttu-id="b4e1c-199">Okres użyteczności składnika majątku</span><span class="sxs-lookup"><span data-stu-id="b4e1c-199">Asset useful life</span></span>          | <span data-ttu-id="b4e1c-200">120</span><span class="sxs-lookup"><span data-stu-id="b4e1c-200">120</span></span>              |
| <span data-ttu-id="b4e1c-201">Typ annuity</span><span class="sxs-lookup"><span data-stu-id="b4e1c-201">Annuity type</span></span>               | <span data-ttu-id="b4e1c-202">Zwykła annuita</span><span class="sxs-lookup"><span data-stu-id="b4e1c-202">Ordinary annuity</span></span> |
| <span data-ttu-id="b4e1c-203">Interwał łączenia</span><span class="sxs-lookup"><span data-stu-id="b4e1c-203">Compounding interval</span></span>       | <span data-ttu-id="b4e1c-204">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="b4e1c-204">Monthly</span></span>          |

<span data-ttu-id="b4e1c-205">**Karta Wiersze harmonogramu płatności**</span><span class="sxs-lookup"><span data-stu-id="b4e1c-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="b4e1c-206">Pole</span><span class="sxs-lookup"><span data-stu-id="b4e1c-206">Field</span></span>             | <span data-ttu-id="b4e1c-207">Wartość</span><span class="sxs-lookup"><span data-stu-id="b4e1c-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="b4e1c-208">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-208">Start date</span></span>        | <span data-ttu-id="b4e1c-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="b4e1c-209">1/1/2020</span></span>   |
| <span data-ttu-id="b4e1c-210">Zakres czasowy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-210">Period interval</span></span>   | <span data-ttu-id="b4e1c-211">Miesiące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-211">Months</span></span>     |
| <span data-ttu-id="b4e1c-212">Okresy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-212">Periods</span></span>           | <span data-ttu-id="b4e1c-213">24</span><span class="sxs-lookup"><span data-stu-id="b4e1c-213">24</span></span>         |
| <span data-ttu-id="b4e1c-214">Data końcowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-214">End date</span></span>          | <span data-ttu-id="b4e1c-215">12/31/2020</span><span class="sxs-lookup"><span data-stu-id="b4e1c-215">12/31/2020</span></span> |
| <span data-ttu-id="b4e1c-216">Częstość płatności</span><span class="sxs-lookup"><span data-stu-id="b4e1c-216">Payment frequency</span></span> | <span data-ttu-id="b4e1c-217">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="b4e1c-217">Monthly</span></span>    |
| <span data-ttu-id="b4e1c-218">Kwota płatności</span><span class="sxs-lookup"><span data-stu-id="b4e1c-218">Payment amount</span></span>    | <span data-ttu-id="b4e1c-219">1 000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-219">1,000</span></span>      |

<span data-ttu-id="b4e1c-220">Aby ten wynajem był rozliczany w dwóch strukturach, należy skorzystać z bieżącej warstwy księgowania i niestandardowej warstwy księgowania.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="b4e1c-221">W poniższej tabeli przedstawiono przykład każdego wpisu w arkuszu wymaganego do rzetelnego reprezentowania finansów w poszczególnych standardach sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="b4e1c-222">Szczegółowy opis każdego wpisu w arkuszu za pierwszy miesiąc wynajmu znajduje się dalej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="b4e1c-223">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="b4e1c-224">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="b4e1c-225">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b4e1c-226">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-226">Current layer total</span></span></th>
<th><span data-ttu-id="b4e1c-227">Księga wycofania (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="b4e1c-228">Księga MSSF 16 (niestandardowa warstwa)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b4e1c-229">Suma Bieżąca warstwa + Niestandardowa warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b4e1c-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="b4e1c-230">JE-100</span></span></th>
<th><span data-ttu-id="b4e1c-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="b4e1c-231">JE-110</span></span></th>
<th><span data-ttu-id="b4e1c-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="b4e1c-232">JE-120</span></span></th>
<th><span data-ttu-id="b4e1c-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="b4e1c-233">JE-130</span></span></th>
<th><span data-ttu-id="b4e1c-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="b4e1c-234">JE-140</span></span></th>
<th><span data-ttu-id="b4e1c-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="b4e1c-235">JE-150</span></span></th>
<th><span data-ttu-id="b4e1c-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="b4e1c-236">JE-160</span></span></th>
<th><span data-ttu-id="b4e1c-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="b4e1c-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b4e1c-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b4e1c-246">1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-246">1</span></span></td>
<td><span data-ttu-id="b4e1c-247">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-247">Lease expense</span></span></td>
<td><span data-ttu-id="b4e1c-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-249">1,000.00</span></span></td>
<td><span data-ttu-id="b4e1c-250">-1000,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-251">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-252">2</span><span class="sxs-lookup"><span data-stu-id="b4e1c-252">2</span></span></td>
<td><span data-ttu-id="b4e1c-253">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-254">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-255">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-256">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-257">3</span><span class="sxs-lookup"><span data-stu-id="b4e1c-257">3</span></span></td>
<td><span data-ttu-id="b4e1c-258">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="b4e1c-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-259">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-260">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-261">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-262">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-262">4</span></span></td>
<td><span data-ttu-id="b4e1c-263">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-263">Clearing account</span></span></td>
<td><span data-ttu-id="b4e1c-264">-1000,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-264">-1,000.00</span></span></td>
<td><span data-ttu-id="b4e1c-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-266">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-266">0.00</span></span></td>
<td><span data-ttu-id="b4e1c-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-268">-1000,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-269">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-270">5</span><span class="sxs-lookup"><span data-stu-id="b4e1c-270">5</span></span></td>
<td><span data-ttu-id="b4e1c-271">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b4e1c-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-272">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-272">-1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-273">1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-274">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-275">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-276">6</span><span class="sxs-lookup"><span data-stu-id="b4e1c-276">6</span></span></td>
<td><span data-ttu-id="b4e1c-277">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="b4e1c-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-278">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b4e1c-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-281">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-281">7</span></span></td>
<td><span data-ttu-id="b4e1c-282">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-283">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-284">-22,794.00</span></span></td>
<td><span data-ttu-id="b4e1c-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-285">1,000.00</span></span></td>
<td><span data-ttu-id="b4e1c-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="b4e1c-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-288">8</span><span class="sxs-lookup"><span data-stu-id="b4e1c-288">8</span></span></td>
<td><span data-ttu-id="b4e1c-289">Odsetki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-290">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-291">94.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-292">94.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-293">9</span><span class="sxs-lookup"><span data-stu-id="b4e1c-293">9</span></span></td>
<td><span data-ttu-id="b4e1c-294">Kasa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-295">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-295">-1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-296">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-297">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-298">10</span><span class="sxs-lookup"><span data-stu-id="b4e1c-298">10</span></span></td>
<td><span data-ttu-id="b4e1c-299">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="b4e1c-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-300">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-301">949.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-301">949.75</span></span></td>
<td><span data-ttu-id="b4e1c-302">949.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-303">11</span><span class="sxs-lookup"><span data-stu-id="b4e1c-303">11</span></span></td>
<td><span data-ttu-id="b4e1c-304">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-305">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-306">-949.75</span></span></td>
<td><span data-ttu-id="b4e1c-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b4e1c-308">Jak widać w powyższych tabelach, wymagane są trzy księgi do raportowania według sprawozdawczości ustawowej i MSSF.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="b4e1c-309">W księdze ustawowej jest rejestrowana opłata z tytułu wynajmu zgodnie z regułami księgowania w metodzie kasowej w bieżącej warstwie.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="b4e1c-310">Księga wycofania ustawowego wycofuje ustawowe wpisy w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="b4e1c-311">Księga MSSF 16 tworzy wpisy w arkuszu wymagane na mocy MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="b4e1c-312">Wynajem musi zostać wprowadzony tylko raz.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-312">You must enter a lease only one time.</span></span> <span data-ttu-id="b4e1c-313">Następnie można otworzyć stronę **Księgi** w celu wyświetlenia wszystkich ksiąg skojarzonych z wynajmem.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="b4e1c-314">Po utworzeniu ksiąg wszystkie trzy z nich muszą być skojarzone z tym samym rekordem wynajmu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="b4e1c-315">Pierwszy wpis w arkuszu rejestruje wydatek z tytułu wynajmu w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="b4e1c-316">Płatności można tworzyć w ramach partii lub wybierając harmonogram płatności w księdze ustawowej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="b4e1c-317">W tym przykładzie dla księgi ustawowej jest tworzony następujący wpis w arkuszu z harmonogramu płatności.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="b4e1c-318">Opłata z tytułu wynajmu — 1/31/2020 — JE 100</span><span class="sxs-lookup"><span data-stu-id="b4e1c-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="b4e1c-319">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-319">Account type</span></span> | <span data-ttu-id="b4e1c-320">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-320">Account number</span></span> | <span data-ttu-id="b4e1c-321">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-321">Layer</span></span>   | <span data-ttu-id="b4e1c-322">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-322">Account description</span></span> | <span data-ttu-id="b4e1c-323">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-323">Debit</span></span>    | <span data-ttu-id="b4e1c-324">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b4e1c-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-325">Ledger</span></span>       | <span data-ttu-id="b4e1c-326">1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-326">1</span></span>              | <span data-ttu-id="b4e1c-327">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-327">Current</span></span> | <span data-ttu-id="b4e1c-328">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-328">Lease expense</span></span>       | <span data-ttu-id="b4e1c-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-329">1,000.00</span></span> |          |
| <span data-ttu-id="b4e1c-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-330">Ledger</span></span>       | <span data-ttu-id="b4e1c-331">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-331">4</span></span>              | <span data-ttu-id="b4e1c-332">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-332">Current</span></span> | <span data-ttu-id="b4e1c-333">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-333">Clearing account</span></span>    |          | <span data-ttu-id="b4e1c-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-334">1,000.00</span></span> |

<span data-ttu-id="b4e1c-335">Pracownik ds. rozrachunków z dostawcami korzysta ze standardowych funkcji systemu Dynamics 365, aby utworzyć fakturę do zapłacenia za wynajem poza wynajmem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="b4e1c-336">Jednak zamiast wybierania **Wydatek z tytułu wynajmu** jako konta debetowego pracownik ds. rozrachunków z dostawcami wybiera konto rozliczeniowe w celu wygenerowania poniższego wpisu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="b4e1c-337">Proces AP — 1/31/2020 — JE 110</span><span class="sxs-lookup"><span data-stu-id="b4e1c-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="b4e1c-338">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-338">Account type</span></span> | <span data-ttu-id="b4e1c-339">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-339">Account number</span></span> | <span data-ttu-id="b4e1c-340">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-340">Layer</span></span>   | <span data-ttu-id="b4e1c-341">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-341">Account description</span></span> | <span data-ttu-id="b4e1c-342">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-342">Debit</span></span>    | <span data-ttu-id="b4e1c-343">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b4e1c-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-344">Ledger</span></span>       | <span data-ttu-id="b4e1c-345">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-345">4</span></span>              | <span data-ttu-id="b4e1c-346">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-346">Current</span></span> | <span data-ttu-id="b4e1c-347">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-347">Clearing account</span></span>    | <span data-ttu-id="b4e1c-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-348">1,000.00</span></span> |          |
| <span data-ttu-id="b4e1c-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-349">Ledger</span></span>       | <span data-ttu-id="b4e1c-350">2</span><span class="sxs-lookup"><span data-stu-id="b4e1c-350">2</span></span>              | <span data-ttu-id="b4e1c-351">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-351">Current</span></span> | <span data-ttu-id="b4e1c-352">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-352">Bank fee</span></span>            | <span data-ttu-id="b4e1c-353">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-353">3.00</span></span>     |          |
| <span data-ttu-id="b4e1c-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-354">Ledger</span></span>       | <span data-ttu-id="b4e1c-355">3</span><span class="sxs-lookup"><span data-stu-id="b4e1c-355">3</span></span>              | <span data-ttu-id="b4e1c-356">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-356">Current</span></span> | <span data-ttu-id="b4e1c-357">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="b4e1c-357">VAT expense</span></span>         | <span data-ttu-id="b4e1c-358">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-358">5.00</span></span>     |          |
| <span data-ttu-id="b4e1c-359">Dostawca</span><span class="sxs-lookup"><span data-stu-id="b4e1c-359">Vendor</span></span>       | <span data-ttu-id="b4e1c-360">5</span><span class="sxs-lookup"><span data-stu-id="b4e1c-360">5</span></span>              | <span data-ttu-id="b4e1c-361">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-361">Current</span></span> | <span data-ttu-id="b4e1c-362">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b4e1c-362">Accounts payable</span></span>    |          | <span data-ttu-id="b4e1c-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-363">1,008.00</span></span> |

<span data-ttu-id="b4e1c-364">Gdy dostawcy jest udzielana instrukcja, należy postępować zgodnie z regularnym procesem płatności.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="b4e1c-365">Podczas tego procesu jest generowany następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="b4e1c-366">Płatność gotówkowa — 1/31/2020 — JE 120</span><span class="sxs-lookup"><span data-stu-id="b4e1c-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="b4e1c-367">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-367">Account type</span></span> | <span data-ttu-id="b4e1c-368">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-368">Account number</span></span> | <span data-ttu-id="b4e1c-369">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-369">Layer</span></span>   | <span data-ttu-id="b4e1c-370">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-370">Account description</span></span> | <span data-ttu-id="b4e1c-371">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-371">Debit</span></span>    | <span data-ttu-id="b4e1c-372">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b4e1c-373">Dostawca</span><span class="sxs-lookup"><span data-stu-id="b4e1c-373">Vendor</span></span>       | <span data-ttu-id="b4e1c-374">5</span><span class="sxs-lookup"><span data-stu-id="b4e1c-374">5</span></span>              | <span data-ttu-id="b4e1c-375">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-375">Current</span></span> | <span data-ttu-id="b4e1c-376">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b4e1c-376">Accounts Payable</span></span>    | <span data-ttu-id="b4e1c-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-377">1,008.00</span></span> |          |
| <span data-ttu-id="b4e1c-378">Bank</span><span class="sxs-lookup"><span data-stu-id="b4e1c-378">Bank</span></span>         | <span data-ttu-id="b4e1c-379">9</span><span class="sxs-lookup"><span data-stu-id="b4e1c-379">9</span></span>              | <span data-ttu-id="b4e1c-380">Bieżące</span><span class="sxs-lookup"><span data-stu-id="b4e1c-380">Current</span></span> | <span data-ttu-id="b4e1c-381">Kasa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-381">Cash</span></span>                |          | <span data-ttu-id="b4e1c-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-382">1,008.00</span></span> |

<span data-ttu-id="b4e1c-383">Na tym etapie wynajem jest w pełni zaksięgowany zgodnie z ustawowymi wymogami sprawozdawczości i można wygenerować bilans próbny, korzystając z bieżącej warstwy.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="b4e1c-384">System zwraca bilans próbny o następujących wartościach:</span><span class="sxs-lookup"><span data-stu-id="b4e1c-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="b4e1c-385">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="b4e1c-386">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="b4e1c-387">Księga ustawowa (bieżąca warstwa)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b4e1c-388">Suma bieżącej warstwy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b4e1c-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="b4e1c-389">JE-100</span></span></th>
<th><span data-ttu-id="b4e1c-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="b4e1c-390">JE-110</span></span></th>
<th><span data-ttu-id="b4e1c-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="b4e1c-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b4e1c-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b4e1c-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b4e1c-395">1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-395">1</span></span></td>
<td><span data-ttu-id="b4e1c-396">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-396">Lease expense</span></span></td>
<td><span data-ttu-id="b4e1c-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-399">2</span><span class="sxs-lookup"><span data-stu-id="b4e1c-399">2</span></span></td>
<td><span data-ttu-id="b4e1c-400">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-401">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-402">3.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-403">3</span><span class="sxs-lookup"><span data-stu-id="b4e1c-403">3</span></span></td>
<td><span data-ttu-id="b4e1c-404">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="b4e1c-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-405">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-406">5.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-407">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-407">4</span></span></td>
<td><span data-ttu-id="b4e1c-408">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-408">Clearing account</span></span></td>
<td><span data-ttu-id="b4e1c-409">-1000,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-409">-1,000.00</span></span></td>
<td><span data-ttu-id="b4e1c-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-411">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-412">5</span><span class="sxs-lookup"><span data-stu-id="b4e1c-412">5</span></span></td>
<td><span data-ttu-id="b4e1c-413">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b4e1c-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="b4e1c-414">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-414">-1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-415">1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-416">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-417">6</span><span class="sxs-lookup"><span data-stu-id="b4e1c-417">6</span></span></td>
<td><span data-ttu-id="b4e1c-418">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="b4e1c-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-419">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-420">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-420">7</span></span></td>
<td><span data-ttu-id="b4e1c-421">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-422">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-423">8</span><span class="sxs-lookup"><span data-stu-id="b4e1c-423">8</span></span></td>
<td><span data-ttu-id="b4e1c-424">Odsetki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-425">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-426">9</span><span class="sxs-lookup"><span data-stu-id="b4e1c-426">9</span></span></td>
<td><span data-ttu-id="b4e1c-427">Kasa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-428">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-428">-1,008.00</span></span></td>
<td><span data-ttu-id="b4e1c-429">-1008,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-430">10</span><span class="sxs-lookup"><span data-stu-id="b4e1c-430">10</span></span></td>
<td><span data-ttu-id="b4e1c-431">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="b4e1c-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-432">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b4e1c-433">11</span><span class="sxs-lookup"><span data-stu-id="b4e1c-433">11</span></span></td>
<td><span data-ttu-id="b4e1c-434">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b4e1c-435">0,00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b4e1c-436">Jeśli ten sam bilans próbny ma zostać wykonany na wartościach MSSF 16, należy wycofać wpisy w arkuszu księgowania ustawowego i zaksięgować wpisy w arkuszu MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="b4e1c-437">Aby wycofać ustawowe wpisy w arkuszu, w tym przykładzie jest zawarta księga wycofania ustawowego, która ma taką samą konfigurację jak księga ustawowa, ale przeciwny profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="b4e1c-438">Na przykład księga ustawowa *obciąża* konto wydatku z tytułu wynajmu, a księga wycofania *uznaje* to konto.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="b4e1c-439">Relacje te są łatwe do zdefiniowania na kontach księgowania wynajmu składników majątku na stronie **Parametry wynajmu składników majątku** (**Wynajem składników majątku \> Ustawienia \> Parametry wynajmu składników majątku**).</span><span class="sxs-lookup"><span data-stu-id="b4e1c-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="b4e1c-440">Jeśli ten sam proces, który był używany dla księgi ustawowej, zostanie użyty w księdze wycofania, tworzony jest następujący wpis w arkuszu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="b4e1c-441">Różnica polega na tym, że księga wycofania księguje zapisy wycofania z księgi ustawowej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="b4e1c-442">Wpisy wycofania są również wprowadzane do niestandardowej warstwy.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="b4e1c-443">Jeśli bilans próbny zostanie wykonany na bieżącej warstwie, wycofujące wpisy w arkuszu nie będą uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="b4e1c-444">Opłata z tytułu wynajmu — 1/31/2020 — JE 130</span><span class="sxs-lookup"><span data-stu-id="b4e1c-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="b4e1c-445">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-445">Account type</span></span> | <span data-ttu-id="b4e1c-446">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-446">Account number</span></span> | <span data-ttu-id="b4e1c-447">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-447">Layer</span></span>  | <span data-ttu-id="b4e1c-448">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-448">Account description</span></span> | <span data-ttu-id="b4e1c-449">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-449">Debit</span></span>    | <span data-ttu-id="b4e1c-450">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="b4e1c-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-451">Ledger</span></span>       | <span data-ttu-id="b4e1c-452">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-452">4</span></span>              | <span data-ttu-id="b4e1c-453">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-453">Custom</span></span> | <span data-ttu-id="b4e1c-454">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-454">Clearing account</span></span>    | <span data-ttu-id="b4e1c-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-455">1,000.00</span></span> |          |
| <span data-ttu-id="b4e1c-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-456">Ledger</span></span>       | <span data-ttu-id="b4e1c-457">1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-457">1</span></span>              | <span data-ttu-id="b4e1c-458">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-458">Custom</span></span> | <span data-ttu-id="b4e1c-459">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-459">Lease expense</span></span>       |          | <span data-ttu-id="b4e1c-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-460">1,000.00</span></span> |

<span data-ttu-id="b4e1c-461">Po usunięciu ustawowych wpisów w arkuszu księgujesz w księdze MSSF 16 wszystkie wpisy w dzienniku, których wymaga MSSF 16.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="b4e1c-462">Do tych wpisów należą początkowe uznanie składnika majątku z PDU i zobowiązanie, a także rekord odsetek i amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="b4e1c-463">Początkowe uznanie — 1/1/2020 — JE 140</span><span class="sxs-lookup"><span data-stu-id="b4e1c-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="b4e1c-464">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-464">Account type</span></span> | <span data-ttu-id="b4e1c-465">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-465">Account number</span></span> | <span data-ttu-id="b4e1c-466">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-466">Layer</span></span>  | <span data-ttu-id="b4e1c-467">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-467">Account description</span></span>      | <span data-ttu-id="b4e1c-468">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-468">Debit</span></span>     | <span data-ttu-id="b4e1c-469">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="b4e1c-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-470">Ledger</span></span>       | <span data-ttu-id="b4e1c-471">6</span><span class="sxs-lookup"><span data-stu-id="b4e1c-471">6</span></span>              | <span data-ttu-id="b4e1c-472">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-472">Custom</span></span> | <span data-ttu-id="b4e1c-473">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="b4e1c-473">ROU Asset</span></span>                | <span data-ttu-id="b4e1c-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b4e1c-474">22,793.90</span></span> |           |
| <span data-ttu-id="b4e1c-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-475">Ledger</span></span>       | <span data-ttu-id="b4e1c-476">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-476">7</span></span>              | <span data-ttu-id="b4e1c-477">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-477">Custom</span></span> | <span data-ttu-id="b4e1c-478">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-478">Finance lease obligation</span></span> |           | <span data-ttu-id="b4e1c-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b4e1c-479">22,793.90</span></span> |

<span data-ttu-id="b4e1c-480">Opłata z tytułu wynajmu jest księgowana jak inne opłaty z tytułu wynajmu.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="b4e1c-481">Przyczyną użycia konta rozliczeniowego jest zapewnienie, aby gotówka była uznawana tylko jeden raz.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="b4e1c-482">Opłata z tytułu wynajmu — 1/31/2020 — JE 150</span><span class="sxs-lookup"><span data-stu-id="b4e1c-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="b4e1c-483">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-483">Account type</span></span> | <span data-ttu-id="b4e1c-484">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-484">Account number</span></span> | <span data-ttu-id="b4e1c-485">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-485">Layer</span></span>  | <span data-ttu-id="b4e1c-486">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-486">Account description</span></span>      | <span data-ttu-id="b4e1c-487">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-487">Debit</span></span>    | <span data-ttu-id="b4e1c-488">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="b4e1c-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-489">Ledger</span></span>       | <span data-ttu-id="b4e1c-490">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-490">7</span></span>              | <span data-ttu-id="b4e1c-491">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-491">Custom</span></span> | <span data-ttu-id="b4e1c-492">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-492">Finance lease obligation</span></span> | <span data-ttu-id="b4e1c-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-493">1,000.00</span></span> |          |
| <span data-ttu-id="b4e1c-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-494">Ledger</span></span>       | <span data-ttu-id="b4e1c-495">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-495">4</span></span>              | <span data-ttu-id="b4e1c-496">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-496">Custom</span></span> | <span data-ttu-id="b4e1c-497">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-497">Clearing account</span></span>         |          | <span data-ttu-id="b4e1c-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-498">1,000.00</span></span> |

<span data-ttu-id="b4e1c-499">Wpis w arkuszu kosztu odsetek jest generowany na podstawie harmonogramu amortyzacji zobowiązań.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="b4e1c-500">Koszt odsetek — 1/31/2020 — JE 160</span><span class="sxs-lookup"><span data-stu-id="b4e1c-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="b4e1c-501">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-501">Account type</span></span> | <span data-ttu-id="b4e1c-502">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-502">Account number</span></span> | <span data-ttu-id="b4e1c-503">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-503">Layer</span></span>  | <span data-ttu-id="b4e1c-504">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-504">Account description</span></span>      | <span data-ttu-id="b4e1c-505">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-505">Debit</span></span> | <span data-ttu-id="b4e1c-506">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="b4e1c-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-507">Ledger</span></span>       | <span data-ttu-id="b4e1c-508">8</span><span class="sxs-lookup"><span data-stu-id="b4e1c-508">8</span></span>              | <span data-ttu-id="b4e1c-509">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-509">Custom</span></span> | <span data-ttu-id="b4e1c-510">Odsetki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-510">Interest expense</span></span>         | <span data-ttu-id="b4e1c-511">94.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-511">94.97</span></span> |        |
| <span data-ttu-id="b4e1c-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-512">Ledger</span></span>       | <span data-ttu-id="b4e1c-513">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-513">7</span></span>              | <span data-ttu-id="b4e1c-514">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-514">Custom</span></span> | <span data-ttu-id="b4e1c-515">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-515">Finance lease obligation</span></span> |       | <span data-ttu-id="b4e1c-516">94.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-516">94.97</span></span>  |

<span data-ttu-id="b4e1c-517">Wpis w arkuszu kosztu amortyzacji jest generowany na podstawie harmonogramu amortyzacji składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="b4e1c-518">Wydatek amortyzacji — 1/31/2020 — JE 170</span><span class="sxs-lookup"><span data-stu-id="b4e1c-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="b4e1c-519">Typ konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-519">Account type</span></span> | <span data-ttu-id="b4e1c-520">Numer konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-520">Account number</span></span> | <span data-ttu-id="b4e1c-521">Warstwa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-521">Layer</span></span>  | <span data-ttu-id="b4e1c-522">Opis konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-522">Account description</span></span>      | <span data-ttu-id="b4e1c-523">Uznanie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-523">Debit</span></span>  | <span data-ttu-id="b4e1c-524">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="b4e1c-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-525">Ledger</span></span>       | <span data-ttu-id="b4e1c-526">10</span><span class="sxs-lookup"><span data-stu-id="b4e1c-526">10</span></span>             | <span data-ttu-id="b4e1c-527">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-527">Custom</span></span> | <span data-ttu-id="b4e1c-528">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="b4e1c-528">Depreciation expense</span></span>     | <span data-ttu-id="b4e1c-529">949.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-529">949.75</span></span> |        |
| <span data-ttu-id="b4e1c-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="b4e1c-530">Ledger</span></span>       | <span data-ttu-id="b4e1c-531">11</span><span class="sxs-lookup"><span data-stu-id="b4e1c-531">11</span></span>             | <span data-ttu-id="b4e1c-532">Niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-532">Custom</span></span> | <span data-ttu-id="b4e1c-533">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="b4e1c-534">949.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-534">949.75</span></span> |

<span data-ttu-id="b4e1c-535">Po utworzeniu i zaksięgowaniu wszystkich tych wpisów w arkuszu będą widoczne następujące wartości „niestandardowej warstwy 1”.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="b4e1c-536">Należy zauważyć, że ostatnia kolumna zawiera opłatę bankową, koszt VAT oraz zmniejszenie ilości gotówki z poprzedniej warstwy, ale nie zawiera wpisów w arkuszu sprawozdawczości ustawowej.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="b4e1c-537">Pozwala to na osiągnięcie prawdziwych możliwości podwójnego raportowania.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="b4e1c-538">W tym momencie firma ma możliwość uruchomienia bilansu próbnego i połączenia bieżącej warstwy z niestandardową warstwą w celu utworzenia bilansu próbnego według MSSF.</span><span class="sxs-lookup"><span data-stu-id="b4e1c-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="b4e1c-539">Nr konta</span><span class="sxs-lookup"><span data-stu-id="b4e1c-539">Account No</span></span> | <span data-ttu-id="b4e1c-540">opis</span><span class="sxs-lookup"><span data-stu-id="b4e1c-540">Description</span></span>              | <span data-ttu-id="b4e1c-541">Księga ustawowa\-bieżąca warstwa\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-542">Księga ustawowa\-bieżąca warstwa\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-543">Księga ustawowa\-bieżąca warstwa\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-544">Bieżąca warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="b4e1c-545">Księga wycofania\-niestandardowa warstwa\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-546">Księga MSSF 16\-niestandardowa warstwa\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-547">Księga MSSF 16\-niestandardowa warstwa\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-548">Księga MSSF 16\-niestandardowa warstwa\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-549">Księga MSSF 16\-niestandardowa warstwa\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b4e1c-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="b4e1c-550">Bieżąca warstwa \+ niestandardowa warstwa \- sumy</span><span class="sxs-lookup"><span data-stu-id="b4e1c-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="b4e1c-551">1</span><span class="sxs-lookup"><span data-stu-id="b4e1c-551">1</span></span>          | <span data-ttu-id="b4e1c-552">Wydatek z tytułu wynajmu</span><span class="sxs-lookup"><span data-stu-id="b4e1c-552">Lease expense</span></span>            | <span data-ttu-id="b4e1c-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="b4e1c-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-554">1,000\.00</span></span>               |   | <span data-ttu-id="b4e1c-555">\-1000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="b4e1c-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-556">0\.00</span></span>                                   |
| <span data-ttu-id="b4e1c-557">2</span><span class="sxs-lookup"><span data-stu-id="b4e1c-557">2</span></span>          | <span data-ttu-id="b4e1c-558">Opłata bankowa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="b4e1c-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="b4e1c-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b4e1c-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-561">3\.00</span></span>                                   |
| <span data-ttu-id="b4e1c-562">3</span><span class="sxs-lookup"><span data-stu-id="b4e1c-562">3</span></span>          | <span data-ttu-id="b4e1c-563">Wydatek VAT</span><span class="sxs-lookup"><span data-stu-id="b4e1c-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="b4e1c-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="b4e1c-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b4e1c-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-566">5\.00</span></span>                                   |
| <span data-ttu-id="b4e1c-567">4</span><span class="sxs-lookup"><span data-stu-id="b4e1c-567">4</span></span>          | <span data-ttu-id="b4e1c-568">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="b4e1c-568">Clearing account</span></span>         | <span data-ttu-id="b4e1c-569">\-1000\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="b4e1c-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="b4e1c-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-571">0\.00</span></span>                   |   | <span data-ttu-id="b4e1c-572">1 000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-572">1,000</span></span>                                           |                                                | <span data-ttu-id="b4e1c-573">\-1000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="b4e1c-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-574">0\.00</span></span>                                   |
| <span data-ttu-id="b4e1c-575">5</span><span class="sxs-lookup"><span data-stu-id="b4e1c-575">5</span></span>          | <span data-ttu-id="b4e1c-576">Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b4e1c-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="b4e1c-577">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="b4e1c-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-578">1,008\.00</span></span>                                         | <span data-ttu-id="b4e1c-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b4e1c-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-580">0\.00</span></span>                                   |
| <span data-ttu-id="b4e1c-581">6</span><span class="sxs-lookup"><span data-stu-id="b4e1c-581">6</span></span>          | <span data-ttu-id="b4e1c-582">Składnik majątku z PDU</span><span class="sxs-lookup"><span data-stu-id="b4e1c-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="b4e1c-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="b4e1c-584">22,794</span><span class="sxs-lookup"><span data-stu-id="b4e1c-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="b4e1c-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="b4e1c-585">22,793\.90</span></span>                              |
| <span data-ttu-id="b4e1c-586">7</span><span class="sxs-lookup"><span data-stu-id="b4e1c-586">7</span></span>          | <span data-ttu-id="b4e1c-587">Zobowiązanie z tytułu leasingu finansowego</span><span class="sxs-lookup"><span data-stu-id="b4e1c-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="b4e1c-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="b4e1c-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="b4e1c-589">\-22,794</span></span>                                       | <span data-ttu-id="b4e1c-590">1 000</span><span class="sxs-lookup"><span data-stu-id="b4e1c-590">1,000</span></span>                                          | <span data-ttu-id="b4e1c-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="b4e1c-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="b4e1c-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="b4e1c-593">8</span><span class="sxs-lookup"><span data-stu-id="b4e1c-593">8</span></span>          | <span data-ttu-id="b4e1c-594">Odsetki</span><span class="sxs-lookup"><span data-stu-id="b4e1c-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="b4e1c-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="b4e1c-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="b4e1c-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="b4e1c-597">94\.97</span></span>                                  |
| <span data-ttu-id="b4e1c-598">9</span><span class="sxs-lookup"><span data-stu-id="b4e1c-598">9</span></span>          | <span data-ttu-id="b4e1c-599">Kasa</span><span class="sxs-lookup"><span data-stu-id="b4e1c-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="b4e1c-600">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="b4e1c-601">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b4e1c-602">\-1008\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="b4e1c-603">10</span><span class="sxs-lookup"><span data-stu-id="b4e1c-603">10</span></span>         | <span data-ttu-id="b4e1c-604">Wydatek amortyzacji</span><span class="sxs-lookup"><span data-stu-id="b4e1c-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="b4e1c-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="b4e1c-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-606">949\.75</span></span>                                        | <span data-ttu-id="b4e1c-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-607">949\.75</span></span>                                 |
| <span data-ttu-id="b4e1c-608">11</span><span class="sxs-lookup"><span data-stu-id="b4e1c-608">11</span></span>         | <span data-ttu-id="b4e1c-609">Umorzenie</span><span class="sxs-lookup"><span data-stu-id="b4e1c-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="b4e1c-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="b4e1c-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="b4e1c-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-611">\-949\.75</span></span>                                      | <span data-ttu-id="b4e1c-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="b4e1c-612">\-949\.75</span></span>                               |


