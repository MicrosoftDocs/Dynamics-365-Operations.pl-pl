---
title: Definiowanie reguł zapotrzebowania na towary
description: Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd44c458da03807ddc1dc9d652da29c1404dbe64
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209612"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="27d73-103">Definiowanie reguł zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="27d73-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27d73-104">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="27d73-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="27d73-105">Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru.</span><span class="sxs-lookup"><span data-stu-id="27d73-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="27d73-106">Pokazuje także sposób określania domyślnych ustawień zapasów.</span><span class="sxs-lookup"><span data-stu-id="27d73-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="27d73-107">Tworzenie grupy zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="27d73-107">Create a coverage group</span></span>
1. <span data-ttu-id="27d73-108">Przejdź do **okienka nawigacji > Moduły > Planowanie główne > Ustawienia > Grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="27d73-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="27d73-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="27d73-109">Click **New**.</span></span>
3. <span data-ttu-id="27d73-110">W polu **Grupa zapotrzebowania** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27d73-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="27d73-111">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27d73-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="27d73-112">W polu **Kalendarz** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27d73-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="27d73-113">Wybierz kalendarz, którego funkcja planowania głównego będzie używać do tworzenia sugestii uzupełniania towarów z tej grupy.</span><span class="sxs-lookup"><span data-stu-id="27d73-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="27d73-114">W polu **Kod zapotrzebowania** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="27d73-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="27d73-115">W tej procedurze wybierz opcję „Zapotrzebowanie”.</span><span class="sxs-lookup"><span data-stu-id="27d73-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="27d73-116">W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „90”.</span><span class="sxs-lookup"><span data-stu-id="27d73-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="27d73-117">W przypadku towarów w tej grupie planowanie główne utworzy sugestie uzupełnienia na maksymalnie 90 dni w przyszłość.</span><span class="sxs-lookup"><span data-stu-id="27d73-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="27d73-118">W polu **Ilość dni** z ujemnym stanem magazynu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="27d73-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="27d73-119">W polu **Ilość dni z dodatnim stanem magazynu** wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="27d73-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="27d73-120">Rozwiń lub zwiń sekcję **Inne**.</span><span class="sxs-lookup"><span data-stu-id="27d73-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="27d73-121">W obszarze **Marginesy bezpieczeństwa (w dniach)** w polu **Zapas czasu dla przyjęcia dodany do daty zapotrzebowania** wprowadź wartość „1”.</span><span class="sxs-lookup"><span data-stu-id="27d73-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="27d73-122">Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 1 dzień, a wiersz zamówienia zakupu ma zaplanowane przyjęcie w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę przyjęcia na 16 maja.</span><span class="sxs-lookup"><span data-stu-id="27d73-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="27d73-123">W polu **Zapas czasu dla rozchodu odjęty od daty zapotrzebowania** wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="27d73-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="27d73-124">Jeśli na przykład margines bezpieczeństwa jest ustawiony na 1 dzień, a wiersz zamówienia sprzedaży ma zaplanowaną dostawę w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę dostawy na 14 maja.</span><span class="sxs-lookup"><span data-stu-id="27d73-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="27d73-125">W polu **Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru** wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="27d73-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="27d73-126">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="27d73-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="27d73-127">Tworzenie nowego produktu</span><span class="sxs-lookup"><span data-stu-id="27d73-127">Create a new product</span></span>
1. <span data-ttu-id="27d73-128">Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="27d73-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="27d73-129">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="27d73-129">Click **New**.</span></span>
3. <span data-ttu-id="27d73-130">W polu **Numer produktu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27d73-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="27d73-131">W polu **Nazwa produktu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="27d73-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="27d73-132">W polu **Grupa modeli towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="27d73-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="27d73-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="27d73-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="27d73-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="27d73-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="27d73-135">W polu **Grupa towarów** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="27d73-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="27d73-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="27d73-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="27d73-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="27d73-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="27d73-138">W polu **Grupa wymiarów magazynowania** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="27d73-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="27d73-139">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="27d73-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="27d73-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="27d73-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="27d73-141">W polu **Grupa wymiarów śledzenia** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="27d73-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="27d73-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="27d73-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="27d73-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="27d73-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="27d73-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="27d73-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="27d73-145">Konfigurowanie domyślnych ustawień zamówienia</span><span class="sxs-lookup"><span data-stu-id="27d73-145">Setup default order settings</span></span>
1. <span data-ttu-id="27d73-146">W **okienku akcji** kliknij pozycję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="27d73-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="27d73-147">W obszarze **Ustawienia zamówień** kliknij pozycję **domyślne ustawienia zamówień**.</span><span class="sxs-lookup"><span data-stu-id="27d73-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="27d73-148">W sekcji **Zamówienie zakupu** w polu **Witryna domyślna** wpisz oddział używany jako domyślny podczas tworzenia zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="27d73-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="27d73-149">W polu **Magazyn domyślny** wpisz oddział, w którym towar jest przechowywany.</span><span class="sxs-lookup"><span data-stu-id="27d73-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="27d73-150">Rozwiń lub zwiń sekcję **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="27d73-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="27d73-151">W polu **Wielokrotność** wpisz wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="27d73-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="27d73-152">W polu **Min. ilość zamówienia** wpisz wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="27d73-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="27d73-153">W polu **Maks. ilość zamówienia** wpisz wartość „100”.</span><span class="sxs-lookup"><span data-stu-id="27d73-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="27d73-154">W polu **Standardowa ilość zamówienia** wpisz wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="27d73-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="27d73-155">W polu **Czas realizacji zakupu** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="27d73-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="27d73-156">Zaznacz lub wyczyść pole wyboru **Dni robocze**.</span><span class="sxs-lookup"><span data-stu-id="27d73-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="27d73-157">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="27d73-157">Click **Save**.</span></span>
13. <span data-ttu-id="27d73-158">W polu **Domyślny typ zamówienia** zaznacz opcję „Zamówienie zakupu”.</span><span class="sxs-lookup"><span data-stu-id="27d73-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="27d73-159">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="27d73-159">Click **Save**.</span></span>
15. <span data-ttu-id="27d73-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="27d73-160">Close the page.</span></span> <span data-ttu-id="27d73-161">Zamknij stronę Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="27d73-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="27d73-162">Dodawanie towaru do grupy zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="27d73-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="27d73-163">Rozwiń lub zwiń sekcję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="27d73-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="27d73-164">W polu **Grupa zapotrzebowania** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="27d73-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="27d73-165">Na liście znajdź utworzoną przez siebie **grupę zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="27d73-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="27d73-166">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="27d73-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="27d73-167">Tworzenie reguł zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="27d73-167">Create item coverage rules</span></span>
1. <span data-ttu-id="27d73-168">W **okienku akcji** kliknij pozycję **Plan**.</span><span class="sxs-lookup"><span data-stu-id="27d73-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="27d73-169">W obszarze**Pokrycie** kliknij opcję **pokrycie zapasu**.</span><span class="sxs-lookup"><span data-stu-id="27d73-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="27d73-170">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="27d73-170">Click **New**.</span></span>
4. <span data-ttu-id="27d73-171">Kliknij kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="27d73-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="27d73-172">Zaznacz pole wyboru w nagłówku ustawień **Zastępowanie grupy zapotrzebowania**.</span><span class="sxs-lookup"><span data-stu-id="27d73-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="27d73-173">W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „60”.</span><span class="sxs-lookup"><span data-stu-id="27d73-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="27d73-174">Mimo iż towary w grupie zapotrzebowania Zapotrzebowanie są zaplanowane na najbliższe 90 dni, ten towar będzie zaplanowany na najbliższe 60 dni.</span><span class="sxs-lookup"><span data-stu-id="27d73-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="27d73-175">W polu **Ilość dni** z ujemnym stanem magazynu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="27d73-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="27d73-176">W polu **Ilość dni z dodatnim stanem magazynu** wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="27d73-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="27d73-177">Kliknij kartę **Czas realizacji**.</span><span class="sxs-lookup"><span data-stu-id="27d73-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="27d73-178">Zaznacz pole wyboru w nagłówku **Zakup**.</span><span class="sxs-lookup"><span data-stu-id="27d73-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="27d73-179">W polu **Godzina zakupu** wpisz „5”.</span><span class="sxs-lookup"><span data-stu-id="27d73-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="27d73-180">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="27d73-180">Click **Save**.</span></span>

