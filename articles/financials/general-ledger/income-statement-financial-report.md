---
title: Raport finansowego zestawienia przychodów
description: W tym artykule opisano domyślny raport o rachunkach wyników. Omówiono również bloki konstrukcyjne skojarzone z tym raportem.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9105e1de86ed2834b04f75c7d08c4021402bcfda
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549157"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="625a9-104">Raport finansowego zestawienia przychodów</span><span class="sxs-lookup"><span data-stu-id="625a9-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="625a9-105">W tym artykule opisano domyślny raport o rachunkach wyników.</span><span class="sxs-lookup"><span data-stu-id="625a9-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="625a9-106">Omówiono również bloki konstrukcyjne skojarzone z tym raportem.</span><span class="sxs-lookup"><span data-stu-id="625a9-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="625a9-107">Raport domyślny zestawienia przychodów</span><span class="sxs-lookup"><span data-stu-id="625a9-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="625a9-108">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="625a9-108">Default report</span></span>             | <span data-ttu-id="625a9-109">Działanie</span><span class="sxs-lookup"><span data-stu-id="625a9-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="625a9-110">Zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="625a9-110">Income Statement – Default</span></span> | <span data-ttu-id="625a9-111">Pokazuje rentowność organizacji w bieżącym okresie i od początku roku.</span><span class="sxs-lookup"><span data-stu-id="625a9-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="625a9-112">Podstawowe elementy</span><span class="sxs-lookup"><span data-stu-id="625a9-112">Building blocks</span></span>
<span data-ttu-id="625a9-113">W raportach finansowych zestawienia przychodów używane są następujące podstawowe elementy.</span><span class="sxs-lookup"><span data-stu-id="625a9-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="625a9-114">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="625a9-114">Default report</span></span>             | <span data-ttu-id="625a9-115">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="625a9-115">Row definition</span></span>                     | <span data-ttu-id="625a9-116">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="625a9-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="625a9-117">Zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="625a9-117">Income Statement - Default</span></span> | <span data-ttu-id="625a9-118">Podsumowujące zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="625a9-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="625a9-119">Okresowe i od początku roku — domyślne</span><span class="sxs-lookup"><span data-stu-id="625a9-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="625a9-120">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="625a9-120">Row definition</span></span>

<span data-ttu-id="625a9-121">Definicja wiersza Podsumowujące zestawienie przychodów — domyślne zawiera sekcję dla każdej części tradycyjnego zestawienia przychodów.</span><span class="sxs-lookup"><span data-stu-id="625a9-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="625a9-122">Wymiar Kategoria konta głównego jest używany do tworzenia definicji tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="625a9-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="625a9-123">Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="625a9-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="625a9-124">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="625a9-124">Column Definition</span></span>

<span data-ttu-id="625a9-125">Definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="625a9-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="625a9-126">**Okresowo i od początku roku — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="625a9-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="625a9-127">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="625a9-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="625a9-128">**FD** — dane finansowe dla bieżącego okresu</span><span class="sxs-lookup"><span data-stu-id="625a9-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="625a9-129">**FD** — dane finansowe od początku roku</span><span class="sxs-lookup"><span data-stu-id="625a9-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="625a9-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="625a9-130">Additional resources</span></span>
--------

[<span data-ttu-id="625a9-131">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="625a9-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="625a9-132">Wyświetlanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="625a9-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="625a9-133">Blog o sprawozdawczości finansowej w systemie Dynamics</span><span class="sxs-lookup"><span data-stu-id="625a9-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)



