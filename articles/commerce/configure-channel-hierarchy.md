---
title: Skonfiguruj kanał, aby używał hierarchii nawigacji kanału
description: W tym temacie opisano sposób konfigurowania kanału do użycia hierarchii nawigacji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7b5041d35d310125c314ab2cb77d3cc40cdb7113
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414845"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="776dd-103">Skonfiguruj kanał, aby używał hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="776dd-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="776dd-104">W tym temacie opisano sposób konfigurowania kanału do użycia hierarchii nawigacji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="776dd-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="776dd-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="776dd-105">Overview</span></span>

<span data-ttu-id="776dd-106">Hierarchie nawigacji kanału organizują produkty w kategoriach, dzięki czemu produkty mogą być przeglądane w witrynie handlu elektronicznego lub w punktach sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="776dd-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="776dd-107">Kanały sieci sprzedaży i online muszą być skonfigurowane za pomocą hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="776dd-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="776dd-108">Konfigurowanie kanału</span><span class="sxs-lookup"><span data-stu-id="776dd-108">Configure the channel</span></span>

<span data-ttu-id="776dd-109">Aby skonfigurować kanał do korzystania z hierarchii nawigacji kanału, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="776dd-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="776dd-110">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Konfiguracja kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="776dd-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="776dd-111">Wybierz kanał do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="776dd-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="776dd-112">W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="776dd-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="776dd-113">W liście rozwijanej **hierarchia kategorii** wybierz odpowiednią hierarchię nawigacji kanałów.</span><span class="sxs-lookup"><span data-stu-id="776dd-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="776dd-114">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="776dd-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="776dd-115">W obszarze **Grupa atrybutów** dodaj wszystkie grupy atrybutów, które będą atrybutami globalnymi dla wszystkich węzłów.</span><span class="sxs-lookup"><span data-stu-id="776dd-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="776dd-116">Poniższy obraz pokazuje, jak skonfigurować kanał, aby używał hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="776dd-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Przykład konfiguracji kanału](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="776dd-118">Metadane ustawiania atrybutu</span><span class="sxs-lookup"><span data-stu-id="776dd-118">Set attribute metadata</span></span>

<span data-ttu-id="776dd-119">Ustawienie metadanych atrybutów pozwoli na konfigurację atrybutów w poszczególnych węzłach.</span><span class="sxs-lookup"><span data-stu-id="776dd-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="776dd-120">Aby ustawić metadane atrybutów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="776dd-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="776dd-121">W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="776dd-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="776dd-122">Dla każdego węzła wybierz **Atrybuty produktu kanału**.</span><span class="sxs-lookup"><span data-stu-id="776dd-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="776dd-123">Ustaw atrybut **Pokaż atrybut w kanale** na **Tak** i **Może być doprecyzowany** do **Tak**, aby włączyć rafinery na tym kanale.</span><span class="sxs-lookup"><span data-stu-id="776dd-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="776dd-124">Po skonfigurowaniu każdego węzła w razie potrzeby w **okienku akcji** wybierz przycisk **Zapisz**, aby zapisać.</span><span class="sxs-lookup"><span data-stu-id="776dd-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="776dd-125">Wybierz **X** w prawym górnym rogu, aby zamknąć ten ekran z powrotem na stronie **Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="776dd-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="776dd-126">Poniższy obraz przedstawia przykładowy zbiór atrybutów produktu kanału skonfigurowanych w węźle kategorii kanału.</span><span class="sxs-lookup"><span data-stu-id="776dd-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Atrybuty kanału w węźle kategorii kanału](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="776dd-128">Publikowanie zmian</span><span class="sxs-lookup"><span data-stu-id="776dd-128">Publish changes</span></span>

<span data-ttu-id="776dd-129">Aby zmiany odniosły skutek, musisz je opublikować.</span><span class="sxs-lookup"><span data-stu-id="776dd-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="776dd-130">Aby opublikować zmiany, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="776dd-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="776dd-131">W okienku akcji wybierz opcję **Publikowanie aktualizacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="776dd-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="776dd-132">W okienku **Publikowanie aktualizacji kanału** wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="776dd-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="776dd-133">Poniższy obraz przedstawia sposób publikowania aktualizacji kanału.</span><span class="sxs-lookup"><span data-stu-id="776dd-133">The following image shows how to publish channel updates.</span></span>

![Publikowanie aktualizacji kanału](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="776dd-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="776dd-135">Additional resources</span></span>

[<span data-ttu-id="776dd-136">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="776dd-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)


