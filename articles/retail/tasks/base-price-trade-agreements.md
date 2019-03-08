---
title: Podstawa ceny i umowy handlowe
description: Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4830ac553318cfbb3cb74395d1662e74dff75290
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "320427"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="f2fa4-103">Podstawa ceny i umowy handlowe</span><span class="sxs-lookup"><span data-stu-id="f2fa4-103">Base price and trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f2fa4-104">Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="f2fa4-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="f2fa4-106">Wybierz kolejno opcje Handel detaliczny i inny > Ceny i rabaty > Grupy cenowe > Wszystkie grupy cenowe.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-106">Go to Retail and commerce > Pricing and discounts > Price groups > All price groups.</span></span>
    * <span data-ttu-id="f2fa4-107">Grupy cenowe służą przypisywaniu umów handlowych do określonych kanałów.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="f2fa4-108">Używanie grup cenowych, aby przypisać umowy handlowe do kanału, pozwala stosować ceny specyficzne dla kanałów.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="f2fa4-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-109">Click New.</span></span>
3. <span data-ttu-id="f2fa4-110">W polu Grupy cenowe wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-110">In the Price groups field, type a value.</span></span>
4. <span data-ttu-id="f2fa4-111">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f2fa4-112">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-112">Click Save.</span></span>
6. <span data-ttu-id="f2fa4-113">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-113">Close the page.</span></span>
7. <span data-ttu-id="f2fa4-114">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-114">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
8. <span data-ttu-id="f2fa4-115">Na liście wybierz opcję „Nowy Jork”.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="f2fa4-116">W okienku akcji kliknij pozycję Sklep.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-116">On the Action Pane, click Store.</span></span>
10. <span data-ttu-id="f2fa4-117">Kliknij opcję Grupy cenowe.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-117">Click Price groups.</span></span>
11. <span data-ttu-id="f2fa4-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-118">Click New.</span></span>
12. <span data-ttu-id="f2fa4-119">W polu Grupy cenowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-119">In the Price groups field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="f2fa4-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f2fa4-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-121">Click Save.</span></span>
15. <span data-ttu-id="f2fa4-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-122">Close the page.</span></span>
16. <span data-ttu-id="f2fa4-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-123">Close the page.</span></span>
17. <span data-ttu-id="f2fa4-124">Wybierz kolejno opcje Handel detaliczny i inny > Produkty i kategorie > Zwolnione produkty według kategorii.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-124">Go to Retail and commerce > Products and categories > Released products by category.</span></span>
18. <span data-ttu-id="f2fa4-125">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="f2fa4-126">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-126">Click Edit.</span></span>
20. <span data-ttu-id="f2fa4-127">Przełącz rozwinięcie sekcji Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-127">Toggle the expansion of the Sell section.</span></span>
21. <span data-ttu-id="f2fa4-128">W polu Cena wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-128">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f2fa4-129">Ta cena jest używana, gdy nie znaleziono żadnych umów handlowych mających zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="f2fa4-130">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-130">Click Save.</span></span>
23. <span data-ttu-id="f2fa4-131">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-131">On the Action Pane, click Sell.</span></span>
24. <span data-ttu-id="f2fa4-132">Kliknij opcję Utwórz umowy handlowe.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-132">Click Create trade agreements.</span></span>
25. <span data-ttu-id="f2fa4-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-133">Click New.</span></span>
26. <span data-ttu-id="f2fa4-134">W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-134">In the Name field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="f2fa4-135">Z listy wybierz pozycję „Handel detaliczny”.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-135">In the list, select 'Retail'.</span></span>
    * <span data-ttu-id="f2fa4-136">W danych demonstracyjnych arkusz o nazwie „Handel detaliczny” ma domyślną relację „Cena (sprzedaż)”.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-136">In the demo data, the 'Retail' journal name has the default relation of 'Price (sales)'.</span></span> <span data-ttu-id="f2fa4-137">Oznacza to, że wszystkie nowo tworzone wiersze domyślnie są dla umów handlowych na cenę sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="f2fa4-138">Kliknij przycisk Wiersze.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-138">Click Lines.</span></span>
29. <span data-ttu-id="f2fa4-139">W polu Kod konta wybierz opcję „Grupa”.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-139">In the Account code field, select 'Group'.</span></span>
30. <span data-ttu-id="f2fa4-140">W polu Wybór konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-140">In the Account selection field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="f2fa4-141">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f2fa4-142">Zakończy to operację łączenia kanału z grupą cenową, a następnie grupy z umową handlową.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="f2fa4-143">W polu Relacja towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-143">In the Item relation field, type a value.</span></span>
33. <span data-ttu-id="f2fa4-144">W polu Kwota w walucie wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-144">In the Amount in currency field, enter a number.</span></span>
34. <span data-ttu-id="f2fa4-145">Zaznacz pole wyboru Znajdź następny lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-145">Check or uncheck the Find next checkbox.</span></span>
    * <span data-ttu-id="f2fa4-146">Jeśli opcja Znajdź następny jest ustawiona na wartość „Tak”, aparat kalkulacji cen będzie wyszukiwał odnośne umowy handlowe z niższą ceną sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-146">When Find next is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="f2fa4-147">Jeśli opcja Znajdź następny jest ustawiony na „Nie”, aparat kalkulacji cen przestanie szukać i użyje bieżącej umowy handlowej.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-147">When Find next is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="f2fa4-148">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-148">Click Post.</span></span>
36. <span data-ttu-id="f2fa4-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-149">Click OK.</span></span>
37. <span data-ttu-id="f2fa4-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-150">Close the page.</span></span>
38. <span data-ttu-id="f2fa4-151">W okienku akcji kliknij pozycję Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-151">On the Action Pane, click Sell.</span></span>
39. <span data-ttu-id="f2fa4-152">Kliknij opcję Cena sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f2fa4-152">Click Sales price.</span></span>

