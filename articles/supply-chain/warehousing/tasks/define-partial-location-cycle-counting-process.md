---
title: Definiowanie procesu częściowej inwentaryzacji ciągłej w lokalizacji
description: Używając planów inwentaryzacji ciągłej do tworzenia pracy inwentaryzacji, można kierować faktycznymi operacjami zliczania poprzez ustawienie żądania, aby były zliczane tylko konkretne produkty i warianty produktów, a nie wszystkie zapasy dostępne w lokalizacji.
author: ShylaThompson
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcda301934c6ccc06f17ed8ae13c52754336d2ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830913"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="13327-103">Definiowanie procesu częściowej inwentaryzacji ciągłej w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="13327-103">Define partial location cycle counting process</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13327-104">Używając planów inwentaryzacji ciągłej do tworzenia pracy inwentaryzacji, można kierować faktycznymi operacjami zliczania poprzez ustawienie żądania, aby były zliczane tylko konkretne produkty i warianty produktów, a nie wszystkie zapasy dostępne w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="13327-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="13327-105">Wyfiltrowując określone produkty, kierownik magazynu może zmniejszyć pracochłonność przeglądu, zapobiec błędom konsolidacji i zaoszczędzić czas.</span><span class="sxs-lookup"><span data-stu-id="13327-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="13327-106">Zazwyczaj zadania konfiguracyjne wykonuje kierownik magazynu.</span><span class="sxs-lookup"><span data-stu-id="13327-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="13327-107">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="13327-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="13327-108">Tworzenie szablonu pracy inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="13327-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="13327-109">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.</span><span class="sxs-lookup"><span data-stu-id="13327-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="13327-110">W polu Typ zlecenia wybierz opcję „Inwentaryzacja ciągła”.</span><span class="sxs-lookup"><span data-stu-id="13327-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="13327-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13327-111">Click New.</span></span>
4. <span data-ttu-id="13327-112">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="13327-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="13327-113">Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby.</span><span class="sxs-lookup"><span data-stu-id="13327-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="13327-114">Wartość musi być większa od 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="13327-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="13327-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13327-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="13327-116">W polu Szablon pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="13327-117">W polu Opis szablonu pracy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="13327-118">W polu Identyfikator puli pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="13327-119">W polu Priorytet pracy wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="13327-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="13327-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13327-120">Click Save.</span></span>
11. <span data-ttu-id="13327-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13327-121">Click New.</span></span>
12. <span data-ttu-id="13327-122">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13327-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="13327-123">W polu Typ pracy zaznacz opcję „Inwentaryzacja”.</span><span class="sxs-lookup"><span data-stu-id="13327-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="13327-124">W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="13327-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13327-125">Click Save.</span></span>
16. <span data-ttu-id="13327-126">Kliknij opcję Podziały wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="13327-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="13327-127">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13327-127">Click New.</span></span>
18. <span data-ttu-id="13327-128">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="13327-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="13327-129">Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby.</span><span class="sxs-lookup"><span data-stu-id="13327-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="13327-130">Wartość musi być większa od 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="13327-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="13327-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13327-131">Click Save.</span></span>
20. <span data-ttu-id="13327-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13327-132">Close the page.</span></span>
21. <span data-ttu-id="13327-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13327-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="13327-134">Tworzenie planu inwentaryzacji ciągłej</span><span class="sxs-lookup"><span data-stu-id="13327-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="13327-135">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Inwentaryzacja ciągła > Plany inwentaryzacji ciągłej.</span><span class="sxs-lookup"><span data-stu-id="13327-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="13327-136">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13327-136">Click New.</span></span>
3. <span data-ttu-id="13327-137">W polu Identyfikator planu inwentaryzacji ciągłej wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="13327-138">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="13327-139">W polu Maksymalna liczba inwentaryzacji ciągłych wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="13327-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="13327-140">W polu Szablon pracy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="13327-141">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="13327-141">Click New.</span></span>
8. <span data-ttu-id="13327-142">W polu Numer sekwencyjny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="13327-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="13327-143">Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby.</span><span class="sxs-lookup"><span data-stu-id="13327-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="13327-144">Wartość musi być większa od 0 (zera).</span><span class="sxs-lookup"><span data-stu-id="13327-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="13327-145">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="13327-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="13327-146">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="13327-146">Click Save.</span></span>
11. <span data-ttu-id="13327-147">Kliknij opcję Definiuj zapytanie produktu.</span><span class="sxs-lookup"><span data-stu-id="13327-147">Click Define product query.</span></span>
12. <span data-ttu-id="13327-148">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="13327-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="13327-149">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="13327-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="13327-150">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="13327-150">Click OK.</span></span>
15. <span data-ttu-id="13327-151">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="13327-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]