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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7344fad7c4dffabd99993924604e2e497bebc5ef
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="ca102-104">Definiowanie programu świadczeń i zarządzanie nim</span><span class="sxs-lookup"><span data-stu-id="ca102-104">Define and manage a benefits program</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="ca102-105">W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="ca102-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="ca102-106">Ten temat zawiera informacje o sposobie konfigurowania i zarządzania świadczeniami.</span><span class="sxs-lookup"><span data-stu-id="ca102-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="ca102-107">Konfiguracja świadczeń</span><span class="sxs-lookup"><span data-stu-id="ca102-107">Benefit setup</span></span>
-------------

<span data-ttu-id="ca102-108">Aby przypisać pracownika do świadczenia, trzeba najpierw utworzyć elementy poszczególnych świadczeń.</span><span class="sxs-lookup"><span data-stu-id="ca102-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="ca102-109">Te elementy łączą podobne plany świadczeń i określają domyślne ustawienia, takie jak stawki potrąceń i szczegóły księgowania.</span><span class="sxs-lookup"><span data-stu-id="ca102-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="ca102-110">Wiele z tych ustawień można dostosować później, bo przypisywaniu pracowników do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="ca102-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="ca102-111">Dla każdego planu świadczenia organizacja może oferować kilka opcji rejestrowania lub pracownik może zrezygnować z rejestracji w planie.</span><span class="sxs-lookup"><span data-stu-id="ca102-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="ca102-112">[![Przebieg procesu świadczeń](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="ca102-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="ca102-113">Elementy świadczenia</span><span class="sxs-lookup"><span data-stu-id="ca102-113">Benefit elements</span></span>
<span data-ttu-id="ca102-114">Przed przystąpieniem do tworzenia świadczeń i przypisywania do nich pracowników, trzeba zdefiniować elementy, które składają się na świadczenie: typ, plan i opcje.</span><span class="sxs-lookup"><span data-stu-id="ca102-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="ca102-115">**Typ** — zbiór planów szczególnych korzyści, takich jak ochrona zdrowia lub parkowanie.</span><span class="sxs-lookup"><span data-stu-id="ca102-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="ca102-116">**Plan** — szczególne świadczenie zakontraktowane u dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ca102-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="ca102-117">**Opcja** — poziom zapotrzebowania, na przykład tylko pracownik lub pracownik i współmałżonek/partner(ka).</span><span class="sxs-lookup"><span data-stu-id="ca102-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="ca102-118">Dla każdego typu świadczenia, np. badania okulistyczne lub opieka stomatologiczna, organizacja może oferować pracownikom jeden lub kilka planów.</span><span class="sxs-lookup"><span data-stu-id="ca102-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="ca102-119">Dla każdego planu organizacja może oferować różne opcje.</span><span class="sxs-lookup"><span data-stu-id="ca102-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="ca102-120">Na przykład pracownicy mogą wykupić dodatkowy zakres ubezpieczenia o wartości swojego rocznego wynagrodzenia, albo dwu- lub trzykrotnie przewyższającej tę wartość.</span><span class="sxs-lookup"><span data-stu-id="ca102-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="ca102-121">Każda kombinacja planu i opcji staje się świadczeniem, na jakie pracownicy mogą się zarejestrować.</span><span class="sxs-lookup"><span data-stu-id="ca102-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="ca102-122">[![ilustracja świadczenia](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="ca102-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="ca102-123">Uprawnienie</span><span class="sxs-lookup"><span data-stu-id="ca102-123">Eligibility</span></span>
<span data-ttu-id="ca102-124">Dostępność świadczeń oferowanych przez pracodawcę zależy od różnych czynników.</span><span class="sxs-lookup"><span data-stu-id="ca102-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="ca102-125">Podczas tworzenia świadczenia w programie Microsoft Talent można ustawić dla niego typ dostępności.</span><span class="sxs-lookup"><span data-stu-id="ca102-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="ca102-126">Można udostępnić świadczenie wszystkim pracownikom.</span><span class="sxs-lookup"><span data-stu-id="ca102-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="ca102-127">Na przykład niektóre firmy oferują przepustki parkingowe wszystkim pracowniom jako świadczenia nieodpłatne.</span><span class="sxs-lookup"><span data-stu-id="ca102-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="ca102-128">Podczas tworzenia tego świadczenia, należy ustawić dostępność na **Dostępne dla wszystkich pracowników**.</span><span class="sxs-lookup"><span data-stu-id="ca102-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="ca102-129">W przypadku innych świadczeń, takich jak zajęcia wierzytelności lub opłaty podatkowe, opcje uprawnień nie mają zastosowania.</span><span class="sxs-lookup"><span data-stu-id="ca102-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="ca102-130">Podczas tworzenia świadczeń tego typu ustawia się uprawnienia na **Pomiń przetwarzanie uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="ca102-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="ca102-131">Uprawnienia do świadczeń mogą również opierać się na regułach.</span><span class="sxs-lookup"><span data-stu-id="ca102-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="ca102-132">Na przykład firma oferuje pracownikom dwa rodzaje ubezpieczeń na życie.</span><span class="sxs-lookup"><span data-stu-id="ca102-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="ca102-133">Członkowie kadry kierowniczej są uprawnieni do jednego planu ubezpieczenia na życie, a dla pozostałych pracowników pełnoetatowych dostępny jest inny plan ubezpieczenia na życie.</span><span class="sxs-lookup"><span data-stu-id="ca102-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="ca102-134">W module Talent można utworzyć regułę wyszukującą wszystkich członków kadry kierowniczej oraz regułę wyszukującą wszystkich pozostałych pracowników pełnoetatowych, a następnie zastosować te reguły do odpowiedniego świadczenia.</span><span class="sxs-lookup"><span data-stu-id="ca102-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="ca102-135">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="ca102-135">Enrollment</span></span>
<span data-ttu-id="ca102-136">Po utworzeniu świadczenia oferowanego w Twojej organizacji i określeniu dostępności, można zarejestrować w nich pracowników.</span><span class="sxs-lookup"><span data-stu-id="ca102-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="ca102-137">W jednym procesie można zarejestrować jednego pracownika w świadczeniu lub wielu pracowników w jednym lub kilku świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="ca102-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="ca102-138">Czasami organizacja wstrzymuje realizację jakiegoś świadczenia.</span><span class="sxs-lookup"><span data-stu-id="ca102-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="ca102-139">W takim przypadku trzeba zaktualizować świadczenie i zarejestrowanych w nim pracowników.</span><span class="sxs-lookup"><span data-stu-id="ca102-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="ca102-140">Grupowe wygaszanie świadczenia pozwala za jednym razem zmienić datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w tym świadczeniu.</span><span class="sxs-lookup"><span data-stu-id="ca102-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="ca102-141">Można również wybrać wielu pracowników, którzy są zarejestrowani do świadczenia i zmienić datę końcową ich polisy.</span><span class="sxs-lookup"><span data-stu-id="ca102-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="ca102-142">To samo dotyczy grupowego przedłużania świadczeń, za pomocą którego można wydłużyć datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w danym świadczeniu, jeśli świadczenie ma być oferowane dłużej, niż pierwotnie zaplanowano.</span><span class="sxs-lookup"><span data-stu-id="ca102-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="see-also"></a><span data-ttu-id="ca102-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="ca102-143">See also</span></span>
--------

[<span data-ttu-id="ca102-144">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="ca102-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




