---
title: "Konfigurowanie odgałęzienia równoległego w przepływie pracy"
description: "Aby skonfigurować gałąź równoległą, należy wykonać następujące procedury w edytorze przepływu pracy."
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
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d0e45f4a6b1f6bcf94103dbcf4a8ca01457dc85d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="configure-a-parallel-branch-in-a-workflow"></a><span data-ttu-id="5e247-103">Konfigurowanie odgałęzienia równoległego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="5e247-103">Configure a parallel branch in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e247-104">Aby skonfigurować gałąź równoległą, należy wykonać następujące procedury w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5e247-104">To configure a parallel branch, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="5e247-105">Gałąź równoległa to zasadniczo przepływ pracy, który jest wykonywany w kontekście nadrzędnego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5e247-105">A parallel branch is essentially a workflow that runs in the context of a parent workflow.</span></span>

## <a name="name-a-branch"></a><span data-ttu-id="5e247-106">Nazywanie gałęzi</span><span class="sxs-lookup"><span data-stu-id="5e247-106">Name a branch</span></span>
<span data-ttu-id="5e247-107">Wykonaj następujące kroki, aby nazwać odgałęzienie równoległe.</span><span class="sxs-lookup"><span data-stu-id="5e247-107">Follow these steps to enter a name for a parallel branch.</span></span>
1.  <span data-ttu-id="5e247-108">Kliknij prawym przyciskiem gałąź równoległą i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="5e247-108">Right-click the parallel branch, and then click **Properties**.</span></span> <span data-ttu-id="5e247-109">Zostanie wyświetlony formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="5e247-109">The **Properties** form is displayed.</span></span>
2.  <span data-ttu-id="5e247-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="5e247-110">In the left pane, click **Basic Settings**.</span></span>
3.  <span data-ttu-id="5e247-111">W polu **Nazwa** wprowadź unikatową nazwę gałęzi równoległej.</span><span class="sxs-lookup"><span data-stu-id="5e247-111">In the **Name** field, enter a unique name for the parallel branch.</span></span>
4.  <span data-ttu-id="5e247-112">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="5e247-112">Click **Close**.</span></span>

## <a name="design-and-configure-the-elements-of-a-branch"></a><span data-ttu-id="5e247-113">Projektowanie i konfigurowanie elementów gałęzi</span><span class="sxs-lookup"><span data-stu-id="5e247-113">Design and configure the elements of a branch</span></span>
<span data-ttu-id="5e247-114">Wykonaj następujące kroki, aby zaprojektować i skonfigurować elementy odgałęzienia równoległego.</span><span class="sxs-lookup"><span data-stu-id="5e247-114">Follow these steps to design and configure the elements of a parallel branch.</span></span>
1.  <span data-ttu-id="5e247-115">Kliknij dwukrotnie gałąź równoległą.</span><span class="sxs-lookup"><span data-stu-id="5e247-115">Double-click the parallel branch.</span></span>
2.  <span data-ttu-id="5e247-116">Przeciągnij elementy przepływu pracy na kanwę, a następnie je skonfiguruj, tak samo jak przy tworzeniu jakiegokolwiek innego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5e247-116">Drag workflow elements onto the canvas, and then configure the elements, just as you would to create any other workflow.</span></span> <span data-ttu-id="5e247-117">Aby uzyskać więcej informacji, zobacz temat Tworzenie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5e247-117">For more information, see Create a workflow.</span></span>



<a name="additional-resources"></a><span data-ttu-id="5e247-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5e247-118">Additional resources</span></span>
--------

[<span data-ttu-id="5e247-119">Tworzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="5e247-119">Create a workflow</span></span>](create-workflow.md)




