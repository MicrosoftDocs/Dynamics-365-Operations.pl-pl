---
title: "Liczenie zapasów w magazynie"
description: "Ta procedura prowadzi przez proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5099e82aa3f0408cbfbf816a69c38c5d48989dd2
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="1dcbb-103">Liczenie zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="1dcbb-103">Count inventory in a warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1dcbb-104">Ta procedura prowadzi przez proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="1dcbb-105">Procedura dotyczy funkcji „podstawowego magazynowania” dostępnej w module Zarządzanie zapasami, a nie funkcji magazynowania dostępnej w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="1dcbb-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="1dcbb-107">Jeśli korzystasz z własnych danych, upewnij się, że masz skonfigurowane produkty i lokalizacje oraz utworzony arkusz magazynowy dla arkuszy inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="1dcbb-108">Inwentaryzacja jest zwykle przeprowadzana przez pracownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="1dcbb-109">Tworzenie arkusza inwentaryzacji zapasów</span><span class="sxs-lookup"><span data-stu-id="1dcbb-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="1dcbb-110">Wybierz kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Zliczanie towarów > Inwentaryzacja.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="1dcbb-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-111">Click New.</span></span>
3. <span data-ttu-id="1dcbb-112">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1dcbb-113">Na liście kliknij nazwę arkusza inwentaryzacji zapasów, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="1dcbb-114">Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="1dcbb-115">W polu Pracownik kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1dcbb-116">Na liście zaznacz pracownika, z którego chcesz skorzystać.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="1dcbb-117">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-117">Click Select.</span></span>
8. <span data-ttu-id="1dcbb-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="1dcbb-119">Tworzenie wierszy arkusza</span><span class="sxs-lookup"><span data-stu-id="1dcbb-119">Create journal lines</span></span>
1. <span data-ttu-id="1dcbb-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-120">Click New.</span></span>
2. <span data-ttu-id="1dcbb-121">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1dcbb-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1dcbb-123">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz opcję „A0001”.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="1dcbb-124">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1dcbb-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1dcbb-126">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz oddział „2”.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="1dcbb-127">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="1dcbb-128">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1dcbb-129">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz magazyn „24”.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="1dcbb-130">W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="1dcbb-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1dcbb-132">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz lokalizację „BULK-001”.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="1dcbb-133">W polu Policzono wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="1dcbb-134">Jeśli wprowadzisz zliczoną liczbę inną niż liczba widoczna w polu Zapasy, pole Ilość zostanie zaktualizowane w celu pokazania niezgodności.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="1dcbb-135">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="1dcbb-136">Księgowanie arkusza inwentaryzacji zapasów</span><span class="sxs-lookup"><span data-stu-id="1dcbb-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="1dcbb-137">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-137">Click Post.</span></span>
    * <span data-ttu-id="1dcbb-138">Jeśli podczas księgowania arkusza inwentaryzacji zapasów zliczona ilość jest inna niż ilość podana w polu Zapasy, nastąpi zaksięgowanie przyjęcia na magazyn lub wydania, zmiana poziomu i wartości zapasów oraz wygenerowanie transakcji finansowych.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="1dcbb-139">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="1dcbb-140">Wyświetlanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="1dcbb-140">View inventory transactions</span></span>
1. <span data-ttu-id="1dcbb-141">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-141">Click Inventory.</span></span>
2. <span data-ttu-id="1dcbb-142">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-142">Click Transactions.</span></span>
    * <span data-ttu-id="1dcbb-143">Tutaj można zobaczyć wszystkie powiązane transakcje, które zostaną utworzone podczas księgowania arkusza inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="1dcbb-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

