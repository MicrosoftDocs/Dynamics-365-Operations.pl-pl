---
title: Omówienie systemu przepływów pracy
description: W tym temacie opisano system przepływów pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd8fba1376dc5e3dbfea888ca5ff5fdeb608fc9d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560708"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="6ea0e-103">Omówienie systemu przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ea0e-104">W tym temacie opisano system przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="6ea0e-105">Co to jest przepływ pracy?</span><span class="sxs-lookup"><span data-stu-id="6ea0e-105">What is workflow?</span></span>

<span data-ttu-id="6ea0e-106">Termin *przepływ pracy* można definiować na dwa sposoby: jako system i jako proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="6ea0e-107">Przepływ pracy jest systemem</span><span class="sxs-lookup"><span data-stu-id="6ea0e-107">Workflow is a system</span></span>

<span data-ttu-id="6ea0e-108">Przepływ pracy to system uruchomiony na serwerze obiektów aplikacji (AOS).</span><span class="sxs-lookup"><span data-stu-id="6ea0e-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="6ea0e-109">System przepływu pracy zawiera funkcjonalność, której można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="6ea0e-110">Przepływ pracy jest procesem biznesowym</span><span class="sxs-lookup"><span data-stu-id="6ea0e-110">Workflow is a business process</span></span>

<span data-ttu-id="6ea0e-111">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-111">A workflow represents a business process.</span></span> <span data-ttu-id="6ea0e-112">Definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="6ea0e-113">Na przykład poniższa ilustracja pokazuje przepływ pracy dla raportów z wydatków.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Przepływ pracy z elementami przypisanymi do użytkowników](./media/workflow_user.gif)

<span data-ttu-id="6ea0e-115">Aby lepiej zrozumieć ten przepływ pracy, załóżmy, że Sam przesyła raport z wydatków na 7000 USD.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="6ea0e-116">W tym scenariuszu Ivan musi przejrzeć pokwitowania wysłane przez Tomasza.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="6ea0e-117">Następnie Wojciech i Magda muszą zatwierdzić raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="6ea0e-118">Teraz załóżmy, że Tomasz przesyła raport z wydatków na kwotę 11 000 USD.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="6ea0e-119">W tym scenariuszu Maciej musi przejrzeć pokwitowania, a Wojciech, Magda i Anna muszą zatwierdzić raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="6ea0e-120"> Zalety używania systemu przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="6ea0e-121">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="6ea0e-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="6ea0e-122">**Spójność procesów** — Możesz zdefiniować sposób przetwarzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="6ea0e-123">System przepływu pracy zapewnia, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="6ea0e-124">**Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="6ea0e-125">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="6ea0e-126">**Scentralizowana lista prac** — użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="6ea0e-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="6ea0e-127">Zawartość przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-127">Workflow content</span></span>

+ [<span data-ttu-id="6ea0e-128">Architektura systemu przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="6ea0e-129">Elementy przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="6ea0e-130">Akcje w procesach zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="6ea0e-131">Omówienie tworzenia przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="6ea0e-132">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="6ea0e-133">Konfigurowanie zadań ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="6ea0e-134">Konfigurowanie zadań wykonywanych automatycznie w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="6ea0e-135">Konfigurowanie procesów zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="6ea0e-136">Konfigurowanie kroków zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="6ea0e-137">Konfigurowanie decyzji ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="6ea0e-138">Konfigurowanie decyzji warunkowych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="6ea0e-139">Konfigurowanie działań równoległych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="6ea0e-140">Konfigurowanie odgałęzień równoległych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="6ea0e-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="6ea0e-141">Konfigurowanie przepływów pracy dla pozycji w wierszach</span><span class="sxs-lookup"><span data-stu-id="6ea0e-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="6ea0e-142">Przepływ pracy — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="6ea0e-142">Workflow FAQ</span></span>](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]