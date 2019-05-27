---
title: Tworzenie struktur kont
description: Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7dd71cc072d49f47b1d77d3a688984cd4aaa624
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571289"
---
# <a name="create-account-structures"></a><span data-ttu-id="c2577-103">Tworzenie struktur kont</span><span class="sxs-lookup"><span data-stu-id="c2577-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2577-104">Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="c2577-105">W krokach użyto danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c2577-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="c2577-106">Wybierz kolejno opcje Księga główna > Plan kont > Struktury > Skonfiguruj strukturę konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="c2577-107">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c2577-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="c2577-108">W polu Struktura konta wpisz nazwę opisującą przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="c2577-109">W polu Opis wprowadź opis określający przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="c2577-110">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="c2577-110">Click Create.</span></span>
6. <span data-ttu-id="c2577-111">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-111">Click Add segment.</span></span>
7. <span data-ttu-id="c2577-112">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="c2577-113">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-113">Click Add segment.</span></span>
9. <span data-ttu-id="c2577-114">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-114">Click Add segment.</span></span>
10. <span data-ttu-id="c2577-115">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="c2577-116">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-116">Click Add segment.</span></span>
12. <span data-ttu-id="c2577-117">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-117">Click Add segment.</span></span>
13. <span data-ttu-id="c2577-118">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="c2577-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="c2577-119">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="c2577-119">Click Add segment.</span></span>
15. <span data-ttu-id="c2577-120">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="c2577-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="c2577-121">Na przykład kliknij pole Konto główne.</span><span class="sxs-lookup"><span data-stu-id="c2577-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="c2577-122">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="c2577-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="c2577-123">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="c2577-124">Na przykład 600000.</span><span class="sxs-lookup"><span data-stu-id="c2577-124">For example, 600000.</span></span>  
18. <span data-ttu-id="c2577-125">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="c2577-126">Na przykład 699999.</span><span class="sxs-lookup"><span data-stu-id="c2577-126">For example, 699999.</span></span>  
19. <span data-ttu-id="c2577-127">Kliknij polecenie Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="c2577-127">Click Apply.</span></span>
20. <span data-ttu-id="c2577-128">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="c2577-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="c2577-129">Na przykład Dział.</span><span class="sxs-lookup"><span data-stu-id="c2577-129">For example, Department.</span></span>  
21. <span data-ttu-id="c2577-130">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="c2577-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="c2577-131">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="c2577-132">Na przykład 022.</span><span class="sxs-lookup"><span data-stu-id="c2577-132">For example, 022.</span></span>  
23. <span data-ttu-id="c2577-133">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="c2577-134">Na przykład 031.</span><span class="sxs-lookup"><span data-stu-id="c2577-134">For example, 031.</span></span>  
24. <span data-ttu-id="c2577-135">Kliknij opcję Dodaj nowe kryteria.</span><span class="sxs-lookup"><span data-stu-id="c2577-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="c2577-136">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="c2577-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="c2577-137">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="c2577-138">Na przykład 033.</span><span class="sxs-lookup"><span data-stu-id="c2577-138">For example, 033.</span></span>  
27. <span data-ttu-id="c2577-139">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="c2577-140">Na przykład 034.</span><span class="sxs-lookup"><span data-stu-id="c2577-140">For example, 034.</span></span>  
28. <span data-ttu-id="c2577-141">Kliknij polecenie Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="c2577-141">Click Apply.</span></span>
29. <span data-ttu-id="c2577-142">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="c2577-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="c2577-143">Na przykład MPK.</span><span class="sxs-lookup"><span data-stu-id="c2577-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="c2577-144">W polu CostCenter wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="c2577-145">Na przykład 007..021.</span><span class="sxs-lookup"><span data-stu-id="c2577-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="c2577-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c2577-146">Click Add.</span></span>
32. <span data-ttu-id="c2577-147">W polu MainAccount wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="c2577-148">Na przykład 600000..699999.</span><span class="sxs-lookup"><span data-stu-id="c2577-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="c2577-149">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="c2577-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="c2577-150">Na przykład Dział.</span><span class="sxs-lookup"><span data-stu-id="c2577-150">For example, Department.</span></span>  
34. <span data-ttu-id="c2577-151">W polu Dział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="c2577-152">Na przykład 032.</span><span class="sxs-lookup"><span data-stu-id="c2577-152">For example, 032.</span></span>  
35. <span data-ttu-id="c2577-153">W polu CostCenter wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2577-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="c2577-154">Na przykład 086.</span><span class="sxs-lookup"><span data-stu-id="c2577-154">For example, 086.</span></span>  
36. <span data-ttu-id="c2577-155">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="c2577-155">Click Validate.</span></span>
37. <span data-ttu-id="c2577-156">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="c2577-156">Click Activate.</span></span>
38. <span data-ttu-id="c2577-157">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="c2577-157">Click Activate.</span></span>

