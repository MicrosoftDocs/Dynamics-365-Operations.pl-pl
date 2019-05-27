---
title: Planowanie ładunków i wysyłki za pomocą warsztatu planowania wysyłki ładunku
description: W tej procedurze pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564810"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="f644a-103">Planowanie ładunków i wysyłki za pomocą warsztatu planowania wysyłki ładunku</span><span class="sxs-lookup"><span data-stu-id="f644a-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f644a-104">W tej procedurze pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f644a-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="f644a-105">Warunkiem wstępnym jest utworzenie zamówienia sprzedaży, co zrobimy najpierw.</span><span class="sxs-lookup"><span data-stu-id="f644a-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="f644a-106">Ta procedura jest częścią codziennej pracy koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="f644a-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="f644a-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f644a-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="f644a-108">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="f644a-108">Create a sales order</span></span>
1. <span data-ttu-id="f644a-109">Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f644a-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="f644a-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f644a-110">Click New.</span></span>
3. <span data-ttu-id="f644a-111">W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f644a-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f644a-112">Wybierz konto US-004.</span><span class="sxs-lookup"><span data-stu-id="f644a-112">Select account US-004.</span></span>
5. <span data-ttu-id="f644a-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f644a-113">Click OK.</span></span>
6. <span data-ttu-id="f644a-114">W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f644a-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f644a-115">Wybierz towar A0001.</span><span class="sxs-lookup"><span data-stu-id="f644a-115">Select item A0001.</span></span>
    * <span data-ttu-id="f644a-116">Towar A0001 jest włączony dla zarządzania transportem.</span><span class="sxs-lookup"><span data-stu-id="f644a-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="f644a-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f644a-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f644a-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="f644a-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="f644a-119">W polu Magazyn wpisz wartość „24”.</span><span class="sxs-lookup"><span data-stu-id="f644a-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="f644a-120">W tym przykładzie należy wybrać magazyn 24.</span><span class="sxs-lookup"><span data-stu-id="f644a-120">In this example select warehouse 24.</span></span> <span data-ttu-id="f644a-121">Ten magazyn jest włączony dla zarządzania transportem i zaawansowanego zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="f644a-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="f644a-122">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f644a-122">Click Save.</span></span>
12. <span data-ttu-id="f644a-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f644a-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="f644a-124">Tworzenie nowego ładunku</span><span class="sxs-lookup"><span data-stu-id="f644a-124">Create a new load</span></span>
1. <span data-ttu-id="f644a-125">Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="f644a-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="f644a-126">Kliknij kartę Wiersze sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f644a-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="f644a-127">Teraz utworzysz ładunek dla utworzonego właśnie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f644a-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="f644a-128">Ładunki można tworzyć na podstawie podaży i popytu z zamówień zakupu, zamówień przeniesienia i zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f644a-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="f644a-129">W okienku akcji kliknij opcję Popyt i podaż.</span><span class="sxs-lookup"><span data-stu-id="f644a-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="f644a-130">Kliknij opcję Do nowego ładunku.</span><span class="sxs-lookup"><span data-stu-id="f644a-130">Click To new load.</span></span>
5. <span data-ttu-id="f644a-131">W polu Identyfikator szablonu ładunku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f644a-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f644a-132">Szablon Ładunek określa maksymalne parametry wagi i objętości całego ładunku.</span><span class="sxs-lookup"><span data-stu-id="f644a-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="f644a-133">Na przykład szablon ładunku może reprezentować rozmiar kontenera lub ciężarówki.</span><span class="sxs-lookup"><span data-stu-id="f644a-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="f644a-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f644a-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="f644a-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f644a-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="f644a-136">Ustawiania stawek i wyznaczania trasy dla ładunku</span><span class="sxs-lookup"><span data-stu-id="f644a-136">Rate and route the load</span></span>
1. <span data-ttu-id="f644a-137">Kliknij opcję Ustawianie stawek i wybór trasy.</span><span class="sxs-lookup"><span data-stu-id="f644a-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="f644a-138">Kliknij opcję Pulpit ustalania stawek i wyznaczania tras.</span><span class="sxs-lookup"><span data-stu-id="f644a-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="f644a-139">Kliknij opcję Szukanie najlepszej stawki.</span><span class="sxs-lookup"><span data-stu-id="f644a-139">Click Rate shop.</span></span>
4. <span data-ttu-id="f644a-140">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f644a-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f644a-141">Kliknij opcję Przypisz.</span><span class="sxs-lookup"><span data-stu-id="f644a-141">Click Assign.</span></span>
6. <span data-ttu-id="f644a-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f644a-142">Close the page.</span></span>
7. <span data-ttu-id="f644a-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f644a-143">Close the page.</span></span>

