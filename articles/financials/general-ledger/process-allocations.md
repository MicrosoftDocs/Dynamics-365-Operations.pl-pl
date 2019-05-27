---
title: Przetwarzanie alokacji
description: Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w Microsoft Dynamics 365 for Finance and Operations oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac531726e04ebec4da9062f47726568723364cce
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567221"
---
# <a name="process-allocations"></a><span data-ttu-id="c9470-105">Przetwarzanie alokacji</span><span class="sxs-lookup"><span data-stu-id="c9470-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9470-106">Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w Microsoft Dynamics 365 for Finance and Operations oraz o sposobach ich wykorzystywania w planowaniu budżetu.</span><span class="sxs-lookup"><span data-stu-id="c9470-106">This article provides information about allocations, the options for processing them in Microsoft Dynamics 365 for Finance and Operations, and how they can be used in budget planning.</span></span> <span data-ttu-id="c9470-107">Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych.</span><span class="sxs-lookup"><span data-stu-id="c9470-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="c9470-108">Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania.</span><span class="sxs-lookup"><span data-stu-id="c9470-108">They help guarantee that expenses or revenue is charged to the correct object in accounting.</span></span>

<span data-ttu-id="c9470-109">Microsoft Dynamics 365 for Finance and Operations oferuje następujące funkcje do obsługi tego procesu:</span><span class="sxs-lookup"><span data-stu-id="c9470-109">Microsoft Dynamics 365 for Finance and Operations provides the following capabilities to support this process:</span></span>

-   <span data-ttu-id="c9470-110">Ręczne przydzielanie kwot transakcji przy użyciu akcji Podział w zasadach podziału księgowań lub poprzez zastosowanie względem dokumentu domyślnych szablonów wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="c9470-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="c9470-111">Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="c9470-111">For more information, see [Accounting distributions.](../accounts-payable/accounting-distributions.md)</span></span>
-   <span data-ttu-id="c9470-112">Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych.</span><span class="sxs-lookup"><span data-stu-id="c9470-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="c9470-113">Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła.</span><span class="sxs-lookup"><span data-stu-id="c9470-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span>
-   <span data-ttu-id="c9470-114">Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="c9470-114">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="c9470-115">Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji.</span><span class="sxs-lookup"><span data-stu-id="c9470-115">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> 

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="c9470-116">Alokacje w planowaniu budżetu</span><span class="sxs-lookup"><span data-stu-id="c9470-116">Allocations in budget planning</span></span>

<span data-ttu-id="c9470-117">Reguły alokacji księgi mogą służyć do obsługi planów budżetowych.</span><span class="sxs-lookup"><span data-stu-id="c9470-117">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="c9470-118">Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="c9470-118">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="c9470-119">Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu.</span><span class="sxs-lookup"><span data-stu-id="c9470-119">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="c9470-120">Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="c9470-120">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="c9470-121">Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.</span><span class="sxs-lookup"><span data-stu-id="c9470-121">You can’t use intercompany ledger allocation rules for budget planning.</span></span>





