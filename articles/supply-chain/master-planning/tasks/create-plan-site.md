---
title: Tworzenie planu dla oddziału
description: Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: daa185864052849b2c78d975a7eb02e9697cb618
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845184"
---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="14171-103">Tworzenie planu dla oddziału</span><span class="sxs-lookup"><span data-stu-id="14171-103">Create a plan for a site</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14171-104">Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru.</span><span class="sxs-lookup"><span data-stu-id="14171-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="14171-105">Po utworzeniu propozycji źródeł zaopatrzenia wyszukuje zamówienia w oddziale, dla którego wykonuje planowanie, i je akceptuje (potwierdza), począwszy od najpilniejszych.</span><span class="sxs-lookup"><span data-stu-id="14171-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="14171-106">Najpilniejszymi zamówieniami są te, które trzeba zaakceptować w bieżącym dniu.</span><span class="sxs-lookup"><span data-stu-id="14171-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="14171-107">Wykonaj te zadania przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="14171-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="14171-108">Tworzenie planu materiałów i zdolności produkcyjnych dla towaru</span><span class="sxs-lookup"><span data-stu-id="14171-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="14171-109">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="14171-109">Click Master planning.</span></span>
    * <span data-ttu-id="14171-110">Należy przejść do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="14171-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="14171-111">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="14171-111">Click Run.</span></span>
3. <span data-ttu-id="14171-112">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="14171-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="14171-113">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="14171-113">Click Filter.</span></span>
5. <span data-ttu-id="14171-114">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="14171-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="14171-115">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="14171-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="14171-116">Przykład: D0001</span><span class="sxs-lookup"><span data-stu-id="14171-116">Example: D0001</span></span>  
7. <span data-ttu-id="14171-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="14171-117">Click OK.</span></span>
8. <span data-ttu-id="14171-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="14171-118">Click OK.</span></span>
    * <span data-ttu-id="14171-119">Może to potrwać kilka minut.</span><span class="sxs-lookup"><span data-stu-id="14171-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="14171-120">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="14171-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="14171-121">Identyfikowanie pilnych zamówień planowanych na towar</span><span class="sxs-lookup"><span data-stu-id="14171-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="14171-122">Otwórz filtr kolumny Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="14171-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="14171-123">Zastosuj filtr w polu „Numer towaru” o wartości „D0001” i użyj operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="14171-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="14171-124">Otwórz filtr kolumny Data zamówienia.</span><span class="sxs-lookup"><span data-stu-id="14171-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="14171-125">Zastosuj filtr do pola „Data zamówienia” z wartością bieżącej daty i operatorem „równa się”.</span><span class="sxs-lookup"><span data-stu-id="14171-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="14171-126">Akceptowanie wszystkich pilnych zamówień na towar</span><span class="sxs-lookup"><span data-stu-id="14171-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="14171-127">Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.</span><span class="sxs-lookup"><span data-stu-id="14171-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="14171-128">Kliknij przycisk Akceptuj.</span><span class="sxs-lookup"><span data-stu-id="14171-128">Click Firm.</span></span>
3. <span data-ttu-id="14171-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="14171-129">Click OK.</span></span>

