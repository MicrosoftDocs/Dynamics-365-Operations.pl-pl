---
title: Planowanie zlecenia produkcyjnego
description: "W tej procedurze pokazano sposób planowania zlecenia produkcyjnego."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 6cbbf509c9e60040e08ab7932fcb0e8eed5ddd22
ms.contentlocale: pl-pl
ms.lasthandoff: 02/06/2018

---
# <a name="schedule-a-production-order"></a><span data-ttu-id="50ae1-103">Planowanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="50ae1-103">Schedule a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50ae1-104">W tej procedurze pokazano sposób planowania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="50ae1-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="50ae1-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="50ae1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="50ae1-106">Jest to trzecia z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="50ae1-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="50ae1-107">Planowanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="50ae1-107">Schedule a production order</span></span>
1. <span data-ttu-id="50ae1-108">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="50ae1-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="50ae1-109">Zaznacz zlecenie produkcyjne, które ma stan Szacowane.</span><span class="sxs-lookup"><span data-stu-id="50ae1-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="50ae1-110">W okienku akcji kliknij pozycję Harmonogram.</span><span class="sxs-lookup"><span data-stu-id="50ae1-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="50ae1-111">Kliknij harmonogram zadań.</span><span class="sxs-lookup"><span data-stu-id="50ae1-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="50ae1-112">Na tej stronie konfiguruje się parametry planowania.</span><span class="sxs-lookup"><span data-stu-id="50ae1-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="50ae1-113">Można skonfigurować parametry dla określonych użytkowników lub wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="50ae1-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="50ae1-114">W polu Kierunek planowania wybierz opcję „W przód od dzisiaj”.</span><span class="sxs-lookup"><span data-stu-id="50ae1-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="50ae1-115">W polu Data planowania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="50ae1-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="50ae1-116">Zaznacz lub wyczyść pole wyboru Ograniczone zdolności produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="50ae1-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="50ae1-117">Zaznacz lub wyczyść pole wyboru Ograniczone materiały.</span><span class="sxs-lookup"><span data-stu-id="50ae1-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="50ae1-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="50ae1-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="50ae1-119">Wyświetlanie wyników planowania</span><span class="sxs-lookup"><span data-stu-id="50ae1-119">View the scheduling results</span></span>
1. <span data-ttu-id="50ae1-120">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="50ae1-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="50ae1-121">Kliknij opcję Wszystkie zadania.</span><span class="sxs-lookup"><span data-stu-id="50ae1-121">Click All jobs.</span></span>
    * <span data-ttu-id="50ae1-122">Ta strona służy do wyświetlania zaplanowanych zadań, które właśnie utworzono.</span><span class="sxs-lookup"><span data-stu-id="50ae1-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="50ae1-123">Rozwiń lub zwiń sekcję Planowanie.</span><span class="sxs-lookup"><span data-stu-id="50ae1-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="50ae1-124">Na skróconej karcie Planowanie można obejrzeć zaplanowaną datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="50ae1-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="50ae1-125">Kliknij przycisk Informacje.</span><span class="sxs-lookup"><span data-stu-id="50ae1-125">Click Inquiries.</span></span>
5. <span data-ttu-id="50ae1-126">Kliknij opcję Obciążenie zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="50ae1-126">Click Capacity load.</span></span>
    * <span data-ttu-id="50ae1-127">Strony Obciążenie zdolności produkcyjnych pokazuje zdolności produkcyjne zarezerwowane wskutek planowania zadań, aktualną łączną liczbę godzin rezerwacji zasobu oraz liczbę godzin, które są dostępne na potrzeby zaplanowania zasobu dla zadań.</span><span class="sxs-lookup"><span data-stu-id="50ae1-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="50ae1-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="50ae1-128">Close the page.</span></span>
7. <span data-ttu-id="50ae1-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="50ae1-129">Close the page.</span></span>

