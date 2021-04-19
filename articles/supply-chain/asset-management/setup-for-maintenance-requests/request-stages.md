---
title: Stany cyklu życia żądania konserwacji
description: W tym temacie opisano, jak konfigurować stany cyklu życia żądań konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c95704b944f86a1cfc0654f0ebf5bc7c79bbeec9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808695"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="91cd4-103">Stany cyklu życia żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="91cd4-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="91cd4-104">Stany cyklu życia żądań konserwacji określają etapy, przez które może przejść żądanie.</span><span class="sxs-lookup"><span data-stu-id="91cd4-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="91cd4-105">Przykładowe stany to **Utworzony**, **Aktywny** i **Włączony**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="91cd4-106">Jeśli żądanie konserwacji jest konwertowane na zlecenie pracy, stan cyklu życia żądania konserwacji musi zostać zaktualizowany do **Zakończony** lub **Zamknięty**, aby było możliwe wskazanie, że żądanie konserwacji nie jest już aktywne.</span><span class="sxs-lookup"><span data-stu-id="91cd4-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="91cd4-107">Na stronie listy **Wszystkie żądania konserwacji** można wyświetlić wszystkie żądania konserwacji, niezależnie od ich stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="91cd4-108">Ustawianie stanów cyklu życia żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="91cd4-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="91cd4-109">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="91cd4-110">Wybierz pozycję **Nowy**, aby utworzyć stan cyklu życia żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="91cd4-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="91cd4-111">W polu **Stan cyklu życia** wprowadź identyfikator stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="91cd4-112">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="91cd4-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="91cd4-113">Na skróconej karcie **Szczegóły** pole **Modele cyklu życia** pokazuje liczbę modeli cyklu życia żądań konserwacji, które używają tego stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="91cd4-114">Na skróconej karcie **Ogólne** ustaw opcję **Aktywne** na **Tak**, jeśli żądanie konserwacji powinno być aktywne w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="91cd4-115">Ustaw opcję **Ustaw rzeczywisty koniec** na **Tak**, jeśli rzeczywista data i godzina zakończenia powinny być automatycznie wprowadzane w żądaniu konserwacji, które znajduje się w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-115">Set the **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="91cd4-116">Ustaw opcję **Utwórz zlecenie pracy** na **Tak**, jeśli zlecenie pracy może być utworzone z żądania konwersacji w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="91cd4-117">Ustaw opcję **Usuń** na **Tak**, jeśli żądanie konserwacji można usunąć, gdy jest w tym stanie cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="91cd4-118">Na skróconej karcie **Aktualizacji** opcje **Przychodzące** i **Wychodzące** w sekcji **Składnik majątku** są odpowiednie, jeśli jest używana Naprawa magazynu.</span><span class="sxs-lookup"><span data-stu-id="91cd4-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.</span></span> <span data-ttu-id="91cd4-119">Należy wybrać odpowiednią opcję **Tak**, jeśli stan cyklu eksploatacji środków trwałych wybrany w żądaniu obsługi powinien być automatycznie aktualizowany na **Przychodzący** lub **Wychodzący**, jeśli stan cyklu życia żądania obsługi jest określony jako **Przychodzący** lub **Wychodzący**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-119">Set the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="91cd4-120">Na poniższej ilustracji pokazano przykład strony **Cykle życia żądań konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-120">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Strona Stany cyklu życia żądania konserwacji](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="91cd4-122">Stany cyklu życia, grupy stanów cyklu życia oraz typy żądania konserwacji są powiązane i używane w taki sam sposób jak stany cyklu życia, grupy stanów cyklu życia oraz typy zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="91cd4-122">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="91cd4-123">Ustawianie modeli cyklu życia żądania konserwacji</span><span class="sxs-lookup"><span data-stu-id="91cd4-123">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="91cd4-124">Po utworzeniu stanów cyklu życia, które są wymagane dla żądań konserwacji, można je podzielić na grupy stanu cyklu życia lub modele cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-124">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="91cd4-125">Modele cyklu życia żądania konserwacji są używane do tworzenia przepływu, który może służyć do różnych typów żądań konserwacji.</span><span class="sxs-lookup"><span data-stu-id="91cd4-125">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="91cd4-126">Jako minimum należy utworzyć jeden standardowy model cyklu życia lokalizacji żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="91cd4-126">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="91cd4-127">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Żądania konserwacji** \> **Modele cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-127">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="91cd4-128">Wybierz pozycję **Nowy**, aby utworzyć model cyklu życia żądania konserwacji.</span><span class="sxs-lookup"><span data-stu-id="91cd4-128">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="91cd4-129">W polu **Model cyklu życia** wprowadź identyfikator modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-129">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="91cd4-130">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="91cd4-130">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="91cd4-131">Na skróconej karcie **Szczegóły** pole **Stany cyklu życia** pokazuje liczbę stanów cyklu życia, które są wybrane w modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-131">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="91cd4-132">Pole **Typy żądania konserwacji** pokazuje liczbę typów żądania konserwacji, które używają tego modelu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="91cd4-132">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="91cd4-133">Na skróconej karcie **Stany cyklu życia** wybierz stany cyklu życia, które powinny być uwzględnione w modelu cyklu życia:</span><span class="sxs-lookup"><span data-stu-id="91cd4-133">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="91cd4-134">Aby uwzględnić stanu cyklu życia w modelu cyku życia, zaznacz go w sekcji **Pozostałe stany cyklu życia**, a następnie wybierz przycisk strzałki w prawo ![Strzałka w prawo](media/03-setup-for-requests.png), aby przenieść go do sekcji **Wybrane stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-134">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="91cd4-135">Aby uwzględnić wszystkie dostępne stany cyklu życia w modelu cyklu życia, wybierz przycisk **Wybierz wszystkie dostępne stany** ![Wybierz wszystkie dostępne stany](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="91cd4-135">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="91cd4-136">Wszystkie stany cyklu życia są przenoszone do sekcji **Wybrane cykle życia**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-136">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="91cd4-137">Aby usunąć stan cyklu życia z modelu cyklu życia, wybierz go w sekcji **Wybrane stany cyklu życia**, a następnie wybierz przycisk strzałki lewo ![Strzałka w lewo](media/05-setup-for-requests.png), aby przenieść go do sekcji **Pozostałe stany cyklu życia**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-137">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="91cd4-138">Na skrócone karcie **Ogólne** pola w sekcji **Aktualizacja** są istotne, jeśli używasz naprawy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="91cd4-138">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="91cd4-139">W polu **Stan cyklu życia odebranego składnika majątku** wybierz stan cyklu życia składnika majątku, że składniki majątku, które są wybrane w żądaniu konserwacji powinny być automatycznie aktualizowane po odebraniu do naprawy w magazynie.</span><span class="sxs-lookup"><span data-stu-id="91cd4-139">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="91cd4-140">W polu **Stan cyklu życia dostarczonego składnika majątku** wybierz stan cyklu życia, że składniki majątku, które są wybrane w żądaniu konserwacji, powinny być automatycznie aktualizowane po zwróceniu z naprawy.</span><span class="sxs-lookup"><span data-stu-id="91cd4-140">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="91cd4-141">Na poniższej ilustracji pokazano przykład strony **Modele cyklu życia żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="91cd4-141">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Strona Modele cyklu życia żądania konserwacji](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]