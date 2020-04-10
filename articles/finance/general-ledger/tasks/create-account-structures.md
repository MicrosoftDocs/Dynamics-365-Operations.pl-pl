---
title: Tworzenie struktur kont
description: Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: b75ee76a1fb874652415a2174441f629955d763a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145170"
---
# <a name="create-account-structures"></a><span data-ttu-id="73925-103">Tworzenie struktur kont</span><span class="sxs-lookup"><span data-stu-id="73925-103">Create account structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="73925-104">Ten przewodnik po zadaniach prowadzi przez proces tworzenia struktury konta.</span><span class="sxs-lookup"><span data-stu-id="73925-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="73925-105">W krokach użyto danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="73925-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="73925-106">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Konfigurowanie struktur kont**.</span><span class="sxs-lookup"><span data-stu-id="73925-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="73925-107">W **okienku akcji** kliknij **Nowe**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="73925-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="73925-108">W polu **Struktura konta** wpisz nazwę opisującą przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="73925-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="73925-109">W polu **Opis** wprowadź opis określający przeznaczenie struktury konta.</span><span class="sxs-lookup"><span data-stu-id="73925-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="73925-110">Kliknij **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="73925-110">Click **Create**.</span></span>
6. <span data-ttu-id="73925-111">W **Segmenty i dozwolone wartości** kliknij przycisk **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="73925-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="73925-112">Na liście wymiary wybierz wymiar, który chcesz dodać do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="73925-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="73925-113">Na końcu listy kliknij przycisk **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="73925-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="73925-114">W razie potrzeby powtórz kroki od 6 do 9.</span><span class="sxs-lookup"><span data-stu-id="73925-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="73925-115">W sekcji **Szczegóły dozwolonych wartości** wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="73925-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="73925-116">Na przykład kliknij pole **Konto główne**.</span><span class="sxs-lookup"><span data-stu-id="73925-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="73925-117">W polu **Operator** wybierz opcję taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="73925-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="73925-118">W polu **Wartość** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="73925-119">Na przykład 600000.</span><span class="sxs-lookup"><span data-stu-id="73925-119">For example, 600000.</span></span>  
13. <span data-ttu-id="73925-120">W polu **za pomocą** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-120">In the **through** field, type a value.</span></span> <span data-ttu-id="73925-121">Na przykład 699999.</span><span class="sxs-lookup"><span data-stu-id="73925-121">For example, 699999.</span></span>  
14. <span data-ttu-id="73925-122">W sekcji **Szczegóły dozwolonych wartości** kliknij przycisk **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="73925-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="73925-123">W razie potrzeby powtórz kroki od 10 do 15.</span><span class="sxs-lookup"><span data-stu-id="73925-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="73925-124">W sekcji **Szczegóły dozwolonych wartości** kliknij przycisk **Dodaj nowe kryteria**.</span><span class="sxs-lookup"><span data-stu-id="73925-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="73925-125">W polu Operator wybierz opcję, taką jak „zawiera się między” lub „zawiera”.</span><span class="sxs-lookup"><span data-stu-id="73925-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="73925-126">W polu **Wartość** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="73925-127">Na przykład 033.</span><span class="sxs-lookup"><span data-stu-id="73925-127">For example, 033.</span></span>  
19. <span data-ttu-id="73925-128">W polu **za pomocą** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-128">In the **through** field, type a value.</span></span> <span data-ttu-id="73925-129">Na przykład 034.</span><span class="sxs-lookup"><span data-stu-id="73925-129">For example, 034.</span></span>  
20. <span data-ttu-id="73925-130">Kliknij polecenie **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="73925-130">Click **Apply**.</span></span>
21. <span data-ttu-id="73925-131">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="73925-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="73925-132">Na przykład MPK.</span><span class="sxs-lookup"><span data-stu-id="73925-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="73925-133">W **polu CostCenter** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="73925-134">Na przykład 007..021.</span><span class="sxs-lookup"><span data-stu-id="73925-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="73925-135">W **Segmenty i dozwolone wartości** kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="73925-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="73925-136">W polu **MainAccount** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="73925-137">Na przykład 600000..699999.</span><span class="sxs-lookup"><span data-stu-id="73925-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="73925-138">W siatce wybierz segment w celu edytowania dozwolonych wartości.</span><span class="sxs-lookup"><span data-stu-id="73925-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="73925-139">Na przykład Dział.</span><span class="sxs-lookup"><span data-stu-id="73925-139">For example, Department.</span></span>  
26. <span data-ttu-id="73925-140">W polu Dział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-140">In the Department field, type a value.</span></span> <span data-ttu-id="73925-141">Na przykład 032.</span><span class="sxs-lookup"><span data-stu-id="73925-141">For example, 032.</span></span>  
27. <span data-ttu-id="73925-142">W polu CostCenter wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="73925-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="73925-143">Na przykład 086.</span><span class="sxs-lookup"><span data-stu-id="73925-143">For example, 086.</span></span>  
28. <span data-ttu-id="73925-144">W **okienku akcji** kliknij pozycję **Weryfikuj**.</span><span class="sxs-lookup"><span data-stu-id="73925-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="73925-145">W **okienku akcji** kliknij pozycję **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="73925-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="73925-146">Kliknij **Aktywacja**.</span><span class="sxs-lookup"><span data-stu-id="73925-146">Click **Activate**.</span></span>

