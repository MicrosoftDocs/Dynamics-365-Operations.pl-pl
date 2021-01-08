---
title: Przypisanie podatku i ręcznych zmian podatków
description: Ta procedura przedstawia sposób przypisywania grup podatków do kanałów handlu.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74a7eed04648c63c0b19d5de26d2bdbef59aec7d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435273"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="ca0c2-103"> Przypisanie i zastąpienia podatku</span><span class="sxs-lookup"><span data-stu-id="ca0c2-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca0c2-104">Ta procedura przedstawia sposób przypisywania grup podatków do kanałów handlu.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="ca0c2-105">Ponadto prowadzi przez proces tworzenia nowej ręcznej zmiany podatku i przypisywania jej do istniejącej grupy ręcznej zmiany podatku.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="ca0c2-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ca0c2-107">Wybierz kolejno opcje Handel detaliczny i inny > Kanały > > Sklepy > Wszystkie sklepy.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="ca0c2-108">Na liście kliknij łącze identyfikatora kanału dla „Houston”.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="ca0c2-109">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-109">Click Edit.</span></span>
    * <span data-ttu-id="ca0c2-110">Pole „Grupa podatków” zawiera listę grup podatków dla bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="ca0c2-111">Aktualnie przypisaną grupą jest standardowa grupa podatków „Texas”.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="ca0c2-112">Istnieją również grupy podatków „Washington” i „Washington, King County”.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="ca0c2-113">Grupy podatków mogą obejmować odnośne podatki dla wielu jednostek administracyjnych.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="ca0c2-114">W polu „Ręczna zmiana podatku” można mapować grupy ręcznych zmian podatków na kanał.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="ca0c2-115">Grupy ręcznych zmian podatków mogą służyć do grupowania ręcznych zmian podatków mających zastosowanie do wielu sklepów.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="ca0c2-116">Zamiast ręcznego przydzielania ręcznych zmian podatków jedna po drugiej można utworzyć grupę i przypisać ją bezpośrednio do kanałów, aby zaoszczędzić czas.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="ca0c2-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-117">Click Save.</span></span>
5. <span data-ttu-id="ca0c2-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-118">Close the page.</span></span>
6. <span data-ttu-id="ca0c2-119">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Ręczne zmiany podatków.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="ca0c2-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-120">Click New.</span></span>
8. <span data-ttu-id="ca0c2-121">W polu Ręczna zmiana podatku nadaj nazwę nowej ręcznej zmianie.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="ca0c2-122">W polu Opis wprowadź opis ręcznej zmiany.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="ca0c2-123">Ustaw stan na „Włącz”.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="ca0c2-124">Rozwiń lub zwiń sekcję Ręczna zmiana.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="ca0c2-125">W polu Typ wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="ca0c2-126">Grupy podatków dla towarów mogą służyć do ręcznej zmiany podatków dla określonych towarów należących do tej grupy.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="ca0c2-127">Na przykład towary żywnościowe są zazwyczaj opodatkowane inaczej niż dobra trwałe i najczęściej mają własną grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="ca0c2-128">Grupy podatków są grupami podatków stosowanymi w konkretnych kanałach sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="ca0c2-129">Na przykład jeśli w kanale jest prowadzona sprzedaż odbiorcom detalicznym i firmom, mogą być używane różne grupy podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="ca0c2-130">Wszystkie stosowne podatki zostaną zmapowane do grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="ca0c2-131">Teraz można wybrać podatki „Z” i „Do” albo ustawienia „Z grupy podatku” i „Do grupy podatku”, aby utworzyć ręczną zmianę podatku.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="ca0c2-132">Pole „Z” wskazuje podatek lub grupę podatków, która ma zostać ręcznie zmieniona.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="ca0c2-133">Ręczna zmiana przy użyciu grupy podatków dla pozycji ma inne opcje niż ręczna zmiana przy użyciu grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="ca0c2-134">Ręczne zmiany podatków można skonfigurować tak, aby zastępowały podatki w całych transakcjach lub tylko w konkretnych wierszach transakcji.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="ca0c2-135">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-135">Click Save.</span></span>
14. <span data-ttu-id="ca0c2-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-136">Close the page.</span></span>
15. <span data-ttu-id="ca0c2-137">Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia kanału > Podatki > Grupy ręcznej zmiany podatku.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="ca0c2-138">W tym kroku przypiszesz nowo utworzoną ręczną zmianę podatku do grupy ręcznej zmiany podatku przypisanej do kanału Houston.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="ca0c2-139">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-139">Click Edit.</span></span>
17. <span data-ttu-id="ca0c2-140">Rozwiń lub zwiń sekcję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="ca0c2-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-141">Click Add.</span></span>
19. <span data-ttu-id="ca0c2-142">W polu Ręczna zmiana podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="ca0c2-143">Na liście zaznacz utworzoną wcześniej ręczną zmianę podatku.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="ca0c2-144">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="ca0c2-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ca0c2-145">Click Save.</span></span>

