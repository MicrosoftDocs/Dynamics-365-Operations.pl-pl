---
title: Sprawdzanie dostępności zapasów w magazynie
description: Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze.
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0c00b2a79ab588ff47c249f73570544d884b79e
ms.sourcegitcommit: 25fe679b73663fda6b5b3c32646026d0993a9f00
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "1995260"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="3af90-103">Sprawdzanie dostępności zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="3af90-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3af90-104">Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze.</span><span class="sxs-lookup"><span data-stu-id="3af90-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="3af90-105">Przedstawia również, jak uzyskać informacje o podaży towaru.</span><span class="sxs-lookup"><span data-stu-id="3af90-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="3af90-106">Fizycznie dostępne zapasy to zapasy na stanie, które są dostępne, to znaczy kupione, przyjęte i zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="3af90-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="3af90-107">Zapasy na stanie obejmują dostępne zapasy będące na stanie, ale również zapasy, które zostały zamówione i są oczekiwane, ale jeszcze nie zostały przyjęte ani zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="3af90-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="3af90-108">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="3af90-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="3af90-109">Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości.</span><span class="sxs-lookup"><span data-stu-id="3af90-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="3af90-110">Te zadania zazwyczaj wykonuje pracownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="3af90-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="3af90-111">Sprawdzanie ilości dostępnych zapasów towaru</span><span class="sxs-lookup"><span data-stu-id="3af90-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="3af90-112">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie zapasami > Zapytania i raporty > Dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="3af90-112">Go to **Navigation pane > Modules > Inventory management > Inquiries and reports > On-hand inventory**.</span></span>
2. <span data-ttu-id="3af90-113">Zaznacz wiersz **Numer towaru**.</span><span class="sxs-lookup"><span data-stu-id="3af90-113">Select the **Item number** row.</span></span> <span data-ttu-id="3af90-114">Aby wykonać zapytanie o dostępne zapasy według kodów towarów, zaznacz wiersz, gdzie ustawienie Tabela ma wartość **Dostępne zapasy**, a ustawienie Pole ma wartość numer **Towaru**.</span><span class="sxs-lookup"><span data-stu-id="3af90-114">To query the on-hand inventory by item number, select the row where the Table is set to **On-hand inventory** and Field is set to **Item** number.</span></span>
3. <span data-ttu-id="3af90-115">W polu **Kryteria** wybierz towar, o który chcesz wykonać zapytanie.</span><span class="sxs-lookup"><span data-stu-id="3af90-115">In the **Criteria** field, select the item you want to query.</span></span> <span data-ttu-id="3af90-116">Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „M9201”.</span><span class="sxs-lookup"><span data-stu-id="3af90-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="3af90-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af90-117">Click **OK**.</span></span>
5. <span data-ttu-id="3af90-118">W **Okienku akcji** kliknij pozycję **Wymiary**.</span><span class="sxs-lookup"><span data-stu-id="3af90-118">On the **Action pane**, click **Dimensions**.</span></span> <span data-ttu-id="3af90-119">Karta **Wymiary** pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach.</span><span class="sxs-lookup"><span data-stu-id="3af90-119">The **Dimensions** tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="3af90-120">Aby uzyskać dane dotyczące rezerwacji, należy wyświetlić wszystkie wymiary magazynowe dla towarów używających zaawansowanych procesów magazynowych (WHS).</span><span class="sxs-lookup"><span data-stu-id="3af90-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>
6. <span data-ttu-id="3af90-121">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af90-121">Click **OK**.</span></span>
7. <span data-ttu-id="3af90-122">W **Okienku akcji** kliknij pozycję **Informacje pokrewne**.</span><span class="sxs-lookup"><span data-stu-id="3af90-122">On the **Action Pane**, click **Related information**.</span></span> <span data-ttu-id="3af90-123">Jeśli nie widać tej opcji, może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić dodatkowe opcje okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="3af90-123">If you don’t see this option, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>
8. <span data-ttu-id="3af90-124">Kliknij przycisk **Przegląd dostaw**.</span><span class="sxs-lookup"><span data-stu-id="3af90-124">Click **Supply overview**.</span></span> <span data-ttu-id="3af90-125">Karta **Przegląd dostaw** zawiera informacje o dostawie określonego towaru, takie jak ilość dostępnych zapasów, czas realizacji i informacje o dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3af90-125">The **Supply overview** tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="3af90-126">Rozwiń sekcję **Dostępne**.</span><span class="sxs-lookup"><span data-stu-id="3af90-126">Expand the **On-hand** section.</span></span>
10. <span data-ttu-id="3af90-127">Rozwiń sekcję **Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="3af90-127">Expand the **Vendors** section.</span></span>
11. <span data-ttu-id="3af90-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-128">Close the page.</span></span>
12. <span data-ttu-id="3af90-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="3af90-130">Sprawdzanie ilości fizycznie dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="3af90-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="3af90-131">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie magazynem > Zapytania i raporty > Fizycznie dostępne zapasy**.</span><span class="sxs-lookup"><span data-stu-id="3af90-131">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > Physical on-hand inventory**.</span></span>
2. <span data-ttu-id="3af90-132">W polu **Numer towaru** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3af90-132">In the **Item number** field, type a value.</span></span> <span data-ttu-id="3af90-133">Można użyć pól Oddział i Magazyn, aby wyfiltrować listę towarów.</span><span class="sxs-lookup"><span data-stu-id="3af90-133">You can use the Site and Warehouse fields to filter the list of items.</span></span> 
3. <span data-ttu-id="3af90-134">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-134">Refresh the page.</span></span>
4. <span data-ttu-id="3af90-135">W **Okienku akcji** kliknij pozycję **Wyświetl wymiary**.</span><span class="sxs-lookup"><span data-stu-id="3af90-135">On the **Action pane**, click **Display Dimensions**.</span></span> <span data-ttu-id="3af90-136">Karta Wyświetlanie wymiarów pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach.</span><span class="sxs-lookup"><span data-stu-id="3af90-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>
5. <span data-ttu-id="3af90-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af90-137">Click **OK**.</span></span>
6. <span data-ttu-id="3af90-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="3af90-139">Sprawdzanie ilości dostępnych zapasów według lokalizacji</span><span class="sxs-lookup"><span data-stu-id="3af90-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="3af90-140">Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie magazynem > Zapytania i raporty > Dostępne zapasy według lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="3af90-140">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > On hand by location**.</span></span>
2. <span data-ttu-id="3af90-141">W polu **Magazyn** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3af90-141">In the **Warehouse** field, type a value.</span></span> <span data-ttu-id="3af90-142">Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „51”.</span><span class="sxs-lookup"><span data-stu-id="3af90-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="3af90-143">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-143">Refresh the page.</span></span>
4. <span data-ttu-id="3af90-144">Kliknij opcję **Wyświetl wymiary**.</span><span class="sxs-lookup"><span data-stu-id="3af90-144">Click **Display Dimensions**.</span></span>
5. <span data-ttu-id="3af90-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af90-145">Click **OK**.</span></span>
6. <span data-ttu-id="3af90-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3af90-146">Close the page.</span></span>

