---
title: Definiowanie zasad i reguł uprawnień do świadczenia
description: W tym artykule pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: fa507591fc89eaebf617deedb15b15a0f93f971d
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010271"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="5f2ea-103">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="5f2ea-103">Define benefit eligibility rules and policies</span></span>

<span data-ttu-id="5f2ea-104">W tym artykule pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-104">This article shows you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="5f2ea-105">Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="5f2ea-106">Tworzenie typu reguły uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="5f2ea-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="5f2ea-107">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="5f2ea-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-108">Click New.</span></span>
3. <span data-ttu-id="5f2ea-109">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="5f2ea-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5f2ea-111">W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5f2ea-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="5f2ea-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-113">Click Save.</span></span>
8. <span data-ttu-id="5f2ea-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="5f2ea-115">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="5f2ea-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="5f2ea-116">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="5f2ea-117">Wybierz istniejącą zasadę świadczenia.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="5f2ea-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5f2ea-119">Przełącz rozwinięcie sekcji Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="5f2ea-120">W tym miejscu można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="5f2ea-121">Rozwiń lub zwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="5f2ea-122">Na liście odszukaj utworzoną wcześniej regułę.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="5f2ea-123">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="5f2ea-124">W polu Data obowiązywania wprowadź dzień, od którego zasada ma obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="5f2ea-125">Ustawienie dat obowiązywania i zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="5f2ea-126">Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Where opis stanowiska równa się Menedżer sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="5f2ea-127">W regule można dodać wiele instrukcji Where z operatorami And lub Or.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="5f2ea-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-128">Click OK.</span></span>
11. <span data-ttu-id="5f2ea-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-129">Close the page.</span></span>
12. <span data-ttu-id="5f2ea-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="5f2ea-131">Przypisywanie reguły do świadczenia</span><span class="sxs-lookup"><span data-stu-id="5f2ea-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="5f2ea-132">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="5f2ea-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5f2ea-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5f2ea-135">Rozwiń lub zwiń sekcję Reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="5f2ea-136">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-136">Click Edit.</span></span>
6. <span data-ttu-id="5f2ea-137">W polu Uprawnienie na liście zaznacz opcję Oparte na regułach.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="5f2ea-138">W polu Typ reguły kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="5f2ea-139">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="5f2ea-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="5f2ea-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-141">Click Save.</span></span>
11. <span data-ttu-id="5f2ea-142">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="5f2ea-142">Close the form.</span></span>

