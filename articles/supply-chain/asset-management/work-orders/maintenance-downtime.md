---
title: Przerwa konserwacyjna
description: W tym temacie opisano przerwy konserwacyjne w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918251"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="eef81-103">Przerwa konserwacyjna</span><span class="sxs-lookup"><span data-stu-id="eef81-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="eef81-104">Można utworzyć rejestracje przestojów podczas obsługi dla środka trwałego wybranego w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="eef81-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="eef81-105">Jest to przydatne w przypadku rejestrowania przestojów konserwacyjnych na co najmniej jednej maszynie w obszarze produkcji.</span><span class="sxs-lookup"><span data-stu-id="eef81-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="eef81-106">Najpierw należy utworzyć kody przyczyn przestojów, które mają być używane, na przykład podział i planowany zatrzymywanie.</span><span class="sxs-lookup"><span data-stu-id="eef81-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="eef81-107">W tym celu należy wykonać czynności związane z **kodami przyczyn przerw konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="eef81-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="eef81-108">Następnie można utworzyć rejestracje **Przerw konserwacyjnych** i dodać odpowiednie kody przyczyn.</span><span class="sxs-lookup"><span data-stu-id="eef81-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="eef81-109">Stwórz kody przyczyny przerwy konserwacyjnej</span><span class="sxs-lookup"><span data-stu-id="eef81-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="eef81-110">Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Kody przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="eef81-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="eef81-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="eef81-111">Click **New**.</span></span>

3. <span data-ttu-id="eef81-112">Wstaw identyfikator w polu kod **Kod przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="eef81-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="eef81-113">Wstaw nazwę kodu przyczyny w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="eef81-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="eef81-114">Zaznacz pole **KPI uwzględniają**, jeśli kod przyczyny ma być uwzględniony w obliczeniach wskaźnika KPI składnika aktywów.</span><span class="sxs-lookup"><span data-stu-id="eef81-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="eef81-115">Na ogół planowane zatrzymania produkcji nie powinny być uwzględniane w obliczeniach wskaźników KPI, ponieważ nie wpływają one na oczekiwaną wydajność.</span><span class="sxs-lookup"><span data-stu-id="eef81-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="eef81-116">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="eef81-116">Click **Save**.</span></span>

![Rysunek 1](media/15-work-orders.png)


<span data-ttu-id="eef81-118">Po utworzeniu kodów przyczyny przestojów, które mają być używane, można utworzyć rejestracje przestojów związanych z obsługą zleceń i składników majątku.</span><span class="sxs-lookup"><span data-stu-id="eef81-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="eef81-119">Utwórz rejestrację przestojów konserwacyjnych</span><span class="sxs-lookup"><span data-stu-id="eef81-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="eef81-120">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="eef81-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="eef81-121">Wybierz zlecenie pracy z listy i kliknij przycisk **Przerwa konserwacyjna.**</span><span class="sxs-lookup"><span data-stu-id="eef81-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="eef81-122">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="eef81-122">Click **New**.</span></span>

4. <span data-ttu-id="eef81-123">Umożliwia wstawienie daty i interwału czasu dla rejestracji przerw konserwacyjnych w polach **Od** i **Do**.</span><span class="sxs-lookup"><span data-stu-id="eef81-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="eef81-124">Po opuszczeniu pola **do** pole czas trwania w godzinach jest automatycznie wstawiany w polu **Czas trwania**.</span><span class="sxs-lookup"><span data-stu-id="eef81-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="eef81-125">Wstaw kod przyczyny w polu **Kod przyczyny przerwy konserwacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="eef81-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="eef81-126">Jeśli chcesz dodać więcej rejestracji, powtórz kroki 3-6</span><span class="sxs-lookup"><span data-stu-id="eef81-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="eef81-127">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="eef81-127">Click **Save**.</span></span>


![Rysunek 2](media/16-work-orders.png)


<span data-ttu-id="eef81-129">Kalendarz używany do obliczania rejestracji przestojów związanych z obsługą zależy od wyboru dokonanego w konfiguracji środków trwałych i parametrów.</span><span class="sxs-lookup"><span data-stu-id="eef81-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="eef81-130">Jeśli zasób jest wybrany dla składnika majątku **Wszystkie składniki majątku** > **Środek trwały** karta skrócona > **Zasób**, zostanie użyty kalendarz skonfigurowany dla skojarzonej grupy zasobów, co pokazano na poniższym rysunku.</span><span class="sxs-lookup"><span data-stu-id="eef81-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Rysunek 3](media/17-work-orders.png)


<span data-ttu-id="eef81-132">Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty standardowy kalendarz wybrany w polu **Parametry zarządzania składnikami majątku** jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="eef81-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Rysunek 4](media/18-work-orders.png)


<span data-ttu-id="eef81-134">Kliknij **Ustawień zarządzania składnikami majątku** > **Zapytania** > **Przerwa konserwacyjna** , aby wyświetlić przegląd wszystkich rejestracji przestojów związanych z konserwacją.</span><span class="sxs-lookup"><span data-stu-id="eef81-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="eef81-135">Wszystkie kalendarze używane w module **Zarządzanie składnikami majątku** są konfigurowane w **Administrowanie organizacją** > **Ustawienia** > **Kalendarze** > **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="eef81-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

