---
title: Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów
description: Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66921d5eddb31ffba0946c41f634719a684e4ad1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976194"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="abe14-103">Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="abe14-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abe14-104">Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="abe14-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="abe14-105">Księgowy kosztów pilnuje, aby koszty zostały rozdzielone między centra kosztów na podstawie wybranej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="abe14-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="abe14-106">Zasada i odnośne reguły są przypisywane do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="abe14-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="abe14-107">W tym przewodniku po zadaniu jest wykorzystywany przykład do pokazania, jak utworzyć zasadę dystrybucji kosztów i odpowiednie reguły.</span><span class="sxs-lookup"><span data-stu-id="abe14-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="abe14-108">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="abe14-108">Create a policy</span></span>
1. <span data-ttu-id="abe14-109">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady dystrybucji kosztów.</span><span class="sxs-lookup"><span data-stu-id="abe14-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="abe14-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="abe14-110">Click New.</span></span>
3. <span data-ttu-id="abe14-111">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="abe14-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="abe14-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="abe14-113">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-114">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="abe14-114">Select Organization.</span></span>  
6. <span data-ttu-id="abe14-115">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-116">Wybierz opcję CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="abe14-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="abe14-117">W polu Wymiar statystyczny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-118">Wybierz opcję Elementy statystyczne.</span><span class="sxs-lookup"><span data-stu-id="abe14-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="abe14-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abe14-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="abe14-120">Tworzenie reguł dla zasad</span><span class="sxs-lookup"><span data-stu-id="abe14-120">Create rules for the policy</span></span>
1. <span data-ttu-id="abe14-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="abe14-121">Click New.</span></span>
2. <span data-ttu-id="abe14-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="abe14-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="abe14-123">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-124">Rozwiń hierarchię i wybierz pozycję 094.</span><span class="sxs-lookup"><span data-stu-id="abe14-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="abe14-125">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-126">Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605110 Sprzątanie.</span><span class="sxs-lookup"><span data-stu-id="abe14-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="abe14-127">W polu Zachowanie kosztów wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="abe14-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="abe14-128">Wybierz opcję Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="abe14-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="abe14-129">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="abe14-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="abe14-130">Click New.</span></span>
8. <span data-ttu-id="abe14-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="abe14-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="abe14-132">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-133">Rozwiń hierarchię i wybierz pozycję 094.</span><span class="sxs-lookup"><span data-stu-id="abe14-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="abe14-134">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="abe14-135">Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605150 Najem.</span><span class="sxs-lookup"><span data-stu-id="abe14-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="abe14-136">W polu Zachowanie kosztów wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="abe14-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="abe14-137">Wybierz opcję Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="abe14-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="abe14-138">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="abe14-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abe14-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="abe14-140">Przypisywanie reguł do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="abe14-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="abe14-141">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="abe14-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="abe14-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="abe14-142">Click New.</span></span>
3. <span data-ttu-id="abe14-143">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="abe14-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="abe14-144">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="abe14-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="abe14-145">Zaznacz dzień 1 września w odpowiednim roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="abe14-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="abe14-146">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="abe14-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="abe14-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="abe14-147">Click Save.</span></span>

