---
title: "Utwórz przepływ pracy"
description: "W tym temacie wyjaśniono, jak utworzyć przepływ pracy."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, UnifiedOperations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4d57e47fe7f38a43ecfdfbdd701d7e6a7d7800d6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-workflow"></a><span data-ttu-id="2185a-103">Utwórz przepływ pracy</span><span class="sxs-lookup"><span data-stu-id="2185a-103">Create a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2185a-104">W tym temacie wyjaśniono, jak utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-104">This topics explains how to create a workflow.</span></span>

<a name="open-the-workflow-editor"></a><span data-ttu-id="2185a-105">Otwórz edytor przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2185a-105">Open the workflow editor</span></span>
------------------------

<span data-ttu-id="2185a-106">Moduł programu Microsoft Dynamics 365 for Finance and Operations, w którym pracujesz, określa typy przepływów pracy, jakie można tworzyć.</span><span class="sxs-lookup"><span data-stu-id="2185a-106">The Microsoft Dynamics 365 for Finance and Operations module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="2185a-107">Wykonaj następujące kroki, aby wybrać typ tworzonego przepływu pracy i otworzyć edytora przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1.  <span data-ttu-id="2185a-108">Otwórz moduł, dla którego chcesz utworzyć nowy przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="2185a-109">Aby na przykład utworzyć przepływ pracy dla zapotrzebowań na zakup, kliknij opcję **Zaopatrzenie i sourcing**.</span><span class="sxs-lookup"><span data-stu-id="2185a-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2.  <span data-ttu-id="2185a-110">Kliknij kolejno opcje **Ustawienia** &gt; **Przepływy pracy modułu \[nazwa modułu\]**.</span><span class="sxs-lookup"><span data-stu-id="2185a-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3.  <span data-ttu-id="2185a-111">Na wyświetlonej stronie listy w okienku akcji kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2185a-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4.  <span data-ttu-id="2185a-112">Na stronie **Utwórz przepływ pracy** wybierz typ przepływu pracy, który ma zostać utworzony, i kliknij przycisk **Utwórz przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="2185a-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="2185a-113">Zostanie wyświetlony edytor przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-113">The workflow editor appears.</span></span> <span data-ttu-id="2185a-114">Teraz można użyć poniższych procedur w celu zaprojektowania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="2185a-115">Przeciągnij elementy przepływu pracy na kanwę</span><span class="sxs-lookup"><span data-stu-id="2185a-115">Drag workflow elements onto the canvas</span></span>
<span data-ttu-id="2185a-116">Obszar **Elementy przepływu pracy** w edytorze przepływu pracy zawiera elementy, które można dodawać do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="2185a-117">Aby dodać elementy do przepływu pracy, przeciągnij na kanwę.</span><span class="sxs-lookup"><span data-stu-id="2185a-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="2185a-118">Połącz elementy</span><span class="sxs-lookup"><span data-stu-id="2185a-118">Connect the elements</span></span>
<span data-ttu-id="2185a-119">Aby połączyć jeden element przepływu pracy z innym, przytrzymaj wskaźnik nad elementem, aż punkty połączeń zostaną wyświetlone.</span><span class="sxs-lookup"><span data-stu-id="2185a-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="2185a-120">Kliknij punkt połączenia i przeciągnij go do innego elementu.</span><span class="sxs-lookup"><span data-stu-id="2185a-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="2185a-121">Należy pamiętać, aby łączyć wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="2185a-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="2185a-122">Konfigurowanie właściwości przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2185a-122">Configure the properties of the workflow</span></span>
<span data-ttu-id="2185a-123">Wykonaj poniższe czynności, aby skonfigurować właściwości przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-123">Follow these steps to configure the properties of the workflow.</span></span>

1.  <span data-ttu-id="2185a-124">Kliknij kanwę, aby upewnić się, że nie został wybrany żaden element przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2.  <span data-ttu-id="2185a-125">Kliknij przycisk **Właściwości**. a zostanie otwarta strona **Właściwości** dotycząca przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3.  <span data-ttu-id="2185a-126">Wykonaj procedury opisane w temacie [Konfigurowanie właściwości przepływu pracy](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2185a-126">Follow the procedures in the [Configure the properties of a workflow](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="2185a-127">Konfigurowanie elementów przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2185a-127">Configure the elements of the workflow</span></span>
<span data-ttu-id="2185a-128">Skonfiguruj każdy element przeciągnięty na kanwę.</span><span class="sxs-lookup"><span data-stu-id="2185a-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="2185a-129">Aby uzyskać więcej informacji dotyczących sposobu konfigurowania każdego elementu przepływu pracy, zobacz następujące tematy.</span><span class="sxs-lookup"><span data-stu-id="2185a-129">For information about how to configure each workflow element, see the following topics:</span></span>

-   [<span data-ttu-id="2185a-130">Konfigurowanie zadania ręcznego</span><span class="sxs-lookup"><span data-stu-id="2185a-130">Configure a manual task</span></span>](configure-manual-task-workflow.md)
-   [<span data-ttu-id="2185a-131">Konfigurowanie zadania wykonywanego automatycznie</span><span class="sxs-lookup"><span data-stu-id="2185a-131">Configure an automated task</span></span>](configure-automated-task-workflow.md)
-   [<span data-ttu-id="2185a-132">Konfigurowanie procesu zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="2185a-132">Configure an approval process</span></span>](configure-approval-process-workflow.md)
-   [<span data-ttu-id="2185a-133">Konfigurowanie kroku zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="2185a-133">Configure an approval step</span></span>](configure-approval-step-workflow.md)
-   [<span data-ttu-id="2185a-134">Konfigurowanie decyzji ręcznej</span><span class="sxs-lookup"><span data-stu-id="2185a-134">Configure a manual decision</span></span>](configure-manual-decision-workflow.md)
-   [<span data-ttu-id="2185a-135">Konfigurowanie decyzji warunkowej</span><span class="sxs-lookup"><span data-stu-id="2185a-135">Configure a conditional decision</span></span>](configure-conditional-decision-workflow.md)
-   [<span data-ttu-id="2185a-136">Konfigurowanie działania równoległego</span><span class="sxs-lookup"><span data-stu-id="2185a-136">Configure a parallel activity</span></span>](configure-parallel-activity-workflow.md)
-   [<span data-ttu-id="2185a-137">Konfigurowanie odgałęzienia równoległego</span><span class="sxs-lookup"><span data-stu-id="2185a-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
-   [<span data-ttu-id="2185a-138">Konfigurowanie przepływu pracy dla pozycji w wierszu</span><span class="sxs-lookup"><span data-stu-id="2185a-138">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="2185a-139">Rozwiąż wszelkie błędy lub ostrzeżenia</span><span class="sxs-lookup"><span data-stu-id="2185a-139">Resolve any errors or warnings</span></span>
<span data-ttu-id="2185a-140">Okienko **Błędy i ostrzeżenia** w dolnej części edytora przepływu pracy pokazuje komunikaty, które zostały wygenerowane dla przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="2185a-141">Aby znaleźć element, w którym wystąpił błąd lub ostrzeżenie, kliknij dwukrotnie błąd lub ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="2185a-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="2185a-142">Wszystkie błędy i ostrzeżenia muszą zostać rozwiązane przed uaktywnieniem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2185a-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="2185a-143">Zapisywanie i aktywowanie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2185a-143">Save and activate the workflow</span></span>
<span data-ttu-id="2185a-144">Gdy wszystko jest gotowe do zapisania i aktywacji przepływu pracy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2185a-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="2185a-145">Kliknij przycisk **Zapisz i zamknij**, aby zamknąć edytor i otworzyć stronę **Zapisz przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="2185a-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2.  <span data-ttu-id="2185a-146">Wprowadź komentarze dotyczące zmian wprowadzonych w przepływie pracy i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2185a-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3.  <span data-ttu-id="2185a-147">Jeśli wszystkie błędy i ostrzeżenia zostały rozwiązane, zostanie wyświetlona strona **Aktywacja przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="2185a-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="2185a-148">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="2185a-148">Select one of the following options:</span></span>
    -   <span data-ttu-id="2185a-149">Aby uaktywnić tę wersję przepływu pracy, kliknij przycisk **Uruchom nową wersję**.</span><span class="sxs-lookup"><span data-stu-id="2185a-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="2185a-150">Gdy przepływ pracy jest aktywny, użytkownicy mogą przesyłać do niego dokumenty w celu przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="2185a-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    -   <span data-ttu-id="2185a-151">Jeśli nie chcesz uaktywnić tej wersję, kliknij przycisk **Nie aktywuj nowej wersji**.</span><span class="sxs-lookup"><span data-stu-id="2185a-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="2185a-152">Możesz aktywować przepływ pracy później.</span><span class="sxs-lookup"><span data-stu-id="2185a-152">You can activate the workflow later.</span></span>






