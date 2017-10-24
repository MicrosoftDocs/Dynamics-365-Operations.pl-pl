--- 
title: "Definiowanie reguł zapotrzebowania na towary"
description: "Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 14f56c30753da9458d66a46da8935305619fd0b8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="33936-103">Definiowanie reguł zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="33936-103">Define coverage rules for items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="33936-104">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="33936-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="33936-105">Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru.</span><span class="sxs-lookup"><span data-stu-id="33936-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="33936-106">Pokazuje także sposób określania domyślnych ustawień zapasów.</span><span class="sxs-lookup"><span data-stu-id="33936-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="33936-107">Tworzenie grupy zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="33936-107">Create a coverage group</span></span>
1. <span data-ttu-id="33936-108">Przejdź do okna Grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="33936-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="33936-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="33936-109">Click New.</span></span>
3. <span data-ttu-id="33936-110">W polu Grupa zapotrzebowania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33936-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="33936-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33936-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="33936-112">W polu Kalendarz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33936-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="33936-113">Wybierz kalendarz, którego funkcja planowania głównego będzie używać do tworzenia sugestii uzupełniania towarów z tej grupy.</span><span class="sxs-lookup"><span data-stu-id="33936-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="33936-114">W polu Kod zapotrzebowania wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="33936-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="33936-115">W tej procedurze wybierz opcję Zapotrzebowanie.</span><span class="sxs-lookup"><span data-stu-id="33936-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="33936-116">W polu Horyzont czasowy zapotrzebowania (dni) wpisz „90”.</span><span class="sxs-lookup"><span data-stu-id="33936-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="33936-117">W przypadku towarów w tej grupie planowanie główne utworzy sugestie uzupełnienia na maksymalnie 90 dni w przyszłość.</span><span class="sxs-lookup"><span data-stu-id="33936-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="33936-118">W polu Ilość dni z ujemnym stanem magazynu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="33936-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="33936-119">W polu Ilość dni z dodatnim stanem magazynu wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="33936-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="33936-120">Rozwiń lub zwiń sekcję Inne.</span><span class="sxs-lookup"><span data-stu-id="33936-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="33936-121">W polu Zapas czasu dla przyjęcia dodany do daty zapotrzebowania wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="33936-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="33936-122">Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 1 dzień, a wiersz zamówienia zakupu ma zaplanowane przyjęcie w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę przyjęcia na 16 maja.</span><span class="sxs-lookup"><span data-stu-id="33936-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="33936-123">W polu Zapas czasu dla rozchodu odjęty od daty zapotrzebowania wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="33936-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="33936-124">Jeśli na przykład margines bezpieczeństwa jest ustawiony na 1 dzień, a wiersz zamówienia sprzedaży ma zaplanowaną dostawę w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę dostawy na 14 maja.</span><span class="sxs-lookup"><span data-stu-id="33936-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="33936-125">W polu Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru wpisz „1”.</span><span class="sxs-lookup"><span data-stu-id="33936-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="33936-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="33936-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="33936-127">Tworzenie nowego produktu</span><span class="sxs-lookup"><span data-stu-id="33936-127">Create a new product</span></span>
1. <span data-ttu-id="33936-128">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="33936-128">Go to Released products.</span></span>
2. <span data-ttu-id="33936-129">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="33936-129">Click New.</span></span>
3. <span data-ttu-id="33936-130">W polu Numer produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33936-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="33936-131">W polu Nazwa produktu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33936-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="33936-132">W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="33936-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="33936-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="33936-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="33936-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="33936-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="33936-135">W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="33936-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="33936-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="33936-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="33936-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="33936-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="33936-138">W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="33936-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="33936-139">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="33936-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="33936-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="33936-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="33936-141">W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="33936-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="33936-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="33936-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="33936-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="33936-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="33936-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="33936-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="33936-145">Konfigurowanie domyślnych ustawień zamówienia</span><span class="sxs-lookup"><span data-stu-id="33936-145">Setup default order settings</span></span>
1. <span data-ttu-id="33936-146">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="33936-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="33936-147">Kliknij opcję Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="33936-147">Click Default order settings.</span></span>
3. <span data-ttu-id="33936-148">W polu Oddział zakupu wpisz oddział używany jako domyślny podczas tworzenia zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="33936-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="33936-149">W polu Oddział zapasów wpisz oddział, w którym towar jest przechowywany.</span><span class="sxs-lookup"><span data-stu-id="33936-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="33936-150">Rozwiń lub zwiń sekcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="33936-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="33936-151">W polu Wiele ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="33936-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="33936-152">W polu Min.</span><span class="sxs-lookup"><span data-stu-id="33936-152">Set Min.</span></span> <span data-ttu-id="33936-153">ilość zamówienia ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="33936-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="33936-154">W polu Maks.</span><span class="sxs-lookup"><span data-stu-id="33936-154">Set Max.</span></span> <span data-ttu-id="33936-155">ilość zamówienia ustaw wartość „100”.</span><span class="sxs-lookup"><span data-stu-id="33936-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="33936-156">W polu Standardowa ilość zamówienia ustaw wartość „10”.</span><span class="sxs-lookup"><span data-stu-id="33936-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="33936-157">W polu Czas realizacji zakupu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="33936-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="33936-158">Zaznacz lub wyczyść pole wyboru Dni robocze.</span><span class="sxs-lookup"><span data-stu-id="33936-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="33936-159">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="33936-159">Click Save.</span></span>
13. <span data-ttu-id="33936-160">W polu Domyślny typ zamówienia zaznacz opcję „Zamówienie zakupu”.</span><span class="sxs-lookup"><span data-stu-id="33936-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="33936-161">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="33936-161">Click Save.</span></span>
15. <span data-ttu-id="33936-162">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="33936-162">Close the page.</span></span>
    * <span data-ttu-id="33936-163">Zamknij stronę Ustawienia domyślne zamówień.</span><span class="sxs-lookup"><span data-stu-id="33936-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="33936-164">Dodawanie towaru do grupy zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="33936-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="33936-165">Rozwiń lub zwiń sekcję Plan.</span><span class="sxs-lookup"><span data-stu-id="33936-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="33936-166">W polu Grupa zapotrzebowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="33936-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="33936-167">Na liście znajdź utworzoną przez siebie grupę zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="33936-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="33936-168">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="33936-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="33936-169">Tworzenie reguł zapotrzebowania na towary</span><span class="sxs-lookup"><span data-stu-id="33936-169">Create item coverage rules</span></span>
1. <span data-ttu-id="33936-170">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="33936-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="33936-171">Kliknij opcję Zapotrzebowanie na towary.</span><span class="sxs-lookup"><span data-stu-id="33936-171">Click Item coverage.</span></span>
3. <span data-ttu-id="33936-172">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="33936-172">Click New.</span></span>
4. <span data-ttu-id="33936-173">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="33936-173">Click the General tab.</span></span>
5. <span data-ttu-id="33936-174">Zaznacz pole wyboru w nagłówku Zastępowanie ustawień grupy zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="33936-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="33936-175">W polu Horyzont czasowy zapotrzebowania (dni) wpisz „60”.</span><span class="sxs-lookup"><span data-stu-id="33936-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="33936-176">Mimo iż towary w grupie zapotrzebowania Zapotrzebowanie są zaplanowane na najbliższe 90 dni, ten towar będzie zaplanowany na najbliższe 60 dni.</span><span class="sxs-lookup"><span data-stu-id="33936-176">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="33936-177">W polu Ilość dni z ujemnym stanem magazynu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="33936-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="33936-178">W polu Ilość dni z dodatnim stanem magazynu wpisz „2”.</span><span class="sxs-lookup"><span data-stu-id="33936-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="33936-179">Kliknij kartę Czas realizacji.</span><span class="sxs-lookup"><span data-stu-id="33936-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="33936-180">Zaznacz pole wyboru w nagłówku Zakup.</span><span class="sxs-lookup"><span data-stu-id="33936-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="33936-181">W polu Godzina zakupu wpisz „5”.</span><span class="sxs-lookup"><span data-stu-id="33936-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="33936-182">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="33936-182">Click Save.</span></span>


