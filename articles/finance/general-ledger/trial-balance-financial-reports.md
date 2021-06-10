---
title: Raporty finansowe bilansu próbnego
description: W tym artykule opisano domyślne raporty o bilansach próbnych. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103665"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="c298d-104">Raporty finansowe bilansu próbnego</span><span class="sxs-lookup"><span data-stu-id="c298d-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c298d-105">W tym artykule opisano domyślne raporty o bilansach próbnych.</span><span class="sxs-lookup"><span data-stu-id="c298d-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="c298d-106">Omówiono również bloki konstrukcyjne skojarzone z tymi raportami oraz sposoby modyfikowania raportów w celu dostosowania ich do wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="c298d-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="c298d-107">Domyślne raporty finansowe bilansu próbnego</span><span class="sxs-lookup"><span data-stu-id="c298d-107">Default trial balance reports</span></span>

<span data-ttu-id="c298d-108">W module Raporty finansowe są dostępne trzy raporty bilansu próbnego.</span><span class="sxs-lookup"><span data-stu-id="c298d-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="c298d-109">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-109">Default report</span></span>                                 | <span data-ttu-id="c298d-110">Działanie</span><span class="sxs-lookup"><span data-stu-id="c298d-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c298d-111">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="c298d-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="c298d-112">Oferuje informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.</span><span class="sxs-lookup"><span data-stu-id="c298d-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="c298d-113">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="c298d-114">Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.</span><span class="sxs-lookup"><span data-stu-id="c298d-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="c298d-115">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="c298d-116">Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego.</span><span class="sxs-lookup"><span data-stu-id="c298d-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="c298d-117">Podstawowe elementy</span><span class="sxs-lookup"><span data-stu-id="c298d-117">Building blocks</span></span>
<span data-ttu-id="c298d-118">Raporty finansowe bilansu próbnego wykorzystują następujące podstawowe elementy.</span><span class="sxs-lookup"><span data-stu-id="c298d-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="c298d-119">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-119">Default report</span></span>                                 | <span data-ttu-id="c298d-120">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="c298d-120">Row definition</span></span>          | <span data-ttu-id="c298d-121">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="c298d-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="c298d-122">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="c298d-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="c298d-123">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-123">Trial Balance - Default</span></span> | <span data-ttu-id="c298d-124">Szczegółowy bilans próbny — domyślne</span><span class="sxs-lookup"><span data-stu-id="c298d-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="c298d-125">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="c298d-126">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-126">Trial Balance - Default</span></span> | <span data-ttu-id="c298d-127">Sumaryczny bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="c298d-128">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="c298d-129">Bilans próbny — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-129">Trial Balance - Default</span></span> | <span data-ttu-id="c298d-130">Sumaryczny bilans próbny rok do roku — domyślny</span><span class="sxs-lookup"><span data-stu-id="c298d-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="c298d-131">Podczas uruchamiania raportu **bilansu próbnego** w sprawozdawczości finansowej należy zaznaczyć pola wyboru **Wyświetlaj wiersze bez kwot** i **Wyświetlaj raporty bez aktywnych wierszy** na karcie **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="c298d-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="c298d-132">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="c298d-132">Row definition</span></span>

<span data-ttu-id="c298d-133">Definicja wiersza Bilans próbny — domyślny zawiera pojedynczy wiersz, który pobiera informacje ze wszystkich kont głównych.</span><span class="sxs-lookup"><span data-stu-id="c298d-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="c298d-134">Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="c298d-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="c298d-135">Podczas przeglądania raportu można przejść do pojedynczego wiersza, aby wyświetlić szczegóły dotyczące poszczególnych kont.</span><span class="sxs-lookup"><span data-stu-id="c298d-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="c298d-136">Można zmodyfikować definicję wiersza, tak aby zawierała więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="c298d-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="c298d-137">Aby zmodyfikować definicję wiersza Bilans próbny — domyślny, by zawierał wiesze dla wszystkich kont, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c298d-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="c298d-138">Kliknij **Edycja**, a następnie kliknij **Wstaw wiersze z wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="c298d-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="c298d-139">Polecenie **Wstaw wiersze z wymiarów** pozwala wybrać wymiary, które mają znaleźć się w definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="c298d-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="c298d-140">Dla tej definicji wiersza użyjesz **Konta głównego**.</span><span class="sxs-lookup"><span data-stu-id="c298d-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="c298d-141">Upewnij się, że **Konto główne** zawiera wszystkie znaki „&”, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c298d-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="c298d-142">Teraz definicja wiersza zawiera wszystkie konta główne dla Twojej domyślnej firmy.</span><span class="sxs-lookup"><span data-stu-id="c298d-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="c298d-143">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="c298d-143">Column definition</span></span>

<span data-ttu-id="c298d-144">Każdy raport bilansu próbnego używa innej definicji kolumny.</span><span class="sxs-lookup"><span data-stu-id="c298d-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="c298d-145">Te definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="c298d-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="c298d-146">**Szczegółowy bilans próbny — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="c298d-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="c298d-147">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="c298d-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="c298d-148">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="c298d-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="c298d-149">**ATTR (3)** — atrybuty:</span><span class="sxs-lookup"><span data-stu-id="c298d-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="c298d-150">Data transakcji</span><span class="sxs-lookup"><span data-stu-id="c298d-150">Transaction Date</span></span>
        -   <span data-ttu-id="c298d-151">Załącznik</span><span class="sxs-lookup"><span data-stu-id="c298d-151">Voucher</span></span>
        -   <span data-ttu-id="c298d-152">Opis arkusza</span><span class="sxs-lookup"><span data-stu-id="c298d-152">Journal Description</span></span>
    -   <span data-ttu-id="c298d-153">**FD** — dane finansowe zawierające tylko debety</span><span class="sxs-lookup"><span data-stu-id="c298d-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="c298d-154">**FD** — dane finansowe zawierające tylko kredyty</span><span class="sxs-lookup"><span data-stu-id="c298d-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="c298d-155">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="c298d-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="c298d-156">**Sumaryczny bilans próbny — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="c298d-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="c298d-157">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="c298d-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="c298d-158">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="c298d-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="c298d-159">**ATTR** – atrybut:</span><span class="sxs-lookup"><span data-stu-id="c298d-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="c298d-160">Załącznik</span><span class="sxs-lookup"><span data-stu-id="c298d-160">Voucher</span></span>
    -   <span data-ttu-id="c298d-161">**FD** — dane finansowe salda początkowego</span><span class="sxs-lookup"><span data-stu-id="c298d-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="c298d-162">**FD** — dane finansowe zawierające tylko debety</span><span class="sxs-lookup"><span data-stu-id="c298d-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="c298d-163">**FD** — dane finansowe zawierające tylko kredyty</span><span class="sxs-lookup"><span data-stu-id="c298d-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="c298d-164">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="c298d-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="c298d-165">**CALC** — saldo zamknięcia</span><span class="sxs-lookup"><span data-stu-id="c298d-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="c298d-166">**Sumaryczny bilans próbny rok do roku — domyślny:**</span><span class="sxs-lookup"><span data-stu-id="c298d-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="c298d-167">**ACCT** — kody konta</span><span class="sxs-lookup"><span data-stu-id="c298d-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="c298d-168">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="c298d-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="c298d-169">**ATTR** – atrybut</span><span class="sxs-lookup"><span data-stu-id="c298d-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="c298d-170">Załącznik</span><span class="sxs-lookup"><span data-stu-id="c298d-170">Voucher</span></span>
    -   <span data-ttu-id="c298d-171">**FD** — dane finansowe salda początkowego dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="c298d-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="c298d-172">**FD** — dane finansowe zawierające tylko debety dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="c298d-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="c298d-173">**FD** — dane finansowe zawierające tylko kredyty dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="c298d-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="c298d-174">**CALC** — różnica netto</span><span class="sxs-lookup"><span data-stu-id="c298d-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="c298d-175">**CALC** — saldo zamknięcia</span><span class="sxs-lookup"><span data-stu-id="c298d-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="c298d-176">**FD** — dane finansowe zawierające tylko debety dla ostatniego roku</span><span class="sxs-lookup"><span data-stu-id="c298d-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="c298d-177">**FD** — dane finansowe zawierające tylko kredyty dla ostatniego roku</span><span class="sxs-lookup"><span data-stu-id="c298d-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c298d-178">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c298d-178">Additional resources</span></span>

[<span data-ttu-id="c298d-179">Omówienie raportowania finansowego</span><span class="sxs-lookup"><span data-stu-id="c298d-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="c298d-180">Wyświetlanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="c298d-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="c298d-181">Blog o sprawozdawczości finansowej w systemie Dynamics</span><span class="sxs-lookup"><span data-stu-id="c298d-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
