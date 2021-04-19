---
title: Zatwierdzanie dostawców określonych produktów
description: W tej procedurze pokazano sposób zatwierdzania dostawców dla określonych produktów.
author: kamaybac
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45f6942c99e03a5abf6de736f1adb0b4e232783f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812501"
---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="c2ebc-103">Zatwierdzanie dostawców określonych produktów</span><span class="sxs-lookup"><span data-stu-id="c2ebc-103">Approve vendors for specific products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2ebc-104">W tej procedurze pokazano sposób zatwierdzania dostawców dla określonych produktów.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="c2ebc-105">Pozwala to na kontrolowanie, którzy dostawcy mogą być używani podczas dodawania produktu do zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="c2ebc-106">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="c2ebc-107">To zadanie zazwyczaj wykonuje menedżer ds. zakupów.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="c2ebc-108">W okienku nawigacji przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Wydane produkty**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-108">In Navigation Pane, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="c2ebc-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c2ebc-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c2ebc-111">Rozwiń skróconą kartę **Zakup**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-111">Expand the **Purchase** fastTab.</span></span> <span data-ttu-id="c2ebc-112">Jeśli w polu **Dostawca** jest wyświetlany główny dostawca, należy dodać tego dostawcy jako zatwierdzonego dostawcę w poniższych krokach.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-112">If there is a primary vendor shown in the **Vendor** field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="c2ebc-113">Zanotuj numer dostawcy, jeśli jest wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="c2ebc-114">W okienku akcji kliknij pozycję **Zakup.**</span><span class="sxs-lookup"><span data-stu-id="c2ebc-114">On the Action Pane, click **Purchase**.</span></span>
6. <span data-ttu-id="c2ebc-115">Kliknij przycisk **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-115">Click **Setup**.</span></span>
7. <span data-ttu-id="c2ebc-116">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-116">Click **Add**.</span></span>
8. <span data-ttu-id="c2ebc-117">W polu Dostawca wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-117">In the Vendor field, enter or select a value.</span></span> <span data-ttu-id="c2ebc-118">Wybierz zatwierdzonego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-118">Select the approved vendor.</span></span> <span data-ttu-id="c2ebc-119">Co najmniej jeden wiersz musi określać głównego dostawcę, jeśli taki dostawca istniał w rekordzie produktu.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="c2ebc-120">Jeśli wcześniej spisano numer dostawcy, zaznacz go w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="c2ebc-121">W polu **Data wygaśnięcia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-121">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="c2ebc-122">Wybierz datę przypadającą za kilka miesięcy.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="c2ebc-123">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-123">Click **Add**.</span></span>
11. <span data-ttu-id="c2ebc-124">W polu **Dostawca** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-124">In the **Vendor** field, enter or select a value.</span></span>
12. <span data-ttu-id="c2ebc-125">W polu **Data wygaśnięcia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-125">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="c2ebc-126">Wybierz datę, która różni się od poprzedniej daty ważności.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="c2ebc-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-127">Close the page.</span></span>
14. <span data-ttu-id="c2ebc-128">W okienku akcji kliknij pozycję **Zatwierdzeni dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-128">On the Action Pane, click **Approved vendors**.</span></span>
15. <span data-ttu-id="c2ebc-129">W polu **Data wygaśnięcia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-129">In the **Expiration** field, enter a date.</span></span> <span data-ttu-id="c2ebc-130">Ta data ta pełni rolę filtra pozwalającego zobaczyć zatwierdzonych dostawców ważnych do określonego dnia.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="c2ebc-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-131">Close the page.</span></span>
17. <span data-ttu-id="c2ebc-132">W okienku akcji kliknij pozycję **Okres obowiązywania**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-132">On the Action Pane, click **Effective period**.</span></span>
18. <span data-ttu-id="c2ebc-133">W polu **Pokaż dostawców wygasających** w wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-133">In the **Show vendors expired by** field, enter a date.</span></span> <span data-ttu-id="c2ebc-134">Można używać tej strony do identyfikowania dostawców, gdy stan zatwierdzenia wygasa po określonej dacie.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="c2ebc-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-135">Close the page.</span></span>
20. <span data-ttu-id="c2ebc-136">Kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-136">Click **Edit**.</span></span>
21. <span data-ttu-id="c2ebc-137">W polu **Metoda sprawdzania zatwierdzonych dostawców** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-137">In the **Approved vendor check method** field, select an option.</span></span> <span data-ttu-id="c2ebc-138">To pole umożliwia wybór zasad mówiących o tym, co ma się stać, jeśli produkt zostanie dodany do wiersza zamówienia zakupu, gdy dostawca nie jest zatwierdzonym dostawcą.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="c2ebc-139">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-139">Click **Save**.</span></span>
23. <span data-ttu-id="c2ebc-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-140">Close the page.</span></span>
24. <span data-ttu-id="c2ebc-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-141">Close the page.</span></span>
25. <span data-ttu-id="c2ebc-142">W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Dostawcy > Relacje dostawca/pozycja > Lista zatwierdzonych dostawców wg pozycji**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-142">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item**.</span></span> <span data-ttu-id="c2ebc-143">Ta strona zawiera przegląd wszystkich produktów i zatwierdzonych dostawców.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="c2ebc-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-144">Close the page.</span></span>
27. <span data-ttu-id="c2ebc-145">W okienku nawigacji przejdź do **Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.**</span><span class="sxs-lookup"><span data-stu-id="c2ebc-145">In Navigation Pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span> <span data-ttu-id="c2ebc-146">Można także rozpocząć od dostawcy, a następnie przejść do wykazu produktów zatwierdzonych dla tego konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="c2ebc-147">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="c2ebc-148">W okienku akcji kliknij pozycję **Zaopatrzenie**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-148">On the Action Pane, click **Procurement**.</span></span>
30. <span data-ttu-id="c2ebc-149">Kliknij opcję **Lista zatwierdzonych dostawców wg dostawców**.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-149">Click **Approved vendor list by vendor**.</span></span>
31. <span data-ttu-id="c2ebc-150">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-150">Close the page.</span></span>
32. <span data-ttu-id="c2ebc-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c2ebc-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]