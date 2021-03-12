---
title: Konfigurowanie działań równoległych w przepływie pracy
description: Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dfbe78f31082ad0b1272f02e3ae9d7adbd993b1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797733"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="9b270-103">Konfigurowanie działań równoległych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="9b270-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b270-104">Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="9b270-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="9b270-105">Działanie równoległe składa się z odgałęzień przepływu pracy, które są uruchomione w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="9b270-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="9b270-106">Nazywanie działania równoległego</span><span class="sxs-lookup"><span data-stu-id="9b270-106">Name a parallel activity</span></span>

<span data-ttu-id="9b270-107">Wykonaj następujące kroki, aby nazwać działanie równoległe.</span><span class="sxs-lookup"><span data-stu-id="9b270-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="9b270-108">Kliknij działanie równoległe prawym przyciskiem myszy i wybierz polecenie **Właściwości**, aby otworzyć formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="9b270-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="9b270-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="9b270-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="9b270-110">W polu **Nazwa** wprowadź unikatową nazwę działania równoległego.</span><span class="sxs-lookup"><span data-stu-id="9b270-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="9b270-111">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="9b270-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="9b270-112">Konfigurowanie odgałęzień działania równoległego</span><span class="sxs-lookup"><span data-stu-id="9b270-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="9b270-113">Wykonaj następujące kroki, aby dodać i skonfigurować gałęzie działania równoległego.</span><span class="sxs-lookup"><span data-stu-id="9b270-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="9b270-114">Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.</span><span class="sxs-lookup"><span data-stu-id="9b270-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="9b270-115">Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie.</span><span class="sxs-lookup"><span data-stu-id="9b270-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="9b270-116">Na poniższej ilustracji przedstawiono punkt wstawiania.</span><span class="sxs-lookup"><span data-stu-id="9b270-116">The following figure shows an insertion point.</span></span>

    ![Punkt wstawiania](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="9b270-118">Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="9b270-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="9b270-119">Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzień równoległych w przepływie pracy](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9b270-119">To configure each branch, see [Configure parallel branches in a workflow](configure-parallel-branch-workflow.md).</span></span>
