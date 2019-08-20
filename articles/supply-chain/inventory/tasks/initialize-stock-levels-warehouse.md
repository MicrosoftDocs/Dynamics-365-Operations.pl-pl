---
title: Inicjowanie poziomów zapasów w magazynie
description: W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych).
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbd6dc6c2e5b7c1abe6e19f00a5df285e0147a92
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845404"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="d8b16-103">Inicjowanie poziomów zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="d8b16-103">Initialize stock levels in the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d8b16-104">W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych).</span><span class="sxs-lookup"><span data-stu-id="d8b16-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="d8b16-105">Zadania z przewodnika można wykonać na danych firmy demonstracyjnej USMF, gdzie wszystkie warunki wstępne, takie jak nazwa arkusza, ustawienia towaru, profile księgowania i konta, są dostępne.</span><span class="sxs-lookup"><span data-stu-id="d8b16-105">(It’s also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="d8b16-106">Przewodnik proponuje określone wartości dla używanego towaru i wymiarów.</span><span class="sxs-lookup"><span data-stu-id="d8b16-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="d8b16-107">Jeśli wybierzesz inny towar, może być konieczne wprowadzenie wartości dla innych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="d8b16-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="d8b16-108">Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Przesunięcie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="d8b16-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d8b16-109">Click New.</span></span>
3. <span data-ttu-id="d8b16-110">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d8b16-111">Wybierz opcję IMov.</span><span class="sxs-lookup"><span data-stu-id="d8b16-111">Select IMov.</span></span>
    * <span data-ttu-id="d8b16-112">Najlepiej korzystać z różnych szablonów nazw arkuszy do różnych celów służbowych.</span><span class="sxs-lookup"><span data-stu-id="d8b16-112">It’s a good practise to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="d8b16-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8b16-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d8b16-114">W polu Konto przeciwstawne wpisz wartość „140200”.</span><span class="sxs-lookup"><span data-stu-id="d8b16-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="d8b16-115">To jest konto przeciwstawne, które będzie kontem domyślnym w wierszach arkusza.</span><span class="sxs-lookup"><span data-stu-id="d8b16-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="d8b16-116">Istnieje możliwość zastąpienia wartości domyślnej, aby przypisać różne konta przeciwstawne poszczególnym wierszom.</span><span class="sxs-lookup"><span data-stu-id="d8b16-116">It’s possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="d8b16-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d8b16-117">Click OK.</span></span>
8. <span data-ttu-id="d8b16-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d8b16-118">Click New.</span></span>
9. <span data-ttu-id="d8b16-119">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d8b16-120">Wybierz towar A0001.</span><span class="sxs-lookup"><span data-stu-id="d8b16-120">Select item A0001.</span></span>
11. <span data-ttu-id="d8b16-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8b16-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d8b16-122">Kliknij kartę Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="d8b16-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="d8b16-123">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d8b16-124">Wybierz oddział 1.</span><span class="sxs-lookup"><span data-stu-id="d8b16-124">Select site 1.</span></span>
15. <span data-ttu-id="d8b16-125">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="d8b16-126">Wybierz magazyn 13.</span><span class="sxs-lookup"><span data-stu-id="d8b16-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="d8b16-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d8b16-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="d8b16-128">W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d8b16-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d8b16-129">Wybierz lokalizację 13.</span><span class="sxs-lookup"><span data-stu-id="d8b16-129">Select location 13.</span></span>
20. <span data-ttu-id="d8b16-130">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="d8b16-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="d8b16-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d8b16-131">Click Save.</span></span>
22. <span data-ttu-id="d8b16-132">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="d8b16-132">Click Post.</span></span>
23. <span data-ttu-id="d8b16-133">Zaznacz lub usuń zaznaczenie pola wyboru Przenoszenie wszystkich błędów księgowania do nowego arkusza.</span><span class="sxs-lookup"><span data-stu-id="d8b16-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="d8b16-134">Jeśli ta opcja jest włączona, wszystkie wiersze, których księgowanie się nie powiedzie, będą kopiowane do nowego arkusza.</span><span class="sxs-lookup"><span data-stu-id="d8b16-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="d8b16-135">Informacje w dzienniku mogą służyć do rozwiązywania problemów i ponownego księgowania wierszy.</span><span class="sxs-lookup"><span data-stu-id="d8b16-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="d8b16-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d8b16-136">Click OK.</span></span>
25. <span data-ttu-id="d8b16-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d8b16-137">Close the page.</span></span>
26. <span data-ttu-id="d8b16-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d8b16-138">Close the page.</span></span>

