--- 
title: "Definiowanie zasad i reguł uprawnień do świadczenia"
description: "W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a9d0d9a3f278a09e89311ee75b6f95fb4f3b04cb
ms.openlocfilehash: 329598430edf07e3a743b0d7061a51825f12a066
ms.contentlocale: pl-pl
ms.lasthandoff: 02/02/2018

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="712c4-103">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="712c4-103">Define benefit eligibility rules and policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="712c4-104">W tym nagraniu pokazano sposób tworzenia reguł i zasad uprawnień do świadczeń, a następnie przypisywania reguł do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="712c4-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="712c4-105">Dane wykorzystane do stworzenia tego nagrania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="712c4-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="712c4-106">Tworzenie typu reguły uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="712c4-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="712c4-107">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Typy reguł uprawnień do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="712c4-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="712c4-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="712c4-108">Click New.</span></span>
3. <span data-ttu-id="712c4-109">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="712c4-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="712c4-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="712c4-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="712c4-111">W polu Nazwa kwerendy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="712c4-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="712c4-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="712c4-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="712c4-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="712c4-113">Click Save.</span></span>
8. <span data-ttu-id="712c4-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="712c4-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="712c4-115">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="712c4-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="712c4-116">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Uprawnienie > Zasady uprawnienia do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="712c4-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="712c4-117">Wybierz istniejącą zasadę świadczenia.</span><span class="sxs-lookup"><span data-stu-id="712c4-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="712c4-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="712c4-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="712c4-119">Przełącz rozwinięcie sekcji Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="712c4-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="712c4-120">W tym miejscu można dodać lub usunąć wszelkie organizacje, które mają zostać uwzględnione w zasadach.</span><span class="sxs-lookup"><span data-stu-id="712c4-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="712c4-121">Rozwiń lub zwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="712c4-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="712c4-122">Na liście odszukaj utworzoną wcześniej regułę.</span><span class="sxs-lookup"><span data-stu-id="712c4-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="712c4-123">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="712c4-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="712c4-124">W polu Data obowiązywania wprowadź dzień, od którego zasada ma obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="712c4-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="712c4-125">Ustawienie dat obowiązywania i zakończenia umożliwi wprowadzanie w przyszłości zmian w regułach i wyeliminowanie potrzeby wracania do zasad, jeśli zechcesz, aby te zmiany zaczęły obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="712c4-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="712c4-126">Na przykład jeżeli chcesz, aby reguła była stosowana tylko do menedżerów sprzedaży, można utworzyć klauzulę Where o treści: Where opis stanowiska równa się Menedżer sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="712c4-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="712c4-127">W regule można dodać wiele instrukcji Where z operatorami And lub Or.</span><span class="sxs-lookup"><span data-stu-id="712c4-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="712c4-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="712c4-128">Click OK.</span></span>
11. <span data-ttu-id="712c4-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="712c4-129">Close the page.</span></span>
12. <span data-ttu-id="712c4-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="712c4-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="712c4-131">Przypisywanie reguły do świadczenia</span><span class="sxs-lookup"><span data-stu-id="712c4-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="712c4-132">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.</span><span class="sxs-lookup"><span data-stu-id="712c4-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="712c4-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="712c4-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="712c4-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="712c4-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="712c4-135">Rozwiń lub zwiń sekcję Reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="712c4-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="712c4-136">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="712c4-136">Click Edit.</span></span>
6. <span data-ttu-id="712c4-137">W polu Uprawnienie na liście zaznacz opcję Oparte na regułach.</span><span class="sxs-lookup"><span data-stu-id="712c4-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="712c4-138">W polu Typ reguły kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="712c4-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="712c4-139">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="712c4-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="712c4-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="712c4-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="712c4-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="712c4-141">Click Save.</span></span>
11. <span data-ttu-id="712c4-142">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="712c4-142">Close the form.</span></span>


