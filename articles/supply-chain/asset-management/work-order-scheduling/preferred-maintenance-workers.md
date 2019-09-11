---
title: Ustawienia preferowanych konserwatorów
description: W tym temacie wyjaśniono, jak konfigurować preferowanych konserwatorów w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887418"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="95bf8-103">Preferowani konserwatorzy</span><span class="sxs-lookup"><span data-stu-id="95bf8-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="95bf8-104">Użytkownik może ustawić preferencję, na której pracownicy konserwacji są przydzielani do wykonywania zleceń pracy podczas planowania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="95bf8-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="95bf8-105">Korzystanie z tej funkcji jest opcjonalne, ale może pomóc w wyborze najbardziej kwalifikowanego pracownika obsługi do wykonania zadania na podstawie umiejętności i kwalifikacji pracownika.</span><span class="sxs-lookup"><span data-stu-id="95bf8-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="95bf8-106">Dlatego podczas planowania zlecenia produkcyjnego ustawienia w **preferowanych konserwatorach** służą do ustalania, czy dla zlecenia pracy ma być zaplanowany określony pracownik obsługi czy grupa pracowników.</span><span class="sxs-lookup"><span data-stu-id="95bf8-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="95bf8-107">Zaplanowane są tylko pracownicy obsługi, którzy są dostępni w czasie planowania.</span><span class="sxs-lookup"><span data-stu-id="95bf8-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="95bf8-108">Jeśli preferowana konfiguracja pracownika obsługi jest zgodna z zleceniem w trakcie planowania, ale pracownik obsługi jest przydzielany do innych zadań, zlecenie produkcyjne będzie zaplanowane na inną, dostępną dla pracownika obsługi.</span><span class="sxs-lookup"><span data-stu-id="95bf8-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="95bf8-109">Aby można było skonfigurować preferowanych konserwatorów, należy skonfigurować konserwatorów oraz grupy konserwatorów, które powinny być dostępne do wybrania.</span><span class="sxs-lookup"><span data-stu-id="95bf8-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="95bf8-110">Aby uzyskać informacje na temat konfiguracji konserwatorów i grup pracowników, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="95bf8-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="95bf8-111">Ustawienia preferowanych pracowników</span><span class="sxs-lookup"><span data-stu-id="95bf8-111">Set up preferred workers</span></span>

<span data-ttu-id="95bf8-112">Preferowany pracownik konserwacji lub grupa pracowników może być powiązana z określonym</span><span class="sxs-lookup"><span data-stu-id="95bf8-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="95bf8-113">handel</span><span class="sxs-lookup"><span data-stu-id="95bf8-113">trade</span></span>  
- <span data-ttu-id="95bf8-114">wariantem typu zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="95bf8-114">maintenance job type variant</span></span>  
- <span data-ttu-id="95bf8-115">typem zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="95bf8-115">maintenance job type</span></span>  
- <span data-ttu-id="95bf8-116">kategorią typu zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="95bf8-116">maintenance job type category</span></span>  
- <span data-ttu-id="95bf8-117">aktywa</span><span class="sxs-lookup"><span data-stu-id="95bf8-117">asset</span></span>  
- <span data-ttu-id="95bf8-118">typem składnika majątku</span><span class="sxs-lookup"><span data-stu-id="95bf8-118">asset type</span></span>  

<span data-ttu-id="95bf8-119">lub kombinacją tych opcji.</span><span class="sxs-lookup"><span data-stu-id="95bf8-119">or a combination of those selections.</span></span> <span data-ttu-id="95bf8-120">Im więcej opcji zostanie wprowadzonych dla tego samego rekordu, tym dokładniejsze będą ustawienia.</span><span class="sxs-lookup"><span data-stu-id="95bf8-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="95bf8-121">Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Pracownicy** > **Preferowani konserwatorzy**.</span><span class="sxs-lookup"><span data-stu-id="95bf8-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="95bf8-122">Naciśnij przycisk **Nowy**, aby utworzyć nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="95bf8-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="95bf8-123">Należy rozpocząć od utworzenia konfiguracji „domyślna” konserwatora lub grupy konserwatorów dla obsługi, która nie ma wybranych opcji w polach podanych na liście punktowanej powyżej.</span><span class="sxs-lookup"><span data-stu-id="95bf8-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="95bf8-124">Oznacza to , że można wybierać tylko w polu **Preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.</span><span class="sxs-lookup"><span data-stu-id="95bf8-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="95bf8-125">Na poniższym rysunku widać przykład w pierwszym rekordzie, w którym "żądania" są wybrane jako preferowana grupa konserwatorów.</span><span class="sxs-lookup"><span data-stu-id="95bf8-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="95bf8-126">Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy podczas planowania zlecenia.</span><span class="sxs-lookup"><span data-stu-id="95bf8-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="95bf8-127">Powtórz krok 2, aby utworzyć nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="95bf8-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="95bf8-128">Dokonaj wymaganych wyborów w zależności od poziomu szczegółowości dla preferowanego pracownika lub grupy pracowników.</span><span class="sxs-lookup"><span data-stu-id="95bf8-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="95bf8-129">*Przykład:* na poniższym rysunku, w szóstym rekordzie, pracownik obsługi technicznej Shawn Richardson jest wybrany jako pracownik preferowany.</span><span class="sxs-lookup"><span data-stu-id="95bf8-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="95bf8-130">Zostanie on automatycznie wybrany podczas planowania zlecenia pracy zawierającego środek trwały „CH-BP1-03-02” i typ zadania konserwacji „Ocena instrumentu”, jeśli jest on dostępny w zaplanowanym czasie.</span><span class="sxs-lookup"><span data-stu-id="95bf8-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="95bf8-131">Jeśli podczas planowania zlecenia pracy wybrano preferowanego konserwatora, Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy **perferowanych konserwatorów**, aby sprawdzić, czy są dostępne w pierwszej kolejności najbardziej specyficzne dane.</span><span class="sxs-lookup"><span data-stu-id="95bf8-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="95bf8-132">Jeśli nie zostanie znalezione dopasowanie, zostanie użyty rekord domyślny z wyborem w polu **preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.</span><span class="sxs-lookup"><span data-stu-id="95bf8-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Rysunek 1](media/02-work-order-scheduling.png)

<span data-ttu-id="95bf8-134">Można również skonfigurować odpowiedzialnych pracowników obsługi, którzy mogą być wybrani w momencie utworzenia zlecenia serwisowego lub zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="95bf8-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="95bf8-135">W przypadku **Wszystkie zlecenia pracy** i **Wszystkie żądania konserwacji**, w razie potrzeby można edytować zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="95bf8-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="95bf8-136">Aby uzyskać więcej informacji należy zapoznać się z [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="95bf8-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="95bf8-137">Podczas planowania zlecenia pracy różne wyniki są obliczane w celu określenia, którzy pracownicy powinni spełniać zadania związane z danym zleceniem (te okresy są ustawiane w **Parametry zarządzania składnikami majątku** > **Planowanie zlecenia pracy** łącze).</span><span class="sxs-lookup"><span data-stu-id="95bf8-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="95bf8-138">Jeśli w przypadku dwóch lub więcej preferowanych pracowników konserwacji lub pracowników odpowiedzialnych za konserwacje uzyskuje się ten sam wynik podczas planowania zleceń, jeden pracownik jest wybierany losowo.</span><span class="sxs-lookup"><span data-stu-id="95bf8-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="95bf8-139">W przeciwnym razie jest on zawsze pracownikiem o najwyższyej ocenie, który jest przydzielony do wykonania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="95bf8-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

