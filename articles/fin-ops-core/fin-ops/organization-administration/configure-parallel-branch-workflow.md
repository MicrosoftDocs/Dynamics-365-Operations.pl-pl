---
title: Konfigurowanie odgałęzień równoległych w przepływie pracy
description: Aby skonfigurować gałąź równoległą, należy wykonać następujące procedury w edytorze przepływu pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37c177e8c4c4e40bd81287430d9ee7598cf917d8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566998"
---
# <a name="configure-parallel-branches-in-a-workflow"></a><span data-ttu-id="648fb-103">Konfigurowanie odgałęzień równoległych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="648fb-103">Configure parallel branches in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="648fb-104">Aby skonfigurować gałąź równoległą, należy wykonać następujące procedury w edytorze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="648fb-104">To configure a parallel branch, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="648fb-105">Gałąź równoległa to zasadniczo przepływ pracy, który jest wykonywany w kontekście nadrzędnego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="648fb-105">A parallel branch is essentially a workflow that runs in the context of a parent workflow.</span></span>

## <a name="name-a-branch"></a><span data-ttu-id="648fb-106">Nazywanie gałęzi</span><span class="sxs-lookup"><span data-stu-id="648fb-106">Name a branch</span></span>

<span data-ttu-id="648fb-107">Wykonaj następujące kroki, aby nazwać odgałęzienie równoległe.</span><span class="sxs-lookup"><span data-stu-id="648fb-107">Follow these steps to enter a name for a parallel branch.</span></span>

1. <span data-ttu-id="648fb-108">Kliknij prawym przyciskiem gałąź równoległą i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="648fb-108">Right-click the parallel branch, and then click **Properties**.</span></span> <span data-ttu-id="648fb-109">Zostanie wyświetlony formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="648fb-109">The **Properties** form is displayed.</span></span>
2. <span data-ttu-id="648fb-110">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="648fb-110">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="648fb-111">W polu **Nazwa** wprowadź unikatową nazwę gałęzi równoległej.</span><span class="sxs-lookup"><span data-stu-id="648fb-111">In the **Name** field, enter a unique name for the parallel branch.</span></span>
4. <span data-ttu-id="648fb-112">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="648fb-112">Click **Close**.</span></span>

## <a name="design-and-configure-the-elements-of-a-branch"></a><span data-ttu-id="648fb-113">Projektowanie i konfigurowanie elementów gałęzi</span><span class="sxs-lookup"><span data-stu-id="648fb-113">Design and configure the elements of a branch</span></span>

<span data-ttu-id="648fb-114">Wykonaj następujące kroki, aby zaprojektować i skonfigurować elementy odgałęzienia równoległego.</span><span class="sxs-lookup"><span data-stu-id="648fb-114">Follow these steps to design and configure the elements of a parallel branch.</span></span>

1. <span data-ttu-id="648fb-115">Kliknij dwukrotnie gałąź równoległą.</span><span class="sxs-lookup"><span data-stu-id="648fb-115">Double-click the parallel branch.</span></span>
2. <span data-ttu-id="648fb-116">Przeciągnij elementy przepływu pracy na kanwę, a następnie je skonfiguruj, tak samo jak przy tworzeniu jakiegokolwiek innego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="648fb-116">Drag workflow elements onto the canvas, and then configure the elements, just as you would to create any other workflow.</span></span> <span data-ttu-id="648fb-117">Aby uzyskać więcej informacji, zobacz temat [Omówienie tworzenia przepływów pracy](create-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="648fb-117">For more information, see [Create workflows overview](create-workflow.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="648fb-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="648fb-118">Additional resources</span></span>

[<span data-ttu-id="648fb-119">Omówienie tworzenia przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="648fb-119">Create workflows overview</span></span>](create-workflow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]