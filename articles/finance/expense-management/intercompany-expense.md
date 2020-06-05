---
title: Wydatki międzyfirmowe
description: Pracownik zatrudniony przez jedną firmę w organizacji może wykonywać pracę dla innej firmy w tej samej organizacji. W takiej sytuacji można użyć funkcji wydatków międzyfirmowych w celu przypisania wydatków pracownika do firmy, dla której wykonano pracę.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390891"
---
# <a name="intercompany-expenses"></a><span data-ttu-id="c95cc-104">Wydatki międzyfirmowe</span><span class="sxs-lookup"><span data-stu-id="c95cc-104">Intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c95cc-105">Pracownik zatrudniony przez jedną firmę w organizacji może wykonywać pracę dla innej firmy w tej samej organizacji.</span><span class="sxs-lookup"><span data-stu-id="c95cc-105">A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization.</span></span> <span data-ttu-id="c95cc-106">W takiej sytuacji można użyć funkcji wydatków międzyfirmowych w celu przypisania wydatków pracownika do firmy, dla której wykonano pracę.</span><span class="sxs-lookup"><span data-stu-id="c95cc-106">In this situation, you can use the intercompany expense feature to assign the worker’s expenses to the legal entity for which the work was performed.</span></span> <span data-ttu-id="c95cc-107">Firma zatrudniająca pracownika nosi nazwę firmy wypożyczającej.</span><span class="sxs-lookup"><span data-stu-id="c95cc-107">The legal entity that employs the worker is called the loaning legal entity.</span></span> <span data-ttu-id="c95cc-108">Firma, dla której pracownik ponosi wydatki nosi nazwę firmy pożyczającej.</span><span class="sxs-lookup"><span data-stu-id="c95cc-108">The legal entity for which the worker incurs expenses is called the borrowing legal entity.</span></span> 

<span data-ttu-id="c95cc-109">Zanim pracownik będzie mógł utworzyć i przesłać wydatki za pracę wykonaną dla różnych firm, w firmie wypożyczającej, na stronie **Parametry zarządzania wydatkami** wybierz opcję **Zezwalaj na wiersze wydatków międzyfirmowych**.</span><span class="sxs-lookup"><span data-stu-id="c95cc-109">Before a worker can create and submit expenses for work that is performed for a different legal entity, in the loaning legal entity, on the **Expense management parameters** page, select the **Allow intercompany expense lines** option.</span></span> 

## <a name="tax-posting-for-intercompany-expenses"></a><span data-ttu-id="c95cc-110">Księgowanie podatku dla wydatków międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="c95cc-110">Tax posting for intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c95cc-111">Jeśli w raporcie wydatków mają być używane grupy podatków skojarzone z firmą wypożyczającą (źródłową), a nie firmą pożyczającą (docelową), należy skonfigurować tę opcję w konfiguracji podatku w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="c95cc-111">If you want to use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you will need to configure this in the General ledger sales tax set up.</span></span> <span data-ttu-id="c95cc-112">Jeśli parametr księgi głównej **Firma do księgowania podatku międzyfirmowego** ma ustawioną wartość **Źródło**, a opcja **Zastosuj zasady opodatkowania dla podatku** została ustawiona na wartość **Nie**, zostanie użyta kombinacja podatków dla firmy wypożyczającej.</span><span class="sxs-lookup"><span data-stu-id="c95cc-112">When the General ledger parameter, **Legal entity for intercompany tax posting** is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity will be used.</span></span> <span data-ttu-id="c95cc-113">Jeśli ten sam parametr jest ustawiony na **Cel**, zostanie użyta kombinacja podatku dla firmy pożyczającej.</span><span class="sxs-lookup"><span data-stu-id="c95cc-113">When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used.</span></span> <span data-ttu-id="c95cc-114">W przypadku firm w Stanach Zjednoczonych, gdy parametr jest ustawiony jako **Źródło**, pole **Podatek naliczony** musi również zostać skonfigurowane na nowej stronie **Grupy księgowania**.</span><span class="sxs-lookup"><span data-stu-id="c95cc-114">For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page.</span></span> <span data-ttu-id="c95cc-115">Aparat księgowania będzie używać informacji z tego pola dla wpisu księgowego związanego z podatkiem.</span><span class="sxs-lookup"><span data-stu-id="c95cc-115">The accounting engine will use the information from this field for tax related accounting entry.</span></span>   
<span data-ttu-id="c95cc-116">Zachowanie jest spójne z wierszami wydatków zaksięgowanymi z projektem lub bez niego.</span><span class="sxs-lookup"><span data-stu-id="c95cc-116">The behavior is consistent for expense lines posted with or without a project.</span></span>  
