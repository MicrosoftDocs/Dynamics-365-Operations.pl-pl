---
title: Tworzenie hierarchii nawigacji kanału
description: W tym temacie opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2e1462c10dfe1c858429e9f4cc5d720ca43df609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221336"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="ea098-103">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="ea098-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ea098-104">W tym temacie opisano, jak dodać utworzyć nową hierarchię nawigacji kanału w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ea098-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ea098-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="ea098-105">Overview</span></span>

<span data-ttu-id="ea098-106">Hierarchia nawigacji kanałów służy do grupowania i organizowania produktów w kategorie, dzięki czemu można je przeglądać online lub w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="ea098-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="ea098-107">Tworzenie hierarchii nawigacji kanału</span><span class="sxs-lookup"><span data-stu-id="ea098-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="ea098-108">Aby utworzyć hierarchię nawigacji kanału, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ea098-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="ea098-109">W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Kategarie nawigacji kanału**.</span><span class="sxs-lookup"><span data-stu-id="ea098-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="ea098-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ea098-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ea098-111">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="ea098-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="ea098-112">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="ea098-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="ea098-113">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ea098-113">Select **Create**.</span></span>
1. <span data-ttu-id="ea098-114">W okienku akcji naciśnij przycisk **Nowy węzeł kategorii**, aby utworzyć węzeł główny.</span><span class="sxs-lookup"><span data-stu-id="ea098-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="ea098-115">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="ea098-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="ea098-116">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="ea098-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="ea098-117">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ea098-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="ea098-118">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ea098-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ea098-119">Poniższy obraz przedstawia przykładowy węzeł główny.</span><span class="sxs-lookup"><span data-stu-id="ea098-119">The following image shows a example root node.</span></span>

![Przykładowy węzeł główny](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="ea098-121">Tworzenie węzłów nawigacji kategorii</span><span class="sxs-lookup"><span data-stu-id="ea098-121">Create navigation category nodes</span></span>

<span data-ttu-id="ea098-122">Aby utworzyć dodatkowe węzły kategorii nawigacji reprezentujące kategorie produktów w kanale, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ea098-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="ea098-123">W okienku nawigacji wybierz węzeł nadrzędny, do którego ma zostać dodana kategoria.</span><span class="sxs-lookup"><span data-stu-id="ea098-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="ea098-124">W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.</span><span class="sxs-lookup"><span data-stu-id="ea098-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="ea098-125">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="ea098-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="ea098-126">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="ea098-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="ea098-127">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="ea098-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="ea098-128">W polu **Kolejność wyświetlania** wprowadź kolejność wyświetlania (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="ea098-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="ea098-129">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ea098-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ea098-130">Poniższy obraz przedstawia przykład ukończonej hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="ea098-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Przykładowa hierarchia kanałów](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="ea098-132">Dodawanie produktów do węzłów kategorii</span><span class="sxs-lookup"><span data-stu-id="ea098-132">Add products to category nodes</span></span>

<span data-ttu-id="ea098-133">Aby dodać produkty do węzłów kategorii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ea098-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="ea098-134">Wybierz węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="ea098-134">Select a category node.</span></span>
1. <span data-ttu-id="ea098-135">W obszarze **Produkty** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ea098-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="ea098-136">Znajdź nowe produkty, których chcesz dodać, używając numeru produktu lub nazwy produktu, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea098-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="ea098-137">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ea098-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ea098-138">Dodawanie produktów do węzła znajdującego się w hierarchii nawigacji kanału nie wystarczy, aby produkty były wyświetlane w wybranym kanale, produkty muszą być także w asortymentach produktu.</span><span class="sxs-lookup"><span data-stu-id="ea098-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="ea098-139">Poniższy obraz przedstawia przykład węzła z dodanymi produktami.</span><span class="sxs-lookup"><span data-stu-id="ea098-139">The following image shows an example node with products added.</span></span>

![Produkty dodane do węzła kategorii](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="ea098-141">Dodawanie grup atrybutów produktu do węzłów kategorii</span><span class="sxs-lookup"><span data-stu-id="ea098-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="ea098-142">Grupy atrybutów należy utworzyć przed dodaniem ich do węzła w hierarchii nawigacji kanału.</span><span class="sxs-lookup"><span data-stu-id="ea098-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="ea098-143">Aby dodać produkt grupę atrybutów do węzła kategorii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ea098-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="ea098-144">Wybierz węzeł kategorii.</span><span class="sxs-lookup"><span data-stu-id="ea098-144">Select a category node.</span></span>
1. <span data-ttu-id="ea098-145">W obszarze **Grupa atrybutów produktu** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ea098-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="ea098-146">Znajdź grupy atrybutów, które chcesz dodać, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea098-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="ea098-147">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ea098-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ea098-148">Poniższy obraz przedstawia przykładowy węzeł z dodanymi grupami atrybutów produktu.</span><span class="sxs-lookup"><span data-stu-id="ea098-148">The following image shows a sample node with product attribute groups added.</span></span>

![Grupy atrybutów produktu w węźle](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="ea098-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ea098-150">Additional resources</span></span>

[<span data-ttu-id="ea098-151">Konfigurowanie asortymentów</span><span class="sxs-lookup"><span data-stu-id="ea098-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="ea098-152">Zarządzanie atrybutami i grupami atrybutów</span><span class="sxs-lookup"><span data-stu-id="ea098-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]