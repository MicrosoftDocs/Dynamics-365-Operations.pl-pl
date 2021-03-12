---
title: Omówienie tworzenia przepływów pracy
description: W tym temacie wyjaśniono, jak utworzyć przepływ pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: d1402019dbaaa60827499fcb6b93ee31440cfc3d
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797659"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="fdf4e-103">Omówienie tworzenia przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdf4e-104">W tym temacie wyjaśniono, jak utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="fdf4e-105">Otwórz edytor przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-105">Open the workflow editor</span></span>

<span data-ttu-id="fdf4e-106">Moduł, w którym pracujesz, określa typy przepływu pracy, które możesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="fdf4e-107">Wykonaj następujące kroki, aby wybrać typ tworzonego przepływu pracy i otworzyć edytora przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="fdf4e-108">Otwórz moduł, dla którego chcesz utworzyć nowy przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="fdf4e-109">Aby na przykład utworzyć przepływ pracy dla zapotrzebowań na zakup, kliknij opcję **Zaopatrzenie i sourcing**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="fdf4e-110">Kliknij kolejno opcje **Ustawienia** &gt; **Przepływy pracy modułu \[nazwa modułu\]**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="fdf4e-111">Na wyświetlonej stronie listy w okienku akcji kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="fdf4e-112">Na stronie **Utwórz przepływ pracy** wybierz typ przepływu pracy, który ma zostać utworzony, i kliknij przycisk **Utwórz przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="fdf4e-113">Zostanie wyświetlony edytor przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-113">The workflow editor appears.</span></span> <span data-ttu-id="fdf4e-114">Teraz można użyć poniższych procedur w celu zaprojektowania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="fdf4e-115">Przeciągnij elementy przepływu pracy na kanwę</span><span class="sxs-lookup"><span data-stu-id="fdf4e-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="fdf4e-116">Obszar **Elementy przepływu pracy** w edytorze przepływu pracy zawiera elementy, które można dodawać do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="fdf4e-117">Aby dodać elementy do przepływu pracy, przeciągnij na kanwę.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="fdf4e-118">Połącz elementy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-118">Connect the elements</span></span>

<span data-ttu-id="fdf4e-119">Aby połączyć jeden element przepływu pracy z innym, przytrzymaj wskaźnik nad elementem, aż punkty połączeń zostaną wyświetlone.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="fdf4e-120">Kliknij punkt połączenia i przeciągnij go do innego elementu.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="fdf4e-121">Należy pamiętać, aby łączyć wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="fdf4e-122">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="fdf4e-123">Wykonaj poniższe czynności, aby skonfigurować właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="fdf4e-124">Kliknij kanwę, aby upewnić się, że nie został wybrany żaden element przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="fdf4e-125">Kliknij przycisk **Właściwości**. a zostanie otwarta strona **Właściwości** dotycząca przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="fdf4e-126">Wykonaj procedury opisane w temacie [Konfigurowanie właściwości przepływu pracy](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fdf4e-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="fdf4e-127">Konfigurowanie elementów przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="fdf4e-128">Skonfiguruj każdy element przeciągnięty na kanwę.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="fdf4e-129">Aby uzyskać więcej informacji dotyczących sposobu konfigurowania każdego elementu przepływu pracy, zobacz następujące tematy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="fdf4e-130">Konfigurowanie zadań ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="fdf4e-131">Konfigurowanie zadań wykonywanych automatycznie w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="fdf4e-132">Konfigurowanie procesów zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="fdf4e-133">Konfigurowanie kroków zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="fdf4e-134">Konfigurowanie decyzji ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="fdf4e-135">Konfigurowanie decyzji warunkowych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="fdf4e-136">Konfigurowanie odgałęzień równoległych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="fdf4e-137">Konfigurowanie odgałęzienia równoległego</span><span class="sxs-lookup"><span data-stu-id="fdf4e-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="fdf4e-138">Konfigurowanie przepływów pracy dla pozycji w wierszach</span><span class="sxs-lookup"><span data-stu-id="fdf4e-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="fdf4e-139">Rozwiąż wszelkie błędy lub ostrzeżenia</span><span class="sxs-lookup"><span data-stu-id="fdf4e-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="fdf4e-140">Okienko **Błędy i ostrzeżenia** w dolnej części edytora przepływu pracy pokazuje komunikaty, które zostały wygenerowane dla przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="fdf4e-141">Aby znaleźć element, w którym wystąpił błąd lub ostrzeżenie, kliknij dwukrotnie błąd lub ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="fdf4e-142">Wszystkie błędy i ostrzeżenia muszą zostać rozwiązane przed uaktywnieniem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="fdf4e-143">Zapisywanie i aktywowanie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="fdf4e-143">Save and activate the workflow</span></span>

<span data-ttu-id="fdf4e-144">Gdy wszystko jest gotowe do zapisania i aktywacji przepływu pracy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="fdf4e-145">Kliknij przycisk **Zapisz i zamknij**, aby zamknąć edytor i otworzyć stronę **Zapisz przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="fdf4e-146">Wprowadź komentarze dotyczące zmian wprowadzonych w przepływie pracy i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="fdf4e-147">Jeśli wszystkie błędy i ostrzeżenia zostały rozwiązane, zostanie wyświetlona strona **Aktywacja przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="fdf4e-148">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="fdf4e-148">Select one of the following options:</span></span>

    - <span data-ttu-id="fdf4e-149">Aby uaktywnić tę wersję przepływu pracy, kliknij przycisk **Uruchom nową wersję**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="fdf4e-150">Gdy przepływ pracy jest aktywny, użytkownicy mogą przesyłać do niego dokumenty w celu przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="fdf4e-151">Jeśli nie chcesz uaktywnić tej wersję, kliknij przycisk **Nie aktywuj nowej wersji**.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="fdf4e-152">Możesz aktywować przepływ pracy później.</span><span class="sxs-lookup"><span data-stu-id="fdf4e-152">You can activate the workflow later.</span></span>
