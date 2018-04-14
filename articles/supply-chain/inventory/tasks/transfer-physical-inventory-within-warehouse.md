---
title: "Przenoszenie zapasów fizycznych w magazynie"
description: "Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 442a608d2f7c7923ec50654d3d96cc429d205537
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="5ab60-103">Przenoszenie zapasów fizycznych w magazynie</span><span class="sxs-lookup"><span data-stu-id="5ab60-103">Transfer physical inventory within the warehouse</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ab60-104">Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej.</span><span class="sxs-lookup"><span data-stu-id="5ab60-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="5ab60-105">Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla przeniesień zapasów.</span><span class="sxs-lookup"><span data-stu-id="5ab60-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="5ab60-106">Procedurę można wykonać przy użyciu firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane, lub za pomocą własnych danych, jeśli masz skonfigurowane produkty i lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="5ab60-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="5ab60-107">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="5ab60-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="5ab60-108">Tworzenie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="5ab60-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="5ab60-109">Przejdź do okna Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="5ab60-109">Go to Transfer.</span></span>
2. <span data-ttu-id="5ab60-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5ab60-110">Click New.</span></span>
3. <span data-ttu-id="5ab60-111">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-111">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="5ab60-112">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5ab60-112">Click OK.</span></span>
    * <span data-ttu-id="5ab60-113">Istnieje opcja umożliwiająca określenie wymiarów „Z” i „Do” dla każdego wiersza arkusza.</span><span class="sxs-lookup"><span data-stu-id="5ab60-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="5ab60-114">Są one niezbędne dla tego typu arkusza.</span><span class="sxs-lookup"><span data-stu-id="5ab60-114">These are essential for this journal type.</span></span> <span data-ttu-id="5ab60-115">Towary można przenosić do lokalizacji za pomocą różnych reguł.</span><span class="sxs-lookup"><span data-stu-id="5ab60-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="5ab60-116">W tym przykładzie przeniesiemy towar w ramach tego samego magazynu z lokalizacji kontrolowanej przez numer identyfikacyjny do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="5ab60-116">In this example we’ll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="5ab60-117">Tworzenie wierszy arkusza</span><span class="sxs-lookup"><span data-stu-id="5ab60-117">Create journal lines</span></span>
1. <span data-ttu-id="5ab60-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5ab60-118">Click New.</span></span>
2. <span data-ttu-id="5ab60-119">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-120">Jeśli używasz firmy USMF, możesz wybrać opcję „A0001”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="5ab60-121">W polu Z oddziału wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-121">In the From site field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-122">Jeśli używasz firmy USMF, możesz wybrać opcję „2”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="5ab60-123">W polu Do oddziału wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-123">In the To site field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-124">Jeśli używasz firmy USMF, możesz wybrać opcję „2”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="5ab60-125">W polu Z magazynu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-125">In the From warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-126">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="5ab60-127">W polu Do magazynu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-127">In the To warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-128">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="5ab60-129">W polu Z lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-129">In the From location field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-130">Jeśli używasz firmy USMF, możesz wybrać opcję „FL-001”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="5ab60-131">W polu Do lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-131">In the To location field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-132">Jeśli używasz firmy USMF, możesz wybrać opcję „BULK-001”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="5ab60-133">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-133">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="5ab60-134">Kliknij kartę Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="5ab60-134">Click the Inventory dimensions tab.</span></span>
11. <span data-ttu-id="5ab60-135">W polu Numer identyfikacyjny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="5ab60-135">In the License plate field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab60-136">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="5ab60-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="5ab60-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="5ab60-137">Click Save.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="5ab60-138">Księgowanie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="5ab60-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="5ab60-139">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="5ab60-139">Click Post.</span></span>
2. <span data-ttu-id="5ab60-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5ab60-140">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="5ab60-141">Wyświetlanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="5ab60-141">View inventory transactions</span></span>
1. <span data-ttu-id="5ab60-142">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="5ab60-142">Click Inventory.</span></span>
2. <span data-ttu-id="5ab60-143">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="5ab60-143">Click Transactions.</span></span>
    * <span data-ttu-id="5ab60-144">W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="5ab60-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

