---
title: Ręcznie utworzone zlecenia pracy
description: W tym temacie opisano ręczne tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8c787dbc9889139df76b9b102deb18fce567e382
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017875"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="793db-103">Ręcznie utworzone zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="793db-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="793db-104">Można także ręcznie tworzyć zlecenia pracy na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="793db-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="793db-105">Na stronie **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**</span><span class="sxs-lookup"><span data-stu-id="793db-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="793db-106">Na stronie **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji** lub **Moje żądania konserwacji lokalizacji czynności konserwacyjnych**</span><span class="sxs-lookup"><span data-stu-id="793db-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="793db-107">Utwórz zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="793db-107">Create work order</span></span>

1. <span data-ttu-id="793db-108">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="793db-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="793db-109">Select **New**.</span></span>

3. <span data-ttu-id="793db-110">W oknie dialogowym **Utwórz zlecenie pracy** wybierz zlecenie pracy w polu **Typ zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="793db-111">Dodaj **Opis** jeśli jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="793db-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="793db-112">W polu **Składnik majątku** wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="793db-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="793db-113">Po wybraniu środka trwałego na liście rozwijanej **Składnik majątku** mogą być dostępne trzy karty:</span><span class="sxs-lookup"><span data-stu-id="793db-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="793db-114">**Aktywne składniki majątku** - ta karta zawiera listę wszystkich składników majątku ze stanem cyklu życia zasobu „Aktywny”.</span><span class="sxs-lookup"><span data-stu-id="793db-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="793db-115">**Widok składników majątku** - na tej karcie jest wyświetlany widok drzewa lokalizacji czynności konserwacyjnych i składników majątku zainstalowanych w tych lokalizacjach czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="793db-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="793db-116">**Moje składniki majątku** - na tej karcie znajdują się składniki majątku powiązane z lokalizacjami czynności konserwacyjnych, do których może być przypisany pracownik zalogowany do systemu.</span><span class="sxs-lookup"><span data-stu-id="793db-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="793db-117">(Aby uzyskać informacje dotyczące konfiguracji, należy zapoznać się z [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).) Jeśli dla pracownika nie jest skonfigurowana żadna lokalizacja czynności konserwacyjnych w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md), karta **Moje składniki majątku** jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="793db-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="793db-118">W polu **Typ zadania konserwacji** wybierz typ zadania konserwacji dla zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="793db-119">W razie potrzeby wybierz **Wariant typu zadania konserwacji** i **zawód**.</span><span class="sxs-lookup"><span data-stu-id="793db-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="793db-120">W razie potrzeby można zmienić poziom usługi zlecenia produkcyjnego w polu **poziomu usług**.</span><span class="sxs-lookup"><span data-stu-id="793db-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="793db-121">Wybierz daty **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** w polach pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="793db-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="793db-122">Kliknij **OK**, aby utworzyć zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="793db-123">Na stronie listy **Wszystkie zlecenia pracy** można edytować to zamówienie pracy w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="793db-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="793db-124">Należy uwzględnić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="793db-124">Note the following points:</span></span>

- <span data-ttu-id="793db-125">W widoku szczegółowym na stronie listy **Wszystkie zlecenia pracy** do zlecenia pracy można dodać kilka składników majątku, dodając wiersze na skróconej karcie **Zadania konserwacji zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="793db-126">Dla składnika moża wybrać tylko typy zadań konserwacji, które są określone w typie składnika majatku, który jest używany dla składnika majatku.</span><span class="sxs-lookup"><span data-stu-id="793db-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="793db-127">Jeśli zmienisz poziom usługi składnika majątku lub krytyczność składnika majątku po użyciu składnika majątku w zleceniu pracy, poziom usług lub krytyczność w zleceniu pracy nie zostanie odpowiednio zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="793db-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="793db-128">Aby uzyskać więcej informacji o poziomach usług i ich krytyczności, zapoznaj się z tematem [Poziomy usług składnika majątku](../setup-for-objects/object-priorities.md) i [Typy krytyczności składnika majątku](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="793db-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="793db-129">Krytyczność na zleceniu pracy jest przeliczana za każdym razem, gdy wiersz zadania zlecenia pracy jest dodawany lub usuwany ze zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="793db-130">W widoku szczegółowym **Wszystkie zlecenia pracy** > na karcie **Nagłówek** > na skróconej karcie **Harmonogram** w polach **Grupa odpowiedzialna** lub **Osoba odpowiedzialna** można wybrać grupę pracowników odpowiedzialnych za obsługę techniczną lub pracownika odpowiedzialnego za obsługę.</span><span class="sxs-lookup"><span data-stu-id="793db-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="793db-131">Te ustawienia można zmienić, gdy jest aktywne zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="793db-132">Można na przykład zmienić je po zmianie stanu cyklu życia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="793db-133">Automatyczne wybieranie dokonane podczas tworzenia zlecenia produkcyjnego jest oparte na ustawieniach na stronie **Odpowiedzialni konserwatorzy**.</span><span class="sxs-lookup"><span data-stu-id="793db-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="793db-134">W przypadku dodawania lub usuwania zadań związanych z zamówieniami pracy po utworzeniu zlecenia pracy i jeśli pola **Grupa odpowiedzialna** i **Osoba odpowiedzialna** są puste po zaktualizowaniu zlecenia pracy, Zarządzanie składnikami majątku stara się znaleźć możliwie pasującą odpowiedzialną grupę konserwatorów lub odpowiedzialnego konserwatora na stronie ustawień.</span><span class="sxs-lookup"><span data-stu-id="793db-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="793db-135">Jeśli pole **Grupa odpowiedzialna** lub **Osoba odpowiedzialna** jest już ustawione podczas aktualizowania zlecenia produkcyjnego, nie są wprowadzane żadne zmiany.</span><span class="sxs-lookup"><span data-stu-id="793db-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="793db-136">Aby uzyskać więcej informacji na temat konfiguracji odpowiedzialnych konserwatorów i grup konserwatorów, zobacz temat [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="793db-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="793db-137">Na stronie [Stan konserwacji](../controlling-and-reporting/maintenance-status.md) można obliczać uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="793db-138">W widoku szczegółów strony **Wszystkie zlecenia pracy** na skróconej karcie **Szczegóły wiersza** można używać pól **Szerokość geograficzna** i **Długość geograficzna** w celu dodania współrzędnych geograficznych wybranego składnika majątku w zadaniu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="793db-139">Utwórz powiązane zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="793db-139">Create related work order</span></span>

<span data-ttu-id="793db-140">Można utworzyć nowe zlecenie pracy odnoszące się do istniejącego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="793db-141">Jest to przydatne, jeśli użytkownik, na przykład, chce pracować z głównymi i pomocniczymi zleceniami pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="793db-142">Nowe zlecenie produkcyjne jest oparte na zadaniu zlecenia produkcyjnego z istniejącego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="793db-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="793db-143">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="793db-144">Wybierz zlecenie pracy, dla którego chcesz stworzyć powiązane zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="793db-145">W okienku akcji, na karcie **Zlecenie pracy**, w grupie **Nowe** wybierz **Powiązane zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="793db-146">W oknie dialogowym **Utwórz pokrewne zlecenie pracy** w polu **Zadanie zlecenia pracy** wybierz zadanie zlecenia pracy, dla którego chcesz stworzyć powiązane zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="793db-147">W polu **Typ zadania konserwacji** wybierz typ zadania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="793db-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="793db-148">W polach **Wariant typu zadania konserwacji** i **Zawód** wybierz wariant i zawód związany z typem zadania konserwacji według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="793db-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="793db-149">Jeśli to zlecenie pracy jest pierwszym powiązanym zleceniem pracy, które zostało utworzone dla wybranego zlecenia pracy, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="793db-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="793db-150">Wybierz opcje **Nowe zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="793db-151">W  polu **Typ zlecenia pracy** wybierz typ zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="793db-152">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="793db-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="793db-153">W polu **Poziom usług** w razie potrzeby można zmienić poziom usługi zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="793db-154">W polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** wybierz oczekiwaną datę początkową i końcową.</span><span class="sxs-lookup"><span data-stu-id="793db-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="793db-155">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="793db-155">Select **OK**.</span></span> <span data-ttu-id="793db-156">Nowe powiązane zlecenie produkcyjne jest wyświetlane na stronie listy **Wszystkie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="793db-157">Jeśli zlecenie pracy tworzone w tym powiązanym zleceniu pracy dla już ma powiązane zlecenia pracy, należy wykonać następujące kroki w celu dodania nowego zadania zlecenia pracy do istniejącego powiązanego zlecenia pracy:</span><span class="sxs-lookup"><span data-stu-id="793db-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="793db-158">Wybierz opcję **Dodaj do pokrewnego zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="793db-159">W polu **Zlecenie pracy** należy wybrać powiązane zlecenie pracy, do którego ma zostać dodane nowe zadanie zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="793db-160">W polu **Poziom usług** w razie potrzeby można zmienić poziom usługi zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="793db-161">W polach **Oczekiwane rozpoczęcie** i **Oczekiwane zakończenie** zmień oczekiwaną datę początkową i końcową według potrzeby.</span><span class="sxs-lookup"><span data-stu-id="793db-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="793db-162">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="793db-162">Select **OK**.</span></span> <span data-ttu-id="793db-163">Zadanie zlecenia produkcyjnego jest dodawane do istniejącego powiązanego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="793db-164">Na poniższej ilustracji pokazano przykład okna dialogowego **Utwórz powiązane zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Rysunek 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="793db-166">W przypadku skonfigurowania powiązanej maski zleceń pracy w polach **Parametry zarządzania składnikami majątku** > **karta Zlecenia pracy** > **Maska powiązanego zlecenia pracy**, identyfikatory zleceń pracy zostaną utworzone zgodnie z konfiguracją maski.</span><span class="sxs-lookup"><span data-stu-id="793db-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="793db-167">Jeśli nie skonfigurowano powiązanej maski zlecenia pracy, dla pokrewnych zleceń pracy jest użyty kolejny dostępny identyfikator zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="793db-168">Kopiuj zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="793db-168">Copy a work order</span></span>

<span data-ttu-id="793db-169">Istnieje możliwość szybkiego utworzenia nowego zlecenia pracy na podstawie istniejącego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="793db-170">Ta metoda pracy z zleceniami pracy różni się od tworzenia zleceń pracy na podstawie [planów konserwacji](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="793db-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="793db-171">Jest to przydatne na przykład wtedy, gdy zlecenie pracy zawiera wiele zadań zlecenia pracy z różnymi zadaniami dotyczącymi różnych składników majątku, które powinny zostać wykonane w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="793db-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="793db-172">Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="793db-173">Umożliwia wybranie zlecenia pracy, z którego ma zostać skopiowana zawartość.</span><span class="sxs-lookup"><span data-stu-id="793db-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="793db-174">W okienku akcji, na karcie > **Zlecenie pracy** > w grupie **Nowe** wybierz **Kopiuj zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="793db-175">Zostanie wyświetlona konfiguracja zlecenia produkcyjnego z wybranego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="793db-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="793db-176">W razie potrzeby można edytować niektóre pola.</span><span class="sxs-lookup"><span data-stu-id="793db-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="793db-177">Wybierz **OK**, aby utworzyć nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="793db-178">Na stronie listy **Wszystkie zlecenia pracy** można edytować to zamówienie pracy w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="793db-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="793db-179">Po utworzeniu nowego zlecenia produkcyjnego niektóre informacje są kopiowane bezpośrednio z istniejącego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="793db-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="793db-180">Nie są kopiowane informacje o prognozach, narzędziach, listach kontrolnych obsługi, lokalizacji czynności konserwacyjnych, adresach i planowaniu.</span><span class="sxs-lookup"><span data-stu-id="793db-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="793db-181">Zamiast tego jest on inicjowany z poziomu bieżącej konfiguracji w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="793db-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="793db-182">Z tego względu, jeśli informacje te zostały zmienione między momentem utworzenia pierwszego zlecenia pracy a momentem dokonania kopii zlecenia, zmiany zostaną uwzględnione w nowym zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="793db-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="793db-183">Przykłady to między innymi zmiany prognoz lub aktualizacje list kontrolnych konserwowanego składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="793db-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="793db-184">Na poniższej ilustracji przedstawiono przykład okna dialogowego **Kopiuj zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Rysunek 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="793db-186">Tworzenie zlecenia pracy oparte na żądaniu konserwacji</span><span class="sxs-lookup"><span data-stu-id="793db-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="793db-187">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Żądania konserwacji** > **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="793db-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="793db-188">Wybierz żądanie konserwacyji, dla którego chcesz utworzyć zlecenie pracy i kliknij pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="793db-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="793db-189">W okienku akcji, na karcie > **Żądanie konserwacji** > w grupie **Nowe** wybierz **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="793db-190">W oknie dialogowym **Zlecenie pracy** określ pola.</span><span class="sxs-lookup"><span data-stu-id="793db-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="793db-191">Jeśli w ramach zlecenia serwisowego wybrano typ zadania obsługi, można wybrać inny typ zadania obsługi, jeśli jest on wymagany podczas tworzenia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="793db-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="793db-192">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="793db-192">Select **OK**.</span></span> <span data-ttu-id="793db-193">Komunikat powiadamia, że zlecenie pracy zostało utworzone.</span><span class="sxs-lookup"><span data-stu-id="793db-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="793db-194">Aby zobaczyć zlecenia pracy, które są połączone z żądaniem konserwacji, wybierz żądanie konserwacji na stronie list **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="793db-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="793db-195">W okienku akcji, na karcie **Żądanie konserwacji** w grupie **Wyświetl** wybierz **Zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="793db-196">Na poniższej ilustracji przedstawiono przykład okna dialogowego **Tworzenie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="793db-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Rysunek 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="793db-198">Jeśli chcesz, żeby zlecenia pracy były tworzone automatycznie, możesz zaplanować zadania planu konserwacji lub ustawić „Automatyczne tworzenie” [planów konserwacji](../preventive-and-reactive-maintenance/maintenance-plans.md) lub [serii czynności konserwacyjnych](../preventive-and-reactive-maintenance/maintenance-rounds.md) dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="793db-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="793db-199">Zlecenia pracy utworzone na podstawie żądań konserwacji na stronie listy **Wszystkie harmonogramy konserwacji** mają typy zadań konserwacji, które są wybrane w żądaniach konserwacji.</span><span class="sxs-lookup"><span data-stu-id="793db-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>

