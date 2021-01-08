---
title: Przepływy pracy dla zaopatrzenia i sourcingu
description: Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję. Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.
author: mkirknel
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22602911fa5d395d439242746f2fe8a27c656bcf
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654155"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="d40f5-104">Przepływy pracy dla zaopatrzenia i sourcingu</span><span class="sxs-lookup"><span data-stu-id="d40f5-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d40f5-105">Niektóre organizacje wymagają, aby zapotrzebowania na zakup i zamówienia zakupu były zatwierdzane przez użytkowników innych niż osoby, która wprowadziły transakcję.</span><span class="sxs-lookup"><span data-stu-id="d40f5-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="d40f5-106">Aby skonfigurować proces zatwierdzania, można utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="d40f5-107">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-107">A workflow represents a business process.</span></span> <span data-ttu-id="d40f5-108">Określa sposób przepływu dokumentu przez system i wskazuje osoby, które muszą zakończyć zadanie lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="d40f5-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="d40f5-109">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="d40f5-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="d40f5-110">**Spójność procesów** — Możesz zdefiniować proces zatwierdzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="d40f5-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="d40f5-111">Używanie systemu przepływu pracy pomaga zapewnić, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="d40f5-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="d40f5-112">**Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="d40f5-113">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="d40f5-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="d40f5-114">**Scentralizowana Lista prac** — Na scentralizowanej liście prac użytkownicy mogą wyświetlać zadania i zatwierdzenia przepływów pracy przypisane im we wszystkich przepływach pracy, w których uczestniczą.</span><span class="sxs-lookup"><span data-stu-id="d40f5-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="d40f5-115">Ta opcja jest dostępna na stronie Elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="d40f5-116"> Dostępne typy przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="d40f5-116">The types of workflows that you can create</span></span>

<span data-ttu-id="d40f5-117">Następujące typy przepływu pracy są dostępne w module Zaopatrzenie i sourcing.</span><span class="sxs-lookup"><span data-stu-id="d40f5-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="d40f5-118">Typ</span><span class="sxs-lookup"><span data-stu-id="d40f5-118">Type</span></span> | <span data-ttu-id="d40f5-119">Ten typ służy do następujących zadań</span><span class="sxs-lookup"><span data-stu-id="d40f5-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="d40f5-120">Przegląd zapotrzebowań na zakup</span><span class="sxs-lookup"><span data-stu-id="d40f5-120">Purchase requisition review</span></span> | <span data-ttu-id="d40f5-121">Tworzenie przepływów pracy przeglądania i zatwierdzania zapotrzebowań zakupu.</span><span class="sxs-lookup"><span data-stu-id="d40f5-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="d40f5-122">Przegląd wiersza zapotrzebowania na zakup</span><span class="sxs-lookup"><span data-stu-id="d40f5-122">Purchase requisition line review</span></span> | <span data-ttu-id="d40f5-123">Tworzenie przepływów pracy przeglądania i zatwierdzania wierszy zapotrzebowań zakupu.</span><span class="sxs-lookup"><span data-stu-id="d40f5-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="d40f5-124">Przepływ pracy zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="d40f5-124">Purchase order workflow</span></span> | <span data-ttu-id="d40f5-125">Tworzenie przepływów pracy przeglądania i zatwierdzania dla zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d40f5-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="d40f5-126">Przepływ pracy wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="d40f5-126">Purchase order line workflow</span></span> | <span data-ttu-id="d40f5-127">Tworzenie przepływów pracy przeglądania i zatwierdzania dla wierszy zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d40f5-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="d40f5-128">Przepływ pracy zgłaszania dodania dostawcy</span><span class="sxs-lookup"><span data-stu-id="d40f5-128">Vendor add application workflow</span></span> | <span data-ttu-id="d40f5-129">Służy do tworzenia przepływów pracy przeglądania i zatwierdzania w celu dodawania nowych dostawców za pomocą wniosków o nowych dostawców.</span><span class="sxs-lookup"><span data-stu-id="d40f5-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="d40f5-130">Podczas dodawania nowego przepływu pracy mogą być również wyświetlane następujące przestarzałe przepływy pracy w oknie dialogowym **Utwórz przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="d40f5-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="d40f5-131">Są one powiązane z funkcją *potwierdzenia odbioru* dostępną w [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), która jest już przestarzała.</span><span class="sxs-lookup"><span data-stu-id="d40f5-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="d40f5-132">Te przepływy pracy są obecnie nieobsługiwane.</span><span class="sxs-lookup"><span data-stu-id="d40f5-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="d40f5-133">Przepływ pracy powiadomienia o terminie dostawy</span><span class="sxs-lookup"><span data-stu-id="d40f5-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="d40f5-134">Przepływ pracy powiadomienia o otrzymaniu faktury</span><span class="sxs-lookup"><span data-stu-id="d40f5-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="d40f5-135">Przepływ pracy powiadamiania o niepowodzeniu przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="d40f5-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="d40f5-136">Przepływ pracy powiadomienia o odrzuconym niepotwierdzonym dokumencie przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="d40f5-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="d40f5-137">Tworzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="d40f5-137">Creating a workflow</span></span>

<span data-ttu-id="d40f5-138">Aby utworzyć przepływ pracy, kliknij kolejno opcje Zaopatrzenie i sourcing &gt; Ustawienia &gt; Przepływy pracy dla zaopatrzenia i sourcingu i utwórz nowy przepływ pracy poprzez wybranie typu przepływu pracy, który chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="d40f5-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="d40f5-139">Na kanwie przepływu pracy możesz przeciągać elementy przepływu pracy do projektanta i łączyć elementy w sekwencje.</span><span class="sxs-lookup"><span data-stu-id="d40f5-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="d40f5-140">Elementy przepływu pracy powinny być skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="d40f5-140">The workflow elements should be configured.</span></span> <span data-ttu-id="d40f5-141">Dla elementów przepływu pracy zatwierdzania i zadań można skonfigurować, którzy uczestnicy powinni wykonywać czynności.</span><span class="sxs-lookup"><span data-stu-id="d40f5-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="d40f5-142">Typy uczestników</span><span class="sxs-lookup"><span data-stu-id="d40f5-142">Types of participants</span></span>

<span data-ttu-id="d40f5-143">Można przypisać krok zatwierdzania do następujących grup uczestników.</span><span class="sxs-lookup"><span data-stu-id="d40f5-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="d40f5-144">Grupa użytkowników</span><span class="sxs-lookup"><span data-stu-id="d40f5-144">User group</span></span> | <span data-ttu-id="d40f5-145">Opis</span><span class="sxs-lookup"><span data-stu-id="d40f5-145">Description</span></span> |
|---|---|
| <span data-ttu-id="d40f5-146">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="d40f5-146">Participant</span></span> | <span data-ttu-id="d40f5-147">Przypisanie kroku zatwierdzania do członków grupy lub roli.</span><span class="sxs-lookup"><span data-stu-id="d40f5-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="d40f5-148">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="d40f5-148">Hierarchy</span></span> | <span data-ttu-id="d40f5-149">Przypisz krok zatwierdzania do użytkowników w określonej hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="d40f5-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="d40f5-150">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="d40f5-150">Workflow user</span></span> | <span data-ttu-id="d40f5-151">Przypisanie kroku zatwierdzania do użytkowników tego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="d40f5-152">Kolejka</span><span class="sxs-lookup"><span data-stu-id="d40f5-152">Queue</span></span> | <span data-ttu-id="d40f5-153">Przypisanie kroku zatwierdzania do kolejki etapów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d40f5-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="d40f5-154">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="d40f5-154">User</span></span> | <span data-ttu-id="d40f5-155">Przypisanie kroku zatwierdzania do określonych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="d40f5-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="d40f5-156">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d40f5-156">Additional resources</span></span>

- [<span data-ttu-id="d40f5-157">Definiowanie przepływów pracy procesów biznesowych dla zapotrzebowań na zakup</span><span class="sxs-lookup"><span data-stu-id="d40f5-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="d40f5-158">Przepływ pracy zapotrzebowań na zakup</span><span class="sxs-lookup"><span data-stu-id="d40f5-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="d40f5-159">Wdrażanie dostawców</span><span class="sxs-lookup"><span data-stu-id="d40f5-159">Onboard vendors</span></span>](vendor-onboarding.md)
