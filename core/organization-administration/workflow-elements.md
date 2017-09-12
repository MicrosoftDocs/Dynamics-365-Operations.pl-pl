---
title: "Elementy przepływu pracy"
description: "Ten artykuł zawiera opis różnych elementów składających się na przepływ pracy."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 5620a91ff9f300bed782170307a295ab79fc5b2e
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="10c66-103">Elementy przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="10c66-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="10c66-104">Ten artykuł zawiera opis różnych elementów składających się na przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="10c66-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="10c66-105">Przepływ pracy składa się z elementów.</span><span class="sxs-lookup"><span data-stu-id="10c66-105">A workflow consists of elements.</span></span> <span data-ttu-id="10c66-106">Sekcje poniżej opisują poszczególne typy elementów.</span><span class="sxs-lookup"><span data-stu-id="10c66-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="10c66-107">Zadania</span><span class="sxs-lookup"><span data-stu-id="10c66-107">Tasks</span></span>
<span data-ttu-id="10c66-108">*Zadanie* jest jednostką pracy, która musi zostać wykonana.</span><span class="sxs-lookup"><span data-stu-id="10c66-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="10c66-109">Do przepływu pracy można dodawać dwa typy zadań: zadania ręczne i zadania automatyczne.</span><span class="sxs-lookup"><span data-stu-id="10c66-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="10c66-110">Zadanie wykonywane ręcznie</span><span class="sxs-lookup"><span data-stu-id="10c66-110">Manual task</span></span>

<span data-ttu-id="10c66-111">*Zadanie ręczne* jest jednostką pracy, która musi zostać wykonana przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="10c66-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="10c66-112">Na przykład przepływu pracy raportu z wydatków może mieć ręczne zadania, które wymagają, by przypisani użytkownicy wykonali następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="10c66-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="10c66-113">przejrzeć przyjęcia, które są przesyłane wraz z raportem z wydatków;</span><span class="sxs-lookup"><span data-stu-id="10c66-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="10c66-114">wezwać przełożonego pracownika.</span><span class="sxs-lookup"><span data-stu-id="10c66-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="10c66-115">Zadanie wykonywane automatycznie</span><span class="sxs-lookup"><span data-stu-id="10c66-115">Automated task</span></span>

<span data-ttu-id="10c66-116">*Zadanie automatyczne* jest jednostką pracy, która musi zostać wykonana przez system.</span><span class="sxs-lookup"><span data-stu-id="10c66-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="10c66-117">Nie są wymagane żadne czynności wykonywane przez człowieka.</span><span class="sxs-lookup"><span data-stu-id="10c66-117">No human interaction is required.</span></span> <span data-ttu-id="10c66-118">Na przykład przepływ pracy zamówienia sprzedaży może mieć zadania automatyczne, które wymagają, aby system wykonał następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="10c66-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="10c66-119">sprawdzić kartę kredytową;</span><span class="sxs-lookup"><span data-stu-id="10c66-119">Perform a credit check.</span></span>
-   <span data-ttu-id="10c66-120">utworzyć rekord odbiorcy dla odbiorcy, jeśli rekord jeszcze nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="10c66-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="10c66-121">Procesy zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="10c66-121">Approval processes</span></span>
<span data-ttu-id="10c66-122">*Proces zatwierdzania* składa się z oddzielnych kroków.</span><span class="sxs-lookup"><span data-stu-id="10c66-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="10c66-123">Na każdym kroku użytkownik może wykonać następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="10c66-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="10c66-124">zatwierdzić dokument;</span><span class="sxs-lookup"><span data-stu-id="10c66-124">Approve the document.</span></span>
-   <span data-ttu-id="10c66-125">odrzucić dokument;</span><span class="sxs-lookup"><span data-stu-id="10c66-125">Reject the document.</span></span>
-   <span data-ttu-id="10c66-126">zażądać wprowadzenia zmian w dokumencie;</span><span class="sxs-lookup"><span data-stu-id="10c66-126">Request a change to the document.</span></span>
-   <span data-ttu-id="10c66-127">przypisać dokument innemu użytkownikowi w celu zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="10c66-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="10c66-128">Elementy przepływu pracy dla wiersza</span><span class="sxs-lookup"><span data-stu-id="10c66-128">Lineitem workflow elements</span></span>
<span data-ttu-id="10c66-129">Przepływ pracy można tworzyć w celu przetwarzania dokumentów lub pozycji w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="10c66-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="10c66-130">Na przykład utworzono przepływ pracy zatwierdzania dla kart czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="10c66-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="10c66-131">(Nazwiemy go *przepływem pracy dokumentu*). Do tego przepływu pracy dokumentu można dodać element *przepływu pracy dla wiersza*.</span><span class="sxs-lookup"><span data-stu-id="10c66-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="10c66-132">Po uruchomieniu tego element wszystkie pozycje wiersza w dokumencie są przesyłane do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="10c66-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="10c66-133">Czasami wszystkie elementy wiersza muszą być przetworzone przez ten sam przepływ pracy lub każdy element musi być przetwarzany przez różne przepływy pracy dla wierszy.</span><span class="sxs-lookup"><span data-stu-id="10c66-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="10c66-134">Załóżmy, że pracownik przesłał kartę czasu pracy podobną do tej na obrazku poniżej.</span><span class="sxs-lookup"><span data-stu-id="10c66-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span> <span data-ttu-id="10c66-135">![Przepływ pracy z pozycjami wiersza](./media/workflow_lineitemworkflow.gif) W tym scenariuszu może być konieczne utworzenie następujących przepływów pracy dla wiersza:</span><span class="sxs-lookup"><span data-stu-id="10c66-135">![Workflow with line items](./media/workflow_lineitemworkflow.gif) In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="10c66-136">**Przepływ pracy utworzony dla pozycji w wierszu 1** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 1111.</span><span class="sxs-lookup"><span data-stu-id="10c66-136">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="10c66-137">**Przepływ pracy utworzony dla pozycji w wierszu 2** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 2222.</span><span class="sxs-lookup"><span data-stu-id="10c66-137">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="10c66-138">**Przepływ pracy utworzony dla pozycji w wierszu 3** — ten przepływ pracy jest używany do przetwarzania pozycji w wierszu z identyfikatorem projektu 3333.</span><span class="sxs-lookup"><span data-stu-id="10c66-138">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="10c66-139">Elementy kontroli przepływu</span><span class="sxs-lookup"><span data-stu-id="10c66-139">Flowcontrol elements</span></span>
<span data-ttu-id="10c66-140">Poniższe elementy pozwalają projektować przepływy pracy z alternatywnymi oddziałami lub oddziałami działającymi jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="10c66-140">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="10c66-141">Decyzja ręczna</span><span class="sxs-lookup"><span data-stu-id="10c66-141">Manual decision</span></span>

<span data-ttu-id="10c66-142">*Ręczna decyzja* to punkt, w którym przepływ pracy rozdziela się na dwie gałęzie.</span><span class="sxs-lookup"><span data-stu-id="10c66-142">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="10c66-143">Użytkownik musi podjąć decyzję, która wskazuje odział używany do przetwarzania przesłanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="10c66-143">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="10c66-144">Decyzja warunkowa</span><span class="sxs-lookup"><span data-stu-id="10c66-144">Conditional decision</span></span>

<span data-ttu-id="10c66-145">*Decyzja warunkowa* to również punkt, w którym przepływ pracy rozdziela się na dwie gałęzie.</span><span class="sxs-lookup"><span data-stu-id="10c66-145">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="10c66-146">Jednak w tym przypadku to system decyduje, który oddział użyty do przetwarzania przesłanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="10c66-146">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="10c66-147">Aby podjąć tę decyzję system ocenia dokument, aby ocenić, czy spełnia on określone warunki.</span><span class="sxs-lookup"><span data-stu-id="10c66-147">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="10c66-148">Działanie równoległe</span><span class="sxs-lookup"><span data-stu-id="10c66-148">Parallel activity</span></span>

<span data-ttu-id="10c66-149">*Działanie równoległe* to element przepływu pracy, który zawiera dwie lub więcej gałęzi przepływu pracy, które są wykonywane w tym samym czasie</span><span class="sxs-lookup"><span data-stu-id="10c66-149">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="10c66-150">Podrzędny przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="10c66-150">Subworkflow</span></span>

<span data-ttu-id="10c66-151">*Podrzędny przepływ pracy* jest przepływem pracy, który działa w kontekście innego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="10c66-151">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




