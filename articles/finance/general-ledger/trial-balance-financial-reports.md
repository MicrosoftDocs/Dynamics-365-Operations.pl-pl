---
title: Raporty finansowe bilansu próbnego
description: W tym artykule opisano domyślne raporty o bilansach próbnych. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b48510febf5a5f9f4a01728b242d9750b3c62c2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446648"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="163d0-104">Raporty finansowe bilansu próbnego</span><span class="sxs-lookup"><span data-stu-id="163d0-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="163d0-105">W tym artykule opisano domyślne raporty o bilansach próbnych.</span><span class="sxs-lookup"><span data-stu-id="163d0-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="163d0-106">Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="163d0-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="163d0-107">Domyślne raporty finansowe bilansu próbnego</span><span class="sxs-lookup"><span data-stu-id="163d0-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="163d0-108">W module Raporty finansowe są dostępne trzy raporty bilansu próbnego.</span><span class="sxs-lookup"><span data-stu-id="163d0-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="163d0-109">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-109">Default report</span></span>                                 | <span data-ttu-id="163d0-110">Działanie</span><span class="sxs-lookup"><span data-stu-id="163d0-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="163d0-111">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="163d0-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="163d0-112">Oferuje informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.</span><span class="sxs-lookup"><span data-stu-id="163d0-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="163d0-113">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="163d0-114">Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.</span><span class="sxs-lookup"><span data-stu-id="163d0-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="163d0-115">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="163d0-116">Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego.</span><span class="sxs-lookup"><span data-stu-id="163d0-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="163d0-117">Podstawowe elementy</span><span class="sxs-lookup"><span data-stu-id="163d0-117">Building blocks</span></span>
<span data-ttu-id="163d0-118">Raporty finansowe bilansu próbnego wykorzystują następujące podstawowe elementy.</span><span class="sxs-lookup"><span data-stu-id="163d0-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="163d0-119">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-119">Default report</span></span>                                 | <span data-ttu-id="163d0-120">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="163d0-120">Row definition</span></span>          | <span data-ttu-id="163d0-121">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="163d0-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="163d0-122">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="163d0-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="163d0-123">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-123">Trial Balance - Default</span></span> | <span data-ttu-id="163d0-124">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="163d0-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="163d0-125">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="163d0-126">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-126">Trial Balance - Default</span></span> | <span data-ttu-id="163d0-127">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="163d0-128">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="163d0-129">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-129">Trial Balance - Default</span></span> | <span data-ttu-id="163d0-130">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="163d0-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="163d0-131">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="163d0-131">Row definition</span></span>

<span data-ttu-id="163d0-132">Definicja wiersza Bilans próbny — domyślny zawiera pojedynczy wiersz, który pobiera informacje ze wszystkich kont głównych.</span><span class="sxs-lookup"><span data-stu-id="163d0-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="163d0-133">Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="163d0-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="163d0-134">Podczas przeglądania raportu można przejść do pojedynczego wiersza, aby wyświetlić szczegóły dotyczące poszczególnych kont.</span><span class="sxs-lookup"><span data-stu-id="163d0-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="163d0-135">Można zmodyfikować definicję wiersza, tak aby zawierała więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="163d0-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="163d0-136">Aby zmodyfikować definicję wiersza Bilans próbny — domyślny, by zawierał wiesze dla wszystkich kont, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="163d0-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="163d0-137">Kliknij **Edycja**, a następnie kliknij **Wstaw wiersze z wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="163d0-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="163d0-138">Polecenie **Wstaw wiersze z wymiarów** pozwala wybrać wymiary, które mają znaleźć się w definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="163d0-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="163d0-139">Dla tej definicji wiersza użyjesz **Konta głównego**.</span><span class="sxs-lookup"><span data-stu-id="163d0-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="163d0-140">Upewnij się, że **Konto główne** zawiera wszystkie znaki „&”, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="163d0-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="163d0-141">Teraz definicja wiersza zawiera wszystkie konta główne dla Twojej domyślnej firmy.</span><span class="sxs-lookup"><span data-stu-id="163d0-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="163d0-142">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="163d0-142">Column definition</span></span>

<span data-ttu-id="163d0-143">Każdy raport bilansu próbnego używa innej definicji kolumny.</span><span class="sxs-lookup"><span data-stu-id="163d0-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="163d0-144">Te definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="163d0-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="163d0-145">**Szczegółowy bilans próbny — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="163d0-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="163d0-146">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="163d0-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="163d0-147">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="163d0-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="163d0-148">**ATTR (3)** — atrybuty:</span><span class="sxs-lookup"><span data-stu-id="163d0-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="163d0-149">Data transakcji</span><span class="sxs-lookup"><span data-stu-id="163d0-149">Transaction Date</span></span>
        -   <span data-ttu-id="163d0-150">Załącznik</span><span class="sxs-lookup"><span data-stu-id="163d0-150">Voucher</span></span>
        -   <span data-ttu-id="163d0-151">Opis arkusza</span><span class="sxs-lookup"><span data-stu-id="163d0-151">Journal Description</span></span>
    -   <span data-ttu-id="163d0-152">**FD** — dane finansowe zawierające tylko debety</span><span class="sxs-lookup"><span data-stu-id="163d0-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="163d0-153">**FD** — dane finansowe zawierające tylko kredyty</span><span class="sxs-lookup"><span data-stu-id="163d0-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="163d0-154">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="163d0-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="163d0-155">**Sumaryczny bilans próbny — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="163d0-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="163d0-156">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="163d0-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="163d0-157">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="163d0-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="163d0-158">**ATTR** – atrybut:</span><span class="sxs-lookup"><span data-stu-id="163d0-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="163d0-159">Załącznik</span><span class="sxs-lookup"><span data-stu-id="163d0-159">Voucher</span></span>
    -   <span data-ttu-id="163d0-160">**FD** — dane finansowe salda początkowego</span><span class="sxs-lookup"><span data-stu-id="163d0-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="163d0-161">**FD** — dane finansowe zawierające tylko debety</span><span class="sxs-lookup"><span data-stu-id="163d0-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="163d0-162">**FD** — dane finansowe zawierające tylko kredyty</span><span class="sxs-lookup"><span data-stu-id="163d0-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="163d0-163">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="163d0-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="163d0-164">**CALC** — saldo zamknięcia</span><span class="sxs-lookup"><span data-stu-id="163d0-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="163d0-165">**Sumaryczny bilans próbny rok do roku — domyślny:**</span><span class="sxs-lookup"><span data-stu-id="163d0-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="163d0-166">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="163d0-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="163d0-167">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="163d0-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="163d0-168">**ATTR** – atrybut</span><span class="sxs-lookup"><span data-stu-id="163d0-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="163d0-169">Załącznik</span><span class="sxs-lookup"><span data-stu-id="163d0-169">Voucher</span></span>
    -   <span data-ttu-id="163d0-170">**FD** — dane finansowe salda początkowego dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="163d0-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="163d0-171">**FD** — dane finansowe zawierające tylko debety dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="163d0-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="163d0-172">**FD** — dane finansowe zawierające tylko kredyty dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="163d0-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="163d0-173">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="163d0-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="163d0-174">**CALC** — saldo zamknięcia</span><span class="sxs-lookup"><span data-stu-id="163d0-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="163d0-175">**FD** — dane finansowe zawierające tylko debety dla ostatniego roku</span><span class="sxs-lookup"><span data-stu-id="163d0-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="163d0-176">**FD** — dane finansowe zawierające tylko kredyty dla ostatniego roku</span><span class="sxs-lookup"><span data-stu-id="163d0-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="163d0-177">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="163d0-177">Additional resources</span></span>
--------

[<span data-ttu-id="163d0-178">Omówienie raportowania finansowego</span><span class="sxs-lookup"><span data-stu-id="163d0-178">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="163d0-179">Wyświetlanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="163d0-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="163d0-180">Blog o sprawozdawczości finansowej w systemie Dynamics</span><span class="sxs-lookup"><span data-stu-id="163d0-180">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



