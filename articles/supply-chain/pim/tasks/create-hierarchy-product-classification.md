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
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 439df63a4f8f0cc1c030554d18f80e9934c88b00
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986198"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="851c5-103">Tworzenie hierarchii klasyfikacji produktów</span><span class="sxs-lookup"><span data-stu-id="851c5-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="851c5-104">W tej procedurze pokazano, jak utworzyć nową hierarchię kategorii oraz przypisać typ hierarchii kodów asortymentu.</span><span class="sxs-lookup"><span data-stu-id="851c5-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="851c5-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="851c5-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="851c5-106">Ta procedura jest przeznaczona dla menedżera kategorii.</span><span class="sxs-lookup"><span data-stu-id="851c5-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="851c5-107">Tworzenie nowej hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="851c5-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="851c5-108">Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie informacjami o produktach > Ustawienia > Kategorie i atrybuty > Hierarchie kategorii.**</span><span class="sxs-lookup"><span data-stu-id="851c5-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="851c5-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-109">Click **New**.</span></span>
3. <span data-ttu-id="851c5-110">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="851c5-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="851c5-112">Kliknij **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="851c5-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="851c5-113">Tworzenie hierarchii</span><span class="sxs-lookup"><span data-stu-id="851c5-113">Build the hierarchy</span></span>
1. <span data-ttu-id="851c5-114">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-114">Click **New** category node.</span></span>
2. <span data-ttu-id="851c5-115">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="851c5-116">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="851c5-117">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="851c5-118">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-118">Click **New** category node.</span></span>
6. <span data-ttu-id="851c5-119">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="851c5-120">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="851c5-121">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="851c5-122">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-122">Click **New** category node.</span></span>
10. <span data-ttu-id="851c5-123">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="851c5-124">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="851c5-125">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="851c5-126">Kliknij węzeł kategorii **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-126">Click **New** category node.</span></span>
14. <span data-ttu-id="851c5-127">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="851c5-128">W polu **Kod** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="851c5-129">W polu **Przyjazna nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="851c5-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="851c5-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="851c5-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="851c5-131">Klasyfikowanie hierarchii</span><span class="sxs-lookup"><span data-stu-id="851c5-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="851c5-132">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="851c5-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="851c5-133">W **okienku akcji** kliknij pozycję **Hierarchia kategorii**.</span><span class="sxs-lookup"><span data-stu-id="851c5-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="851c5-134">Kliknij opcję **Powiązanie typu hierarchii**.</span><span class="sxs-lookup"><span data-stu-id="851c5-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="851c5-135">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="851c5-135">Click **New**.</span></span>
5. <span data-ttu-id="851c5-136">W polu **Typ hierarchii kategorii** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="851c5-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="851c5-137">Wybierz **typ hierarchii kategorii kodów asortymentu dla klasyfikacji produktów**.</span><span class="sxs-lookup"><span data-stu-id="851c5-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="851c5-138">W polu **Hierarchia kategorii** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="851c5-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="851c5-139">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="851c5-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="851c5-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="851c5-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="851c5-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="851c5-141">Close the page.</span></span>

