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
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d040f9495c7fb36985b5f96c15ac43aa226da24
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841328"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="0c513-103">Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="0c513-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0c513-104">Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="0c513-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="0c513-105">Księgowy kosztów pilnuje, aby koszty zostały rozdzielone między centra kosztów na podstawie wybranej podstawy alokacji.</span><span class="sxs-lookup"><span data-stu-id="0c513-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="0c513-106">Zasada i odnośne reguły są przypisywane do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="0c513-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="0c513-107">W tym przewodniku po zadaniu jest wykorzystywany przykład do pokazania, jak utworzyć zasadę dystrybucji kosztów i odpowiednie reguły.</span><span class="sxs-lookup"><span data-stu-id="0c513-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="0c513-108">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="0c513-108">Create a policy</span></span>
1. <span data-ttu-id="0c513-109">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady dystrybucji kosztów.</span><span class="sxs-lookup"><span data-stu-id="0c513-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="0c513-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c513-110">Click New.</span></span>
3. <span data-ttu-id="0c513-111">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="0c513-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="0c513-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0c513-113">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-114">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="0c513-114">Select Organization.</span></span>  
6. <span data-ttu-id="0c513-115">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-116">Wybierz opcję CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="0c513-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="0c513-117">W polu Wymiar statystyczny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-118">Wybierz opcję Elementy statystyczne.</span><span class="sxs-lookup"><span data-stu-id="0c513-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="0c513-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0c513-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="0c513-120">Tworzenie reguł dla zasad</span><span class="sxs-lookup"><span data-stu-id="0c513-120">Create rules for the policy</span></span>
1. <span data-ttu-id="0c513-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c513-121">Click New.</span></span>
2. <span data-ttu-id="0c513-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0c513-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="0c513-123">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-124">Rozwiń hierarchię i wybierz pozycję 094.</span><span class="sxs-lookup"><span data-stu-id="0c513-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="0c513-125">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-126">Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605110 Sprzątanie.</span><span class="sxs-lookup"><span data-stu-id="0c513-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="0c513-127">W polu Zachowanie kosztów wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0c513-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="0c513-128">Wybierz opcję Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="0c513-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="0c513-129">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="0c513-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c513-130">Click New.</span></span>
8. <span data-ttu-id="0c513-131">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0c513-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0c513-132">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-133">Rozwiń hierarchię i wybierz pozycję 094.</span><span class="sxs-lookup"><span data-stu-id="0c513-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="0c513-134">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="0c513-135">Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605150 Najem.</span><span class="sxs-lookup"><span data-stu-id="0c513-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="0c513-136">W polu Zachowanie kosztów wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0c513-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="0c513-137">Wybierz opcję Koszt stały.</span><span class="sxs-lookup"><span data-stu-id="0c513-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="0c513-138">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="0c513-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0c513-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="0c513-140">Przypisywanie reguł do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="0c513-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="0c513-141">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="0c513-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="0c513-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0c513-142">Click New.</span></span>
3. <span data-ttu-id="0c513-143">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0c513-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0c513-144">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="0c513-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="0c513-145">Zaznacz dzień 1 września w odpowiednim roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="0c513-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="0c513-146">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c513-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="0c513-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0c513-147">Click Save.</span></span>

