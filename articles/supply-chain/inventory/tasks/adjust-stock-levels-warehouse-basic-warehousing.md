---
title: Korygowanie poziomów zapasów w magazynie (podstawowe magazynowanie)
description: Ta procedura prowadzi przez proces tworzenia i księgowania arkusza korekt zapasów w celu skorygowania poziomów zapasów produktów w magazynie.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 450e95d8a4d5a216b84a3c944c6c63b4a8ad10c5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838830"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="296b2-103">Korygowanie poziomów zapasów w magazynie (podstawowe magazynowanie)</span><span class="sxs-lookup"><span data-stu-id="296b2-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="296b2-104">Ta procedura prowadzi przez proces tworzenia i księgowania arkusza korekt zapasów w celu skorygowania poziomów zapasów produktów w magazynie.</span><span class="sxs-lookup"><span data-stu-id="296b2-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="296b2-105">Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla korekt zapasów.</span><span class="sxs-lookup"><span data-stu-id="296b2-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="296b2-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="296b2-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="296b2-107">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="296b2-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="296b2-108">Tworzenie arkusza korekt zapasów</span><span class="sxs-lookup"><span data-stu-id="296b2-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="296b2-109">Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Korekta zapasów.</span><span class="sxs-lookup"><span data-stu-id="296b2-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="296b2-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="296b2-110">Click New.</span></span>
3. <span data-ttu-id="296b2-111">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="296b2-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="296b2-112">Na liście kliknij nazwę arkusza korekty zapasów, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="296b2-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="296b2-113">Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza korekty zapasów.</span><span class="sxs-lookup"><span data-stu-id="296b2-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="296b2-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="296b2-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="296b2-115">Tworzenie wierszy arkusza</span><span class="sxs-lookup"><span data-stu-id="296b2-115">Create journal lines</span></span>
1. <span data-ttu-id="296b2-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="296b2-116">Click New.</span></span>
2. <span data-ttu-id="296b2-117">Na liście zaznacz pole numeru towaru.</span><span class="sxs-lookup"><span data-stu-id="296b2-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="296b2-118">W polu Numer towaru zaznacz towar.</span><span class="sxs-lookup"><span data-stu-id="296b2-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="296b2-119">Jeśli używasz danych firmy demonstracyjnej USMF, wpisz „D0001”.</span><span class="sxs-lookup"><span data-stu-id="296b2-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="296b2-120">W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="296b2-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="296b2-121">Na liście zaznacz oddział.</span><span class="sxs-lookup"><span data-stu-id="296b2-121">In the list, select a site.</span></span>
6. <span data-ttu-id="296b2-122">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="296b2-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="296b2-123">Na liście zaznacz magazyn.</span><span class="sxs-lookup"><span data-stu-id="296b2-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="296b2-124">Jeśli wybrano towar z lokalizacją jako wymaganym wymiarem, trzeba określić lokalizację w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="296b2-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="296b2-125">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="296b2-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="296b2-126">Pole kosztu własnego określa koszt jednostkowy dla przyjęć na magazyn.</span><span class="sxs-lookup"><span data-stu-id="296b2-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="296b2-127">Jeśli koszt nie został określony dla danego numeru towaru lub musi zostać ręcznie zmodyfikowany, należy to zrobić w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="296b2-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="296b2-128">Sprawdzanie poprawności i księgowanie arkusza korekt zapasów</span><span class="sxs-lookup"><span data-stu-id="296b2-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="296b2-129">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="296b2-129">Click Validate.</span></span>
2. <span data-ttu-id="296b2-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="296b2-130">Click OK.</span></span>
3. <span data-ttu-id="296b2-131">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="296b2-131">Click Post.</span></span>
    * <span data-ttu-id="296b2-132">Podczas księgowania arkusza tego rodzaju księgowane jest przyjęcie do magazynu lub wydanie z magazynu, zmieniane są poziom i wartość zapasów oraz generowane są transakcje finansowe.</span><span class="sxs-lookup"><span data-stu-id="296b2-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="296b2-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="296b2-133">Click OK.</span></span>
5. <span data-ttu-id="296b2-134">Zamknij formularz.</span><span class="sxs-lookup"><span data-stu-id="296b2-134">Close the form.</span></span>
6. <span data-ttu-id="296b2-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="296b2-135">Close the page.</span></span>

