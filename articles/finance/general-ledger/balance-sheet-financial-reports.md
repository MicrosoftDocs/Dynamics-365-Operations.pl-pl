---
title: Raporty finansowe bilansu
description: W tym artykule opisano domyślne raporty o bilansach. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9dcac902118c643b9a9d783c12f02fa5c90827b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179372"
---
# <a name="balance-sheet-financial-reports"></a><span data-ttu-id="16f09-104">Raporty finansowe bilansu</span><span class="sxs-lookup"><span data-stu-id="16f09-104">Balance sheet financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16f09-105">W tym artykule opisano domyślne raporty o bilansach.</span><span class="sxs-lookup"><span data-stu-id="16f09-105">This article describes the default reports for balance sheets.</span></span> <span data-ttu-id="16f09-106">Omówiono również bloki konstrukcyjne skojarzone z tymi raportami.</span><span class="sxs-lookup"><span data-stu-id="16f09-106">It also describes the building blocks that are associated with these reports.</span></span> 

<a name="default-balance-sheet-reports"></a><span data-ttu-id="16f09-107">Domyślne raporty finansowe bilansu</span><span class="sxs-lookup"><span data-stu-id="16f09-107">Default balance sheet reports</span></span>
-----------------------------

<span data-ttu-id="16f09-108">Dostępne są dwa domyślne raporty finansowe bilansu.</span><span class="sxs-lookup"><span data-stu-id="16f09-108">There are two default balance sheet reports.</span></span> <span data-ttu-id="16f09-109">Na jednym raporcie sekcje są ułożone w słupkach.</span><span class="sxs-lookup"><span data-stu-id="16f09-109">On one report, the sections are stacked.</span></span> <span data-ttu-id="16f09-110">Na drugim raporcie sekcje są ułożone obok siebie.</span><span class="sxs-lookup"><span data-stu-id="16f09-110">On the other report, the sections are side by side.</span></span>

| <span data-ttu-id="16f09-111">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="16f09-111">Default report</span></span>                       | <span data-ttu-id="16f09-112">Działanie</span><span class="sxs-lookup"><span data-stu-id="16f09-112">What it does</span></span>                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="16f09-113">Bilans — domyślne</span><span class="sxs-lookup"><span data-stu-id="16f09-113">Balance Sheet – Default</span></span>              | <span data-ttu-id="16f09-114">Oferuje widok pozycji finansowej organizacji w danym roku.</span><span class="sxs-lookup"><span data-stu-id="16f09-114">Provides a view of the organization's financial position for the year.</span></span>                                                                 |
| <span data-ttu-id="16f09-115">Obok arkusza bilansowego — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-115">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="16f09-116">Oferuje widok pozycji finansowej organizacji w danym roku.</span><span class="sxs-lookup"><span data-stu-id="16f09-116">Provides a view of the organization's financial position for the year.</span></span> <span data-ttu-id="16f09-117">Aktywa i pasywa oraz kapitał własny udziałowców są pokazane równolegle.</span><span class="sxs-lookup"><span data-stu-id="16f09-117">Assets and liability and shareholder’s equity are side by side.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="16f09-118">Podstawowe elementy</span><span class="sxs-lookup"><span data-stu-id="16f09-118">Building blocks</span></span>
<span data-ttu-id="16f09-119">Raporty finansowe bilansu wykorzystują następujące podstawowe elementy.</span><span class="sxs-lookup"><span data-stu-id="16f09-119">The balance sheet financial reports use the following building blocks.</span></span>

| <span data-ttu-id="16f09-120">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="16f09-120">Default report</span></span>                       | <span data-ttu-id="16f09-121">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="16f09-121">Row definition</span></span>                       | <span data-ttu-id="16f09-122">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="16f09-122">Column definition</span></span>             |
|--------------------------------------|--------------------------------------|-------------------------------|
| <span data-ttu-id="16f09-123">Bilans — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-123">Balance Sheet - Default</span></span>              | <span data-ttu-id="16f09-124">Bilans — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-124">Balance Sheet - Default</span></span>              | <span data-ttu-id="16f09-125">Od początku roku i odchylenie — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-125">YTD and Variance - Default</span></span>    |
| <span data-ttu-id="16f09-126">Obok arkusza bilansowego — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-126">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="16f09-127">Obok arkusza bilansowego — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-127">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="16f09-128">Kolumna Od początku roku — domyślna</span><span class="sxs-lookup"><span data-stu-id="16f09-128">Year to Date Column - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="16f09-129">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="16f09-129">Row definition</span></span>

<span data-ttu-id="16f09-130">Definicje wierszy dla obu raportów bilansu zwierają konkretne sekcje dla każdej z części bilansu tradycyjnego.</span><span class="sxs-lookup"><span data-stu-id="16f09-130">The row definitions for both balance sheet reports contain sections for each part of a traditional balance sheet.</span></span> <span data-ttu-id="16f09-131">Raport równoległy zawiera podział kolumn, tak aby pasywa i kapitał własny właściciela były widoczne obok aktywów.</span><span class="sxs-lookup"><span data-stu-id="16f09-131">The side-by-side report includes a column break, so that liability and the owner’s equity appear next to assets.</span></span> <span data-ttu-id="16f09-132">Wymiar Kategoria konta głównego jest używany do tworzenia obu definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="16f09-132">The Main Account Category dimension is used to build both row definitions.</span></span> <span data-ttu-id="16f09-133">Dlatego każdy może wygenerować raporty bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="16f09-133">Therefore, anyone can generate the reports without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="16f09-134">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="16f09-134">Column definition</span></span>

<span data-ttu-id="16f09-135">Definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="16f09-135">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="16f09-136">**Od początku roku i Odchylenie — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="16f09-136">**YTD and Variance – Default column types:**</span></span>
    -   <span data-ttu-id="16f09-137">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="16f09-137">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="16f09-138">**FD** — dane finansowe od początku roku dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="16f09-138">**FD** – Year-to-date financial data for the current year</span></span>
    -   <span data-ttu-id="16f09-139">**FD** — dane finansowe od początku roku dla ostatniego roku</span><span class="sxs-lookup"><span data-stu-id="16f09-139">**FD** – Year-to-date financial data for the last year</span></span>
    -   <span data-ttu-id="16f09-140">**CALC** — odchylenie od odjęcia ostatniego rok od tego roku</span><span class="sxs-lookup"><span data-stu-id="16f09-140">**CALC** – The variance from subtracting last year from this year</span></span>

<!-- -->

-   <span data-ttu-id="16f09-141">**Kolumna Od początku roku — domyślna:**</span><span class="sxs-lookup"><span data-stu-id="16f09-141">**Year to Date Column – Default:**</span></span>
    -   <span data-ttu-id="16f09-142">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="16f09-142">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="16f09-143">**FD** — dane finansowe od początku roku dla bieżącego roku</span><span class="sxs-lookup"><span data-stu-id="16f09-143">**FD** – Year-to-date financial data for the current year</span></span>



<a name="additional-resources"></a><span data-ttu-id="16f09-144">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="16f09-144">Additional resources</span></span>
--------

[<span data-ttu-id="16f09-145">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="16f09-145">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="16f09-146">Wyświetlanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="16f09-146">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="16f09-147">Blog o sprawozdawczości finansowej w systemie Dynamics</span><span class="sxs-lookup"><span data-stu-id="16f09-147">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



