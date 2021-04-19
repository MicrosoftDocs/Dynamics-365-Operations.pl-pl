---
title: Harmonogram konserwacji
description: W tym temacie wyjaśniono harmonogram konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f7bed45ccf151a2667dcc8dddd5c0586a594ca58
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839590"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="9a916-103">Harmonogram konserwacji</span><span class="sxs-lookup"><span data-stu-id="9a916-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9a916-104">Harmonogram konserwacji zawiera listę wszystkich oczekiwanych planów konserwacji, zgłoszeń serwisowych i serii czynności konserwacji. Niektóre wiersze harmonogramu mogły zostać przekonwertowane na zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="9a916-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="9a916-105">Cztery widoki harmonogramu konserwacji są nieco inne, w zależności od tego, które wiersze harmonogramu konserwacji mają być widoczne.</span><span class="sxs-lookup"><span data-stu-id="9a916-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="9a916-106">Element menu</span><span class="sxs-lookup"><span data-stu-id="9a916-106">Menu item</span></span>                  | <span data-ttu-id="9a916-107">Opis zawartości</span><span class="sxs-lookup"><span data-stu-id="9a916-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9a916-108">Wszystkie harmonogramy konserwacji</span><span class="sxs-lookup"><span data-stu-id="9a916-108">All maintenance schedule</span></span>       | <span data-ttu-id="9a916-109">Wszystkie wiersze harmonogramu konserwacji są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="9a916-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="9a916-110">Mój harmonogram składników majątku</span><span class="sxs-lookup"><span data-stu-id="9a916-110">My asset schedule</span></span>        | <span data-ttu-id="9a916-111">Na tej liście są wyświetlane wszystkie wiersze harmonogramu konserwacji zawierające składniki majątku zainstalowane w lokalizacjach czynności konserwacyjnych, z którymi powiązany jest pracownik (skonfigurowany w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="9a916-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="9a916-112">Otwieranie wierszy harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="9a916-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="9a916-113">Wiersze harmonogramu konserwacji ze stanem „utworzone” — oznacza, że nie zostały jeszcze przekształcone na zlecenie pracy lub odrzucone — są wyświetlane na tej liście.</span><span class="sxs-lookup"><span data-stu-id="9a916-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="9a916-114">Otwieranie puli harmonogramów konserwacji</span><span class="sxs-lookup"><span data-stu-id="9a916-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="9a916-115">Na tej liście są wyświetlane wiersze harmonogramu konserwacji powiązane z pulą zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="9a916-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="9a916-116">Jeśli wiersz harmonogramu konserwacji jest uwzględniony w kilku pulach zleceń pracy (zapoznaj się z [Pule zleceń pracy](../work-orders/work-order-pools.md)), dla każdej puli w polu **Otwieranie puli harmonogramów konserwacji** jest wyświetlany jeden rekord.</span><span class="sxs-lookup"><span data-stu-id="9a916-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="9a916-117">W ten sposób można zoptymalizować opcje filtrowania w pulach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="9a916-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="9a916-118">Aby otworzyć wierszy harmonogramu konserwacji</span><span class="sxs-lookup"><span data-stu-id="9a916-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="9a916-119">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Harmonogram konserwacji** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** lub **Otwieranie puli harmonogramów konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="9a916-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="9a916-120">Aby zaktualizować harmonogram konserwacji, należy kliknąć **Plan konserwacji** lub **Serie czynności konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="9a916-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="9a916-121">Wiersz harmonogramu konserwacji można edytować, zaznaczając go i klikając przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="9a916-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="9a916-122">Można na przykład łatwo zaktualizować poziom usług lub pracownika odpowiedzialnego za zadanie.</span><span class="sxs-lookup"><span data-stu-id="9a916-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="9a916-123">Można edytować tylko wiersze harmonogramu konserwacji, które nie zostały jeszcze połączone ze zleceniem pracy.</span><span class="sxs-lookup"><span data-stu-id="9a916-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="9a916-124">Wiersz harmonogramu konserwacji można usunąć, zaznaczając go na stronie listy i klikając przycisk **Usuń.**</span><span class="sxs-lookup"><span data-stu-id="9a916-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="9a916-125">Wiersz harmonogramu konserwacji można odrzucić, zaznaczając go na stronie listy i klikając przycisk **Odrzuć.**</span><span class="sxs-lookup"><span data-stu-id="9a916-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="9a916-126">Ta funkcja jest przydatna, jeśli na przykład składnik majątku ma plan obsługi technicznej 2 000 km i plan obsługi technicznej 10 000 km.</span><span class="sxs-lookup"><span data-stu-id="9a916-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="9a916-127">Następnie użytkownik może chcieć odrzucić wiersz utworzony na podstawie planu konserwacji 2 000 km, gdy jest on zgodny z 10 000 km, 20 000 km, 30 000 km itd.</span><span class="sxs-lookup"><span data-stu-id="9a916-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="9a916-128">Jeśli odrzucisz wiersz harmonogramu konserwacji związany z planem eksploatacji, wiersz ten nigdy nie będzie wyświetlany po zaplanowaniu planu konserwacji.</span><span class="sxs-lookup"><span data-stu-id="9a916-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="9a916-129">Można wybrać kilka wierszy planowania obsługi technicznej we **Wszystkie harmonogramy konserwacji** eksploatacji i kliknąć opcję **Pula zleceń pracy**, jeśli wszystkie wybrane wiersze mają zostać uwzględnione w tej samej puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="9a916-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="9a916-130">Można wybrać kilka wierszy harmonogramu obsługi we **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** albo **Otwieranie puli harmonogramów konserwacji** i kliknąć przycisk **Koryguj harmonogram**, jeśli należy wprowadzić takie same korekty w kilku wierszach.</span><span class="sxs-lookup"><span data-stu-id="9a916-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="9a916-131">Można zmienić oczekiwane daty rozpoczęcia i zakończenia, poziom usług oraz odpowiedzialną za nią grupę pracowników obsługi lub odpowiedzialną obsługę techniczną związane z wybranymi wierszami harmonogramu obsługi.</span><span class="sxs-lookup"><span data-stu-id="9a916-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="9a916-132">Jeśli wiersz harmonogramu konserwacji został powiązany ze zleceniem pracy, identyfikator zlecenia pracy zostanie wyświetlony w polu **Zlecenie pracy**.</span><span class="sxs-lookup"><span data-stu-id="9a916-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="9a916-133">W szczegółowym widoku **Wszystkie składniki majątku** > skrócona karta **Plany konserwacji składnika majątku**, można wybierać plany konserwacji dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="9a916-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="9a916-134">Późniejsze usunięcie wiersza planu konserwacji lub serii czynności konserwacyjnych związanej ze składnikiem majątku w menu **Wszystkie składniki majątku** powoduje również automatyczne usunięcie wszystkich harmonogramów konserwacji ze stanem „Utworzono”, które zostały utworzone na podstawie tego planu konserwacji lub serii czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="9a916-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="9a916-135">Przejrzyj również [Tworzenie składnika majątku](../objects/create-an-object.md)</span><span class="sxs-lookup"><span data-stu-id="9a916-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="9a916-136">Na poniższej ilustracji pokazano stronę z listą **Wszystkie harmonogramy konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="9a916-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![Rysunek 1](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]