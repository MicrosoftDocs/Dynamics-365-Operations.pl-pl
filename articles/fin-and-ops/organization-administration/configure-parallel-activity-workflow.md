---
title: "Konfigurowanie działania równoległego w przepływie pracy"
description: "Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ec1c1d8abc49deb8ef16322370c59d40b01d344c
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="configure-a-parallel-activity-in-a-workflow"></a><span data-ttu-id="90d4b-103">Konfigurowanie działania równoległego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="90d4b-103">Configure a parallel activity in a workflow</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="90d4b-104">Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="90d4b-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="90d4b-105">Działanie równoległe składa się z odgałęzień przepływu pracy, które są uruchomione w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="90d4b-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="90d4b-106">Nazywanie działania równoległego</span><span class="sxs-lookup"><span data-stu-id="90d4b-106">Name a parallel activity</span></span>
<span data-ttu-id="90d4b-107">Wykonaj następujące kroki, aby nazwać działanie równoległe.</span><span class="sxs-lookup"><span data-stu-id="90d4b-107">Follow these steps to enter a name for a parallel activity.</span></span>
1.  <span data-ttu-id="90d4b-108">Kliknij działanie równoległe prawym przyciskiem myszy i wybierz polecenie **Właściwości**, aby otworzyć formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="90d4b-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2.  <span data-ttu-id="90d4b-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="90d4b-109">In the left pane, click **Basic Settings**.</span></span>
3.  <span data-ttu-id="90d4b-110">W polu **Nazwa** wprowadź unikatową nazwę działania równoległego.</span><span class="sxs-lookup"><span data-stu-id="90d4b-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4.  <span data-ttu-id="90d4b-111">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="90d4b-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="90d4b-112">Konfigurowanie odgałęzień działania równoległego</span><span class="sxs-lookup"><span data-stu-id="90d4b-112">Configure the branches of a parallel activity</span></span>
<span data-ttu-id="90d4b-113">Wykonaj następujące kroki, aby dodać i skonfigurować gałęzie działania równoległego.</span><span class="sxs-lookup"><span data-stu-id="90d4b-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>
1. <span data-ttu-id="90d4b-114">Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.</span><span class="sxs-lookup"><span data-stu-id="90d4b-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="90d4b-115">Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie.</span><span class="sxs-lookup"><span data-stu-id="90d4b-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="90d4b-116">Na poniższej ilustracji przedstawiono punkt wstawiania.![Punkt wstawiania](./media/workflow_insertionpoint.gif)</span><span class="sxs-lookup"><span data-stu-id="90d4b-116">The following figure shows an insertion point.![Insertion point](./media/workflow_insertionpoint.gif)</span></span>

   |                                              <span data-ttu-id="90d4b-117"><strong>Uwaga</strong></span><span class="sxs-lookup"><span data-stu-id="90d4b-117"><strong>Note</strong></span></span>                                               |
   |------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="90d4b-118">Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="90d4b-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span> |


3. <span data-ttu-id="90d4b-119">Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzienia równoległego](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="90d4b-119">To configure each branch, see [Configure a parallel branch](configure-parallel-branch-workflow.md).</span></span>






