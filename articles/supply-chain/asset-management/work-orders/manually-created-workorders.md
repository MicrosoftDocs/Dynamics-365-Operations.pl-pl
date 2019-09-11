---
title: Ręcznie utworzone zlecenia pracy
description: W tym temacie opisano ręczne tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875839"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="2eb89-103">Ręcznie utworzone zlecenia pracy</span><span class="sxs-lookup"><span data-stu-id="2eb89-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="2eb89-104">Można także ręcznie tworzyć zlecenia pracy na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="2eb89-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="2eb89-105">We **wszystkich zleceniach** lub **aktywnych zleceniach roboczych**</span><span class="sxs-lookup"><span data-stu-id="2eb89-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="2eb89-106">we **wszystkich żądań konserwacji** lub **aktywnych żądań konserwacji** albo **moich żądań konserwacji lokalizacji czynności konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="2eb89-107">Utwórz zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="2eb89-107">Create work order</span></span>

1. <span data-ttu-id="2eb89-108">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2eb89-109">Kliknij przycisk **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-109">Click the **New** button.</span></span>

3. <span data-ttu-id="2eb89-110">W menu rozwijanym **Utwórz zlecenie pracy** wybierz typ zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="2eb89-111">Dodaj opis jeśli jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="2eb89-111">If required, select a description.</span></span>

5. <span data-ttu-id="2eb89-112">Umożliwia wybór środka trwałego dla zlecenia produkcyjnego oraz typu zadania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2eb89-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="2eb89-113">Po wybraniu nadrzędnego składnika majątku dwie lub trzy karty są dostępne: karta **Moje składniki majątku** zawiera składniki majątku związane z lokalizacjami czynności konserwacyjnych, do których możesz (pracownik, który jest zalogowany w systemie) zostać przydzielony (ustalane w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="2eb89-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="2eb89-114">Jeśli lokalizacje czynności konserwacyjnych nie są skonfigurowane dla konserwatora w formularzu [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md), karta **Moje składniki majątku** nie będzie widoczna.</span><span class="sxs-lookup"><span data-stu-id="2eb89-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="2eb89-115">Karta **Aktywne składniki majątku** zawiera listę wszystkich składników majątku ze stanem cyklu życia zasobu „Aktywny”.</span><span class="sxs-lookup"><span data-stu-id="2eb89-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="2eb89-116">Na karcie **Widok składników majątku** jest wyświetlany widok drzewa lokalizacji czynności konserwacyjnych i składników majątku zainstalowanych w tych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="2eb89-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="2eb89-117">W razie potrzeby wybierz **Wariant typu zadania konserwacji** i **zawód**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="2eb89-118">W razie potrzeby można zmienić poziom usługi zlecenia produkcyjnego w polu **poziomu usług**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="2eb89-119">Wybierz oczekiwane daty rozpoczęcia i zakończenia w polach pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="2eb89-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="2eb89-120">Kliknij przycisk **OK**, aby utworzyć nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="2eb89-121">W razie potrzeby edytuj zlecenie produkcyjne we **wszystkichzleceniach roboczych**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="2eb89-122">We **wszystkich zleceniach pracy** do zlecenia produkcyjnego w widoku Szczegóły można dodać kilka środków trwałych, dodając wiersze w skróconej karcie **Zadania konserwacji zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="2eb89-123">Dla składnika moża wybrać tylko typy zadań konserwacji, które są związane z konfiguracją typu składnika majatku, który jest używany dla składnika majatku.</span><span class="sxs-lookup"><span data-stu-id="2eb89-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="2eb89-124">Jeśli zmieniłeś poziom obsługi zasobów lub krytyczność zasobu po użyciu ich w zleceniu pracy (odnieś się do [Poziomy usług składnika majątku](../setup-for-objects/object-priorities.md) [Krytyczności składników majątku](../setup-for-objects/object-criticalities.md)), poziom usługi lub krytyczność zlecenia pracy nie są odpowiednio aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="2eb89-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="2eb89-125">Krytyczność zlecenia pracy jest ponownie obliczana za każdym razem, gdy wiersz zlecenia pracy jest dodawany lub usuwany w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="2eb89-126">W **Wszystkie zlecenia pracy** widoku szczegółowym > widok **Nagłówek** > na skróconej karcie **Harmonogram** można wybrać grupę pracowników odpowiedzialnych za obsługę techniczną lub pracownika odpowiedzialnego za obsługę w polach **Grupa odpowiedzialna** lub **Osoba odpowiedzialna**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="2eb89-127">Te ustawienia można zmieniać, dopóki jest aktywne zlecenie produkcyjne, na przykład w przypadku zmiany stanu cyklu życia zamówienia pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="2eb89-128">Automatyczne wybieranie dokonane podczas tworzenia zlecenia produkcyjnego jest oparte na ustawieniach **odpowiedzialnych pracowników obsługi technicznej**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="2eb89-129">W przypadku dodawania lub usuwania zadań związanych z zamówieniami pracy po utworzeniu zlecenia produkcyjnego pole **Grupa odpowiedzialna** i **osoba odpowiedzialna** są puste po zaktualizowaniu zlecenia produkcyjnego formularz ustawień dla grupy pracowników odpowiedzialnej za konserwację lub odpowiedzialnego pracownika obsługi.</span><span class="sxs-lookup"><span data-stu-id="2eb89-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="2eb89-130">Jeśli pole **grupy** lub **osoby** odpowiedzialnej jest już wypełnione podczas aktualizowania zlecenia produkcyjnego, nie są wprowadzane żadne zmiany.</span><span class="sxs-lookup"><span data-stu-id="2eb89-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="2eb89-131">W **Stan konserwacji** można obliczać uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="2eb89-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="2eb89-132">W skróconej karcie **szczegółów wiersza** należy używać **pól szerokości geograficznej** i **długości geograficznej** w celu dodania współrzędnych geograficznych środka trwałego wybranego dla zadania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="2eb89-133">Utwórz powiązane zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="2eb89-133">Create related work order</span></span>

<span data-ttu-id="2eb89-134">Można utworzyć powiązane zlecenie robocze z istniejącym zleceniem produkcyjnym, jeśli na przykład użytkownik chce pracować z głównymi i pomocniczymi zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="2eb89-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="2eb89-135">Nowe zlecenie produkcyjne jest oparte na zadaniu zlecenia produkcyjnego z istniejącego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="2eb89-136">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2eb89-137">Wybierz zlecenie produkcyjne, dla którego chcesz wykonać powiązane zlecenie</span><span class="sxs-lookup"><span data-stu-id="2eb89-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="2eb89-138">Kliknij **Powiązane zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="2eb89-139">W oknie rozwijanym **Utwórz pokrewne zlecenie pracy** wybierz zadanie zlecenia produkcyjnego, dla którego ma zostać utworzone powiązane zlecenie produkcyjne w **polu zadanie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="2eb89-140">Wybierz zadanie konserwacji, wpisz pole **typu zadania konserwacji** i w razie potrzeby pokrewny typ zadania związanego wariant i zawód w polach **Wariant typu zadania konserwacji** i **Zawód** .</span><span class="sxs-lookup"><span data-stu-id="2eb89-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="2eb89-141">Jeśli jest to pierwsze powiązane ze sobą zlecenie robocze, kliknij przycisk **Nowe zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="2eb89-142">Wybierz **typ zlecenia pracy** i **opis** w odpowiednich polach.</span><span class="sxs-lookup"><span data-stu-id="2eb89-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="2eb89-143">W razie potrzeby można zmienić poziom usługi zlecenia pracy w polu **poziomu usług**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="2eb89-144">Wpisz oczekiwane daty rozpoczęcia i zakończenia w polach pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="2eb89-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="2eb89-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-145">Click **OK**.</span></span> <span data-ttu-id="2eb89-146">Nowe powiązane zlecenie produkcyjne jest wyświetlane na liście **wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="2eb89-147">W przypadku utworzenia powiązanego zlecenia produkcyjnego w zleceniu produkcyjnym, które ma już powiązane zlecenia, można dodać zadanie zlecenia produkcyjnego do już powiązanego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="2eb89-148">Aby to zrobić, należy kliknąć **Dodaj do powiązanego zlecenia pracy** przycisk w kroku 6.</span><span class="sxs-lookup"><span data-stu-id="2eb89-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="2eb89-149">Następnie należy wybrać powiązane zlecenie produkcyjne, do którego ma zostać dodane nowe zadanie zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="2eb89-150">W razie potrzeby edytuj pola **Poziom usług**, **Oczekiwana data rozpoczęcia** i **Oczekiwana data zakończenia** i kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="2eb89-151">Zadanie zlecenia produkcyjnego jest dodawane do istniejącego powiązanego zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-151">The work order job is added to the existing related work order.</span></span>


![Rysunek 1](media/03-work-orders.png)

<span data-ttu-id="2eb89-153">**Uwaga:** w przypadku skonfigurowania powiązanej maski zleceń roboczych w polach **Parametry zarządzania składnikami majątku** > **Zlecenia pracy** złącze > **Maska powiązanego zlecenia pracy**, identyfikatory zleceń roboczych zostaną utworzone zgodnie z konfiguracją maski.</span><span class="sxs-lookup"><span data-stu-id="2eb89-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="2eb89-154">Jeśli nie skonfigurowano powiązanej maski zlecenia produkcyjnego, dla pokrewnych zleceń produkcyjnych zostanie użyty kolejny dostępny identyfikator zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="2eb89-155">Kopiuj zlecenie pracy</span><span class="sxs-lookup"><span data-stu-id="2eb89-155">Copy work order</span></span>

<span data-ttu-id="2eb89-156">Istnieje możliwość szybkiego utworzenia nowego zlecenia produkcyjnego na podstawie istniejącego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="2eb89-157">Ta metoda pracy z zleceniami produkcyjnymi różni się od tworzenia zleceń roboczych na podstawie planów konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2eb89-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="2eb89-158">Jest to przydatne na przykład wtedy, gdy zlecenie produkcyjne zawiera wiele zadań zlecenia pracy z różnymi zadaniami dotyczącymi różnych środków trwałych, które powinny zostać wykonane w regularnych odstępach czasu.</span><span class="sxs-lookup"><span data-stu-id="2eb89-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="2eb89-159">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2eb89-160">Umożliwia wybranie zlecenia produkcyjnego, z którego ma zostać skopiowana zawartość.</span><span class="sxs-lookup"><span data-stu-id="2eb89-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="2eb89-161">Kliknij **Kopiuj zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-161">Click **Copy work order**.</span></span> <span data-ttu-id="2eb89-162">Zostanie wyświetlona konfiguracja zlecenia produkcyjnego z wybranego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="2eb89-163">W razie potrzeby można edytować niektóre pola.</span><span class="sxs-lookup"><span data-stu-id="2eb89-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="2eb89-164">Kliknij **OK**, aby utworzyć nowe zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="2eb89-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="2eb89-165">W razie potrzeby edytuj zlecenie produkcyjne we **wszystkichzleceniach roboczych**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="2eb89-166">Po utworzeniu nowego zlecenia produkcyjnego niektóre informacje są kopiowane bezpośrednio z istniejącego zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="2eb89-167">Informacje dotyczące prognoz, narzędzi, list kontrolnych obsługi, lokalizacji funkcjonalnej, adresów i planowania nie są kopiowane, ale zostały zainicjowane z bieżących ustawień modułu Zarządzanie środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="2eb89-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="2eb89-168">Oznacza to, że w przypadku wprowadzenia w nich zmian w czasie tworzenia pierwszego zlecenia produkcyjnego, zmiany te zostaną uwzględnione w nowo utworzonym zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="2eb89-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="2eb89-169">Przykłady to zmiany prognoz lub zaktualizowane listy kontrolne obsługi.</span><span class="sxs-lookup"><span data-stu-id="2eb89-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Rysunek 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="2eb89-171">Tworzenie zlecenia pracy oparte na żądaniu konserwacji</span><span class="sxs-lookup"><span data-stu-id="2eb89-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="2eb89-172">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Żądania konserwacji** > **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="2eb89-173">Wybierz zadania konserwacyjne, dla których chcesz utworzyć zlecenie prac i kliknij pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="2eb89-174">We **wszystkich żądaniach**kliknij przycisk **zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="2eb89-175">Wprowadź listę rozwijaną **zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="2eb89-176">Jeśli w ramach zlecenia serwisowego wybrano typ zadania obsługi, można wybrać inny typ zadania obsługi, jeśli jest on wymagany podczas tworzenia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="2eb89-177">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-177">Click **OK**.</span></span> <span data-ttu-id="2eb89-178">Zostanie wyświetlony komunikat informujący o utworzeniu zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2eb89-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="2eb89-179">Aby sprawdzić, które zlecenia produkcyjne są połączone z **żądaniem obsługi, wybierz żądanie konserwacji na listach Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji** obsługi technicznej, a następnie kliknij przycisk **Zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="2eb89-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Rysunek 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="2eb89-181">Zlecenia produkcyjne mogą być również tworzone automatycznie przez planowanie zadań planu konserwacji lub przez skonfigurowanie w składniku aktywów opcji automatycznego tworzenia lub zaokrąglania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2eb89-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="2eb89-182">Zlecenia produkcyjne utworzone na podstawie żądań obsługi w **harmonogramie konserwacji** są tworzone przy użyciu typów zadań konserwacji wybranych w ramach żądań obsługi.</span><span class="sxs-lookup"><span data-stu-id="2eb89-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

