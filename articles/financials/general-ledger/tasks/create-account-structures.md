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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2183f88356fc8094781af147bf079c4e53ffb2b4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846710"
---
# <a name="create-account-structures"></a><span data-ttu-id="4847e-103">Tworzenie struktur kont</span><span class="sxs-lookup"><span data-stu-id="4847e-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4847e-104">Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="4847e-105">W krokach użyto danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4847e-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="4847e-106">Wybierz kolejno opcje Księga główna > Plan kont > Struktury > Skonfiguruj strukturę konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="4847e-107">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4847e-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="4847e-108">W polu Struktura konta wpisz nazwę opisującą przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="4847e-109">W polu Opis wprowadź opis określający przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="4847e-110">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="4847e-110">Click Create.</span></span>
6. <span data-ttu-id="4847e-111">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-111">Click Add segment.</span></span>
7. <span data-ttu-id="4847e-112">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="4847e-113">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-113">Click Add segment.</span></span>
9. <span data-ttu-id="4847e-114">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-114">Click Add segment.</span></span>
10. <span data-ttu-id="4847e-115">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="4847e-116">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-116">Click Add segment.</span></span>
12. <span data-ttu-id="4847e-117">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-117">Click Add segment.</span></span>
13. <span data-ttu-id="4847e-118">Na liście Wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="4847e-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="4847e-119">Kliknij przycisk Dodaj segment.</span><span class="sxs-lookup"><span data-stu-id="4847e-119">Click Add segment.</span></span>
15. <span data-ttu-id="4847e-120">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="4847e-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="4847e-121">Na przykład kliknij pole Konto główne.</span><span class="sxs-lookup"><span data-stu-id="4847e-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="4847e-122">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="4847e-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="4847e-123">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="4847e-124">Na przykład 600000.</span><span class="sxs-lookup"><span data-stu-id="4847e-124">For example, 600000.</span></span>  
18. <span data-ttu-id="4847e-125">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="4847e-126">Na przykład 699999.</span><span class="sxs-lookup"><span data-stu-id="4847e-126">For example, 699999.</span></span>  
19. <span data-ttu-id="4847e-127">Kliknij polecenie Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="4847e-127">Click Apply.</span></span>
20. <span data-ttu-id="4847e-128">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="4847e-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="4847e-129">Na przykład Dział.</span><span class="sxs-lookup"><span data-stu-id="4847e-129">For example, Department.</span></span>  
21. <span data-ttu-id="4847e-130">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="4847e-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="4847e-131">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="4847e-132">Na przykład 022.</span><span class="sxs-lookup"><span data-stu-id="4847e-132">For example, 022.</span></span>  
23. <span data-ttu-id="4847e-133">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="4847e-134">Na przykład 031.</span><span class="sxs-lookup"><span data-stu-id="4847e-134">For example, 031.</span></span>  
24. <span data-ttu-id="4847e-135">Kliknij opcję Dodaj nowe kryteria.</span><span class="sxs-lookup"><span data-stu-id="4847e-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="4847e-136">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="4847e-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="4847e-137">W polu Wartość wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="4847e-138">Na przykład 033.</span><span class="sxs-lookup"><span data-stu-id="4847e-138">For example, 033.</span></span>  
27. <span data-ttu-id="4847e-139">W polu „za pomocą” wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="4847e-140">Na przykład 034.</span><span class="sxs-lookup"><span data-stu-id="4847e-140">For example, 034.</span></span>  
28. <span data-ttu-id="4847e-141">Kliknij polecenie Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="4847e-141">Click Apply.</span></span>
29. <span data-ttu-id="4847e-142">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="4847e-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="4847e-143">Na przykład MPK.</span><span class="sxs-lookup"><span data-stu-id="4847e-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="4847e-144">W polu CostCenter wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="4847e-145">Na przykład 007..021.</span><span class="sxs-lookup"><span data-stu-id="4847e-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="4847e-146">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="4847e-146">Click Add.</span></span>
32. <span data-ttu-id="4847e-147">W polu MainAccount wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="4847e-148">Na przykład 600000..699999.</span><span class="sxs-lookup"><span data-stu-id="4847e-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="4847e-149">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="4847e-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="4847e-150">Na przykład Dział.</span><span class="sxs-lookup"><span data-stu-id="4847e-150">For example, Department.</span></span>  
34. <span data-ttu-id="4847e-151">W polu Dział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="4847e-152">Na przykład 032.</span><span class="sxs-lookup"><span data-stu-id="4847e-152">For example, 032.</span></span>  
35. <span data-ttu-id="4847e-153">W polu CostCenter wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4847e-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="4847e-154">Na przykład 086.</span><span class="sxs-lookup"><span data-stu-id="4847e-154">For example, 086.</span></span>  
36. <span data-ttu-id="4847e-155">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="4847e-155">Click Validate.</span></span>
37. <span data-ttu-id="4847e-156">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="4847e-156">Click Activate.</span></span>
38. <span data-ttu-id="4847e-157">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="4847e-157">Click Activate.</span></span>

