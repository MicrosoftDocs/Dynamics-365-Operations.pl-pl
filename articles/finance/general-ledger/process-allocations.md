---
title: Przetwarzanie alokacji
description: Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w Microsoft Dynamics 365 Finance oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a715fe2ae0cb32e523248ffb15bdde4b36bd01d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990221"
---
# <a name="process-allocations"></a><span data-ttu-id="b710c-105">Przetwarzanie alokacji</span><span class="sxs-lookup"><span data-stu-id="b710c-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b710c-106">Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania oraz o sposobach ich wykorzystywania w planowaniu budżetu.</span><span class="sxs-lookup"><span data-stu-id="b710c-106">This article provides information about allocations, the options for processing them, and how they can be used in budget planning.</span></span> <span data-ttu-id="b710c-107">Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych.</span><span class="sxs-lookup"><span data-stu-id="b710c-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="b710c-108">Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.</span><span class="sxs-lookup"><span data-stu-id="b710c-108">They help ensure that expenses or revenues are charged to the correct object in accounting.</span></span>

<span data-ttu-id="b710c-109">Ten proces obsługuje następujące możliwości:</span><span class="sxs-lookup"><span data-stu-id="b710c-109">The following capabilities support this process:</span></span>

-   <span data-ttu-id="b710c-110">Ręczne przydzielanie kwot transakcji przy użyciu akcji Podział w zasadach podziału księgowań lub poprzez zastosowanie względem dokumentu domyślnych szablonów wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="b710c-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="b710c-111">Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="b710c-111">For more information, see [Accounting distributions](../accounts-payable/accounting-distributions.md).</span></span>
-   <span data-ttu-id="b710c-112">Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych.</span><span class="sxs-lookup"><span data-stu-id="b710c-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="b710c-113">Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła.</span><span class="sxs-lookup"><span data-stu-id="b710c-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span> <span data-ttu-id="b710c-114">Aby uzyskać więcej informacji, zobacz [Warunki alokacji konta głównego](../general-ledger/main-account-allocation-terms.md)</span><span class="sxs-lookup"><span data-stu-id="b710c-114">For more information, see [Main account allocation terms](../general-ledger/main-account-allocation-terms.md)</span></span>
-   <span data-ttu-id="b710c-115">Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi.</span><span class="sxs-lookup"><span data-stu-id="b710c-115">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="b710c-116">Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji.</span><span class="sxs-lookup"><span data-stu-id="b710c-116">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> <span data-ttu-id="b710c-117">Aby uzyskać więcej informacji, zobacz temat [Reguły alokacji](../general-ledger/ledger-allocation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b710c-117">For more information, see [Allocation rules](../general-ledger/ledger-allocation-rules.md).</span></span>

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="b710c-118">Alokacje w planowaniu budżetu</span><span class="sxs-lookup"><span data-stu-id="b710c-118">Allocations in budget planning</span></span>

<span data-ttu-id="b710c-119">Reguły alokacji księgi mogą służyć do obsługi planów budżetowych.</span><span class="sxs-lookup"><span data-stu-id="b710c-119">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="b710c-120">Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="b710c-120">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="b710c-121">Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu.</span><span class="sxs-lookup"><span data-stu-id="b710c-121">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="b710c-122">Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="b710c-122">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="b710c-123">Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.</span><span class="sxs-lookup"><span data-stu-id="b710c-123">You can’t use intercompany ledger allocation rules for budget planning.</span></span>

