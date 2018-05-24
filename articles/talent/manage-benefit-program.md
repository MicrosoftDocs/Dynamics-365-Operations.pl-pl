---
title: "Definiowanie programu świadczeń i zarządzanie nim"
description: "W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu. Ten artykuł zawiera informacje o sposobie konfigurowania zarządzania świadczeniami."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fc325b519299098a4f8257c013bce0842237f9ea
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="c9a6b-104">Definiowanie programu świadczeń i zarządzanie nim</span><span class="sxs-lookup"><span data-stu-id="c9a6b-104">Define and manage a benefits program</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c9a6b-105">W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="c9a6b-106">Ten temat zawiera informacje o sposobie konfigurowania i zarządzania świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="c9a6b-107">Konfiguracja świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9a6b-107">Benefit setup</span></span>
-------------

<span data-ttu-id="c9a6b-108">Aby przypisać pracownika do świadczenia, trzeba najpierw utworzyć elementy poszczególnych świadczeń.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="c9a6b-109">Te elementy łączą podobne plany świadczeń i określają domyślne ustawienia, takie jak stawki potrąceń i szczegóły księgowania.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="c9a6b-110">Wiele z tych ustawień można dostosować później, bo przypisywaniu pracowników do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="c9a6b-111">Dla każdego planu świadczenia organizacja może oferować kilka opcji rejestrowania lub pracownik może zrezygnować z rejestracji w planie.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="c9a6b-112">[![Przebieg procesu świadczeń](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="c9a6b-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="c9a6b-113">Elementy świadczenia</span><span class="sxs-lookup"><span data-stu-id="c9a6b-113">Benefit elements</span></span>
<span data-ttu-id="c9a6b-114">Przed przystąpieniem do tworzenia świadczeń i przypisywania do nich pracowników, trzeba zdefiniować elementy, które składają się na świadczenie: typ, plan i opcje.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="c9a6b-115">**Typ** — zbiór planów szczególnych korzyści, takich jak ochrona zdrowia lub parkowanie.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="c9a6b-116">**Plan** — szczególne świadczenie zakontraktowane u dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="c9a6b-117">**Opcja** — poziom zapotrzebowania, na przykład tylko pracownik lub pracownik i współmałżonek/partner(ka).</span><span class="sxs-lookup"><span data-stu-id="c9a6b-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="c9a6b-118">Dla każdego typu świadczenia, np. badania okulistyczne lub opieka stomatologiczna, organizacja może oferować pracownikom jeden lub kilka planów.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="c9a6b-119">Dla każdego planu organizacja może oferować różne opcje.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="c9a6b-120">Na przykład pracownicy mogą wykupić dodatkowy zakres ubezpieczenia o wartości swojego rocznego wynagrodzenia, albo dwu- lub trzykrotnie przewyższającej tę wartość.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="c9a6b-121">Każda kombinacja planu i opcji staje się świadczeniem, na jakie pracownicy mogą się zarejestrować.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="c9a6b-122">[![ilustracja świadczenia](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="c9a6b-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="c9a6b-123">Uprawnienie</span><span class="sxs-lookup"><span data-stu-id="c9a6b-123">Eligibility</span></span>
<span data-ttu-id="c9a6b-124">Dostępność świadczeń oferowanych przez pracodawcę zależy od różnych czynników.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="c9a6b-125">Podczas tworzenia świadczenia w programie Microsoft Talent można ustawić dla niego typ dostępności.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="c9a6b-126">Można udostępnić świadczenie wszystkim pracownikom.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="c9a6b-127">Na przykład niektóre firmy oferują przepustki parkingowe wszystkim pracowniom jako świadczenia nieodpłatne.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="c9a6b-128">Podczas tworzenia tego świadczenia, należy ustawić dostępność na **Dostępne dla wszystkich pracowników**.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="c9a6b-129">W przypadku innych świadczeń, takich jak zajęcia wierzytelności lub opłaty podatkowe, opcje uprawnień nie mają zastosowania.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="c9a6b-130">Podczas tworzenia świadczeń tego typu ustawia się uprawnienia na **Pomiń przetwarzanie uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="c9a6b-131">Uprawnienia do świadczeń mogą również opierać się na regułach.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="c9a6b-132">Na przykład firma oferuje pracownikom dwa rodzaje ubezpieczeń na życie.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="c9a6b-133">Członkowie kadry kierowniczej są uprawnieni do jednego planu ubezpieczenia na życie, a dla pozostałych pracowników pełnoetatowych dostępny jest inny plan ubezpieczenia na życie.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="c9a6b-134">W module Talent można utworzyć regułę wyszukującą wszystkich członków kadry kierowniczej oraz regułę wyszukującą wszystkich pozostałych pracowników pełnoetatowych, a następnie zastosować te reguły do odpowiedniego świadczenia.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="c9a6b-135">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="c9a6b-135">Enrollment</span></span>
<span data-ttu-id="c9a6b-136">Po utworzeniu świadczenia oferowanego w Twojej organizacji i określeniu dostępności, można zarejestrować w nich pracowników.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="c9a6b-137">W jednym procesie można zarejestrować jednego pracownika w świadczeniu lub wielu pracowników w jednym lub kilku świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="c9a6b-138">Czasami organizacja wstrzymuje realizację jakiegoś świadczenia.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="c9a6b-139">W takim przypadku trzeba zaktualizować świadczenie i zarejestrowanych w nim pracowników.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="c9a6b-140">Grupowe wygaszanie świadczenia pozwala za jednym razem zmienić datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w tym świadczeniu.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="c9a6b-141">Można również wybrać wielu pracowników, którzy są zarejestrowani do świadczenia i zmienić datę końcową ich polisy.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="c9a6b-142">To samo dotyczy grupowego przedłużania świadczeń, za pomocą którego można wydłużyć datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w danym świadczeniu, jeśli świadczenie ma być oferowane dłużej, niż pierwotnie zaplanowano.</span><span class="sxs-lookup"><span data-stu-id="c9a6b-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="additional-resources"></a><span data-ttu-id="c9a6b-143">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c9a6b-143">Additional resources</span></span>
--------

[<span data-ttu-id="c9a6b-144">Zasady uprawnień do świadczeń</span><span class="sxs-lookup"><span data-stu-id="c9a6b-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




