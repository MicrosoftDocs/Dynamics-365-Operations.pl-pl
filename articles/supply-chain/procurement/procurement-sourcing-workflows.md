---
title: "Przepływy pracy dla zaopatrzenia i sourcingu"
description: "Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3bf244786e308ebcaee27a16fae378f41086f963
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="cdd5d-104">Przepływy pracy dla zaopatrzenia i sourcingu</span><span class="sxs-lookup"><span data-stu-id="cdd5d-104">Procurement and sourcing workflows</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cdd5d-105">Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="cdd5d-106">Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="cdd5d-107">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-107">A workflow represents a business process.</span></span> <span data-ttu-id="cdd5d-108">Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="cdd5d-109">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="cdd5d-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="cdd5d-110">**Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="cdd5d-111">Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="cdd5d-112">**Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-112">**Process visibility**— You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="cdd5d-113">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="cdd5d-114">**Scentralizowana Lista prac** — Na scentralizowanej liście prac użytkownicy mogą wyświetlać zadania i zatwierdzenia przepływów pracy przypisane im we wszystkich przepływach pracy, w których uczestniczą.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-114">**Centralized work list**— Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="cdd5d-115">Ta opcja jest dostępna na stronie Elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="cdd5d-116"> Dostępne typy przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="cdd5d-116">The types of workflows that you can create</span></span>
<span data-ttu-id="cdd5d-117">Następujące typy przepływu pracy są dostępne w module Zaopatrzenie i sourcing.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="cdd5d-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cdd5d-118">**Type**</span></span>                         | <span data-ttu-id="cdd5d-119">**Ten typ służy do następujących zadań**</span><span class="sxs-lookup"><span data-stu-id="cdd5d-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="cdd5d-120">Przegląd zapotrzebowań na zakup</span><span class="sxs-lookup"><span data-stu-id="cdd5d-120">Purchase requisition review</span></span>      | <span data-ttu-id="cdd5d-121">Tworzenie przepływów pracy przeglądu zatwierdzania zapotrzebowań zakupu.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-121">Create review workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="cdd5d-122">Przegląd wiersza zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="cdd5d-122">Purchase requisition line review</span></span> | <span data-ttu-id="cdd5d-123">Tworzenie przepływów pracy przeglądu wierszy zapotrzebowania zakupu.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-123">Create review workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="cdd5d-124">Przepływ pracy zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="cdd5d-124">Purchase order workflow</span></span>          | <span data-ttu-id="cdd5d-125">Tworzenie przepływów pracy przeglądania i zatwierdzania dla zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="cdd5d-126">Przepływ pracy wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="cdd5d-126">Purchase order line workflow</span></span>     | <span data-ttu-id="cdd5d-127">Tworzenie przepływów pracy przeglądania i zatwierdzania dla wierszy zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-127">Create review and approve workflows for purchase order lines.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="cdd5d-128">Tworzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="cdd5d-128">Creating a workflow</span></span>
<span data-ttu-id="cdd5d-129">Aby utworzyć przepływ pracy, kliknij kolejno opcje Zaopatrzenie i sourcing &gt; Ustawienia &gt; Przepływy pracy dla zaopatrzenia i sourcingu i utwórz nowy przepływ pracy poprzez wybranie typu przepływu pracy, który chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-129">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="cdd5d-130">Na kanwie przepływu pracy możesz przeciągać elementy przepływu pracy do projektanta i łączyć elementy w sekwencje.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-130">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="cdd5d-131">Elementy przepływu pracy powinny być skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-131">The workflow elements should be configured.</span></span> <span data-ttu-id="cdd5d-132">Dla elementów przepływu pracy zatwierdzania i zadań można skonfigurować, którzy uczestnicy powinni wykonywać czynności.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-132">For approval and task workflow elements you can configure which participant should take action.</span></span>
<span data-ttu-id="cdd5d-133">Typy uczestników</span><span class="sxs-lookup"><span data-stu-id="cdd5d-133">Types of participants</span></span>
----------------------

<span data-ttu-id="cdd5d-134">Można przypisać krok zatwierdzania do następujących grup uczestników.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-134">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="cdd5d-135">Grupa użytkowników</span><span class="sxs-lookup"><span data-stu-id="cdd5d-135">User group</span></span>    | <span data-ttu-id="cdd5d-136">Opis</span><span class="sxs-lookup"><span data-stu-id="cdd5d-136">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="cdd5d-137">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="cdd5d-137">Participant</span></span>   | <span data-ttu-id="cdd5d-138">Przypisanie kroku zatwierdzania do członków grupy lub roli.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-138">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="cdd5d-139">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="cdd5d-139">Hierarchy</span></span>     | <span data-ttu-id="cdd5d-140">Przypisz krok zatwierdzania do użytkowników w określonej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-140">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="cdd5d-141">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="cdd5d-141">Workflow user</span></span> | <span data-ttu-id="cdd5d-142">Przypisanie kroku zatwierdzania do użytkowników tego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-142">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="cdd5d-143">Kolejka</span><span class="sxs-lookup"><span data-stu-id="cdd5d-143">Queue</span></span>         | <span data-ttu-id="cdd5d-144">Przypisanie kroku zatwierdzania do kolejki etapów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-144">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="cdd5d-145">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="cdd5d-145">User</span></span>          | <span data-ttu-id="cdd5d-146">Przypisanie kroku zatwierdzania do określonych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="cdd5d-146">Assign the approval step to specific users.</span></span>                               |



<a name="see-also"></a><span data-ttu-id="cdd5d-147">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="cdd5d-147">See also</span></span>
--------

[<span data-ttu-id="cdd5d-148">Definiowanie przepływów pracy procesów biznesowych dla zapotrzebowań na zakup</span><span class="sxs-lookup"><span data-stu-id="cdd5d-148">Defining business process workflows for purchase requisitions</span></span>](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[<span data-ttu-id="cdd5d-149">Przepływ pracy zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="cdd5d-149">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)




