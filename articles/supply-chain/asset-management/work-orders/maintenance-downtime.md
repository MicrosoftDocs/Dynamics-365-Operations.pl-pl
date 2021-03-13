---
title: Przerwa konserwacyjną dla zleceń pracy
description: Ten temat wyjaśnia, jak można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53487a0173453ef7a8f5ea818672d999fe71cb65
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020918"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="ce9e7-103">Przerwa konserwacyjną dla zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="ce9e7-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="ce9e7-104">Można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="ce9e7-105">Ta możliwość jest przydatna w przypadku rejestrowania przerw konserwacyjnych na co najmniej jednej maszynie w obszarze produkcji.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="ce9e7-106">Najpierw należy utworzyć kody przyczyn przerw konserwacyjnych, które mają być używane, na przykład **Awaria** i **Planowane zatrzymywanie**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="ce9e7-107">W tym celu należy wykonać czynności ze strony **Kody przyczyn przerw konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="ce9e7-108">Następnie można utworzyć rejestracje przerw konserwacyjnych na stronie **Przerwa konserwacyjna** i dodać odpowiednie kody przyczyn przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="ce9e7-109">Stwórz kody przyczyny przerwy konserwacyjnej</span><span class="sxs-lookup"><span data-stu-id="ce9e7-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="ce9e7-110">Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Kody przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="ce9e7-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-111">Select **New**.</span></span>

3. <span data-ttu-id="ce9e7-112">W polu **Kod przyczyny przerwy konserwacyjnej** wprowadź identyfikator dla kodu przyczyny przerwy konserwacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="ce9e7-113">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="ce9e7-114">Zaznacz pole wyboru **KPI uwzględniają**, jeśli kod przyczyny ma być uwzględniony w obliczeniach kluczowych wskaźników wydajności (KPI) dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="ce9e7-115">Na ogół planowane zatrzymania produkcji nie powinny być uwzględniane w obliczeniach wskaźników KPI, ponieważ nie wpływają one na oczekiwaną wydajność.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="ce9e7-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-116">Select **Save**.</span></span>

<span data-ttu-id="ce9e7-117">Na poniższej ilustracji pokazano przykład strony **Kody przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Rysunek 1](media/15-work-orders.png)

<span data-ttu-id="ce9e7-119">Po utworzeniu kodów przyczyny przestojów, które mają być używane, można utworzyć rejestracje przestojów związanych z obsługą zleceń i składników majątku.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="ce9e7-120">Utwórz rejestrację przestojów konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="ce9e7-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="ce9e7-121">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ce9e7-122">Wybierz zlecenie produkcyjne, a następnie na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Przerwa konserwacyjna**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="ce9e7-123">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-123">Select **New**.</span></span>

4. <span data-ttu-id="ce9e7-124">W polach **Od** i **Do** wstaw datę i interwał czasu dla rejestracji przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="ce9e7-125">Po opuszczeniu pola **do** pole czas trwania w godzinach jest automatycznie wstawiany w polu **Czas trwania**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="ce9e7-126">Wybierz kod przyczyny w polu **Kod przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="ce9e7-127">Powtórz kroki od 3 do 5, aby dodać więcej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="ce9e7-128">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-128">Select **Save**.</span></span>

<span data-ttu-id="ce9e7-129">Na poniższej ilustracji pokazano przykład rejestracji przerwy konserwacyjnej.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Rysunek 2](media/16-work-orders.png)

<span data-ttu-id="ce9e7-131">Kalendarz używany do obliczania rejestracji przerw konserwacyjnych związanych z obsługą zależy od wyboru dokonanego w konfiguracji składników majątku i parametrów.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="ce9e7-132">Jeśli zasób jest wybrany dla składnika majątku w polu **Zasób**, na karcie skróconej **Środek trwały** na stronie **Wszystkie składniki majątku** zostanie użyty kalendarz skonfigurowany dla skojarzonej grupy zasobów, co pokazano na poniższym rysunku.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Rysunek 3](media/17-work-orders.png)

<span data-ttu-id="ce9e7-134">Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty standardowy kalendarz wybrany na stronie **Parametry zarządzania składnikami majątku** jak pokazano na ilustracji poniżej.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Rysunek 4](media/18-work-orders.png)

<span data-ttu-id="ce9e7-136">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Przerwa konserwacyjna** , aby wyświetlić przegląd wszystkich rejestracji przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="ce9e7-137">Wszystkie kalendarze używane w module **Zarządzanie składnikami majątku** są konfigurowane w **Administrowanie organizacją** > **Ustawienia** > **Kalendarze** > **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

