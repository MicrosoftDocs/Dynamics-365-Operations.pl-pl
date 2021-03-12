---
title: Poprawianie informacji o śledzeniu zapasów
description: Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c70dba7d21eab372cec235efa5a4be19587a409
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000141"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="456f9-103">Poprawianie informacji o śledzeniu zapasów</span><span class="sxs-lookup"><span data-stu-id="456f9-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="456f9-104">Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów.</span><span class="sxs-lookup"><span data-stu-id="456f9-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="456f9-105">W tym przykładzie zaktualizujemy informacje o towarze wchodzącym skład partii, zmieniając niepoprawnie zarejestrowaną partię na inną partię.</span><span class="sxs-lookup"><span data-stu-id="456f9-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="456f9-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USPI lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="456f9-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="456f9-107">W przypadku korzystania z własnych danych musi istnieć towar, który może wchodzić w skład partii, ale nie jest kontrolowany przez lokalizację.</span><span class="sxs-lookup"><span data-stu-id="456f9-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="456f9-108">Trzeba mieć również skonfigurowany arkusz zapasów dla przeniesień zapasów.</span><span class="sxs-lookup"><span data-stu-id="456f9-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="456f9-109">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="456f9-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="456f9-110">Tworzenie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="456f9-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="456f9-111">Przejdź do okna Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="456f9-111">Go to Transfer.</span></span>
2. <span data-ttu-id="456f9-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="456f9-112">Click New.</span></span>
3. <span data-ttu-id="456f9-113">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="456f9-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="456f9-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="456f9-115">Tworzenie wierszy arkusza</span><span class="sxs-lookup"><span data-stu-id="456f9-115">Create journal lines</span></span>
1. <span data-ttu-id="456f9-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="456f9-116">Click New.</span></span>
2. <span data-ttu-id="456f9-117">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="456f9-118">Jeśli używasz firmy USPI, wybierz opcję M5003.</span><span class="sxs-lookup"><span data-stu-id="456f9-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="456f9-119">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="456f9-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="456f9-120">Kliknij kartę Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="456f9-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="456f9-121">W polu Numer partii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="456f9-122">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="456f9-123">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="456f9-124">W polu Numer partii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="456f9-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="456f9-125">Księguj arkusz</span><span class="sxs-lookup"><span data-stu-id="456f9-125">Post the journal</span></span>
1. <span data-ttu-id="456f9-126">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="456f9-126">Click Post.</span></span>
2. <span data-ttu-id="456f9-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="456f9-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="456f9-128">Sprawdzanie informacji o śledzeniu</span><span class="sxs-lookup"><span data-stu-id="456f9-128">Check tracing information</span></span>
1. <span data-ttu-id="456f9-129">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="456f9-129">Click Inventory.</span></span>
2. <span data-ttu-id="456f9-130">Kliknij przycisk Śledzenie.</span><span class="sxs-lookup"><span data-stu-id="456f9-130">Click Trace.</span></span>
3. <span data-ttu-id="456f9-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="456f9-131">Click OK.</span></span>
    * <span data-ttu-id="456f9-132">Przy użyciu tych informacji śledzenia można prześledzić wstecz, z której partii dokonano korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="456f9-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="456f9-133">Wyświetlanie tych informacji umożliwia także strona Śledzenie towaru.</span><span class="sxs-lookup"><span data-stu-id="456f9-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="456f9-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="456f9-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="456f9-135">Sprawdzanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="456f9-135">Check inventory transactions</span></span>
1. <span data-ttu-id="456f9-136">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="456f9-136">Click Inventory.</span></span>
2. <span data-ttu-id="456f9-137">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="456f9-137">Click Transactions.</span></span>
    * <span data-ttu-id="456f9-138">W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="456f9-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

