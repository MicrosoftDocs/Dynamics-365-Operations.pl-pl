---
title: "Poprawianie informacji o śledzeniu zapasów"
description: "Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 55f9ae337aac673ae2f80d7bfa9221b6060f9119
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="b9c98-103">Poprawianie informacji o śledzeniu zapasów</span><span class="sxs-lookup"><span data-stu-id="b9c98-103">Correct inventory tracking information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9c98-104">Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu skorygowania informacji o śledzeniu zapasów.</span><span class="sxs-lookup"><span data-stu-id="b9c98-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="b9c98-105">W tym przykładzie zaktualizujemy informacje o towarze wchodzącym skład partii, zmieniając niepoprawnie zarejestrowaną partię na inną partię.</span><span class="sxs-lookup"><span data-stu-id="b9c98-105">In this example, we’ll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="b9c98-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USPI lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="b9c98-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="b9c98-107">W przypadku korzystania z własnych danych musi istnieć towar, który może wchodzić w skład partii, ale nie jest kontrolowany przez lokalizację.</span><span class="sxs-lookup"><span data-stu-id="b9c98-107">If you use your own data, you need to have an item that’s batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="b9c98-108">Trzeba mieć również skonfigurowany arkusz zapasów dla przeniesień zapasów.</span><span class="sxs-lookup"><span data-stu-id="b9c98-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="b9c98-109">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="b9c98-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="b9c98-110">Tworzenie arkusza przeniesienia zapasów</span><span class="sxs-lookup"><span data-stu-id="b9c98-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="b9c98-111">Przejdź do okna Przeniesienie.</span><span class="sxs-lookup"><span data-stu-id="b9c98-111">Go to Transfer.</span></span>
2. <span data-ttu-id="b9c98-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b9c98-112">Click New.</span></span>
3. <span data-ttu-id="b9c98-113">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="b9c98-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b9c98-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="b9c98-115">Tworzenie wierszy arkusza</span><span class="sxs-lookup"><span data-stu-id="b9c98-115">Create journal lines</span></span>
1. <span data-ttu-id="b9c98-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="b9c98-116">Click New.</span></span>
2. <span data-ttu-id="b9c98-117">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="b9c98-118">Jeśli używasz firmy USPI, wybierz opcję M5003.</span><span class="sxs-lookup"><span data-stu-id="b9c98-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="b9c98-119">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="b9c98-120">Kliknij kartę Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="b9c98-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="b9c98-121">W polu Numer partii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="b9c98-122">W polu Oddział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="b9c98-123">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="b9c98-124">W polu Numer partii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c98-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="b9c98-125">Księguj arkusz</span><span class="sxs-lookup"><span data-stu-id="b9c98-125">Post the journal</span></span>
1. <span data-ttu-id="b9c98-126">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="b9c98-126">Click Post.</span></span>
2. <span data-ttu-id="b9c98-127">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b9c98-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="b9c98-128">Sprawdzanie informacji o śledzeniu</span><span class="sxs-lookup"><span data-stu-id="b9c98-128">Check tracing information</span></span>
1. <span data-ttu-id="b9c98-129">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="b9c98-129">Click Inventory.</span></span>
2. <span data-ttu-id="b9c98-130">Kliknij przycisk Śledzenie.</span><span class="sxs-lookup"><span data-stu-id="b9c98-130">Click Trace.</span></span>
3. <span data-ttu-id="b9c98-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="b9c98-131">Click OK.</span></span>
    * <span data-ttu-id="b9c98-132">Przy użyciu tych informacji śledzenia można prześledzić wstecz, z której partii dokonano korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="b9c98-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="b9c98-133">Wyświetlanie tych informacji umożliwia także strona Śledzenie towaru.</span><span class="sxs-lookup"><span data-stu-id="b9c98-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="b9c98-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b9c98-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="b9c98-135">Sprawdzanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="b9c98-135">Check inventory transactions</span></span>
1. <span data-ttu-id="b9c98-136">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="b9c98-136">Click Inventory.</span></span>
2. <span data-ttu-id="b9c98-137">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="b9c98-137">Click Transactions.</span></span>
    * <span data-ttu-id="b9c98-138">W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.</span><span class="sxs-lookup"><span data-stu-id="b9c98-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

