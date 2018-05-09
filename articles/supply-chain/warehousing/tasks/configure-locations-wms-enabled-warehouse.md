--- 
title: "Konfigurowanie lokalizacji w magazynie z obsługą WMS"
description: "W tym przewodniku pokazano, jak skonfigurować lokalizację dla nowego magazynu obsługującego WMS (magazynu, który używa zaawansowanych procesów zarządzania magazynem)."
author: perlynne
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
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7a920ae932cb38f70d06b33ccf688dc713fcb16c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a><span data-ttu-id="7ca92-103">Konfigurowanie lokalizacji w magazynie z obsługą WMS</span><span class="sxs-lookup"><span data-stu-id="7ca92-103">Configure locations in a WMS-enabled warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ca92-104">W tym przewodniku pokazano, jak skonfigurować lokalizację dla nowego magazynu obsługującego WMS (magazynu, który używa zaawansowanych procesów zarządzania magazynem).</span><span class="sxs-lookup"><span data-stu-id="7ca92-104">This guide shows you how to configure the location setup for a new WMS-enabled warehouse (a warehouse that uses advanced warehouse management processes).</span></span> <span data-ttu-id="7ca92-105">Ten proces jest zwykle wykonywany przez kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-105">The process is typically done by a warehouse manager.</span></span> <span data-ttu-id="7ca92-106">Można wykonać zadania z tego przewodnika przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="7ca92-106">You can run this guide in demo data company USMF or on your own data.</span></span> <span data-ttu-id="7ca92-107">Warunkiem wstępnym jest posiadanie co najmniej jednego skonfigurowanego oddziału.</span><span class="sxs-lookup"><span data-stu-id="7ca92-107">A precondition is that you have at least one site configured.</span></span>


## <a name="create-a-new-warehouse"></a><span data-ttu-id="7ca92-108">Tworzenie nowego magazynu</span><span class="sxs-lookup"><span data-stu-id="7ca92-108">Create a new warehouse</span></span>
1. <span data-ttu-id="7ca92-109">Przejdź do okna Magazyny.</span><span class="sxs-lookup"><span data-stu-id="7ca92-109">Go to Warehouses.</span></span>
2. <span data-ttu-id="7ca92-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-110">Click New.</span></span>
3. <span data-ttu-id="7ca92-111">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-111">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="7ca92-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-113">W polu Oddział wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-113">In the Site field, type a value.</span></span>
6. <span data-ttu-id="7ca92-114">Rozwiń lub zwiń sekcję Magazyn.</span><span class="sxs-lookup"><span data-stu-id="7ca92-114">Expand or collapse the Warehouse section.</span></span>
7. <span data-ttu-id="7ca92-115">W opcji Użyj procesów zarządzania magazynami zaznacz wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="7ca92-115">Set the Use warehouse management processes option to Yes.</span></span>
    * <span data-ttu-id="7ca92-116">To ustawienie pozwala uruchomiać zaawansowane procesy magazynowe przy użyciu pracy magazynowej i urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="7ca92-116">This setting allows you to  run advanced warehousing processes using warehouse work and mobile devices.</span></span>  
8. <span data-ttu-id="7ca92-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-117">Close the page.</span></span>

## <a name="define-a-location-format"></a><span data-ttu-id="7ca92-118">Definiowanie formatu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-118">Define a location format</span></span>
1. <span data-ttu-id="7ca92-119">Przejdź do okna Formaty lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-119">Go to Location formats.</span></span>
    * <span data-ttu-id="7ca92-120">Formaty lokalizacji to system nazewnictwa używany do tworzenia unikatowych i spójnych nazw dla różnych pozycji pojemników w lokalizacji używanych w magazynie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-120">Location formats are a naming-system used to create unique and consistent names for the different location bin positions used within a warehouse.</span></span> <span data-ttu-id="7ca92-121">Może być korzystne używanie separatorów jako elementu formatu lokalizacji, aby ułatwić identyfikowanie składników lokalizacji, takich jak numer alei.</span><span class="sxs-lookup"><span data-stu-id="7ca92-121">It can be useful to use separators as part of the location format to make it easier to identify components of the location such as the aisle number.</span></span> <span data-ttu-id="7ca92-122">W tym przykładzie utworzymy nazwę z czterema składnikami.</span><span class="sxs-lookup"><span data-stu-id="7ca92-122">In this example, we’ll create a name with four components.</span></span> <span data-ttu-id="7ca92-123">Mogą to być na przykład korytarz, regał, półka i pojemnik.</span><span class="sxs-lookup"><span data-stu-id="7ca92-123">For example, these could be aisle, rack, shelf, and bin.</span></span>  
2. <span data-ttu-id="7ca92-124">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-124">Click New.</span></span>
3. <span data-ttu-id="7ca92-125">W polu Format lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-125">In the Location format field, type a value.</span></span>
4. <span data-ttu-id="7ca92-126">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-126">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-127">W polu Opis segmentu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-127">In the Segment description field, type a value.</span></span>
    * <span data-ttu-id="7ca92-128">Opisuje to, co reprezentuje pierwsza część nazwy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-128">This describes what the first component of the location name represents.</span></span> <span data-ttu-id="7ca92-129">Na przykład może to być korytarz.</span><span class="sxs-lookup"><span data-stu-id="7ca92-129">For example, it could be Aisle.</span></span>  
6. <span data-ttu-id="7ca92-130">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-130">In the Length field, enter a number.</span></span>
    * <span data-ttu-id="7ca92-131">Określa, ile znaków musi mieć ta część nazwy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-131">This determines how many characters this part of the location name must have.</span></span> <span data-ttu-id="7ca92-132">Należy zwrócić uwagę, że suma liczby znaków we wszystkich składnikach nazwy, łącznie z separatorami, nie może przekroczyć 10.</span><span class="sxs-lookup"><span data-stu-id="7ca92-132">Note that the total of all components in the name, including the separators, cannot exceed 10 characters.</span></span>  
7. <span data-ttu-id="7ca92-133">W polu Separator wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-133">In the Separator field, type a value.</span></span>
    * <span data-ttu-id="7ca92-134">Określa, który znak lub symbol jest używany między pierwszym a drugim składnikiem nazwy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-134">This determines which character or symbol is used between the first and second component of the name.</span></span>  
8. <span data-ttu-id="7ca92-135">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-135">Click New.</span></span>
9. <span data-ttu-id="7ca92-136">W polu Opis segmentu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-136">In the Segment description field, type a value.</span></span>
10. <span data-ttu-id="7ca92-137">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-137">In the Length field, enter a number.</span></span>
11. <span data-ttu-id="7ca92-138">W polu Separator wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-138">In the Separator field, type a value.</span></span>
12. <span data-ttu-id="7ca92-139">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-139">Click New.</span></span>
13. <span data-ttu-id="7ca92-140">W polu Opis segmentu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-140">In the Segment description field, type a value.</span></span>
14. <span data-ttu-id="7ca92-141">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-141">In the Length field, enter a number.</span></span>
15. <span data-ttu-id="7ca92-142">W polu Separator wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-142">In the Separator field, type a value.</span></span>
16. <span data-ttu-id="7ca92-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-143">Click New.</span></span>
17. <span data-ttu-id="7ca92-144">W polu Opis segmentu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-144">In the Segment description field, type a value.</span></span>
18. <span data-ttu-id="7ca92-145">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-145">In the Length field, enter a number.</span></span>
19. <span data-ttu-id="7ca92-146">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7ca92-146">Click Save.</span></span>
20. <span data-ttu-id="7ca92-147">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-147">Close the page.</span></span>

## <a name="define-location-types"></a><span data-ttu-id="7ca92-148">Definiowanie typów lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-148">Define location types</span></span>
1. <span data-ttu-id="7ca92-149">Przejdź do okna Typy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-149">Go to Location types.</span></span>
    * <span data-ttu-id="7ca92-150">Typy lokalizacji mogą służyć jako opcje filtrowania do kontrolowania różnych procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ca92-150">Location types can be used as filtering options to control the different warehouse management processes.</span></span> <span data-ttu-id="7ca92-151">Jako minimum należy utworzyć pośrednie i docelowe typy lokalizacji wysyłki w celu zdefiniowania procesu zarządzania wysyłkami z magazynu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-151">As a minimum, you need to create staging and final shipping location types in order to define the outbound warehouse management process.</span></span>  
2. <span data-ttu-id="7ca92-152">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-152">Click New.</span></span>
3. <span data-ttu-id="7ca92-153">W polu Typ lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-153">In the Location type field, type a value.</span></span>
4. <span data-ttu-id="7ca92-154">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="7ca92-154">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7ca92-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-155">Close the page.</span></span>

## <a name="define-location-profile"></a><span data-ttu-id="7ca92-156">Definiowanie profilu lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-156">Define location profile</span></span>
1. <span data-ttu-id="7ca92-157">Przejdź do okna Profile lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-157">Go to Location profiles.</span></span>
    * <span data-ttu-id="7ca92-158">Zdefiniowanie profili lokalizacji jest bardzo ważne.</span><span class="sxs-lookup"><span data-stu-id="7ca92-158">The definition of location profiles is very important.</span></span> <span data-ttu-id="7ca92-159">W tym miejscu można kontrolować pojemność zgrupowanych lokalizacji oraz zasady dotyczących tego, które zapasy i jak są przechowywane.</span><span class="sxs-lookup"><span data-stu-id="7ca92-159">Grouped locations capacity can be controlled here, as well as the policies related to what inventory gets stored, and how it is stored.</span></span> <span data-ttu-id="7ca92-160">Profile lokalizacji mogą służyć jako opcje filtrowania do kontrolowania różnych procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ca92-160">Location profiles can be used as filtering options to control the different warehouse management processes.</span></span> <span data-ttu-id="7ca92-161">Jako minimum należy utworzyć profil lokalizacji użytkownika w celu umożliwienia procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ca92-161">As a minimum, you must create a user location profile in order to enable the warehouse management processes.</span></span>  
2. <span data-ttu-id="7ca92-162">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-162">Click New.</span></span>
3. <span data-ttu-id="7ca92-163">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-163">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="7ca92-164">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-164">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-165">W polu Format lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-165">In the Location format field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7ca92-166">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-166">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7ca92-167">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-167">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7ca92-168">W polu Typ lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-168">In the Location type field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7ca92-169">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-169">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="7ca92-170">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-170">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7ca92-171">Zaznacz lub wyczyść pole wyboru Pozwól na mieszane stany zapasów.</span><span class="sxs-lookup"><span data-stu-id="7ca92-171">Select or clear the Allow mixed  inventory statuses check box.</span></span>
    * <span data-ttu-id="7ca92-172">Włącz tę opcję, aby zezwalać na mieszane wartości stanu zapasów w lokalizacjach, które mają być grupowane w tym profilu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-172">Enable this option if you want to allow mixed inventory status values in the locations that are going to be grouped by this location profile.</span></span>  
12. <span data-ttu-id="7ca92-173">Zaznacz lub wyczyść pole wyboru Zastąp reguły dla dni partii.</span><span class="sxs-lookup"><span data-stu-id="7ca92-173">Select or clear the Override rules for batch days check box.</span></span>
    * <span data-ttu-id="7ca92-174">Włącz tę opcję, aby zastąpić regułę dopuszczalnej liczby dni różnicy daty ważności partii zapasów i umożliwić mieszanie partii zapasów, które nie przestrzegają tej reguły.</span><span class="sxs-lookup"><span data-stu-id="7ca92-174">Enable this option to override the rule for how many days the inventory batch expiration dates can differ, to allow mixing of inventory batches that don’t obeying this rule.</span></span>  
13. <span data-ttu-id="7ca92-175">Zaznacz lub wyczyść pole wyboru Pozwól na inwentaryzację ciągłą.</span><span class="sxs-lookup"><span data-stu-id="7ca92-175">Select or clear the Allow cycle counting check box.</span></span>
    * <span data-ttu-id="7ca92-176">Włącz tę opcję, aby zezwolić na inwentaryzację ciągłą we wszystkich lokalizacjach, które mają być grupowane w tym profilu lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-176">Enable this option to allow cycle counting processing in all the locations that are going to be grouped by this location profile.</span></span>  
14. <span data-ttu-id="7ca92-177">Rozwiń lub zwiń sekcję Wymiary.</span><span class="sxs-lookup"><span data-stu-id="7ca92-177">Expand or collapse the Dimensions section.</span></span>
    * <span data-ttu-id="7ca92-178">Karta Wymiary umożliwia zdefiniowanie parametrów oraz metod w celu umożliwienia dokładnego obliczania obciążenia pojemności w każdej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-178">The Dimensions tab allows you to define parameters and methods to enable precise calculations of the load capacity within each of the locations.</span></span>  
15. <span data-ttu-id="7ca92-179">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-179">Close the page.</span></span>

## <a name="enable-warehouse-management-parameters"></a><span data-ttu-id="7ca92-180">Włączanie parametrów zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="7ca92-180">Enable warehouse management parameters</span></span>
1. <span data-ttu-id="7ca92-181">Przejdź do okna Parametry zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ca92-181">Go to Warehouse management parameters.</span></span>
    * <span data-ttu-id="7ca92-182">Aby móc wykonywać prace magazynowe, należy ustawić parametry profilu lokalizacji użytkownika dla lokalizacji pośredniej i lokalizacji końcowej wysyłki. Z chwilą zakończenia procesu wysyłki w lokalizacji końcowej wysyłki o zdefiniowanym typie powiązane transakcje wysyłki zostaną zaktualizowane stanu „Pobrane”.</span><span class="sxs-lookup"><span data-stu-id="7ca92-182">To be able to process warehouse work, you need to set parameters for the user location profile the staging location type, and the final shipping location type  As soon as the outbound process ends at the final shipping location type that you define, the related outbound transactions will be updated to ‘Picked’.</span></span>  
2. <span data-ttu-id="7ca92-183">Rozwiń lub zwiń sekcję Profile lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-183">Expand or collapse the Location profiles section.</span></span>
3. <span data-ttu-id="7ca92-184">W polu Lokalizacja użytkownika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-184">In the User location field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7ca92-185">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-185">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7ca92-186">Rozwiń lub zwiń sekcję Typy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-186">Expand or collapse the Location types section.</span></span>
6. <span data-ttu-id="7ca92-187">W polu Typ lokalizacji pośredniej kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-187">In the Staging location type field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7ca92-188">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-188">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7ca92-189">W polu Typ lokalizacja końcowej wysyłki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-189">In the Final shipping location type field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7ca92-190">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-190">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="7ca92-191">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-191">Close the page.</span></span>

## <a name="define-warehouse-zone-groups"></a><span data-ttu-id="7ca92-192">Definiowanie grup stref magazynowych</span><span class="sxs-lookup"><span data-stu-id="7ca92-192">Define warehouse zone groups</span></span>
1. <span data-ttu-id="7ca92-193">Przejdź do okna Grupy stref magazynowych.</span><span class="sxs-lookup"><span data-stu-id="7ca92-193">Go to Warehouse zone groups.</span></span>
    * <span data-ttu-id="7ca92-194">Strefy magazynowe mogą służyć jako filtry opcji do kontrolowania różnych procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="7ca92-194">Warehouse zones can be used as filters for options to control the different warehouse management processes.</span></span> <span data-ttu-id="7ca92-195">Aby można było zdefiniować strefę, należy utworzyć grupę stref.</span><span class="sxs-lookup"><span data-stu-id="7ca92-195">You need to create a zone group before you can define a zone.</span></span>  
2. <span data-ttu-id="7ca92-196">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-196">Click New.</span></span>
3. <span data-ttu-id="7ca92-197">W polu Identyfikator grupy strefy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-197">In the Zone group ID field, type a value.</span></span>
4. <span data-ttu-id="7ca92-198">W polu Nazwa grupy strefy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-198">In the Zone group name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-199">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-199">Close the page.</span></span>

## <a name="define-warehouse-zones"></a><span data-ttu-id="7ca92-200">Definiowanie strefy magazynowych</span><span class="sxs-lookup"><span data-stu-id="7ca92-200">Define Warehouse zones</span></span>
1. <span data-ttu-id="7ca92-201">Przejdź do okna Strefy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-201">Go to Zones.</span></span>
2. <span data-ttu-id="7ca92-202">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-202">Click New.</span></span>
3. <span data-ttu-id="7ca92-203">W polu Identyfikator strefy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-203">In the Zone ID field, type a value.</span></span>
4. <span data-ttu-id="7ca92-204">W polu Nazwa strefy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-204">In the Zone name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-205">W polu Identyfikator grupy strefy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-205">In the Zone group ID field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7ca92-206">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-206">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7ca92-207">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-207">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7ca92-208">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-208">Close the page.</span></span>

## <a name="create-locations-using-the-location-setup-wizard"></a><span data-ttu-id="7ca92-209">Tworzenie lokalizacji za pomocą Kreatora konfiguracji lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-209">Create locations using the Location setup wizard</span></span>
1. <span data-ttu-id="7ca92-210">Przejdź do okna Kreator konfiguracji lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-210">Go to Location setup wizard.</span></span>
2. <span data-ttu-id="7ca92-211">W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-211">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7ca92-212">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-212">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7ca92-213">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-213">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7ca92-214">W polu Identyfikator strefy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-214">In the Zone ID field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7ca92-215">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-215">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7ca92-216">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-216">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7ca92-217">W polu Identyfikator profilu lokalizacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-217">In the Location profile ID field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="7ca92-218">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-218">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="7ca92-219">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-219">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7ca92-220">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7ca92-220">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="7ca92-221">W polu Numer początkowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-221">In the From number field, enter a number.</span></span>
    * <span data-ttu-id="7ca92-222">Wartości w polach Numer początkowy i Numer końcowy określają, ile lokalizacji zostanie utworzonych.</span><span class="sxs-lookup"><span data-stu-id="7ca92-222">The From number and To number fields define how many locations will be created.</span></span> <span data-ttu-id="7ca92-223">Na przykład jeśli ustawisz Numer początkowy na 1, a Numer końcowy na 3 dla wszystkich czterech wierszy w formacie lokalizacji, zostanie utworzonych 81 lokalizacji (3x3x3x3).</span><span class="sxs-lookup"><span data-stu-id="7ca92-223">For example, if you set From number to 1 and To number to 3 for all four lines in the location format, 81 locations will be created (3x3x3x3).</span></span>  
13. <span data-ttu-id="7ca92-224">W polu Numer końcowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-224">In the To number field, enter a number.</span></span>
14. <span data-ttu-id="7ca92-225">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-225">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="7ca92-226">W polu Numer początkowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-226">In the From number field, enter a number.</span></span>
16. <span data-ttu-id="7ca92-227">W polu Numer końcowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-227">In the To number field, enter a number.</span></span>
17. <span data-ttu-id="7ca92-228">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-228">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="7ca92-229">W polu Numer początkowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-229">In the From number field, enter a number.</span></span>
19. <span data-ttu-id="7ca92-230">W polu Numer końcowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-230">In the To number field, enter a number.</span></span>
20. <span data-ttu-id="7ca92-231">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7ca92-231">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="7ca92-232">W polu Numer początkowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-232">In the From number field, enter a number.</span></span>
22. <span data-ttu-id="7ca92-233">W polu Numer końcowy wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-233">In the To number field, enter a number.</span></span>
23. <span data-ttu-id="7ca92-234">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="7ca92-234">Click Create.</span></span>

## <a name="create-locations-manually"></a><span data-ttu-id="7ca92-235">Ręczne tworzenie lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-235">Create locations manually</span></span>
1. <span data-ttu-id="7ca92-236">Przejdź do okna Lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="7ca92-236">Go to Locations.</span></span>
    * <span data-ttu-id="7ca92-237">Można łatwo ręcznie tworzyć lokalizacje w magazynie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-237">Manually creation of locations within a warehouse can easily be done.</span></span> <span data-ttu-id="7ca92-238">Nazwa lokalizacji i identyfikator profilu lokalizacji są wartościami wymaganymi.</span><span class="sxs-lookup"><span data-stu-id="7ca92-238">The location name and the Location profile ID are mandatory values.</span></span>  
2. <span data-ttu-id="7ca92-239">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-239">Click New.</span></span>
3. <span data-ttu-id="7ca92-240">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-240">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="7ca92-241">W polu Lokalizacja wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-241">In the Location field, type a value.</span></span>
    * <span data-ttu-id="7ca92-242">Należy zauważyć, że tworzysz tutaj nową lokalizację, więc należy wpisać nową unikatową nazwę zamiast wybierać już istniejącą.</span><span class="sxs-lookup"><span data-stu-id="7ca92-242">Note that you're creating a new location here, so you need to type a new unique name, rather than selecting an existing one.</span></span>  
5. <span data-ttu-id="7ca92-243">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-243">In the Location profile ID field, type a value.</span></span>
6. <span data-ttu-id="7ca92-244">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-244">Close the page.</span></span>

## <a name="define-pack-size-categories"></a><span data-ttu-id="7ca92-245">Definiowanie kategorii wielkości pakunków</span><span class="sxs-lookup"><span data-stu-id="7ca92-245">Define Pack size categories</span></span>
1. <span data-ttu-id="7ca92-246">Przejdź do okna Kategorie wielkości pakunków.</span><span class="sxs-lookup"><span data-stu-id="7ca92-246">Go to Pack size categories.</span></span>
    * <span data-ttu-id="7ca92-247">Kategorie wielkości pakunków mogą służyć do grupowania towarów o podobnych fizycznie rozmiarach opakowań.</span><span class="sxs-lookup"><span data-stu-id="7ca92-247">Pack size categories can be used to group items that have similar physical packing sizes.</span></span> <span data-ttu-id="7ca92-248">W tym przykładzie kategoria wielkości pakunków posłuży do sterowania pojemnością w lokalizacjach pobrania w określonej strefie magazynu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-248">In this example the pack size category will be used to control the capacity at the picking locations within a specific zone of the warehouse.</span></span> <span data-ttu-id="7ca92-249">Należy zauważyć, że najpierw należy przypisać identyfikator kategorii wielkości pakunków do jednostki zwalnianego produktu, aby umożliwić używanie kategorii w ramach przetwarzania limitów składowania.</span><span class="sxs-lookup"><span data-stu-id="7ca92-249">Please note that the pack size category ID must be assigned to the released product entity in order to be used as part of the stocking limits processing.</span></span>  
2. <span data-ttu-id="7ca92-250">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-250">Click New.</span></span>
3. <span data-ttu-id="7ca92-251">W polu Identyfikator kategorii wielkości pakunków wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-251">In the Pack size category ID field, type a value.</span></span>
4. <span data-ttu-id="7ca92-252">W polu Nazwa kategorii wielkości pakunków wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-252">In the Pack size category name field, type a value.</span></span>
5. <span data-ttu-id="7ca92-253">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-253">Close the page.</span></span>

## <a name="define-location-stocking-limits"></a><span data-ttu-id="7ca92-254">Określ limity składowania w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7ca92-254">Define location stocking limits</span></span>
1. <span data-ttu-id="7ca92-255">Przejdź do okna Limity składowania w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7ca92-255">Go to Location stocking limits.</span></span>
    * <span data-ttu-id="7ca92-256">Limity składowania w lokalizacji pomagają się upewnić, że nie jest tworzone żądanie umieszczenia zapasów w lokalizacji, która nie ma fizycznej pojemności do zmieszczenia tych zapasów.</span><span class="sxs-lookup"><span data-stu-id="7ca92-256">Location stocking limits help to make sure that work isn't created to request that inventory to be put in a location that doesn't have the physical capacity to carry the inventory.</span></span>  
2. <span data-ttu-id="7ca92-257">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-257">Click New.</span></span>
3. <span data-ttu-id="7ca92-258">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-258">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="7ca92-259">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-259">In the Location profile ID field, type a value.</span></span>
5. <span data-ttu-id="7ca92-260">W polu Identyfikator kategorii wielkości pakunków wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-260">In the Pack size category ID field, type a value.</span></span>
6. <span data-ttu-id="7ca92-261">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-261">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="7ca92-262">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7ca92-262">Click Save.</span></span>
8. <span data-ttu-id="7ca92-263">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-263">Close the page.</span></span>

## <a name="define-fixed-picking-locations"></a><span data-ttu-id="7ca92-264">Definiowanie stałych lokalizacji pobrania</span><span class="sxs-lookup"><span data-stu-id="7ca92-264">Define fixed picking locations</span></span>
1. <span data-ttu-id="7ca92-265">Przejdź do okna Stałe lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="7ca92-265">Go to Fixed locations.</span></span>
    * <span data-ttu-id="7ca92-266">Lokalizacje, które mają być używane, można określić dla każdego produktu lub dla wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-266">You can define the locations to be used per product or per product variant.</span></span> <span data-ttu-id="7ca92-267">Istnieje możliwość utworzenia wielu stałych lokalizacji dla tego samego produktu w tym samym magazynie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-267">It is possible to create multiple fixed locations for the same product within the same warehouse.</span></span>  
2. <span data-ttu-id="7ca92-268">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7ca92-268">Click New.</span></span>
3. <span data-ttu-id="7ca92-269">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-269">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="7ca92-270">W polu Magazyn wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7ca92-270">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="7ca92-271">W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7ca92-271">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7ca92-272">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7ca92-272">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7ca92-273">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7ca92-273">Close the page.</span></span>


