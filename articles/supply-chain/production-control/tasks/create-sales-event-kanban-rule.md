--- 
title: "Tworzenie reguły Kanban dla zdarzenia sprzedaży"
description: "Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży."
author: ChristianRytt
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 67dc36565739b8e902334d9a55af226a0cef5b85
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="64a28-103">Tworzenie reguły Kanban dla zdarzenia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="64a28-103">Create a sales event kanban rule</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64a28-104">Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="64a28-105">Reguła kanban zdarzenia uzupełnia zapotrzebowania wynikające z wierszy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="64a28-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="64a28-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="64a28-107">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.</span><span class="sxs-lookup"><span data-stu-id="64a28-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="64a28-108">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="64a28-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="64a28-109">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="64a28-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="64a28-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64a28-110">Click New.</span></span>
3. <span data-ttu-id="64a28-111">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="64a28-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="64a28-112">Wybranie opcji Zdarzenie spowoduje, że reguła Kanban będzie inicjowana przez zdarzenie, na przykład utworzenie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="64a28-113">Ustawienie jest stosowane do obszarów, gdzie każda karta Kanban powinna pokrywać konkretne zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="64a28-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="64a28-114">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64a28-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="64a28-115">Wybierz opcję Montaż końcowy.</span><span class="sxs-lookup"><span data-stu-id="64a28-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="64a28-116">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="64a28-116">Expand the Details section.</span></span>
6. <span data-ttu-id="64a28-117">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64a28-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="64a28-118">Wybierz opcję L0050.</span><span class="sxs-lookup"><span data-stu-id="64a28-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="64a28-119">Definiowanie zdarzenia</span><span class="sxs-lookup"><span data-stu-id="64a28-119">Define an event</span></span>
1. <span data-ttu-id="64a28-120">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="64a28-120">Expand the Events section.</span></span>
2. <span data-ttu-id="64a28-121">W polu Zdarzenie sprzedaży wybierz opcję „Automatyczne”.</span><span class="sxs-lookup"><span data-stu-id="64a28-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="64a28-122">Wybranie zdarzenia sprzedaży Automatyczne spowoduje, że ta reguła Kanban będzie uruchamiana automatycznie, gdy wiersz sprzedaży pasuje do lokalizacji produktu i przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="64a28-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="64a28-123">W tej procedurze jest to produkt L0050 w magazynie 13.</span><span class="sxs-lookup"><span data-stu-id="64a28-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="64a28-124">W polu Ilość minimalna dla zdarzenia ustaw wartość „50”.</span><span class="sxs-lookup"><span data-stu-id="64a28-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="64a28-125">Przy ilości minimalnej dla zdarzenia wynoszącej 50 reguła Kanban będzie wywoływana tylko przez zdarzenia z ilością 50 lub większą.</span><span class="sxs-lookup"><span data-stu-id="64a28-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="64a28-126">Rozwiń sekcję Przepływ produkcji.</span><span class="sxs-lookup"><span data-stu-id="64a28-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="64a28-127">Należy zauważyć, że lokalizacją przyjęcia jest magazyn 13.</span><span class="sxs-lookup"><span data-stu-id="64a28-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="64a28-128">Oznacza to, że ta reguła Kanban będzie uruchamiana dla tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="64a28-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="64a28-129">W tym przykładzie ta reguła Kanban będzie uruchamiana przez wiersz sprzedaży produktu L0050 z ilością 50 lub więcej w magazynie 13.</span><span class="sxs-lookup"><span data-stu-id="64a28-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="64a28-130">Tworzenie wiersza sprzedaży w celu wyzwalania reguły Kanban zdarzenia</span><span class="sxs-lookup"><span data-stu-id="64a28-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="64a28-131">Przejdź do okna Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="64a28-132">Podczas zapisywania reguły Kanban jest wyświetlane ostrzeżenie, co oznacza, że karty Kanban będą tworzone w czasie rzeczywistym podczas tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="64a28-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64a28-133">Click New.</span></span>
3. <span data-ttu-id="64a28-134">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64a28-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="64a28-135">Na przykład zaznacz US-003.</span><span class="sxs-lookup"><span data-stu-id="64a28-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="64a28-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="64a28-136">Click OK.</span></span>
5. <span data-ttu-id="64a28-137">W polu Numer pozycji wpisz „L0050”.</span><span class="sxs-lookup"><span data-stu-id="64a28-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="64a28-138">W polu Oddział wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="64a28-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="64a28-139">Wybierz Oddział 1, ponieważ magazyn 13 znajduje się w oddziale 1.</span><span class="sxs-lookup"><span data-stu-id="64a28-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="64a28-140">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64a28-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="64a28-141">W polu Magazyn ustaw 13.</span><span class="sxs-lookup"><span data-stu-id="64a28-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="64a28-142">W polu Ilość wpisz wartość 75.</span><span class="sxs-lookup"><span data-stu-id="64a28-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="64a28-143">Wprowadź ilość 50 lub większą, aby wyzwalać utworzoną regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="64a28-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="64a28-144">Weryfikowanie utworzenia karty Kanban</span><span class="sxs-lookup"><span data-stu-id="64a28-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="64a28-145">Kliknij opcję Produkt i dostawa.</span><span class="sxs-lookup"><span data-stu-id="64a28-145">Click Product and supply.</span></span>
2. <span data-ttu-id="64a28-146">Kliknij opcję Wyświetl drzewo oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="64a28-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="64a28-147">Zwróć uwagę, że jest tworzona karta Kanban z taką samą ilością, jak ilość w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64a28-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="64a28-148">Można również wyświetlić wydania materiałów potrzebnych do wytworzenia produktu L0050.</span><span class="sxs-lookup"><span data-stu-id="64a28-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="64a28-149">Jest to ostatni krok w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="64a28-149">This is the last step in this procedure.</span></span>  


