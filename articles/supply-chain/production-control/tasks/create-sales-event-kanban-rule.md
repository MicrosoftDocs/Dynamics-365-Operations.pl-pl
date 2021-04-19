---
title: Tworzenie reguły Kanban dla zdarzenia sprzedaży
description: Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9325bbb8d28587baeb60cdf1fc37121c236f1a10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828929"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="4ec0d-103">Tworzenie reguły Kanban dla zdarzenia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4ec0d-103">Create a sales event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4ec0d-104">Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="4ec0d-105">Reguła kanban zdarzenia uzupełnia zapotrzebowania wynikające z wierszy zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="4ec0d-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4ec0d-107">Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="4ec0d-108">Utwórz nową regułę Kanban</span><span class="sxs-lookup"><span data-stu-id="4ec0d-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="4ec0d-109">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="4ec0d-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-110">Click New.</span></span>
3. <span data-ttu-id="4ec0d-111">W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="4ec0d-112">Wybranie opcji Zdarzenie spowoduje, że reguła Kanban będzie inicjowana przez zdarzenie, na przykład utworzenie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="4ec0d-113">Ustawienie jest stosowane do obszarów, gdzie każda karta Kanban powinna pokrywać konkretne zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="4ec0d-114">W polu Pierwsze działanie planu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4ec0d-115">Wybierz opcję Montaż końcowy.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="4ec0d-116">Rozwiń sekcję Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-116">Expand the Details section.</span></span>
6. <span data-ttu-id="4ec0d-117">W polu Produkt wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="4ec0d-118">Wybierz opcję L0050.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="4ec0d-119">Definiowanie zdarzenia</span><span class="sxs-lookup"><span data-stu-id="4ec0d-119">Define an event</span></span>
1. <span data-ttu-id="4ec0d-120">Rozwiń sekcję Zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-120">Expand the Events section.</span></span>
2. <span data-ttu-id="4ec0d-121">W polu Zdarzenie sprzedaży wybierz opcję „Automatyczne”.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="4ec0d-122">Wybranie zdarzenia sprzedaży Automatyczne spowoduje, że ta reguła Kanban będzie uruchamiana automatycznie, gdy wiersz sprzedaży pasuje do lokalizacji produktu i przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="4ec0d-123">W tej procedurze jest to produkt L0050 w magazynie 13.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="4ec0d-124">W polu Ilość minimalna dla zdarzenia ustaw wartość „50”.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="4ec0d-125">Przy ilości minimalnej dla zdarzenia wynoszącej 50 reguła Kanban będzie wywoływana tylko przez zdarzenia z ilością 50 lub większą.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="4ec0d-126">Rozwiń sekcję Przepływ produkcji.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="4ec0d-127">Należy zauważyć, że lokalizacją przyjęcia jest magazyn 13.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="4ec0d-128">Oznacza to, że ta reguła Kanban będzie uruchamiana dla tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="4ec0d-129">W tym przykładzie ta reguła Kanban będzie uruchamiana przez wiersz sprzedaży produktu L0050 z ilością 50 lub więcej w magazynie 13.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="4ec0d-130">Tworzenie wiersza sprzedaży w celu wyzwalania reguły Kanban zdarzenia</span><span class="sxs-lookup"><span data-stu-id="4ec0d-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="4ec0d-131">Przejdź do okna Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="4ec0d-132">Podczas zapisywania reguły Kanban jest wyświetlane ostrzeżenie, co oznacza, że karty Kanban będą tworzone w czasie rzeczywistym podczas tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="4ec0d-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-133">Click New.</span></span>
3. <span data-ttu-id="4ec0d-134">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="4ec0d-135">Na przykład zaznacz US-003.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="4ec0d-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-136">Click OK.</span></span>
5. <span data-ttu-id="4ec0d-137">W polu Numer pozycji wpisz „L0050”.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="4ec0d-138">W polu Oddział wpisz wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="4ec0d-139">Wybierz Oddział 1, ponieważ magazyn 13 znajduje się w oddziale 1.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="4ec0d-140">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="4ec0d-141">W polu Magazyn ustaw 13.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="4ec0d-142">W polu Ilość wpisz wartość 75.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="4ec0d-143">Wprowadź ilość 50 lub większą, aby wyzwalać utworzoną regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="4ec0d-144">Weryfikowanie utworzenia karty Kanban</span><span class="sxs-lookup"><span data-stu-id="4ec0d-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="4ec0d-145">Kliknij opcję Produkt i dostawa.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-145">Click Product and supply.</span></span>
2. <span data-ttu-id="4ec0d-146">Kliknij opcję Wyświetl drzewo oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="4ec0d-147">Zwróć uwagę, że jest tworzona karta Kanban z taką samą ilością, jak ilość w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="4ec0d-148">Można również wyświetlić wydania materiałów potrzebnych do wytworzenia produktu L0050.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="4ec0d-149">Jest to ostatni krok w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="4ec0d-149">This is the last step in this procedure.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]