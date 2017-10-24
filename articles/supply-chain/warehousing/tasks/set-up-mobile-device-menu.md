--- 
title: "Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy w ramach zamówienia zakupu"
description: "W tej procedurze pokazano sposób konfigurowania elementu menu urządzenia przenośnego."
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b80c258d6a779a8fc5bb6c846abd3af7e69d5e06
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a><span data-ttu-id="a4189-103">Konfigurowanie elementu menu urządzenia przenośnego do wykonania pracy w ramach zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="a4189-103">Set up a mobile device menu item for completing work in a purchase order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a4189-104">W tej procedurze pokazano sposób konfigurowania elementu menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="a4189-104">This procedure shows how to set up a Mobile device menu item.</span></span> <span data-ttu-id="a4189-105">W tym przykładzie element menu służy do wykonywania pracy typu Zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="a4189-105">In this example, the menu item is used for performing work of type Purchase order.</span></span> <span data-ttu-id="a4189-106">Klasa pracy powiązana z elementem menu decyduje o tym, która praca jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="a4189-106">The work class that’s associated with the menu item determines which work is valid.</span></span> <span data-ttu-id="a4189-107">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a4189-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="a4189-108">Ta procedura jest zwykle wykonywana przez kierownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="a4189-108">This procedure is typically carried out by a warehouse manager.</span></span>


## <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="a4189-109">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="a4189-109">Create a mobile device menu item</span></span>
1. <span data-ttu-id="a4189-110">Przejdź do okna Elementy menu urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="a4189-110">Go to Mobile device menu items.</span></span>
2. <span data-ttu-id="a4189-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a4189-111">Click New.</span></span>
3. <span data-ttu-id="a4189-112">W polu Nazwa elementu menu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a4189-112">In the Menu item name field, type a value.</span></span>
    * <span data-ttu-id="a4189-113">Wprowadź unikatową wartość.</span><span class="sxs-lookup"><span data-stu-id="a4189-113">Enter a unique value.</span></span> <span data-ttu-id="a4189-114">Na przykład można wpisać „PrzeniesienieZZ”.</span><span class="sxs-lookup"><span data-stu-id="a4189-114">For example, you could type POMove.</span></span> <span data-ttu-id="a4189-115">Zapamiętaj tę wartość, będzie potrzebna później.</span><span class="sxs-lookup"><span data-stu-id="a4189-115">Remember the value, you'll need it later.</span></span>  
4. <span data-ttu-id="a4189-116">W polu Tytuł wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a4189-116">In the Title field, type a value.</span></span>
    * <span data-ttu-id="a4189-117">Jest to tytuł, który będzie wyświetlany w urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="a4189-117">This is the title which will be displayed on the mobile device.</span></span> <span data-ttu-id="a4189-118">Na przykład można wpisać Przeniesienie ZZ.</span><span class="sxs-lookup"><span data-stu-id="a4189-118">For example, you could type PO Move.</span></span>  
5. <span data-ttu-id="a4189-119">W polu Tryb wybierz opcję „Praca”.</span><span class="sxs-lookup"><span data-stu-id="a4189-119">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="a4189-120">W polu Użyj istniejącej pracy zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a4189-120">Select Yes in the Use existing work field.</span></span>
    * <span data-ttu-id="a4189-121">Ten element menu urządzenia przenośnego jest używany do wykonywania istniejącej pracy.</span><span class="sxs-lookup"><span data-stu-id="a4189-121">This mobile device menu item is used to perform existing work.</span></span> <span data-ttu-id="a4189-122">W związku z tym należy ustawić wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="a4189-122">Therefore you must set this value to Yes.</span></span>  
    * <span data-ttu-id="a4189-123">Pole Wyświetl stan zapasów określa, czy stan dostępnych zapasów będzie wyświetlany pracownikowi magazynu na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="a4189-123">The Display inventory status field determines whether the inventory status of the on-hand inventory will be displayed to the warehouse worker on the mobile device.</span></span>  
7. <span data-ttu-id="a4189-124">W polu Sterowane przez wybierz opcję „Grupowanie systemowe”.</span><span class="sxs-lookup"><span data-stu-id="a4189-124">In the Directed by field, select 'System grouping'.</span></span>
    * <span data-ttu-id="a4189-125">Po wybraniu wartości w polu Sterowane przez zostaną wyświetlone dodatkowe pola w sekcji Ogólne na tej stronie.</span><span class="sxs-lookup"><span data-stu-id="a4189-125">When you select something in the Directed by field, additional fields appear in the General section on this page.</span></span> <span data-ttu-id="a4189-126">Wyświetlane pola zależą od wybranej wartości.</span><span class="sxs-lookup"><span data-stu-id="a4189-126">The fields that appear depend on what you selected.</span></span> <span data-ttu-id="a4189-127">Po wybraniu opcji Grupowanie systemowe są dodawane dwa nowe pola.</span><span class="sxs-lookup"><span data-stu-id="a4189-127">When you select System grouping, two new fields are added.</span></span> <span data-ttu-id="a4189-128">Omówiono je poniżej.</span><span class="sxs-lookup"><span data-stu-id="a4189-128">These are explained below.</span></span>  
8. <span data-ttu-id="a4189-129">W polu Grupowanie systemowe zaznacz wartość „WorkPoolId”.</span><span class="sxs-lookup"><span data-stu-id="a4189-129">In the System grouping field, select 'WorkPoolId'.</span></span>
    * <span data-ttu-id="a4189-130">Gdy pracownik magazynu otwiera ten element menu, zobaczy monit o zeskanowanie identyfikatora puli pracy.</span><span class="sxs-lookup"><span data-stu-id="a4189-130">When warehouse workers open this menu item, they’ll be asked to scan a Work pool ID.</span></span> <span data-ttu-id="a4189-131">Wszystkie zlecenia o tym identyfikatorze puli pracy oraz otwarte wiersze zlecenia, które mają jedną z klas pracy dodanych do tego elementu menu, zostaną wysłane do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a4189-131">All work orders with this Work pool ID and open work order lines with one of the work classes added to this menu item will be pushed to the user.</span></span>  
9. <span data-ttu-id="a4189-132">W polu Etykieta grup systemowych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a4189-132">In the System grouping label field, type a value.</span></span>
    * <span data-ttu-id="a4189-133">Jest to tekst wyświetlany użytkownikowi na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="a4189-133">This is the text displayed to the user on the mobile device.</span></span> <span data-ttu-id="a4189-134">Na przykład można wpisać Pula pracy.</span><span class="sxs-lookup"><span data-stu-id="a4189-134">For example, you could type Work pool.</span></span>  
10. <span data-ttu-id="a4189-135">W polu Zastąp numer identyfikacyjny podczas odłożenia zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a4189-135">Select Yes in the Override license plate during put field.</span></span>
    * <span data-ttu-id="a4189-136">Ta opcja umożliwia pracownikom magazynu zastępowanie docelowego numeru identyfikacyjnego, gdy towary są odkładane do lokalizacji kontrolowanej przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="a4189-136">This option allows warehouse workers to override the target license plate when items are put down on a license plate controlled location.</span></span>  
11. <span data-ttu-id="a4189-137">W polu Grupuj odłożone wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="a4189-137">Select Yes in the Group put away field.</span></span>
    * <span data-ttu-id="a4189-138">Jeśli wszystkie wiersze odłożenia w zleceniu mają tę samą lokalizację, użytkownik otrzyma jedną zbiorczą instrukcję odłożenia dla wszystkich wierszy.</span><span class="sxs-lookup"><span data-stu-id="a4189-138">If all the Put lines on the work order share the same location, the user will receive one combined Put instruction for all lines.</span></span>  
    * <span data-ttu-id="a4189-139">Identyfikator szablonu inspekcji: Szablon inspekcji pracy pozwala określić, że proces pracy dla elementu menu ma zostać przerwany, aby można było wykonać inną operację.</span><span class="sxs-lookup"><span data-stu-id="a4189-139">Audit template ID: A work audit template allows you to specify that the work process for a menu item should be interrupted so that another operation can be performed.</span></span> <span data-ttu-id="a4189-140">Na przykład jeśli element menu dotyczy pracy przychodzącej, szablon inspekcji może wymagać, by pracownik sprawdził temperaturę.</span><span class="sxs-lookup"><span data-stu-id="a4189-140">For example, if this menu item is for inbound work, the audit template might require that the worker checks the temperature.</span></span> <span data-ttu-id="a4189-141">Punkt, w którym proces zostanie przerwany, jest określony w szablonie inspekcji i może być np. momentem rozpoczęcia lub ukończenia pracy albo zmiany stanu.</span><span class="sxs-lookup"><span data-stu-id="a4189-141">The point at which the process is interrupted is specified on the audit template and can be, for example, when work is started or completed, or when its status changes.</span></span>  
12. <span data-ttu-id="a4189-142">Rozwiń sekcję Klasy robocze.</span><span class="sxs-lookup"><span data-stu-id="a4189-142">Expand the Work classes section.</span></span>
13. <span data-ttu-id="a4189-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a4189-143">Click New.</span></span>
14. <span data-ttu-id="a4189-144">W polu Identyfikator klasy roboczej wpisz „Zakup”.</span><span class="sxs-lookup"><span data-stu-id="a4189-144">In the Work class ID field, type 'Purchase'.</span></span>
    * <span data-ttu-id="a4189-145">Pula pracy ogranicza pracę, dla której można używać elementu menu.</span><span class="sxs-lookup"><span data-stu-id="a4189-145">The work pool restricts the work that the menu item can be used for.</span></span> <span data-ttu-id="a4189-146">W tym przypadku będzie ona używana dla otwartych wierszy zlecenia, które mają identyfikator klasy pracy Zakup.</span><span class="sxs-lookup"><span data-stu-id="a4189-146">In this case it will be used for open work order lines that have the Purchase work class ID.</span></span>  
15. <span data-ttu-id="a4189-147">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a4189-147">Click Save.</span></span>

## <a name="set-up-work-confirmation"></a><span data-ttu-id="a4189-148">Konfigurowanie potwierdzenia pracy</span><span class="sxs-lookup"><span data-stu-id="a4189-148">Set up work confirmation</span></span>
1. <span data-ttu-id="a4189-149">Kliknij opcję Konfiguracja potwierdzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="a4189-149">Click Work confirmation setup.</span></span>
2. <span data-ttu-id="a4189-150">W polu Typ pracy zaznacz opcję „Pobranie”.</span><span class="sxs-lookup"><span data-stu-id="a4189-150">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="a4189-151">Zaznacz pole wyboru Automatyczne potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="a4189-151">Select the Auto confirm check box.</span></span>
    * <span data-ttu-id="a4189-152">Instrukcja pracy o typie pracy Pobranie zostanie potwierdzona automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a4189-152">The work instruction with work type Pick will be auto-confirmed.</span></span> <span data-ttu-id="a4189-153">Ta instrukcja nie będzie przedstawiana użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="a4189-153">This instruction will not be presented to the user.</span></span>  
4. <span data-ttu-id="a4189-154">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a4189-154">Click New.</span></span>
5. <span data-ttu-id="a4189-155">W polu Typ pracy zaznacz opcję „Odłożenie”.</span><span class="sxs-lookup"><span data-stu-id="a4189-155">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="a4189-156">Zaznacz pole wyboru Potwierdzenie lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="a4189-156">Select the Location confirmation check box.</span></span>
    * <span data-ttu-id="a4189-157">Pracownik magazynu zostanie poproszony o wykonanie skanowania potwierdzającego w lokalizacji po odłożeniu towaru.</span><span class="sxs-lookup"><span data-stu-id="a4189-157">The warehouse worker will be asked to perform a confirmation scan of the location, when the item is put down.</span></span>  
7. <span data-ttu-id="a4189-158">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a4189-158">Click Save.</span></span>
8. <span data-ttu-id="a4189-159">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a4189-159">Close the page.</span></span>
9. <span data-ttu-id="a4189-160">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a4189-160">Close the page.</span></span>

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="a4189-161">Dodawanie element menu do menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="a4189-161">Add the menu item to a mobile device menu</span></span>
1. <span data-ttu-id="a4189-162">Przejdź do okna Menu urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="a4189-162">Go to Mobile device menu.</span></span>
2. <span data-ttu-id="a4189-163">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="a4189-163">Click Edit.</span></span>
3. <span data-ttu-id="a4189-164">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="a4189-164">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a4189-165">Na przykład wyfiltruj według pola Nazwa z wartością „przychodzące”.</span><span class="sxs-lookup"><span data-stu-id="a4189-165">For example, filter on the Name field with a value of 'inbound'.</span></span>
    * <span data-ttu-id="a4189-166">Chcesz znaleźć menu używane dla towarów przychodzących.</span><span class="sxs-lookup"><span data-stu-id="a4189-166">You want to find the menu you use for inbound menu items.</span></span> <span data-ttu-id="a4189-167">W firmie USMF nosi ono nazwę Przychodzące.</span><span class="sxs-lookup"><span data-stu-id="a4189-167">In USMF this is called Inbound.</span></span>  
4. <span data-ttu-id="a4189-168">W drzewie zaznacz wartość.</span><span class="sxs-lookup"><span data-stu-id="a4189-168">In the tree, select 'a value'.</span></span>
5. <span data-ttu-id="a4189-169">Kliknij strzałkę wskazującą w prawo.</span><span class="sxs-lookup"><span data-stu-id="a4189-169">Click on the arrow that points to the right.</span></span>
6. <span data-ttu-id="a4189-170">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a4189-170">Click Save.</span></span>
7. <span data-ttu-id="a4189-171">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a4189-171">Close the page.</span></span>


