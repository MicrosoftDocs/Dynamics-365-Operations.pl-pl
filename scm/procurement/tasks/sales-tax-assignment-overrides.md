--- 
title: "Przypisanie podatku i ręcznych zmian podatków"
description: "Ta procedura przedstawia sposób przypisywania grup podatków do kanałów sprzedaży detalicznej."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b3f13738044c81d32098072f26f204a4acb2d08d
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="2e1b1-103">Przypisanie podatku i ręcznych zmian podatków</span><span class="sxs-lookup"><span data-stu-id="2e1b1-103">Sales tax assignment and overrides</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e1b1-104">Ta procedura przedstawia sposób przypisywania grup podatków do kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-104">This procedure demonstrates how to assign sales tax groups to retail channels.</span></span> <span data-ttu-id="2e1b1-105">Ponadto prowadzi przez proces tworzenia nowej ręcznej zmiany podatku i przypisywania jej do istniejącej grupy ręcznej zmiany podatku.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="2e1b1-106">Ta procedura</span><span class="sxs-lookup"><span data-stu-id="2e1b1-106">This procedure</span></span>

<span data-ttu-id="2e1b1-107">wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-107">uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="2e1b1-108">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-108">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="2e1b1-109">Na liście kliknij łącze identyfikatora kanału sprzedaży detalicznej „Houston”.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-109">In the list, click the Retail Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="2e1b1-110">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-110">Click Edit.</span></span>
    * <span data-ttu-id="2e1b1-111">Pole „Grupa podatków” zawiera listę grup podatków dla bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-111">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="2e1b1-112">Aktualnie przypisaną grupą jest standardowa grupa podatków „Texas”.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-112">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="2e1b1-113">Istnieją również grupy podatków „Washington” i „Washington, King County”.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-113">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="2e1b1-114">Grupy podatków mogą obejmować odnośne podatki dla wielu jednostek administracyjnych.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-114">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="2e1b1-115">W polu „Ręczna zmiana podatku” można mapować grupy ręcznych zmian podatków na kanał.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-115">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="2e1b1-116">Grupy ręcznych zmian podatków mogą służyć do grupowania ręcznych zmian podatków mających zastosowanie do wielu sklepów.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-116">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="2e1b1-117">Zamiast ręcznego przydzielania ręcznych zmian podatków jedna po drugiej można utworzyć grupę i przypisać ją bezpośrednio do kanałów, aby zaoszczędzić czas.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-117">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="2e1b1-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-118">Click Save.</span></span>
5. <span data-ttu-id="2e1b1-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-119">Close the page.</span></span>
6. <span data-ttu-id="2e1b1-120">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Ręczne zmiany podatków.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-120">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="2e1b1-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-121">Click New.</span></span>
8. <span data-ttu-id="2e1b1-122">W polu Ręczna zmiana podatku nadaj nazwę nowej ręcznej zmianie.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-122">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="2e1b1-123">W polu Opis wprowadź opis ręcznej zmiany.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-123">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="2e1b1-124">Ustaw stan na „Włącz”.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-124">Set the status to "Enable."</span></span>
11. <span data-ttu-id="2e1b1-125">Rozwiń lub zwiń sekcję Ręczna zmiana.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-125">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="2e1b1-126">W polu Typ wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-126">In the Type field, select an option.</span></span>
    * <span data-ttu-id="2e1b1-127">Grupy podatków dla towarów mogą służyć do ręcznej zmiany podatków dla określonych towarów należących do tej grupy.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-127">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="2e1b1-128">Na przykład towary żywnościowe są zazwyczaj opodatkowane inaczej niż dobra trwałe i najczęściej mają własną grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-128">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span>     <span data-ttu-id="2e1b1-129">Grupy podatków są grupami podatków stosowanymi w konkretnych kanałach sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-129">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="2e1b1-130">Na przykład jeśli w kanale jest prowadzona sprzedaż odbiorcom detalicznym i firmom, mogą być używane różne grupy podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-130">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="2e1b1-131">Wszystkie stosowne podatki zostaną zmapowane do grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-131">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="2e1b1-132">Teraz można wybrać podatki „Z” i „Do” albo ustawienia „Z grupy podatku” i „Do grupy podatku”, aby utworzyć ręczną zmianę podatku.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-132">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span>    <span data-ttu-id="2e1b1-133">Pole „Z” wskazuje podatek lub grupę podatków, która ma zostać ręcznie zmieniona.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-133">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="2e1b1-134">Ręczna zmiana przy użyciu grupy podatków dla pozycji ma inne opcje niż ręczna zmiana przy użyciu grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-134">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span>    <span data-ttu-id="2e1b1-135">Ręczne zmiany podatków można skonfigurować tak, aby zastępowały podatki w całych transakcjach lub tylko w konkretnych wierszach transakcji.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-135">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="2e1b1-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-136">Click Save.</span></span>
14. <span data-ttu-id="2e1b1-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-137">Close the page.</span></span>
15. <span data-ttu-id="2e1b1-138">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Grupy ręcznej zmiany podatku.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-138">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="2e1b1-139">W tym kroku przypiszesz nowo utworzoną ręczną zmianę podatku do grupy ręcznej zmiany podatku przypisanej do kanału Houston.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-139">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="2e1b1-140">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-140">Click Edit.</span></span>
17. <span data-ttu-id="2e1b1-141">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-141">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="2e1b1-142">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-142">Click Add.</span></span>
19. <span data-ttu-id="2e1b1-143">W polu Ręczna zmiana podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-143">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="2e1b1-144">Na liście zaznacz utworzoną wcześniej ręczną zmianę podatku.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-144">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="2e1b1-145">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-145">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="2e1b1-146">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2e1b1-146">Click Save.</span></span>


