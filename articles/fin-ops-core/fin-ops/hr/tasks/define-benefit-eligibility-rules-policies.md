---
title: Definiowanie zasad i reguł uprawnień do świadczenia
description: W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d35266c95cfbf3473a14fec47a1c748229dd25
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190564"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="e4b4c-103">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="e4b4c-103">Define benefit eligibility rules and policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4b4c-104">W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="e4b4c-105">Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="e4b4c-106">Tworzenie typu reguły uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="e4b4c-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="e4b4c-107">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="e4b4c-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-108">Click New.</span></span>
3. <span data-ttu-id="e4b4c-109">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="e4b4c-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e4b4c-111">W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="e4b4c-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e4b4c-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-113">Click Save.</span></span>
8. <span data-ttu-id="e4b4c-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="e4b4c-115">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="e4b4c-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="e4b4c-116">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="e4b4c-117">Wybierz istniejącą zasadę świadczenia.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="e4b4c-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e4b4c-119">Przełącz rozwinięcie sekcji Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="e4b4c-120">W tym miejscu można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="e4b4c-121">Rozwiń lub zwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="e4b4c-122">Na liście odszukaj utworzoną wcześniej regułę.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="e4b4c-123">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="e4b4c-124">W polu Data obowiązywania wprowadź dzień, od którego zasada ma obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="e4b4c-125">Ustawienie dat obowiązywania i zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="e4b4c-126">Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Where opis stanowiska równa się Menedżer sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="e4b4c-127">W regule można dodać wiele instrukcji Where z operatorami And lub Or.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="e4b4c-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-128">Click OK.</span></span>
11. <span data-ttu-id="e4b4c-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-129">Close the page.</span></span>
12. <span data-ttu-id="e4b4c-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="e4b4c-131">Przypisywanie reguły do świadczenia</span><span class="sxs-lookup"><span data-stu-id="e4b4c-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="e4b4c-132">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="e4b4c-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e4b4c-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e4b4c-135">Rozwiń lub zwiń sekcję Reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="e4b4c-136">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-136">Click Edit.</span></span>
6. <span data-ttu-id="e4b4c-137">W polu Uprawnienie na liście zaznacz opcję Oparte na regułach.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="e4b4c-138">W polu Typ reguły kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="e4b4c-139">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="e4b4c-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e4b4c-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-141">Click Save.</span></span>
11. <span data-ttu-id="e4b4c-142">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="e4b4c-142">Close the form.</span></span>

