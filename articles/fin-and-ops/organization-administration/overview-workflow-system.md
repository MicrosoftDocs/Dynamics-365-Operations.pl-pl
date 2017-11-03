---
title: "Omówienie przepływu pracy"
description: "W tym temacie opisano system przepływów pracy dostępny w programie Microsoft Dynamics 365 for Finance and Operations."
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f4e2167290618aaf6ad144e7db8274514078388b
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="workflow-overview"></a><span data-ttu-id="aad42-103">Omówienie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-103">Workflow overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="aad42-104">W tym temacie opisano system przepływów pracy dostępny w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aad42-104">This topic describes the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="what-is-workflow"></a><span data-ttu-id="aad42-105">Co to jest przepływ pracy?</span><span class="sxs-lookup"><span data-stu-id="aad42-105">What is workflow?</span></span>
-----------------

<span data-ttu-id="aad42-106">Termin *przepływ pracy* można definiować na dwa sposoby: jako system i jako proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="aad42-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>
### <a name="workflow-is-a-system"></a><span data-ttu-id="aad42-107">Przepływ pracy jest systemem</span><span class="sxs-lookup"><span data-stu-id="aad42-107">Workflow is a system</span></span>

<span data-ttu-id="aad42-108">Przepływ pracy to system instalowany razem z programem Finance and Operations i uruchamiany na serwerze obiektów aplikacji (AOS).</span><span class="sxs-lookup"><span data-stu-id="aad42-108">Workflow is a system that is installed with Finance and Operations and runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="aad42-109">System przepływu pracy zawiera funkcjonalność, której można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="aad42-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="aad42-110">Przepływ pracy jest procesem biznesowym</span><span class="sxs-lookup"><span data-stu-id="aad42-110">Workflow is a business process</span></span>

<span data-ttu-id="aad42-111">Przepływ pracy reprezentuje proces biznesowy.</span><span class="sxs-lookup"><span data-stu-id="aad42-111">A workflow represents a business process.</span></span> <span data-ttu-id="aad42-112">Definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="aad42-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="aad42-113">Na przykład poniższa ilustracja pokazuje przepływ pracy dla raportów z wydatków.</span><span class="sxs-lookup"><span data-stu-id="aad42-113">For example, the following illustration shows a workflow for expense reports.</span></span> 

![Przepływ pracy z elementami przypisanymi do użytkowników](./media/workflow_user.gif) 

<span data-ttu-id="aad42-115">Aby lepiej zrozumieć ten przepływ pracy, załóżmy, że Sam przesyła raport z wydatków na 7000 USD.</span><span class="sxs-lookup"><span data-stu-id="aad42-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="aad42-116">W tym scenariuszu Ivan musi przejrzeć pokwitowania wysłane przez Tomasza.</span><span class="sxs-lookup"><span data-stu-id="aad42-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="aad42-117">Następnie Wojciech i Magda muszą zatwierdzić raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="aad42-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="aad42-118">Teraz załóżmy, że Tomasz przesyła raport z wydatków na kwotę 11 000 USD.</span><span class="sxs-lookup"><span data-stu-id="aad42-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="aad42-119">W tym scenariuszu Maciej musi przejrzeć pokwitowania, a Wojciech, Magda i Anna muszą zatwierdzić raport z wydatków.</span><span class="sxs-lookup"><span data-stu-id="aad42-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="aad42-120"> Zalety używania systemu przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="aad42-121">Używanie systemu przepływu pracy w organizacji ma kilka zalet:</span><span class="sxs-lookup"><span data-stu-id="aad42-121">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="aad42-122">**Spójność procesów** — Możesz zdefiniować sposób przetwarzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków.</span><span class="sxs-lookup"><span data-stu-id="aad42-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="aad42-123">System przepływu pracy zapewnia, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.</span><span class="sxs-lookup"><span data-stu-id="aad42-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="aad42-124">**Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="aad42-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="aad42-125">Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.</span><span class="sxs-lookup"><span data-stu-id="aad42-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="aad42-126">**Scentralizowana lista prac** — użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="aad42-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="aad42-127">Zawartość przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-127">Workflow content</span></span>

+ [<span data-ttu-id="aad42-128">Architektura przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="aad42-129">Elementy przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="aad42-130">Akcje przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="aad42-131">Tworzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="aad42-132">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="aad42-133">Konfigurowanie zadania ręcznego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="aad42-134">Konfigurowanie zadania wykonywanego automatycznie w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="aad42-135">Konfigurowanie procesu zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="aad42-136">Konfigurowanie etapu zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="aad42-137">Konfigurowanie ręcznej decyzji w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="aad42-138">Konfigurowanie decyzji warunkowej w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="aad42-139">Konfigurowanie działania równoległego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="aad42-140">Konfigurowanie odgałęzienia równoległego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="aad42-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="aad42-141">Konfigurowanie przepływu pracy dla pozycji w wierszu</span><span class="sxs-lookup"><span data-stu-id="aad42-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

