---
title: Tworzenie hierarchii klasyfikacji produktów
description: W tej procedurze pokazano, jak utworzyć nową hierarchię kategorii oraz przypisać typ hierarchii kodów asortymentu.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0ff1a2ba20059d3fcb0347220e6e81130e03ac0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203740"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="116c6-103">Tworzenie hierarchii klasyfikacji produktów</span><span class="sxs-lookup"><span data-stu-id="116c6-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="116c6-104">W tej procedurze pokazano, jak utworzyć nową hierarchię kategorii oraz przypisać typ hierarchii kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="116c6-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="116c6-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="116c6-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="116c6-106">Ta procedura jest przeznaczona dla menedżera kategorii.</span><span class="sxs-lookup"><span data-stu-id="116c6-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="116c6-107">Tworzenie nowej hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="116c6-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="116c6-108">Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie informacjami o produktach > Ustawienia > Kategorie i atrybuty > Hierarchie kategorii.**</span><span class="sxs-lookup"><span data-stu-id="116c6-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="116c6-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-109">Click **New**.</span></span>
3. <span data-ttu-id="116c6-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="116c6-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="116c6-112">Kliknij **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="116c6-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="116c6-113">Tworzenie hierarchii</span><span class="sxs-lookup"><span data-stu-id="116c6-113">Build the hierarchy</span></span>
1. <span data-ttu-id="116c6-114">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-114">Click **New** category node.</span></span>
2. <span data-ttu-id="116c6-115">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="116c6-116">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="116c6-117">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="116c6-118">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-118">Click **New** category node.</span></span>
6. <span data-ttu-id="116c6-119">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="116c6-120">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="116c6-121">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="116c6-122">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-122">Click **New** category node.</span></span>
10. <span data-ttu-id="116c6-123">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="116c6-124">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="116c6-125">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="116c6-126">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-126">Click **New** category node.</span></span>
14. <span data-ttu-id="116c6-127">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="116c6-128">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="116c6-129">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="116c6-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="116c6-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="116c6-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="116c6-131">Klasyfikowanie hierarchii</span><span class="sxs-lookup"><span data-stu-id="116c6-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="116c6-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="116c6-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="116c6-133">W **okienku akcji** kliknij pozycję **Hierarchia kategorii**.</span><span class="sxs-lookup"><span data-stu-id="116c6-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="116c6-134">Kliknij opcję **Powiązanie typu hierarchii**.</span><span class="sxs-lookup"><span data-stu-id="116c6-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="116c6-135">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="116c6-135">Click **New**.</span></span>
5. <span data-ttu-id="116c6-136">W polu **Typ hierarchii kategorii** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="116c6-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="116c6-137">Wybierz **typ hierarchii kategorii kodów asortymentu dla klasyfikacji produktów**.</span><span class="sxs-lookup"><span data-stu-id="116c6-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="116c6-138">W polu **Hierarchia kategorii** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="116c6-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="116c6-139">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="116c6-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="116c6-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="116c6-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="116c6-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="116c6-141">Close the page.</span></span>

