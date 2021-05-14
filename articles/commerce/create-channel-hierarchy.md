---
title: Tworzenie hierarchii nawigacji kanału
description: W tym temacie opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
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
ms.openlocfilehash: 5df46de9dadfa0b7160a9b340ef36fdf963a0ad3
ms.sourcegitcommit: 6c2f5c3b038f696532c335e20b0fbafa155d6858
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5951915"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="5a3fb-103">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="5a3fb-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5a3fb-104">W tym temacie opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5a3fb-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="5a3fb-105">Overview</span></span>

<span data-ttu-id="5a3fb-106">Hierarchia nawigacji kanałów służy do grupowania i organizowania produktów w kategorie, dzięki czemu można je przeglądać online lub w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="5a3fb-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="5a3fb-107">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="5a3fb-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="5a3fb-108">Aby utworzyć hierarchię nawigacji kanału, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="5a3fb-109">W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Kategarie nawigacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="5a3fb-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="5a3fb-111">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="5a3fb-112">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="5a3fb-113">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-113">Select **Create**.</span></span>
1. <span data-ttu-id="5a3fb-114">W okienku akcji naciśnij przycisk **Nowy węzeł kategorii**, aby utworzyć węzeł główny.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="5a3fb-115">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="5a3fb-116">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="5a3fb-117">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="5a3fb-118">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="5a3fb-119">Poniższy obraz przedstawia przykładowy węzeł główny.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-119">The following image shows a example root node.</span></span>

![Przykładowy węzeł główny](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="5a3fb-121">Tworzenie węzłów nawigacji kategorii</span><span class="sxs-lookup"><span data-stu-id="5a3fb-121">Create navigation category nodes</span></span>

<span data-ttu-id="5a3fb-122">Aby utworzyć dodatkowe węzły kategorii nawigacji reprezentujące kategorie produktów w kanale, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="5a3fb-123">W okienku nawigacji wybierz węzeł nadrzędny, do którego ma zostać dodana kategoria.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="5a3fb-124">W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="5a3fb-125">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="5a3fb-126">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="5a3fb-127">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="5a3fb-128">W polu **Kolejność wyświetlania** wprowadź kolejność wyświetlania (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="5a3fb-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="5a3fb-129">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="5a3fb-130">Poniższy obraz przedstawia przykład ukończonej hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Przykładowa hierarchia kanałów](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="5a3fb-132">Dodawanie produktów do węzłów kategorii</span><span class="sxs-lookup"><span data-stu-id="5a3fb-132">Add products to category nodes</span></span>

<span data-ttu-id="5a3fb-133">Aby dodać produkty do węzłów kategorii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="5a3fb-134">Wybierz węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-134">Select a category node.</span></span>
1. <span data-ttu-id="5a3fb-135">W obszarze **Produkty** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="5a3fb-136">Znajdź nowe produkty, których chcesz dodać, używając numeru produktu lub nazwy produktu, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="5a3fb-137">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5a3fb-138">Dodawanie produktów do węzła znajdującego się w hierarchii nawigacji kanału nie wystarczy, aby produkty były wyświetlane w wybranym kanale, produkty muszą być także w asortymentach kanału.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a channel.</span></span> <span data-ttu-id="5a3fb-139">Aby uzyskać więcej informacji o asortymentach, zobacz temat [Zarządzanie asortymentem](assortments.md).</span><span class="sxs-lookup"><span data-stu-id="5a3fb-139">For more information on assortments, see [Assortment management](assortments.md).</span></span>

<span data-ttu-id="5a3fb-140">Poniższy obraz przedstawia przykład węzła z dodanymi produktami.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-140">The following image shows an example node with products added.</span></span>

![Produkty dodane do węzła kategorii](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="5a3fb-142">Dodawanie grup atrybutów produktu do węzłów kategorii</span><span class="sxs-lookup"><span data-stu-id="5a3fb-142">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="5a3fb-143">Grupy atrybutów należy utworzyć przed dodaniem ich do węzła w hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-143">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="5a3fb-144">Aby dodać produkt grupę atrybutów do węzła kategorii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-144">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="5a3fb-145">Wybierz węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-145">Select a category node.</span></span>
1. <span data-ttu-id="5a3fb-146">W obszarze **Grupa atrybutów produktu** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-146">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="5a3fb-147">Znajdź grupy atrybutów, które chcesz dodać, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-147">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="5a3fb-148">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="5a3fb-149">Poniższy obraz przedstawia przykładowy węzeł z dodanymi grupami atrybutów produktu.</span><span class="sxs-lookup"><span data-stu-id="5a3fb-149">The following image shows a sample node with product attribute groups added.</span></span>

![Grupy atrybutów produktu w węźle](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="5a3fb-151">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5a3fb-151">Additional resources</span></span>

[<span data-ttu-id="5a3fb-152">Konfigurowanie asortymentów</span><span class="sxs-lookup"><span data-stu-id="5a3fb-152">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="5a3fb-153">Zarządzanie atrybutami i grupami atrybutów</span><span class="sxs-lookup"><span data-stu-id="5a3fb-153">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
