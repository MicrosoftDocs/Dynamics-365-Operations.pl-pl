---
title: Ustawienia preferowanych konserwatorów
description: W tym temacie wyjaśniono, jak konfigurować preferowanych konserwatorów w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 327cda12a05ad54b310e472a652f1c822ad97142
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215339"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="826d5-103">Ustawienia preferowanych konserwatorów</span><span class="sxs-lookup"><span data-stu-id="826d5-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="826d5-104">Podczas planowania zlecenia pracy, użytkownik może ustawić preferencję, na której konserwatorzy lub grupy konserwatorów są przydzielane do wykonywania zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="826d5-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="826d5-105">Korzystanie z tej funkcji jest opcjonalne, ale może pomóc w wyborze najbardziej kwalifikowanego pracownika obsługi do wykonania zadania na podstawie umiejętności i kwalifikacji pracownika.</span><span class="sxs-lookup"><span data-stu-id="826d5-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="826d5-106">Zaplanowane są tylko pracownicy obsługi, którzy są dostępni w czasie planowania.</span><span class="sxs-lookup"><span data-stu-id="826d5-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="826d5-107">Jeśli preferowana konfiguracja pracownika obsługi jest zgodna z zleceniem w trakcie planowania, ale pracownik obsługi jest przydzielany do innych zadań, zlecenie pracy będzie zaplanowane na inną, dostępną dla konserwatora.</span><span class="sxs-lookup"><span data-stu-id="826d5-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="826d5-108">Aby można było skonfigurować preferowanych konserwatorów, należy najpierw skonfigurować konserwatorów i grupy konserwatorów.</span><span class="sxs-lookup"><span data-stu-id="826d5-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="826d5-109">Aby uzyskać informacje na temat konfiguracji konserwatorów i grup konserwatorów, zobacz temat [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="826d5-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="826d5-110">Ustawienia preferowanych pracowników</span><span class="sxs-lookup"><span data-stu-id="826d5-110">Set up preferred workers</span></span>

<span data-ttu-id="826d5-111">Preferowany pracownik konserwacji lub grupa konserwatorów może być powiązana z jednym lub więcej z następujących:</span><span class="sxs-lookup"><span data-stu-id="826d5-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="826d5-112">handel</span><span class="sxs-lookup"><span data-stu-id="826d5-112">trade</span></span>  
- <span data-ttu-id="826d5-113">wariantem typu zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="826d5-113">maintenance job type variant</span></span>  
- <span data-ttu-id="826d5-114">typem zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="826d5-114">maintenance job type</span></span>  
- <span data-ttu-id="826d5-115">kategorią typu zadania konserwacji</span><span class="sxs-lookup"><span data-stu-id="826d5-115">maintenance job type category</span></span>  
- <span data-ttu-id="826d5-116">aktywa</span><span class="sxs-lookup"><span data-stu-id="826d5-116">asset</span></span>  
- <span data-ttu-id="826d5-117">typem składnika majątku</span><span class="sxs-lookup"><span data-stu-id="826d5-117">asset type</span></span>  

<span data-ttu-id="826d5-118">Im więcej opcji zostanie wprowadzonych dla tego samego rekordu, tym dokładniejsze będą ustawienia.</span><span class="sxs-lookup"><span data-stu-id="826d5-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="826d5-119">Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Pracownicy** > **Preferowani konserwatorzy**.</span><span class="sxs-lookup"><span data-stu-id="826d5-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="826d5-120">Naciśnij przycisk **Nowy**, aby utworzyć nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="826d5-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="826d5-121">Aby rozpocząć, Utwórz „domyślnego” konserwatora lub grupę konserwatorów.</span><span class="sxs-lookup"><span data-stu-id="826d5-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="826d5-122">Oznacza to , że można wybierać tylko w polu **Preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.</span><span class="sxs-lookup"><span data-stu-id="826d5-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="826d5-123">Na poniższym zrzucie ekranu widać przykład w pierwszym rekordzie, w którym "żądania" są wybrane jako **Preferowana grupa konserwatorów**.</span><span class="sxs-lookup"><span data-stu-id="826d5-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="826d5-124">Ta domyślna konfiguracja będzie używana podczas planowania zleceń pracy, jeśli żadna inna określona kombinacja nie pasuje do zawartości zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="826d5-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="826d5-125">Powtórz krok 2, aby utworzyć nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="826d5-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="826d5-126">Dokonaj wymaganych wyborów w zależności od poziomu szczegółowości dla preferowanego pracownika lub grupy pracowników.</span><span class="sxs-lookup"><span data-stu-id="826d5-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="826d5-127">*Przykład:* na poniższym zrzucie ekranu, w szóstym rekordzie, konserwator Shawn Richardson jest wybrany jako pracownik preferowany.</span><span class="sxs-lookup"><span data-stu-id="826d5-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="826d5-128">Zostanie on automatycznie wybrany podczas planowania zlecenia pracy zawierającego środek trwały „CH-BP1-03-02” i typ zadania konserwacji „Ocena instrumentu”, jeśli jest on dostępny w zaplanowanym czasie.</span><span class="sxs-lookup"><span data-stu-id="826d5-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="826d5-129">Jeśli podczas planowania zlecenia pracy wybrano preferowanego konserwatora, Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy **perferowanych konserwatorów**, aby sprawdzić, czy są dostępne w pierwszej kolejności najbardziej specyficzne dane.</span><span class="sxs-lookup"><span data-stu-id="826d5-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="826d5-130">Jeśli nie zostanie znalezione dopasowanie, zostanie użyty rekord domyślny z wyborem w polu **preferowana grupa konserwatorów** lub w polu **preferowany konserwator**.</span><span class="sxs-lookup"><span data-stu-id="826d5-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Rysunek 1](media/02-work-order-scheduling.png)

<span data-ttu-id="826d5-132">Można również skonfigurować *odpowiedzialnych* konserwatorów, którzy mogą być wybrani w momencie utworzenia zlecenia konserwacji lub zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="826d5-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="826d5-133">Można edytowac wszystkie wybory w **Wszystkie zlecenia pracy** i **Wszystkie żądania konserwacji** w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="826d5-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="826d5-134">Aby uzyskać więcej informacji należy zapoznać się z [Odpowiedzialni konserwatorzy](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="826d5-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="826d5-135">Podczas planowania zlecenia pracy różne wyniki są obliczane w celu określenia, którzy pracownicy powinni spełniać zadania związane z danym zleceniem (te okresy są ustawiane w **Parametry zarządzania składnikami majątku** > **Planowanie zlecenia pracy** łącze).</span><span class="sxs-lookup"><span data-stu-id="826d5-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="826d5-136">Jeśli w przypadku dwóch lub więcej preferowanych pracowników konserwacji lub pracowników odpowiedzialnych za konserwacje uzyskuje się ten sam wynik podczas planowania zleceń, jeden pracownik jest wybierany losowo.</span><span class="sxs-lookup"><span data-stu-id="826d5-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="826d5-137">W przeciwnym razie jest on zawsze pracownikiem o najwyższyej ocenie, który jest przydzielony do wykonania zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="826d5-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

