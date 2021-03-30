---
title: Tworzenie nowego produktu w programie Commerce
description: W tym temacie opisano, jak dodać utworzyć nowy produkt w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: cb0137468d690649abb18b9d19673ff740d52e5d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207926"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="d4fc8-103">Tworzenie nowego produktu w programie Commerce</span><span class="sxs-lookup"><span data-stu-id="d4fc8-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d4fc8-104">W tym temacie opisano, jak dodać utworzyć nowy produkt w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d4fc8-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="d4fc8-105">Overview</span></span>

<span data-ttu-id="d4fc8-106">Produkt jest definiowany głównie przez numer produktu, nazwę i opis.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="d4fc8-107">Są jednak potrzebne również inne dane, aby odpowiednio opisać produkt lub usługę:</span><span class="sxs-lookup"><span data-stu-id="d4fc8-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="d4fc8-108">Tworzenie nowego produktu</span><span class="sxs-lookup"><span data-stu-id="d4fc8-108">Create a new product</span></span>

1. <span data-ttu-id="d4fc8-109">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Produkty i kategorie \> Produkty według kategorii**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="d4fc8-110">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d4fc8-111">Z listy rozwijanej **Typ produktu** wybierz opcję **Towar** lub **Usługa**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="d4fc8-112">Z listy rozwijanej **Podtyp produktu** wybierz **Produkt** (jeśli produkt nie będzie miał wariantów) lub **Produkt główny** (jeśli produkt będzie miał warianty).</span><span class="sxs-lookup"><span data-stu-id="d4fc8-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="d4fc8-113">W polu **numer produktu** wprowadź numer produktu, jeśli nie został on jeszcze wstępnie wypełniony.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="d4fc8-114">W polu **Nazwa produktu** wprowadź nazwę produktu.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="d4fc8-115">W polu **Nazwa wyszukiwania** wprowadź nazwę wyszukiwaną.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="d4fc8-116">Z listy rozwijanej **Kategoria sieci sprzedaży** wybierz odpowiednią kategorię.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="d4fc8-117">Jeśli produkt jest zestawem, wybierz **Tak** dla **Zestawu produktów**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="d4fc8-118">Jeśli podtyp produktu jest produktem głównym, należy skonfigurować **grupę wymiarów produktu** w taki sposób, aby obejmowała ona obsługiwane warianty.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="d4fc8-119">Wybierz **kolor**, **rozmiar**, **styl** i **konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="d4fc8-120">W razie potrzeby może być konieczne utworzenie dodatkowych grup wymiarów produktów.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="d4fc8-121">Z listy rozwijanej **Technologia konfiguracji** wybierz odpowiednią opcję.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="d4fc8-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-122">Select **OK**.</span></span>

<span data-ttu-id="d4fc8-123">Poniższy obraz przedstawia przykład dodawanego produktu.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-123">The following image shows an example product being added.</span></span>

![Tworzenie produktu](media/create-new-product.png)

<span data-ttu-id="d4fc8-125">Po dodaniu produktu można dla niego określić dodatkowe dane, takie jak **opis produktu**, **grupy wariantów**, **grupy wymiarów**, **atrybuty produktów** i **produkty pokrewne**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="d4fc8-126">Poniższy obraz przedstawia dodatkowe szczegóły produktu.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-126">The following image shows a product's additional details.</span></span>

![Szczegóły produktu](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="d4fc8-128">Utwórz warianty produktu</span><span class="sxs-lookup"><span data-stu-id="d4fc8-128">Create product variants</span></span>

<span data-ttu-id="d4fc8-129">Jeśli podtyp produktu to **produkt główny**, konieczne będzie utworzenie konkretnych wariantów.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="d4fc8-130">Aby utworzyć warianty produktu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="d4fc8-131">W okienku akcji wybierz pozycję **Warianty produktu**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="d4fc8-132">Jeśli w okienku akcji wybrano grupy wariantów, wybierz \**Sugestie wariantów*.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="d4fc8-133">Wybierz warianty, które chcesz obsługiwać dla produktu.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="d4fc8-134">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="d4fc8-135">Zwolnienie produktu</span><span class="sxs-lookup"><span data-stu-id="d4fc8-135">Release a product</span></span>

<span data-ttu-id="d4fc8-136">Aby sprzedać produkt, należy go najpierw zwolnić do firmy.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="d4fc8-137">Na stronie produkt wybierz pozycję **Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-137">From the product page, select **Release products**.</span></span>

    ![Zwolniony produkt](media/create-new-product-3.png)

1. <span data-ttu-id="d4fc8-139">Wybierz produkt, który ma zostać zwolniony, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-139">Select the product to release, and then select **Next**.</span></span>

    ![Wybierz produkt do zwolnienia](media/create-new-product-4.png)

1. <span data-ttu-id="d4fc8-141">Wybierz zestaw wariantów produktu, który ma zostać zwolniony, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Wybierz warianty do zwolnienia](media/create-new-product-5.png)

1. <span data-ttu-id="d4fc8-143">Wybierz firmę i wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-143">Select the legal entity, and then select **Next**.</span></span>

    ![Wybierz firmę](media/create-new-product-6.png)

1. <span data-ttu-id="d4fc8-145">Wybierz **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-145">Select **Finish**.</span></span>

    ![Zakończ zwolnienie produktu](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="d4fc8-147">Konfiguruj zwolniony produkt</span><span class="sxs-lookup"><span data-stu-id="d4fc8-147">Configure a released product</span></span>

<span data-ttu-id="d4fc8-148">Po zwolnieniu produkt będzie wymagał dodatkowej konfiguracji, która obejmuje dodanie ceny do produktu.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="d4fc8-149">W okienku nawigacji przejdź do **Moduły \> Retail i commerce \> Produkty i kategorie \> Zwolnione produkty według kategorii**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="d4fc8-150">Wybierz węzeł kategorii produktów dla produktu, który został zwolniony, a następnie wybierz produkt z listy produktów.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="d4fc8-151">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="d4fc8-152">W sekcji **zakup** skonfiguruj wymagane właściwości, takie jak **jednostka**, **cena** i **ilość**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="d4fc8-153">W okienku akcji wybierz opcję **Sprawdzanie poprawności**, aby upewnić się, że nie zgłoszono błędów dla brakujących pól.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="d4fc8-154">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d4fc8-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d4fc8-155">Poniższy obraz przedstawia przykład konfiguracji dla zwolnionego produktu..</span><span class="sxs-lookup"><span data-stu-id="d4fc8-155">The following image shows an example configuration for a released product.</span></span>

![Konfiguruj zwolniony produkt](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="d4fc8-157">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d4fc8-157">Additional resources</span></span>

[<span data-ttu-id="d4fc8-158">Tworzenie firm</span><span class="sxs-lookup"><span data-stu-id="d4fc8-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="d4fc8-159">Utwórz grupę wariantów</span><span class="sxs-lookup"><span data-stu-id="d4fc8-159">Create a variant group</span></span>](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]