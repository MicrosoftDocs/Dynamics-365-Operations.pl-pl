---
title: Dodawanie kanał do hierarchii organizacyjnej
description: W tym temacie opisano, jak dodać kanał do hierarchii organizacyjnej w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7ff6d8ee7e526e45975cfa500b5e6d6079054dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800694"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="e2674-103">Dodawanie kanał do hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="e2674-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e2674-104">W tym temacie opisano, jak dodać kanał do hierarchii organizacyjnej w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e2674-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e2674-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e2674-105">Overview</span></span>

<span data-ttu-id="e2674-106">Kanały muszą być skojarzone z co najmniej jedną hierarchią organizacyjną.</span><span class="sxs-lookup"><span data-stu-id="e2674-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="e2674-107">Przed utworzeniem kanałów należy upewnić się, że zostały skonfigurowane hierarchie organizacyjne.</span><span class="sxs-lookup"><span data-stu-id="e2674-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="e2674-108">Aby uzyskać więcej informacji na temat tworzenia hierarchii organizacyjnych, należy zapoznać się z [Hierarchie organizacyjne](channels-org-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="e2674-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="e2674-109">Wybierz hierarchię</span><span class="sxs-lookup"><span data-stu-id="e2674-109">Select a hierarchy</span></span>

<span data-ttu-id="e2674-110">Aby wybrać hierarchię, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="e2674-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="e2674-111">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Hierarchie organizacyjne**.</span><span class="sxs-lookup"><span data-stu-id="e2674-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="e2674-112">Z listy wybierz hierarchię organizacyjną, do której będzie dodawany kanał.</span><span class="sxs-lookup"><span data-stu-id="e2674-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="e2674-113">W okienku akcji wybierz opcję **Widok**, aby wyświetlić szczegóły hierarchii.</span><span class="sxs-lookup"><span data-stu-id="e2674-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="e2674-114">Poniższy obraz przedstawia szczegóły hierarchii organizacyjnej dla wybranej hierarchii.</span><span class="sxs-lookup"><span data-stu-id="e2674-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Szczegóły hierarchii organizacyjnej dla wybranej hierarchii](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="e2674-116">Dodawanie kanału do węzła hierachy</span><span class="sxs-lookup"><span data-stu-id="e2674-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="e2674-117">Aby dodać kanał do węzła hierarchii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e2674-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="e2674-118">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="e2674-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="e2674-119">Wybierz węzeł hierachy, do którego chcesz dodać kanał, a następnie z listy rozwijanej **Wstaw** wybierz opcję **Kanał sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="e2674-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="e2674-120">Wybierz kanał do dodania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2674-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="e2674-121">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e2674-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="e2674-122">W okienku akcji wybierz opcję **Publikuj** i w przeszłości podaj **Data wejścia w życie** tej akcji, aby ta akcja zaczęła obowiązywać natychmiast.</span><span class="sxs-lookup"><span data-stu-id="e2674-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="e2674-123">Poniższy obraz przedstawia sposób wybierania kanału, który ma zostać dodany do węzła hierarchii.</span><span class="sxs-lookup"><span data-stu-id="e2674-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Wybierz kanał do dodania do węzła hierarchii organizacyjnej](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="e2674-125">Poniższy obraz przedstawia hierarchię z różnymi dodanymi kanałami.</span><span class="sxs-lookup"><span data-stu-id="e2674-125">The following image shows a hierarchy with various channels added.</span></span>

![Hierarchia z różnymi dodanymi kanałami](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="e2674-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e2674-127">Additional resources</span></span>

[<span data-ttu-id="e2674-128">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="e2674-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="e2674-129">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="e2674-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="e2674-130">Omówienie organizacji i hierarchii organizacyjnych</span><span class="sxs-lookup"><span data-stu-id="e2674-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="e2674-131">Planowanie hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="e2674-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="e2674-132">Hierarchie organizacyjne</span><span class="sxs-lookup"><span data-stu-id="e2674-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="e2674-133">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e2674-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="e2674-134">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="e2674-134">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]