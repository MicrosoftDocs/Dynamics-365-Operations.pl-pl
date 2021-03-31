---
title: Tworzenie nowego układu magazynu
description: W tym temacie opisano sposób konfigurowania informacji na temat lokalizacji w magazynie.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f6f97bc13bc27ec88570992872a256926522c52
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218712"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="a21dc-103">Tworzenie nowego układu magazynu</span><span class="sxs-lookup"><span data-stu-id="a21dc-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a21dc-104">W tym temacie opisano sposób konfigurowania informacji na temat lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a21dc-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="a21dc-105">Dotyczy to tylko magazynów utworzonych przy użyciu funkcji „podstawowego magazynowania” dostępnych w module Zarządzanie zapasami, a nie magazynów utworzonych w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="a21dc-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="a21dc-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="a21dc-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="a21dc-107">Ustawianie domyślnej pojemności lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a21dc-107">Set the default location capacity</span></span>
1. <span data-ttu-id="a21dc-108">Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="a21dc-109">Wybierz kartę **Lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="a21dc-110">W polu **Standardowa szerokość** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="a21dc-111">W polu **Standardowa długość** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="a21dc-112">W polu **Standardowa wysokość** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="a21dc-113">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-113">Select **Save**.</span></span>
7. <span data-ttu-id="a21dc-114">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="a21dc-115">Określanie formatu nazwy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="a21dc-115">Define the location name format</span></span>
1. <span data-ttu-id="a21dc-116">Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Podział magazynu > Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="a21dc-117">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-117">Select **New**.</span></span>
3. <span data-ttu-id="a21dc-118">W polu **Magazyn** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a21dc-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="a21dc-119">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a21dc-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="a21dc-120">W polu **Oddział** wybierz odpowiedni rekord z wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="a21dc-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="a21dc-121">Przełącz rozwinięcie sekcji **Nazwy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="a21dc-122">Opcje w tej sekcji definiują domyślny format nazw lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a21dc-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="a21dc-123">W naszym przykładzie uwzględnimy numery alei, regału i półki.</span><span class="sxs-lookup"><span data-stu-id="a21dc-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="a21dc-124">W opcji **Uwzględnij korytarz** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="a21dc-125">W opcji **Uwzględnij regał** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="a21dc-126">W polu **Format** dla regału wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a21dc-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="a21dc-127">W opcji **Uwzględnij półkę** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="a21dc-128">W polu **Format** dla półki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a21dc-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="a21dc-129">Określanie lokalizacji w magazynach</span><span class="sxs-lookup"><span data-stu-id="a21dc-129">Define warehouse locations</span></span>
1. <span data-ttu-id="a21dc-130">W okienku akcji kliknij pozycję **Magazyn**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="a21dc-131">Wybierz tę **Kreator lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="a21dc-132">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-132">Select **Next**.</span></span>
4. <span data-ttu-id="a21dc-133">Usuń zaznaczenie opcji **Doki załadunkowe**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="a21dc-134">Usuń zaznaczenie opcji **Lokalizacje zbiorcze**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="a21dc-135">Wybierz **Następny**, aż zostanie wybrana opcja **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="a21dc-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="a21dc-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-136">Close the page.</span></span>
8. <span data-ttu-id="a21dc-137">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="a21dc-137">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]