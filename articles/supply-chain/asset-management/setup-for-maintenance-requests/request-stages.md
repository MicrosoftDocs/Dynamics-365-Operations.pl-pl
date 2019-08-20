---
title: Stany cyklu życia żądania konserwacji
description: W tym temacie opisano, jak konfigurować stany cyklu życia żądań konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f68e11a1cd14bc35282b957a4262cbecdd627b3b
ms.sourcegitcommit: 2c73749779274e0b0abbcb4041bbc1df0fb6d6e4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/26/2019
ms.locfileid: "1790530"
---
# <a name="maintenance-request-states"></a><span data-ttu-id="2197c-103">Stany żądań konserwacji</span><span class="sxs-lookup"><span data-stu-id="2197c-103">Maintenance request states</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="2197c-104">Stany cyklu życia żądań konserwacji określają etapy, przez które może przejść żądanie.</span><span class="sxs-lookup"><span data-stu-id="2197c-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="2197c-105">Przykładowe stany to **Utworzony**, **Aktywny** i **Włączony**.</span><span class="sxs-lookup"><span data-stu-id="2197c-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="2197c-106">Jeśli żądanie konserwacji jest konwertowane na zlecenie pracy, stan cyklu życia żądania konserwacji musi zostać zaktualizowany do **Zakończony** lub **Zamknięty**, aby było możliwe wskazanie, że żądanie konserwacji nie jest już aktywne.</span><span class="sxs-lookup"><span data-stu-id="2197c-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="2197c-107">Na stronie listy **Wszystkie żądania konserwacji** można wyświetlić wszystkie żądania konserwacji, niezależnie od ich stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="2197c-108">Ustawianie stanów cyklu życia żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="2197c-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="2197c-109">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="2197c-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="2197c-110">Wybierz pozycję **Nowy**, aby utworzyć stan cyklu życia żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2197c-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="2197c-111">W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="2197c-112">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="2197c-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="2197c-113">Na skróconej karcie **Szczegóły** pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia żądań konserwacji, które używają tego stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="2197c-114">Na skróconej karcie **Ogólne** ustaw opcję **Aktywne** na **Tak**, jeśli żądanie konserwacji powinno być aktywne w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="2197c-115">Ustaw opcję **Ustaw rzeczywisty koniec** na **Tak**, jeśli rzeczywista data i godzina zakończenia powinny być automatycznie wprowadzane w żądaniu konserwacji, które znajduje się w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-115">Set he **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="2197c-116">Ustaw opcję **Utwórz zlecenie pracy**na **Tak**, jeśli zlecenie pracy może być utworzone z żądania konwersacji w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="2197c-117">Ustaw opcję **Usuń** na **Tak**, jeśli żądanie konserwacji można usunąć, gdy jest w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="2197c-118">Na skróconej karcie **Aktualizacja** opcje **Przychodzący** i **Wychodzący** w sekcji **Składnik majątku** są istotne w kontekście naprawy w magazynie. Ustaw odpowiednią opcję na **Tak**, jeśli stan cyklu życia składników majątku wybranych na żądaniu konserwacji powinien być automatycznie aktualizowany na **Przychodzący** lub **Wychodzący**, kiedy stan cyklu życia tego żądania konserwacji jest ustawiony na **Przychodzący** lub **Wychodzący**.</span><span class="sxs-lookup"><span data-stu-id="2197c-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.cSet the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="2197c-119">Na poniższej ilustracji pokazano przykład strony **Cykle życia żądań konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="2197c-119">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Rysunek 1](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="2197c-121">Stany cyklu życia, grupy stanów cyklu życia oraz typy żądania konserwacji są powiązane i używane w taki sam sposób jak stany cyklu życia, grupy stanów cyklu życia oraz typy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="2197c-121">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="2197c-122">Ustawianie modeli cyklu życia żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="2197c-122">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="2197c-123">Po utworzeniu stanów cyklu życia, które są wymagane dla żądań konserwacji, można je podzielić na grupy stanu cyklu życia lub modele cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-123">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="2197c-124">Modele cyklu życia żądania konserwacji są używane do tworzenia przepływu, który może służyć do różnych typów żądań konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2197c-124">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="2197c-125">Jako minimum należy utworzyć jeden standardowy model cyklu życia lokalizacji żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2197c-125">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="2197c-126">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Modele cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="2197c-126">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="2197c-127">Wybierz pozycję **Nowy**, aby utworzyć model cyklu życia żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="2197c-127">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="2197c-128">W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-128">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="2197c-129">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="2197c-129">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="2197c-130">Na skróconej karcie **Szczegóły** pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia, które są wybrane w modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-130">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="2197c-131">Pole **Typy żądania konserwacji** pokazuje liczbę typów żądania konserwacji, które używają tego modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="2197c-131">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="2197c-132">Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia, które powinny być uwzględnione w modelu cyklu życia:</span><span class="sxs-lookup"><span data-stu-id="2197c-132">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="2197c-133">Aby uwzględnić stanu cyklu życia w modelu cyku życia, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo](media/03-setup-for-requests.png), aby przenieść go do sekcji **Wybrane stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="2197c-133">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="2197c-134">Aby uwzględnić wszystkie dostępne stany cyklu życia w modelu cyklu życia, wybierz przycisk **Wybierz wszystkie dostępne stany** ![Wybierz wszystkie dostępne stany](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="2197c-134">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="2197c-135">Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.</span><span class="sxs-lookup"><span data-stu-id="2197c-135">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="2197c-136">Aby usunąć stan cyklu życia z modelu cyklu życia, wybierz go w sekcji **Wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki lewo ![Strzałka w lewo](media/05-setup-for-requests.png), aby przenieść go do sekcji **Pozostałe stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="2197c-136">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="2197c-137">Na skrócone karcie **Ogólne** pola w sekcji **Aktualizacja** są istotne, jeśli używasz naprawy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="2197c-137">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="2197c-138">W polu **Stan cyklu życia odebranego składnika majątku** wybierz stan cyklu życia składnika majątku, że składniki majątku, które są wybrane w żądaniu konserwacji powinny być automatycznie aktualizowane po odebraniu do naprawy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="2197c-138">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="2197c-139">W polu **Stan cyklu życia dostarczonego składnika majątku** wybierz stan cyklu życia, że składniki majątku, które są wybrane w żądaniu konserwacji, powinny być automatycznie aktualizowane po zwróceniu z naprawy.</span><span class="sxs-lookup"><span data-stu-id="2197c-139">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="2197c-140">Na poniższej ilustracji pokazano przykład strony **Modele cyklu życia żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="2197c-140">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Rysunek 2](media/06-setup-for-requests.png)
