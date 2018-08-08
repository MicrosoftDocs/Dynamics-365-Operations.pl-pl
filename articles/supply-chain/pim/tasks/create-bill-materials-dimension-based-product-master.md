--- 
title: "Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach"
description: "Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań."
author: ShylaThompson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d6d98b33d819fd7c68af7d0d5df8eaeb381853b1
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="824f5-103">Tworzenie listy składowej (BOM) dla produktu głównego opartego na wymiarach</span><span class="sxs-lookup"><span data-stu-id="824f5-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="824f5-104">Przed wykonaniem tej procedury należy wykonać 4 poprzednie przewodniki z tej sekwencji ośmiu nagrań.</span><span class="sxs-lookup"><span data-stu-id="824f5-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="824f5-105">Pierwsze 4 nagrania obejmują skonfigurowanie danych wymaganych do wykonania tej procedury.</span><span class="sxs-lookup"><span data-stu-id="824f5-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="824f5-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="824f5-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="824f5-107">To zadanie jest zazwyczaj wykonywane przez projektanta produktów.</span><span class="sxs-lookup"><span data-stu-id="824f5-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="824f5-108">Wybieranie produktu</span><span class="sxs-lookup"><span data-stu-id="824f5-108">Select the product</span></span>
1. <span data-ttu-id="824f5-109">Kliknij pozycję Obsługa zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="824f5-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="824f5-110">Kliknij opcję Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="824f5-110">Click Released products.</span></span>
3. <span data-ttu-id="824f5-111">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="824f5-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="824f5-112">Znajdź zwolniony produkt główny z technologią konfiguracji opartej na wymiarach, który utworzono w pierwszym przewodniku po zadaniach w tej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="824f5-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="824f5-113">W okienku akcji kliknij pozycję Konstruuj.</span><span class="sxs-lookup"><span data-stu-id="824f5-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="824f5-114">Kliknij opcję Wersje BOM.</span><span class="sxs-lookup"><span data-stu-id="824f5-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="824f5-115">Tworzenie nowej BOM i wersji BOM</span><span class="sxs-lookup"><span data-stu-id="824f5-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="824f5-116">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="824f5-116">Click New.</span></span>
2. <span data-ttu-id="824f5-117">Kliknij opcję BOM i wersja BOM.</span><span class="sxs-lookup"><span data-stu-id="824f5-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="824f5-118">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="824f5-119">Ustawianie oddziału</span><span class="sxs-lookup"><span data-stu-id="824f5-119">Setting a site</span></span>  
    * <span data-ttu-id="824f5-120">W tej procedurze nie ustawimy konkretnego oddziału dla BOM.</span><span class="sxs-lookup"><span data-stu-id="824f5-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="824f5-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="824f5-121">Click OK.</span></span>
5. <span data-ttu-id="824f5-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="824f5-122">Click New.</span></span>
    * <span data-ttu-id="824f5-123">W tej procedurze dodamy cztery wiersze do BOM.</span><span class="sxs-lookup"><span data-stu-id="824f5-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="824f5-124">Dwa wiersze reprezentują opcje kabla, a dwa opcje szafy.</span><span class="sxs-lookup"><span data-stu-id="824f5-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="824f5-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="824f5-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="824f5-126">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-127">Wybierz towar o numerze A0001 HDMI 6' Cables (kable HDMI o długości 1,8 m).</span><span class="sxs-lookup"><span data-stu-id="824f5-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="824f5-128">W polu Grupa konfiguracji wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-129">Wybierz grupę konfiguracji Kabel utworzoną w przewodniku 4 w tej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="824f5-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="824f5-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="824f5-130">Click New.</span></span>
    * <span data-ttu-id="824f5-131">Wybierz towar o numerze A0002 HDMI 6' Cables (kable HDMI o długości 3,6 m).</span><span class="sxs-lookup"><span data-stu-id="824f5-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="824f5-132">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="824f5-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="824f5-133">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="824f5-134">W polu Grupa konfiguracji wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-135">Ponownie zaznacz grupę konfiguracji Kabel.</span><span class="sxs-lookup"><span data-stu-id="824f5-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="824f5-136">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="824f5-136">Click New.</span></span>
14. <span data-ttu-id="824f5-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="824f5-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="824f5-138">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-139">Wybierz towar o numerze D0002 Cabinet (Szafa).</span><span class="sxs-lookup"><span data-stu-id="824f5-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="824f5-140">W polu Grupa konfiguracji wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-141">Dla tego wiersza BOM wybierz grupę konfiguracji Szafa.</span><span class="sxs-lookup"><span data-stu-id="824f5-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="824f5-142">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="824f5-142">Click New.</span></span>
18. <span data-ttu-id="824f5-143">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="824f5-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="824f5-144">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-145">Jako ostatni wiersz BOM wybierz towar o numerze 0007 StandardCabinet (Standardowa szafa).</span><span class="sxs-lookup"><span data-stu-id="824f5-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="824f5-146">W polu Grupa konfiguracji wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="824f5-147">Dla ostatniego wiersza BOM wybierz grupę konfiguracji Szafa.</span><span class="sxs-lookup"><span data-stu-id="824f5-147">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="824f5-148">Zatwierdź i aktywuj</span><span class="sxs-lookup"><span data-stu-id="824f5-148">Approve and activate</span></span>
1. <span data-ttu-id="824f5-149">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="824f5-149">Close the page.</span></span>
2. <span data-ttu-id="824f5-150">Kliknij przycisk Zatwierdź.</span><span class="sxs-lookup"><span data-stu-id="824f5-150">Click Approve.</span></span>
3. <span data-ttu-id="824f5-151">W polu Zatwierdzone przez wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="824f5-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="824f5-152">W polu Czy chcesz także zatwierdzić listę składową (BOM)? zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="824f5-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="824f5-153">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="824f5-153">Click OK.</span></span>
6. <span data-ttu-id="824f5-154">Kliknij Aktywacja.</span><span class="sxs-lookup"><span data-stu-id="824f5-154">Click Activate.</span></span>


