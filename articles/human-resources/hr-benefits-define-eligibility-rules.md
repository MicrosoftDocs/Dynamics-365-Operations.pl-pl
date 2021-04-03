---
title: Definiowanie zasad i reguł uprawnień do świadczenia
description: W tym artykule pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 39a9a1c96ae2a12a32b3c5fbc67571bcf983c898
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467994"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="c5f51-103">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="c5f51-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c5f51-104">W tym temacie pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="c5f51-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="c5f51-105">Tworzenie typu reguły uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="c5f51-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="c5f51-106">Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="c5f51-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-107">Select **New**.</span></span>
3. <span data-ttu-id="c5f51-108">Wprowadź wartość w polu **Nazwa reguły**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="c5f51-109">W polu **Opis** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c5f51-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="c5f51-110">W polu **Nazwa kwerendy** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c5f51-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c5f51-111">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c5f51-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="c5f51-112">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-112">Select **Save**.</span></span>
8. <span data-ttu-id="c5f51-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c5f51-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="c5f51-114">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="c5f51-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="c5f51-115">Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="c5f51-116">Wybierz istniejącą zasadę świadczenia.</span><span class="sxs-lookup"><span data-stu-id="c5f51-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="c5f51-117">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c5f51-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="c5f51-118">Przełącz rozwinięcie sekcji **Organizacje zasad**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="c5f51-119">Można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.</span><span class="sxs-lookup"><span data-stu-id="c5f51-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="c5f51-120">Rozwiń lub zwiń sekcję **Reguły zasad**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="c5f51-121">Na liście odszukaj utworzoną wcześniej regułę.</span><span class="sxs-lookup"><span data-stu-id="c5f51-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="c5f51-122">Wybierz pozycję **Utwórz regułę**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="c5f51-123">W polu **Data obowiązywania** wprowadź dzień, od którego zasada ma obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="c5f51-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="c5f51-124">Ustawienie dat zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="c5f51-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="c5f51-125">W razie potrzeby dodaj klauzulę where do pola **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="c5f51-126">Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Gdzie opis stanowiska równa się Menedżer sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c5f51-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="c5f51-127">W regule można dodać wiele instrukcji Where.</span><span class="sxs-lookup"><span data-stu-id="c5f51-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="c5f51-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-128">Select **OK**.</span></span>
11. <span data-ttu-id="c5f51-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c5f51-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="c5f51-130">Przypisywanie reguły do świadczenia</span><span class="sxs-lookup"><span data-stu-id="c5f51-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="c5f51-131">Wybierz kolejno opcje **Zasoby ludzkie > Świadczenia > Świadczenia**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="c5f51-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c5f51-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c5f51-133">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c5f51-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="c5f51-134">Rozwiń lub zwiń sekcję **Reguły uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="c5f51-135">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-135">Select **Edit**.</span></span>
6. <span data-ttu-id="c5f51-136">W polu **Uprawnienie** zaznacz regułę.</span><span class="sxs-lookup"><span data-stu-id="c5f51-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="c5f51-137">W polu **Typ reguły** zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="c5f51-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="c5f51-138">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c5f51-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="c5f51-139">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c5f51-139">Select **Save**.</span></span>
11. <span data-ttu-id="c5f51-140">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="c5f51-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]