---
title: Zlecenia serwisowe
description: "Zlecenie serwisowe reprezentuje wizytę serwisanta w siedzibie odbiorcy w określonym dniu."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 647bbe9cca0167d33048ad07e092708f90b41fc3
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="service-orders"></a><span data-ttu-id="e5774-103">Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="e5774-103">Service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e5774-104">Zlecenie serwisowe reprezentuje wizytę serwisanta w siedzibie odbiorcy w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="e5774-104">A service order represents a visit that a service technician makes to a customer site on a specific date.</span></span> <span data-ttu-id="e5774-105">Każde zlecenie serwisowe składa się z jednego lub większej liczby wierszy zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e5774-105">Each service order consists of one or more service order lines.</span></span> <span data-ttu-id="e5774-106">Wiersze zlecenia serwisowego reprezentują godziny pracy, jaką musi wykonać serwisant, oraz powiązane towary, wydatki i opłaty.</span><span class="sxs-lookup"><span data-stu-id="e5774-106">Service order lines represent the hours of work that must be performed by the service technician, and the related items, expenses, and fees.</span></span>

<span data-ttu-id="e5774-107">Do wiersza zlecenia serwisowego można dołączać zadania i przedmioty.</span><span class="sxs-lookup"><span data-stu-id="e5774-107">You can attach tasks and objects to a service order line.</span></span> <span data-ttu-id="e5774-108">Umożliwi to następnie grupowanie wierszy zleceń serwisowych według zadań lub przedmiotów.</span><span class="sxs-lookup"><span data-stu-id="e5774-108">You can then group service order lines by task or by object.</span></span> <span data-ttu-id="e5774-109">Do wierszy zlecenia serwisowego można również dołączać towary wyświetlane na liście zapasów.</span><span class="sxs-lookup"><span data-stu-id="e5774-109">You can also attach items that are listed in inventory to service order lines.</span></span>

## <a name="create-service-orders"></a><span data-ttu-id="e5774-110">Tworzenie zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="e5774-110">Create service orders</span></span>

<span data-ttu-id="e5774-111">Zlecenia serwisowe można tworzyć na podstawie umowy serwisowej i zawartych w niej wierszy.</span><span class="sxs-lookup"><span data-stu-id="e5774-111">You can create service orders based on a service agreement and the lines that are contained in that agreement.</span></span> <span data-ttu-id="e5774-112">Jednak zlecenia serwisowe skojarzone z umową serwisową można tworzyć tylko w okresie, który jest określony w umowie.</span><span class="sxs-lookup"><span data-stu-id="e5774-112">However, you can create service orders that are associated with a service agreement only in the period that is specified in the agreement.</span></span> <span data-ttu-id="e5774-113">Na przykład jeśli umowa serwisowa jest ważna w roku kalendarzowym 2011, można tworzyć zlecenia serwisowe dla tej umowy w dniach od 1 stycznia 2011 r. do 31 grudnia 2011 r.</span><span class="sxs-lookup"><span data-stu-id="e5774-113">For example, if a service agreement is valid for the 2011 calendar year, you can create service orders for the agreement from January 1, 2011, and December 31, 2011.</span></span>

<span data-ttu-id="e5774-114">Można również tworzyć zlecenia serwisowe indywidualnie, bez kojarzenia ich z umową.</span><span class="sxs-lookup"><span data-stu-id="e5774-114">You can also create service orders individually, without associating them with an agreement.</span></span> <span data-ttu-id="e5774-115">Takie zlecenia serwisowe mogą służyć do obsługi niezaplanowanych lub jednorazowych wizyt serwisowych.</span><span class="sxs-lookup"><span data-stu-id="e5774-115">These service orders can be used to handle unscheduled or one-time service visits.</span></span> <span data-ttu-id="e5774-116">Na przykład w marcu odbiorca prosi o wykonanie dodatkowego serwisu dla dwóch urządzeń, oprócz maszyn określonych w umowie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e5774-116">For example, in the month of March, your customer wants service to be performed on two machines, in addition to the machines that are specified in the service agreement.</span></span> <span data-ttu-id="e5774-117">Dla tego zadania tworzysz zlecenia serwisowe, ale nie kojarzysz ich z umową.</span><span class="sxs-lookup"><span data-stu-id="e5774-117">For this task, you create service orders but do not associate them with an agreement.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e5774-118">Aby utworzyć zlecenia serwisowe, które nie są powiązane z umową serwisową, należy zaznaczyć pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e5774-118">To create service orders that are not associated with a service agreement, you must select the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form.</span></span></P>

<span data-ttu-id="e5774-119">**Scenariusz**</span><span class="sxs-lookup"><span data-stu-id="e5774-119">**Scenario**</span></span>

<span data-ttu-id="e5774-120">Poniższy scenariusz opisuje inną sytuację, w której warto utworzyć zlecenie serwisowe, które nie jest powiązane z umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="e5774-120">The following scenario describes another situation where it is useful to create a service order that is not associated with a service agreement.</span></span>

<span data-ttu-id="e5774-121">Dyspozytor w firmie odbiera zgłoszenie dotyczące pilnego serwisu windy.</span><span class="sxs-lookup"><span data-stu-id="e5774-121">The company dispatcher receives a call requesting emergency service on an elevator.</span></span> <span data-ttu-id="e5774-122">Nie czasu na konfigurowanie umowy serwisowej i projektu na wykonanie prac serwisowych.</span><span class="sxs-lookup"><span data-stu-id="e5774-122">There is no time to set up a service agreement and a project for the service.</span></span> <span data-ttu-id="e5774-123">Z tego względu dyspozytor tworzy zlecenie serwisowe bezpośrednio w formularzu **Zlecenia serwisowe**, dołącza zlecenie serwisowe do istniejącego projektu, a następnie tworzy wiersze zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e5774-123">Therefore, the dispatcher creates a service order directly in the **Service orders** form, attaches the service order to an existing project, and creates the service order lines.</span></span> <span data-ttu-id="e5774-124">Ponadto dyspozytor tworzy relację zadania lub przedmiotu dla istniejącego zlecenia serwisowego w celu rejestrowania pracy, która nie jest związana z umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="e5774-124">The dispatcher also creates a task or object relation for an existing service order, to record work that is not related to the service agreement.</span></span> <span data-ttu-id="e5774-125">Aby uzyskać więcej informacji, zobacz [Ręczne tworzenie zleceń serwisowych](create-service-orders-manually.md) i [Tworzenie relacji zadania serwisowego](create-service-task-relations.md).</span><span class="sxs-lookup"><span data-stu-id="e5774-125">For more information, see [Create service orders manually](create-service-orders-manually.md) and [Create service task relations](create-service-task-relations.md).</span></span>

## <a name="monitor-the-progress-of-service-orders"></a><span data-ttu-id="e5774-126">Monitorowanie postępu realizacji zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="e5774-126">Monitor the progress of service orders</span></span>

<span data-ttu-id="e5774-127">Aby monitorować postęp realizacji zleceń serwisowych w różnych zespołach i procesach roboczych, można skonfigurować system etapów i kodów przyczyn dla zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="e5774-127">To monitor the progress of a sales order through the different teams and work processes, you can set up a system of stages and reason codes for service orders.</span></span> <span data-ttu-id="e5774-128">Dla każdego etapu można określić dozwolone działania.</span><span class="sxs-lookup"><span data-stu-id="e5774-128">For each stage, you can specify the actions that are allowed.</span></span> <span data-ttu-id="e5774-129">Aby uzyskać więcej informacji, zobacz [Tworzenie kodów przyczyn](create-reason-codes.md).</span><span class="sxs-lookup"><span data-stu-id="e5774-129">For more information, see [Create reason codes](create-reason-codes.md).</span></span>

<span data-ttu-id="e5774-130">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="e5774-130">**Example**</span></span>

<span data-ttu-id="e5774-131">Zlecenie serwisowe jest zatwierdzane przez dyspozytora.</span><span class="sxs-lookup"><span data-stu-id="e5774-131">A service order is approved by the dispatcher.</span></span> <span data-ttu-id="e5774-132">Dyspozytor aktualizuje etap realizacji zlecenia serwisowego i ustawia kod przyczyny, który wskazuje, że zlecenie serwisowe zostało zwolnione do serwisanta.</span><span class="sxs-lookup"><span data-stu-id="e5774-132">The dispatcher updates the stage of the service order and specifies a reason code that indicates that the service order has been released to the service technician.</span></span> <span data-ttu-id="e5774-133">Serwisant udaje się do siedziby odbiorcy i wykonuje prace serwisowe.</span><span class="sxs-lookup"><span data-stu-id="e5774-133">The technician goes to the customer site and performs the service.</span></span>

## <a name="specify-item-requirements-for-service-orders"></a><span data-ttu-id="e5774-134">Określanie zapotrzebowań na towary do zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="e5774-134">Specify item requirements for service orders</span></span>

<span data-ttu-id="e5774-135">Można określić pozycje magazynowe, które są wymagane dla zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="e5774-135">You can specify the inventory items that are required for service orders.</span></span> <span data-ttu-id="e5774-136">W tym celu zlecenie serwisowe musi być skojarzone z projektem.</span><span class="sxs-lookup"><span data-stu-id="e5774-136">However, the service order must be associated with a project.</span></span> <span data-ttu-id="e5774-137">Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu.</span><span class="sxs-lookup"><span data-stu-id="e5774-137">Item requirements for service orders are processed through a project.</span></span> 

<span data-ttu-id="e5774-138">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="e5774-138">**Example**</span></span>

<span data-ttu-id="e5774-139">Zlecenia serwisowe utworzone na podstawie umowy serwisowej są przetwarzane przez dyspozytora.</span><span class="sxs-lookup"><span data-stu-id="e5774-139">The service orders that are created from the service agreement are processed by the dispatcher.</span></span> <span data-ttu-id="e5774-140">Przy pierwszym zleceniu serwisowym dyspozytor zdał sobie sprawę, że serwisantowi potrzebna jest ważna zapasowa część, której nie ma w dostępnych zapasach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="e5774-140">For the first service order, the dispatcher realizes that the service technician requires an important spare part that is not in the on-hand inventory.</span></span> <span data-ttu-id="e5774-141">Tworzy więc zapotrzebowanie na towar dotyczące tej części bezpośrednio ze zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e5774-141">Therefore, the dispatcher creates an item requirement for the spare part directly from the service order.</span></span>

## <a name="move-and-post-lines"></a><span data-ttu-id="e5774-142">Przenoszenie i księgowanie wierszy</span><span class="sxs-lookup"><span data-stu-id="e5774-142">Move and post lines</span></span>

<span data-ttu-id="e5774-143">Po powrocie z wizyty serwisowej serwisant modyfikuje i aktualizuje wiersze zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="e5774-143">A service technician returns from a service visit, and then modifies and updates the service order lines.</span></span> <span data-ttu-id="e5774-144">W trakcie tej wizyty serwisowej serwisant wykonał pracę serwisową, która była zaplanowana na następną wizytę.</span><span class="sxs-lookup"><span data-stu-id="e5774-144">During the service visit, the technician performed a service job that was scheduled for the next service visit.</span></span> <span data-ttu-id="e5774-145">W związku z tym serwisant przenosi wiersze z następnej wizyty serwisowej do bieżącej wizyty serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e5774-145">Therefore, the technician moves the lines from the next service visit to the current service visit.</span></span> <span data-ttu-id="e5774-146">Następnie serwisant księguje zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="e5774-146">The technician then posts the service order.</span></span> <span data-ttu-id="e5774-147">Aby uzyskać więcej informacji, zobacz [Przenoszenie wierszy zlecenia serwisowego](move-service-order-lines.md).</span><span class="sxs-lookup"><span data-stu-id="e5774-147">For more information, see [Move service order lines](move-service-order-lines.md).</span></span>

## <a name="cancel-service-orders"></a><span data-ttu-id="e5774-148">Anuluj zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="e5774-148">Cancel service orders</span></span>

<span data-ttu-id="e5774-149">Jedno z pozostałych zleceń serwisowych wygenerowanych dla stycznia stało się nieaktualne z powodu anulowania pracy.</span><span class="sxs-lookup"><span data-stu-id="e5774-149">One of the other service orders that was generated for the month of January becomes obsolete, because the job is canceled.</span></span> <span data-ttu-id="e5774-150">W związku z tym dyspozytor anuluje zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="e5774-150">Therefore, the service dispatcher cancels the service order.</span></span> <span data-ttu-id="e5774-151">Aby uzyskać więcej informacji, zobacz [Anulowanie zleceń serwisowych](cancel-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="e5774-151">For more information, see [Cancel service orders](cancel-service-orders.md).</span></span>

## <a name="post-from-projects"></a><span data-ttu-id="e5774-152">Księgowanie z projektów</span><span class="sxs-lookup"><span data-stu-id="e5774-152">Post from projects</span></span>

<span data-ttu-id="e5774-153">W końcu każdego tygodnia dyspozytor chce zaksięgować wszystkie zlecenia serwisowe dołączone do określonego projektu.</span><span class="sxs-lookup"><span data-stu-id="e5774-153">At the end of each week, the dispatcher wants to post all service orders that are attached to a specific project.</span></span> <span data-ttu-id="e5774-154">W związku z tym dyspozytor odszukuje odpowiedni projekt w formularzu **Projekty** i księguje zlecenia serwisowe, które zostały ukończone.</span><span class="sxs-lookup"><span data-stu-id="e5774-154">Therefore, the dispatcher locates the relevant project in the **Projects** form and posts the service orders that have been completed.</span></span> <span data-ttu-id="e5774-155">Aby uzyskać więcej informacji, zobacz [Księgowanie zleceń serwisowych (formularzy klasy)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="e5774-155">For more information, see [Post service orders (class form)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).</span></span>

## <a name="delete-service-orders"></a><span data-ttu-id="e5774-156">Usuń zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="e5774-156">Delete service orders</span></span>

<span data-ttu-id="e5774-157">W drugiej połowie roku odbiorca doszedł do wniosku, że wizyty serwisowe są zbyt rzadkie.</span><span class="sxs-lookup"><span data-stu-id="e5774-157">During the second half of the year, your customer decides that the service visits are too infrequent.</span></span> <span data-ttu-id="e5774-158">Należy utworzyć nową, liczącą więcej pozycji serię wizyt serwisowych w pozostałym czasie umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="e5774-158">You must create a new, more frequent series of service visits for the remaining time on the service agreement.</span></span> <span data-ttu-id="e5774-159">W tym celu należy usunąć istniejące zlecenia serwisowe i utworzyć nowe.</span><span class="sxs-lookup"><span data-stu-id="e5774-159">Therefore, you must delete the existing service orders and create new service orders.</span></span> <span data-ttu-id="e5774-160">Aby uzyskać więcej informacji, zobacz [Usuwanie zleceń serwisowych](delete-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="e5774-160">For more information, see [Delete service orders](delete-service-orders.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5774-161">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e5774-161">See also</span></span>

<span data-ttu-id="e5774-162">[Zlecenia serwisowe (formularz)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e5774-162">[Service orders (form)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))</span></span>

  


