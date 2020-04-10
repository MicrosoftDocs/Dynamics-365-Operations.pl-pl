---
title: Definiowanie harmonogramów sprzedaży ciągłej
description: Ten temat prowadzi przez proces konfigurowania programu sprzedaży ciągłej (znanego również jako zamówienia cykliczne).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06fd1e23ad84fdc5e94e309717d5a96fbff45035
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140906"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="ce628-103">Definiowanie harmonogramów sprzedaży ciągłej</span><span class="sxs-lookup"><span data-stu-id="ce628-103">Define continuity schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce628-104">Ten temat prowadzi przez proces konfigurowania programu sprzedaży ciągłej (znanego również jako zamówienia cykliczne).</span><span class="sxs-lookup"><span data-stu-id="ce628-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="ce628-105">Temat wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ce628-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="ce628-106">Tworzenie programu sprzedaży ciągłej</span><span class="sxs-lookup"><span data-stu-id="ce628-106">Create continuity program</span></span>
1. <span data-ttu-id="ce628-107">Wybierz kolejno opcje Retail i Commerce > Ciągłość > Programy sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="ce628-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="ce628-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ce628-108">Click New.</span></span>
3. <span data-ttu-id="ce628-109">W polu Identyfikator harmonogramu wpisz identyfikator harmonogramu programu ciągłości sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ce628-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="ce628-110">W polu Początek zamówienia wybierz opcję „Pierwsze zdarzenie”.</span><span class="sxs-lookup"><span data-stu-id="ce628-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="ce628-111">Jeśli odbiorca złoży nowe zamówienie w programie sprzedaży ciągłej, istnieją dwie opcje wysłania produktu: 1.</span><span class="sxs-lookup"><span data-stu-id="ce628-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="ce628-112">Pierwsze zdarzenie: zostanie wysłany pierwszy produkt w programie sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="ce628-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="ce628-113">2.</span><span class="sxs-lookup"><span data-stu-id="ce628-113">2.</span></span> <span data-ttu-id="ce628-114">Bieżące zdarzenie: zostanie wysłany bieżący produkt.</span><span class="sxs-lookup"><span data-stu-id="ce628-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="ce628-115">Na przykład</span><span class="sxs-lookup"><span data-stu-id="ce628-115">For example.</span></span> <span data-ttu-id="ce628-116">w trzecim miesiącu trwania programu odbiorca otrzyma trzeci produkt przewidziany w programie.</span><span class="sxs-lookup"><span data-stu-id="ce628-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="ce628-117">Wybierz opcję „Tak” w monicie o datę początkową zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ce628-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="ce628-118">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="ce628-118">Click Add line.</span></span>
7. <span data-ttu-id="ce628-119">W polu Numer pozycji wpisz numer towaru dla pierwszego produktu („0013”).</span><span class="sxs-lookup"><span data-stu-id="ce628-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="ce628-120">Wpisz „CP”.</span><span class="sxs-lookup"><span data-stu-id="ce628-120">Type 'CP'.</span></span>
9. <span data-ttu-id="ce628-121">Wprowadź datę, kiedy pierwszy produkt będzie dostępny do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ce628-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="ce628-122">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="ce628-122">Click Add line.</span></span>
11. <span data-ttu-id="ce628-123">W polu Numer towaru wpisz wartość „0014”.</span><span class="sxs-lookup"><span data-stu-id="ce628-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="ce628-124">W polu Kod zakresu dat wyczyścić wartość, tak aby pole było puste.</span><span class="sxs-lookup"><span data-stu-id="ce628-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="ce628-125">Do wykonania tej procedury należy wyczyścić przedział dat.</span><span class="sxs-lookup"><span data-stu-id="ce628-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="ce628-126">Ustawisz datę jako przyrostową od daty początkowej pierwszego towaru.</span><span class="sxs-lookup"><span data-stu-id="ce628-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="ce628-127">W tym miejscu wprowadzisz przedział czasu, w jakim produkty są wysłane.</span><span class="sxs-lookup"><span data-stu-id="ce628-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="ce628-128">Wpisz „30”.</span><span class="sxs-lookup"><span data-stu-id="ce628-128">Type '30'.</span></span>
    * <span data-ttu-id="ce628-129">Dla programu miesięcznego wprowadzisz interwał 30 dni.</span><span class="sxs-lookup"><span data-stu-id="ce628-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="ce628-130">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="ce628-130">Click Add line.</span></span>
15. <span data-ttu-id="ce628-131">W polu Numer towaru wpisz wartość „0015”.</span><span class="sxs-lookup"><span data-stu-id="ce628-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="ce628-132">Wpisz „Koniec”.</span><span class="sxs-lookup"><span data-stu-id="ce628-132">Type 'End'.</span></span>
17. <span data-ttu-id="ce628-133">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ce628-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="ce628-134">Przypisywanie do pozycji w sprzedaży ciągłej</span><span class="sxs-lookup"><span data-stu-id="ce628-134">Assign to continuity item</span></span>
1. <span data-ttu-id="ce628-135">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="ce628-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ce628-136">Wybierz towar „0016”.</span><span class="sxs-lookup"><span data-stu-id="ce628-136">Select item '0016'.</span></span>
    * <span data-ttu-id="ce628-137">W tej procedurze wybierzesz numer towaru 0016.</span><span class="sxs-lookup"><span data-stu-id="ce628-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="ce628-138">Normalnie tworzy się zwolniony produkt, który ma stosowaną dodatkową logikę biznesową ciągłości, gdy jest umieszczany w zamówieniu sprzedaży w biurze obsługi.</span><span class="sxs-lookup"><span data-stu-id="ce628-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="ce628-139">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ce628-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ce628-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ce628-140">Click Edit.</span></span>
5. <span data-ttu-id="ce628-141">Rozwiń lub zwiń sekcję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="ce628-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="ce628-142">W tym miejscu wprowadzisz program ciągłości sprzedaży, który reprezentuje ten towar.</span><span class="sxs-lookup"><span data-stu-id="ce628-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="ce628-143">Wpisz utworzony wcześniej identyfikator harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="ce628-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="ce628-144">Gdy ten towar jest sprzedawany przez biuro obsługi, jest do niego stosowana dodatkowa logika biznesowa z wybranego programu sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="ce628-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="ce628-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ce628-145">Click Save.</span></span>

