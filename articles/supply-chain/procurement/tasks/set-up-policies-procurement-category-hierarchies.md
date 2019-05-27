---
title: Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia
description: Niniejszej procedury należy użyć w celu skonfigurowania reguły dla zamówionych produktów z kategorii.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1fdf357466de12bd0188fc43cd266c67af762c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569921"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="29fdf-103">Konfigurowanie zasad dla hierarchii kategorii zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="29fdf-103">Set up policies for procurement category hierarchies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="29fdf-104">Niniejszej procedury należy użyć w celu skonfigurowania reguły dla zamówionych produktów z kategorii.</span><span class="sxs-lookup"><span data-stu-id="29fdf-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="29fdf-105">Reguły są definiowane dla określonej zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="29fdf-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="29fdf-106">Reguła dostępu do kategorii określa kategorie zaopatrzenia, do których mają dostęp pracownicy podczas tworzenia zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="29fdf-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="29fdf-107">Gdy pracownik tworzy zapotrzebowanie, stosowana zasada zakupów i reguła dostępu do kategorii zależą od firmy i jednostki operacyjnej, do której należy pracownik.</span><span class="sxs-lookup"><span data-stu-id="29fdf-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="29fdf-108">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="29fdf-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="29fdf-109">To zadanie zazwyczaj wykonuje kierownik ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="29fdf-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="29fdf-110">Znajdowanie zasad zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="29fdf-110">Find the procurement policy</span></span>
1. <span data-ttu-id="29fdf-111">Wybierz kolejno opcje Zaopatrzenie i sourcing > Ustawienia > Zasady > Zasady zakupów.</span><span class="sxs-lookup"><span data-stu-id="29fdf-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="29fdf-112">Kliknij łącze na zasadzie Procurement Policy USMF.</span><span class="sxs-lookup"><span data-stu-id="29fdf-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="29fdf-113">To jest zasada, do której dodasz regułę.</span><span class="sxs-lookup"><span data-stu-id="29fdf-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="29fdf-114">Musi to być aktywna zasada.</span><span class="sxs-lookup"><span data-stu-id="29fdf-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="29fdf-115">Tworzenie reguły dostępu do kategorii</span><span class="sxs-lookup"><span data-stu-id="29fdf-115">Create a category access rule</span></span>
1. <span data-ttu-id="29fdf-116">Wybierz regułę dostępu do kategorii.</span><span class="sxs-lookup"><span data-stu-id="29fdf-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="29fdf-117">Jeśli przycisk Utwórz regułę jest wygaszony, oznacza to, że już istnieje aktywna reguła dostępu do kategorii.</span><span class="sxs-lookup"><span data-stu-id="29fdf-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="29fdf-118">Sprawdź wartości w polach Data obowiązywania i Data ważności, aby określić, która data powoduje problem, zaznacz ją, a następnie kliknij przycisk Wycofanie reguły.</span><span class="sxs-lookup"><span data-stu-id="29fdf-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="29fdf-119">Jeśli przycisk Utwórz regułę jest dostępny, nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="29fdf-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="29fdf-120">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="29fdf-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="29fdf-121">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="29fdf-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="29fdf-122">Czas nie może się pokrywać z inną regułą, która jest już aktywna.</span><span class="sxs-lookup"><span data-stu-id="29fdf-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="29fdf-123">Wybierz kategorię, której będzie dotyczyć reguła.</span><span class="sxs-lookup"><span data-stu-id="29fdf-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="29fdf-124">Zapamiętaj lub zapisz, która to kategoria — będzie to później potrzebne.</span><span class="sxs-lookup"><span data-stu-id="29fdf-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="29fdf-125">Po wybraniu kategorii jej wszystkie kategorie nadrzędne są również dodawane do listy Wybrane kategorie.</span><span class="sxs-lookup"><span data-stu-id="29fdf-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="29fdf-126">Aby zastosować regułę do wszystkich podkategorii wybranej kategorii, zaznacz pole wyboru Uwzględnij podkategorie.</span><span class="sxs-lookup"><span data-stu-id="29fdf-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="29fdf-127">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="29fdf-127">Click Add.</span></span>
    * <span data-ttu-id="29fdf-128">Jeśli w opcji Uwzględnij regułę nadrzędną zaznaczysz wartość Tak, reguła zdefiniowana przez Ciebie dla kategorii nadrzędnej zostanie przypisana również do jej kategorii podrzędnych, jeśli kategorie podrzędne nie mają zdefiniowanej żadnej reguły.</span><span class="sxs-lookup"><span data-stu-id="29fdf-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="29fdf-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="29fdf-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="29fdf-130">Tworzenie reguły dla kategorii</span><span class="sxs-lookup"><span data-stu-id="29fdf-130">Create a category policy rule</span></span>
1. <span data-ttu-id="29fdf-131">Wybór reguły kategorii</span><span class="sxs-lookup"><span data-stu-id="29fdf-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="29fdf-132">Jeśli przycisk Utwórz regułę jest wyszarzony, zaznacz aktywną regułę, a następnie kliknij opcję Wycofanie reguły.</span><span class="sxs-lookup"><span data-stu-id="29fdf-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="29fdf-133">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="29fdf-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="29fdf-134">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="29fdf-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="29fdf-135">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="29fdf-135">Click Add.</span></span>
5. <span data-ttu-id="29fdf-136">Zaznacz tę samą kategorię, jak użyta w regule dostępu kategorii.</span><span class="sxs-lookup"><span data-stu-id="29fdf-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="29fdf-137">W polu Wybór dostawcy wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="29fdf-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="29fdf-138">Zaznacz regułę mającą kontrolować, jakiego rodzaju dostawców można wybierać dla kategorii podczas tworzenia zapotrzebowań.</span><span class="sxs-lookup"><span data-stu-id="29fdf-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="29fdf-139">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="29fdf-139">Click Close.</span></span>
    * <span data-ttu-id="29fdf-140">Zdefiniowane przez Ciebie reguły dotyczą zapotrzebowań typu Zużycie.</span><span class="sxs-lookup"><span data-stu-id="29fdf-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="29fdf-141">Jeśli trzeba zdefiniować zasady dla zapotrzebowań typu Uzupełnienie zapasów, należy utworzyć regułę dla typu reguły o nazwie „Reguła dostępu do kategorii uzupełniania zapasów”.</span><span class="sxs-lookup"><span data-stu-id="29fdf-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  

