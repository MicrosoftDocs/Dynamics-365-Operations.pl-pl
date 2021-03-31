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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ceb6aa65c2ed5bc8d4224bdaf7095fba769181e8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220589"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="2e957-103">Skonfiguruj kanał, aby używał hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="2e957-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2e957-104">W tym temacie opisano sposób konfigurowania kanału do użycia hierarchii nawigacji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2e957-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2e957-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="2e957-105">Overview</span></span>

<span data-ttu-id="2e957-106">Hierarchie nawigacji kanału organizują produkty w kategoriach, dzięki czemu produkty mogą być przeglądane w witrynie handlu elektronicznego lub w punktach sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="2e957-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="2e957-107">Kanały sieci sprzedaży i online muszą być skonfigurowane za pomocą hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="2e957-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="2e957-108">Konfigurowanie kanału</span><span class="sxs-lookup"><span data-stu-id="2e957-108">Configure the channel</span></span>

<span data-ttu-id="2e957-109">Aby skonfigurować kanał do korzystania z hierarchii nawigacji kanału, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2e957-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="2e957-110">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Konfiguracja kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="2e957-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="2e957-111">Wybierz kanał do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="2e957-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="2e957-112">W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="2e957-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="2e957-113">W liście rozwijanej **hierarchia kategorii** wybierz odpowiednią hierarchię nawigacji kanałów.</span><span class="sxs-lookup"><span data-stu-id="2e957-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="2e957-114">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2e957-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="2e957-115">W obszarze **Grupa atrybutów** dodaj wszystkie grupy atrybutów, które będą atrybutami globalnymi dla wszystkich węzłów.</span><span class="sxs-lookup"><span data-stu-id="2e957-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="2e957-116">Poniższy obraz pokazuje, jak skonfigurować kanał, aby używał hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="2e957-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Przykład konfiguracji kanału](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="2e957-118">Metadane ustawiania atrybutu</span><span class="sxs-lookup"><span data-stu-id="2e957-118">Set attribute metadata</span></span>

<span data-ttu-id="2e957-119">Ustawienie metadanych atrybutów pozwoli na konfigurację atrybutów w poszczególnych węzłach.</span><span class="sxs-lookup"><span data-stu-id="2e957-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="2e957-120">Aby ustawić metadane atrybutów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2e957-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="2e957-121">W okienku akcji wybierz opcję **Metadane ustawiania atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="2e957-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="2e957-122">Dla każdego węzła wybierz **Atrybuty produktu kanału**.</span><span class="sxs-lookup"><span data-stu-id="2e957-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="2e957-123">Ustaw atrybut **Pokaż atrybut w kanale** na **Tak** i **Może być doprecyzowany** do **Tak**, aby włączyć rafinery na tym kanale.</span><span class="sxs-lookup"><span data-stu-id="2e957-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="2e957-124">Po skonfigurowaniu każdego węzła w razie potrzeby w **okienku akcji** wybierz przycisk **Zapisz**, aby zapisać.</span><span class="sxs-lookup"><span data-stu-id="2e957-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="2e957-125">Wybierz **X** w prawym górnym rogu, aby zamknąć ten ekran z powrotem na stronie **Kategorie kanału sprzedaży i atrybuty produktów**.</span><span class="sxs-lookup"><span data-stu-id="2e957-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="2e957-126">Poniższy obraz przedstawia przykładowy zbiór atrybutów produktu kanału skonfigurowanych w węźle kategorii kanału.</span><span class="sxs-lookup"><span data-stu-id="2e957-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Atrybuty kanału w węźle kategorii kanału](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="2e957-128">Publikowanie zmian</span><span class="sxs-lookup"><span data-stu-id="2e957-128">Publish changes</span></span>

<span data-ttu-id="2e957-129">Aby zmiany odniosły skutek, musisz je opublikować.</span><span class="sxs-lookup"><span data-stu-id="2e957-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="2e957-130">Aby opublikować zmiany, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2e957-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="2e957-131">W okienku akcji wybierz opcję **Publikowanie aktualizacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="2e957-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="2e957-132">W okienku **Publikowanie aktualizacji kanału** wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e957-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="2e957-133">Poniższy obraz przedstawia sposób publikowania aktualizacji kanału.</span><span class="sxs-lookup"><span data-stu-id="2e957-133">The following image shows how to publish channel updates.</span></span>

![Publikowanie aktualizacji kanału](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="2e957-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2e957-135">Additional resources</span></span>

[<span data-ttu-id="2e957-136">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="2e957-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]