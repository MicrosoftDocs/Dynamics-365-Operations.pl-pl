---
title: Wyświetlanie zamówień planowanych, zarządzanie nimi i zatwierdzanie
description: Ten temat zawiera informacje dotyczące wyświetlania zamówień planowanych, zarządzania nimi i zatwierdzania ich w optymalizacji planowania.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935664"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="9b9b4-103">Wyświetlanie zamówień planowanych, zarządzanie nimi i zatwierdzanie</span><span class="sxs-lookup"><span data-stu-id="9b9b4-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b9b4-104">Ten temat zawiera informacje dotyczące wyświetlania zamówień planowanych, zarządzania nimi i zatwierdzania ich w optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="9b9b4-105">Wyświetlanie zamówień planowanych i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="9b9b4-105">View and manage planned orders</span></span>

<span data-ttu-id="9b9b4-106">Zamówienia planowane można wyświetlać na dowolnej stronie listy zamówień planowanych i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="9b9b4-107">Przejdź do jednego z następujących miejsc, w zależności od typu zamówień planowanych, z którymi chcesz pracować:</span><span class="sxs-lookup"><span data-stu-id="9b9b4-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="9b9b4-108">Planowanie główne \> Obszary robocze \> Planowanie główne</span><span class="sxs-lookup"><span data-stu-id="9b9b4-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="9b9b4-109">Planowanie główne \> Planowanie główne \> Zamówienia planowane</span><span class="sxs-lookup"><span data-stu-id="9b9b4-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="9b9b4-110">Kontrola produkcji \> Zlecenia produkcyjne \> Planowane zlecenie produkcyjne</span><span class="sxs-lookup"><span data-stu-id="9b9b4-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="9b9b4-111">Zaopatrzenie i sourcing \> Zamówienia zakupu \> Planowane zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="9b9b4-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="9b9b4-112">Zarządzanie zapasami \> Zamówienia przychodzące \> Planowane przeniesienia</span><span class="sxs-lookup"><span data-stu-id="9b9b4-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="9b9b4-113">Zarządzanie zapasami \> Zamówienia wychodzące \> Planowane przeniesienia</span><span class="sxs-lookup"><span data-stu-id="9b9b4-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="9b9b4-114">Wyświetlanie i edytowanie stanu zamówień planowanych</span><span class="sxs-lookup"><span data-stu-id="9b9b4-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="9b9b4-115">Pole **Stan** każdego planowanego zamówienia umożliwia śledzenie postępu lub zmianę sposobu przetwarzania zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="9b9b4-116">Dostępne są następujące wartości pola **Stan**:</span><span class="sxs-lookup"><span data-stu-id="9b9b4-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="9b9b4-117">**Nieprzetworzone** — gdy planowane główne generuje zamówienia planowane, otrzymują one ten stan.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="9b9b4-118">Zamówienia planowane o tym stanie zostaną usunięte podczas następnego uruchomienia planowania.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="9b9b4-119">**Zakończone** — ten stan wskazuje, że zamówienie planowane zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="9b9b4-120">Jeżeli nie chcesz ustalać zamówienia planowanego, możesz ręcznie zmienić jego stan na *Zakończone*.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="9b9b4-121">Należy zauważyć, że system traktuje stany *Nieprzetworzone* i *Zakończone* w taki sam sposób.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="9b9b4-122">**Zatwierdzone** — ten stan wskazuje, że zamówienie planowane jest zatwierdzone do ustalenia.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="9b9b4-123">Aby ustalić zamówienie planowane, można zmienić stan na *zatwierdzone*.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="9b9b4-124">Jeśli chcesz zachować zmiany wprowadzone w zamówieniu planowanym lub jeśli chcesz ustalić zamówienie planowane, zmień jego stan na *Zatwierdzone*.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="9b9b4-125">Zamówienia planowane o stanie *Zatwierdzone* są przez planowanie główne uznawane za ustalone i oczekujące na dostawę.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="9b9b4-126">W związku z tym nie są one modyfikowane ani usuwane podczas późniejszego planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="9b9b4-127">Aby osiągnąć to zachowanie, logika planowania kopiuje zamówienia planowane w stanie *Zatwierdzone* ze starej wersji planu do nowej wersji planu podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="9b9b4-128">Należy zauważyć, że zamówienia planowane w stanie *Zatwierdzone* są uznawane za dostawę tylko w ramach określonego planu głównego.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="9b9b4-129">Aby zmienić stan pojedynczego zamówienia planowanego, [otwórz stronę z listą zamówień planowanych](#view-planned-orders), otwórz zamówienie, a następnie wykonaj jedną z poniższych czynności:</span><span class="sxs-lookup"><span data-stu-id="9b9b4-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="9b9b4-130">Na skróconej karcie **Ogólne** zmień wartość pola **Stan**.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="9b9b4-131">W okienku akcji, na karcie **Zamówienia planowane** w grupie **Proces** wybierz **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="9b9b4-132">Aby zaznaczyć zamówienie jako zatwierdzone, w okienku akcji wybierz opcję **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="9b9b4-133">Aby jednocześnie zmienić stan kilku planowanych zamówień, [otwórz stronę listy zamówień planowanych](#view-planned-orders), zaznacz pole wyboru obok każdego zamówienia, które chcesz zmienić, a następnie wykonaj jedną z poniższych czynności:</span><span class="sxs-lookup"><span data-stu-id="9b9b4-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="9b9b4-134">W okienku akcji, na karcie **Zamówienia planowane** w grupie **Proces** wybierz **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="9b9b4-135">Aby zaznaczyć zamówienia jako zatwierdzone, w okienku akcji wybierz opcję **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="9b9b4-136">Zatwierdzanie zamówień planowanych</span><span class="sxs-lookup"><span data-stu-id="9b9b4-136">Approve planned orders</span></span>

<span data-ttu-id="9b9b4-137">Zatwierdzanie zamówień planowanych jest opcjonalnym krokiem w procesie tworzenia ustalonego zamówienia na podstawie zamówienia planowanego.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="9b9b4-138">Na poniższej ilustracji pokazano, jak można używać wartości **Stan** przypisanej do każdego planowanego zamówienia w celu zaimplementowania przepływu pracy zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="9b9b4-139">Aby wdrożyć proces zatwierdzania, ręcznie dostosuj wartość pola **Stan** dla każdego planowanego zamówienia, zgodnie z opisem w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Przepływ zamówienia planowanego](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="9b9b4-141">Zaleca się zatwierdzanie zmodyfikowanych zamówień planowanych.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="9b9b4-142">W przeciwnym razie modyfikacje zostaną zignorowane i zastąpione podczas następnego planowania.</span><span class="sxs-lookup"><span data-stu-id="9b9b4-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b9b4-143">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9b9b4-143">Additional resources</span></span>

- [<span data-ttu-id="9b9b4-144">Zaakceptuj zamówienia planowane</span><span class="sxs-lookup"><span data-stu-id="9b9b4-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
