---
title: Przenoszenie zapasów fizycznych w magazynie
description: Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 540ba2266ea74c36babce57670f84159c89018f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435476"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="d1701-103">Przenoszenie zapasów fizycznych w magazynie</span><span class="sxs-lookup"><span data-stu-id="d1701-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1701-104">Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej.</span><span class="sxs-lookup"><span data-stu-id="d1701-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="d1701-105">Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla przeniesień zapasów.</span><span class="sxs-lookup"><span data-stu-id="d1701-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="d1701-106">Procedurę można wykonać przy użyciu firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane, lub za pomocą własnych danych, jeśli masz skonfigurowane produkty i lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="d1701-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="d1701-107">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="d1701-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="d1701-108">Tworzenie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="d1701-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="d1701-109">W **okienku nawigacji** przejdź do **Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Transfer**.</span><span class="sxs-lookup"><span data-stu-id="d1701-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="d1701-110">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d1701-110">Click **New**.</span></span>
3. <span data-ttu-id="d1701-111">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="d1701-112">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1701-112">Click **OK**.</span></span> <span data-ttu-id="d1701-113">Istnieje opcja umożliwiająca określenie wymiarów „Z” i „Do” dla każdego wiersza arkusza.</span><span class="sxs-lookup"><span data-stu-id="d1701-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="d1701-114">Są one niezbędne dla tego typu arkusza.</span><span class="sxs-lookup"><span data-stu-id="d1701-114">These are essential for this journal type.</span></span> <span data-ttu-id="d1701-115">Towary można przenosić do lokalizacji za pomocą różnych reguł.</span><span class="sxs-lookup"><span data-stu-id="d1701-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="d1701-116">W tym przykładzie przeniesiemy towar w ramach tego samego magazynu z lokalizacji kontrolowanej przez numer identyfikacyjny do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="d1701-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="d1701-117">Utwórz wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="d1701-117">Create journal lines</span></span>
1. <span data-ttu-id="d1701-118">Na **Wiersze arkusza skróconej karcie**, kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d1701-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="d1701-119">W polu **Kod towaru** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="d1701-120">Jeśli używasz firmy USMF, możesz wybrać opcję „A0001”.</span><span class="sxs-lookup"><span data-stu-id="d1701-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="d1701-121">W polu **Z oddziału** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="d1701-122">Jeśli używasz firmy USMF, możesz wybrać opcję „2”.</span><span class="sxs-lookup"><span data-stu-id="d1701-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="d1701-123">W polu **Do oddziału** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="d1701-124">Jeśli używasz firmy USMF, możesz wybrać opcję „2”.</span><span class="sxs-lookup"><span data-stu-id="d1701-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="d1701-125">W polu **Z magazynu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="d1701-126">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="d1701-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="d1701-127">W polu **Do magazynu** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="d1701-128">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="d1701-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="d1701-129">W polu **Z lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="d1701-130">Jeśli używasz firmy USMF, możesz wybrać opcję „FL-001”.</span><span class="sxs-lookup"><span data-stu-id="d1701-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="d1701-131">W polu **Do lokalizacji** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="d1701-132">Jeśli używasz firmy USMF, możesz wybrać opcję „BULK-001”.</span><span class="sxs-lookup"><span data-stu-id="d1701-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="d1701-133">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d1701-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="d1701-134">W skróconej karcie **Szczegóły wiersza** kliknij kartę **Wymiary magazynowe**.</span><span class="sxs-lookup"><span data-stu-id="d1701-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="d1701-135">W **Od wymiarów magazynowych** w polu **Numer identyfikacyjny** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d1701-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="d1701-136">Jeśli używasz firmy USMF, możesz wybrać opcję „24”.</span><span class="sxs-lookup"><span data-stu-id="d1701-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="d1701-137">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d1701-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="d1701-138">Księgowanie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="d1701-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="d1701-139">W **okienku akcji** kliknij pozycję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="d1701-139">On the **Action Pane**, click **Post**.</span></span>
2. <span data-ttu-id="d1701-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1701-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="d1701-141">Wyświetlanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="d1701-141">View inventory transactions</span></span>
1. <span data-ttu-id="d1701-142">Kliknij przycisk **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="d1701-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="d1701-143">Kliknij opcję **Transakcje**.</span><span class="sxs-lookup"><span data-stu-id="d1701-143">Click **Transactions**.</span></span> <span data-ttu-id="d1701-144">W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="d1701-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

