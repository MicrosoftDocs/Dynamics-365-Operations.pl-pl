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
ms.openlocfilehash: ba24ae9e82debf9a67761e4e2ca0817e1645db28
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209738"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="f3949-103">Przerwa konserwacyjną dla zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="f3949-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="f3949-104">Można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="f3949-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="f3949-105">Ta możliwość jest przydatna w przypadku rejestrowania przerw konserwacyjnych na co najmniej jednej maszynie w obszarze produkcji.</span><span class="sxs-lookup"><span data-stu-id="f3949-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="f3949-106">Najpierw należy utworzyć kody przyczyn przerw konserwacyjnych, które mają być używane, na przykład **Awaria** i **Planowane zatrzymywanie**.</span><span class="sxs-lookup"><span data-stu-id="f3949-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="f3949-107">W tym celu należy wykonać czynności ze strony **Kody przyczyn przerw konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="f3949-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="f3949-108">Następnie można utworzyć rejestracje przerw konserwacyjnych na stronie **Przerwa konserwacyjna** i dodać odpowiednie kody przyczyn przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="f3949-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="f3949-109">Stwórz kody przyczyny przerwy konserwacyjnej</span><span class="sxs-lookup"><span data-stu-id="f3949-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="f3949-110">Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Kody przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="f3949-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="f3949-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3949-111">Select **New**.</span></span>

3. <span data-ttu-id="f3949-112">W polu **Kod przyczyny przerwy konserwacyjnej** wprowadź identyfikator dla kodu przyczyny przerwy konserwacyjnej.</span><span class="sxs-lookup"><span data-stu-id="f3949-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="f3949-113">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="f3949-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="f3949-114">Zaznacz pole wyboru **KPI uwzględniają**, jeśli kod przyczyny ma być uwzględniony w obliczeniach kluczowych wskaźników wydajności (KPI) dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="f3949-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="f3949-115">Na ogół planowane zatrzymania produkcji nie powinny być uwzględniane w obliczeniach wskaźników KPI, ponieważ nie wpływają one na oczekiwaną wydajność.</span><span class="sxs-lookup"><span data-stu-id="f3949-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="f3949-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3949-116">Select **Save**.</span></span>

<span data-ttu-id="f3949-117">Na poniższej ilustracji pokazano przykład strony **Kody przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="f3949-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Rysunek 1](media/15-work-orders.png)

<span data-ttu-id="f3949-119">Po utworzeniu kodów przyczyny przestojów, które mają być używane, można utworzyć rejestracje przestojów związanych z obsługą zleceń i składników majątku.</span><span class="sxs-lookup"><span data-stu-id="f3949-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="f3949-120">Utwórz rejestrację przestojów konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="f3949-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="f3949-121">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="f3949-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f3949-122">Wybierz zlecenie produkcyjne, a następnie na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Przerwa konserwacyjna**.</span><span class="sxs-lookup"><span data-stu-id="f3949-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="f3949-123">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f3949-123">Select **New**.</span></span>

4. <span data-ttu-id="f3949-124">W polach **Od** i **Do** wstaw datę i interwał czasu dla rejestracji przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="f3949-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="f3949-125">Po opuszczeniu pola **do** pole czas trwania w godzinach jest automatycznie wstawiany w polu **Czas trwania**.</span><span class="sxs-lookup"><span data-stu-id="f3949-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="f3949-126">Wybierz kod przyczyny w polu **Kod przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="f3949-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="f3949-127">Powtórz kroki od 3 do 5, aby dodać więcej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="f3949-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="f3949-128">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f3949-128">Select **Save**.</span></span>

<span data-ttu-id="f3949-129">Na poniższej ilustracji pokazano przykład rejestracji przerwy konserwacyjnej.</span><span class="sxs-lookup"><span data-stu-id="f3949-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Rysunek 2](media/16-work-orders.png)

<span data-ttu-id="f3949-131">Kalendarz używany do obliczania rejestracji przerw konserwacyjnych związanych z obsługą zależy od wyboru dokonanego w konfiguracji składników majątku i parametrów.</span><span class="sxs-lookup"><span data-stu-id="f3949-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="f3949-132">Jeśli zasób jest wybrany dla składnika majątku w polu **Zasób**, na karcie skróconej **Środek trwały** na stronie **Wszystkie składniki majątku** zostanie użyty kalendarz skonfigurowany dla skojarzonej grupy zasobów, co pokazano na poniższym rysunku.</span><span class="sxs-lookup"><span data-stu-id="f3949-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Rysunek 3](media/17-work-orders.png)

<span data-ttu-id="f3949-134">Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty standardowy kalendarz wybrany na stronie **Parametry zarządzania składnikami majątku** jak pokazano na ilustracji poniżej.</span><span class="sxs-lookup"><span data-stu-id="f3949-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Rysunek 4](media/18-work-orders.png)

<span data-ttu-id="f3949-136">Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Przerwa konserwacyjna** , aby wyświetlić przegląd wszystkich rejestracji przerw konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="f3949-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="f3949-137">Wszystkie kalendarze używane w module **Zarządzanie składnikami majątku** są konfigurowane w **Administrowanie organizacją** > **Ustawienia** > **Kalendarze** > **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="f3949-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]