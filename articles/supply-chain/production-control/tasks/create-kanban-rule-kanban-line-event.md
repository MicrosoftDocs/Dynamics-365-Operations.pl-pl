---
title: Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban
description: Ta procedura tworzy regułę Kanban poprzez użycie ustawienia zdarzenia wiersza Kanban w celu zainicjowania ssania z działania procesu.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bff5f16c1911739a29d50c546c3c2a9ab85c2371
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "350235"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="2adad-103">Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban</span><span class="sxs-lookup"><span data-stu-id="2adad-103">Create a kanban rule using a kanban line event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2adad-104">Ta procedura tworzy regułę Kanban poprzez użycie ustawienia zdarzenia wiersza Kanban w celu zainicjowania ssania z działania procesu.</span><span class="sxs-lookup"><span data-stu-id="2adad-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="2adad-105">Reguła Kanban jest wyzwalana przez działania procesu Kanban, każde z ilością większą lub równą 25.</span><span class="sxs-lookup"><span data-stu-id="2adad-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="2adad-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="2adad-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="2adad-107">To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="2adad-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="2adad-108">Tworzenie reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="2adad-108">Create a kanban rule</span></span>
1. <span data-ttu-id="2adad-109">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="2adad-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2adad-110">Click New.</span></span>
3. <span data-ttu-id="2adad-111">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="2adad-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="2adad-112">Spowoduje to wygenerowanie kart Kanban bezpośrednio z popytu.</span><span class="sxs-lookup"><span data-stu-id="2adad-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="2adad-113">Operacja służy do ustawiania reguł, które definiują scenariusz produkcji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="2adad-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="2adad-114">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2adad-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="2adad-115">Wpisz lub wybierz czynność SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="2adad-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="2adad-116">Pierwsze działanie produkcyjnej reguły Kanban musi być działaniem procesu w przepływie produkcji.</span><span class="sxs-lookup"><span data-stu-id="2adad-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="2adad-117">Po wybraniu działania daty ważności działania są kopiowane do pola dat ważności reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="2adad-118">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="2adad-118">Expand the Details section.</span></span>
6. <span data-ttu-id="2adad-119">W polu Produkt wpisz „L0001”.</span><span class="sxs-lookup"><span data-stu-id="2adad-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="2adad-120">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="2adad-120">Expand the Events section.</span></span>
8. <span data-ttu-id="2adad-121">W polu Zdarzenie wiersza Kanban wybierz opcję „Automatyczne”.</span><span class="sxs-lookup"><span data-stu-id="2adad-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="2adad-122">Spowoduje to wygenerowanie kart Kanban dla zdarzenia na żądanie.</span><span class="sxs-lookup"><span data-stu-id="2adad-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="2adad-123">Pole służy do konfigurowania reguł Kanban, które uzupełniają materiały wymagane do obsługi działań od dostawcy do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2adad-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="2adad-124">Po wybraniu opcji Automatyczne karty Kanban zdarzeń są tworzone z popytem.</span><span class="sxs-lookup"><span data-stu-id="2adad-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="2adad-125">To ustawienie jest zalecane, jeśli oczekujesz, że produkcja zostanie wykonana tego samego dnia.</span><span class="sxs-lookup"><span data-stu-id="2adad-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="2adad-126">W polu Ilość minimalna dla zdarzenia ustaw wartość „25”.</span><span class="sxs-lookup"><span data-stu-id="2adad-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="2adad-127">Karty Kanban zdarzeń są generowane, gdy ilość zapotrzebowania jest równa lub wyższa niż wartość w tym polu.</span><span class="sxs-lookup"><span data-stu-id="2adad-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="2adad-128">Jest to przydatne, jeśli chcesz wyprodukować ilość z zamówienia mniejszą niż wartość w tym polu na jednej maszynie, a większą niż wartość w tym polu na innej maszynie.</span><span class="sxs-lookup"><span data-stu-id="2adad-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="2adad-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2adad-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="2adad-130">Tworzenie zamówienia sprzedaży i wyzwalanie łańcucha Kanban</span><span class="sxs-lookup"><span data-stu-id="2adad-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="2adad-131">Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2adad-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="2adad-132">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2adad-132">Click New.</span></span>
3. <span data-ttu-id="2adad-133">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2adad-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="2adad-134">W ustawieniu Konto odbiorcy zaznacz wartość US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="2adad-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="2adad-135">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="2adad-135">Click OK.</span></span>
5. <span data-ttu-id="2adad-136">W polu Numer pozycji wpisz „L0001”.</span><span class="sxs-lookup"><span data-stu-id="2adad-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="2adad-137">L0001 to towar, dla którego utworzono regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="2adad-138">W polu Ilość wpisz wartość 27.</span><span class="sxs-lookup"><span data-stu-id="2adad-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="2adad-139">Ponieważ 27 jest większe niż ilość minimalna 25 określona w regule Kanban, spowoduje to wygenerowanie karty Kanban zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="2adad-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="2adad-140">W polu Oddział wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="2adad-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="2adad-141">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="2adad-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="2adad-142">Wybierz magazyn 13.</span><span class="sxs-lookup"><span data-stu-id="2adad-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="2adad-143">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2adad-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="2adad-144">Wyświetlanie karty Kanban wygenerowanej przez regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="2adad-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="2adad-145">Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="2adad-146">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="2adad-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2adad-147">Rozwiń sekcję Karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="2adad-148">Należy zauważyć, że karta Kanban dla ilości 27 została utworzona w celu przetwarzania działania na podstawie utworzonej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="2adad-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="2adad-149">To jest ostatni krok.</span><span class="sxs-lookup"><span data-stu-id="2adad-149">This is the last step.</span></span>  

