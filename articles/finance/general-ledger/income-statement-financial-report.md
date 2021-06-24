---
title: Raport finansowego zestawienia przychodów
description: W tym artykule opisano domyślny raport o rachunkach wyników. Omówiono również bloki konstrukcyjne skojarzone z tym raportem.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ab5e7a2675705cc2265b7f894d9b12d4465aea1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187827"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="d491b-104">Raport finansowego zestawienia przychodów</span><span class="sxs-lookup"><span data-stu-id="d491b-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d491b-105">W tym artykule opisano domyślny raport o rachunkach wyników.</span><span class="sxs-lookup"><span data-stu-id="d491b-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="d491b-106">Omówiono również bloki konstrukcyjne skojarzone z tym raportem.</span><span class="sxs-lookup"><span data-stu-id="d491b-106">It also describes the building blocks that are associated with this report.</span></span> 

## <a name="default-income-statement-report"></a><span data-ttu-id="d491b-107">Raport domyślny zestawienia przychodów</span><span class="sxs-lookup"><span data-stu-id="d491b-107">Default income statement report</span></span>

| <span data-ttu-id="d491b-108">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="d491b-108">Default report</span></span>             | <span data-ttu-id="d491b-109">Działanie</span><span class="sxs-lookup"><span data-stu-id="d491b-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d491b-110">Zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="d491b-110">Income Statement – Default</span></span> | <span data-ttu-id="d491b-111">Pokazuje rentowność organizacji w bieżącym okresie i od początku roku.</span><span class="sxs-lookup"><span data-stu-id="d491b-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="d491b-112">Podstawowe elementy</span><span class="sxs-lookup"><span data-stu-id="d491b-112">Building blocks</span></span>
<span data-ttu-id="d491b-113">W raportach finansowych zestawienia przychodów używane są następujące podstawowe elementy.</span><span class="sxs-lookup"><span data-stu-id="d491b-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="d491b-114">Raport domyślny</span><span class="sxs-lookup"><span data-stu-id="d491b-114">Default report</span></span>             | <span data-ttu-id="d491b-115">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="d491b-115">Row definition</span></span>                     | <span data-ttu-id="d491b-116">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="d491b-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="d491b-117">Zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="d491b-117">Income Statement - Default</span></span> | <span data-ttu-id="d491b-118">Podsumowujące zestawienie przychodów — domyślne</span><span class="sxs-lookup"><span data-stu-id="d491b-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="d491b-119">Okresowe i od początku roku — domyślne</span><span class="sxs-lookup"><span data-stu-id="d491b-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="d491b-120">Definicja wiersza</span><span class="sxs-lookup"><span data-stu-id="d491b-120">Row definition</span></span>

<span data-ttu-id="d491b-121">Definicja wiersza Podsumowujące zestawienie przychodów — domyślne zawiera sekcję dla każdej części tradycyjnego zestawienia przychodów.</span><span class="sxs-lookup"><span data-stu-id="d491b-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="d491b-122">Wymiar Kategoria konta głównego jest używany do tworzenia definicji tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="d491b-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="d491b-123">Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="d491b-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="d491b-124">Definicja kolumny</span><span class="sxs-lookup"><span data-stu-id="d491b-124">Column Definition</span></span>

<span data-ttu-id="d491b-125">Definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="d491b-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="d491b-126">**Okresowo i od początku roku — domyślne typy kolumn:**</span><span class="sxs-lookup"><span data-stu-id="d491b-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="d491b-127">**DESC** — opis z definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="d491b-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="d491b-128">**FD** — dane finansowe dla bieżącego okresu</span><span class="sxs-lookup"><span data-stu-id="d491b-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="d491b-129">**FD** — dane finansowe od początku roku</span><span class="sxs-lookup"><span data-stu-id="d491b-129">**FD** – Financial data for the year to date</span></span>



## <a name="additional-resources"></a><span data-ttu-id="d491b-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d491b-130">Additional resources</span></span>

[<span data-ttu-id="d491b-131">Omówienie raportowania finansowego</span><span class="sxs-lookup"><span data-stu-id="d491b-131">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="d491b-132">Wyświetlanie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="d491b-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="d491b-133">Blog o sprawozdawczości finansowej w systemie Dynamics</span><span class="sxs-lookup"><span data-stu-id="d491b-133">Dynamics Financial Reporting Blog</span></span>](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]