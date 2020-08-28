---
title: Moduł szczegółów zamówienia
description: W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5876b953a3b3d960c106acf37731fde13b93f8e7
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661179"
---
# <a name="order-details-module"></a><span data-ttu-id="90c5e-103">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="90c5e-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="90c5e-104">W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="90c5e-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="90c5e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="90c5e-105">Overview</span></span>

<span data-ttu-id="90c5e-106">Moduł szczegółów zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu.</span><span class="sxs-lookup"><span data-stu-id="90c5e-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="90c5e-107">Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności oraz metodę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="90c5e-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="90c5e-108">Właściwości modułu szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="90c5e-108">Order details module properties</span></span>

| <span data-ttu-id="90c5e-109">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="90c5e-109">Property name</span></span>  | <span data-ttu-id="90c5e-110">Wartości</span><span class="sxs-lookup"><span data-stu-id="90c5e-110">Values</span></span> | <span data-ttu-id="90c5e-111">opis</span><span class="sxs-lookup"><span data-stu-id="90c5e-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="90c5e-112">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="90c5e-112">Heading</span></span>        | <span data-ttu-id="90c5e-113">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="90c5e-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="90c5e-114">Moduł szczegółów zamówienia może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="90c5e-114">The order details module can have a heading.</span></span> <span data-ttu-id="90c5e-115">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="90c5e-116">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="90c5e-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="90c5e-117">Numer osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="90c5e-117">Contact number</span></span> | <span data-ttu-id="90c5e-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="90c5e-118">Text</span></span> | <span data-ttu-id="90c5e-119">Numer kontaktowy może być podawany dla pytań związanych z zamówieniami.</span><span class="sxs-lookup"><span data-stu-id="90c5e-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="90c5e-120">Moduły, których można używać na stronie szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="90c5e-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="90c5e-121">Podczas tworzenia strony szczegóły zamówienia można dodać także inne odpowiednie moduły oprócz modułu szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="90c5e-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="90c5e-122">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="90c5e-122">Here are some examples:</span></span>

- <span data-ttu-id="90c5e-123">**Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony szczegółów zamówienia w celu zaproponowania odbiorcy innych produktów.</span><span class="sxs-lookup"><span data-stu-id="90c5e-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="90c5e-124">**Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony Szczegóły zamówień, aby wyświetlić zawartość marketingową.</span><span class="sxs-lookup"><span data-stu-id="90c5e-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="90c5e-125">Dodawanie modułu szczegółów zamówienia do strony</span><span class="sxs-lookup"><span data-stu-id="90c5e-125">Add an order details module to a page</span></span>

<span data-ttu-id="90c5e-126">Aby dodać moduł szczegółów zamówienia do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="90c5e-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="90c5e-127">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="90c5e-127">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="90c5e-128">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon szczegółów zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-128">In the **New Template** dialog box, under **Template name**, enter the name **Order details template**, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-129">W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-129">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="90c5e-130">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-131">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-131">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="90c5e-132">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Szczegółóy zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-133">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd szablonu.</span><span class="sxs-lookup"><span data-stu-id="90c5e-133">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="90c5e-134">Moduł szczegółów zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="90c5e-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="90c5e-135">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="90c5e-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="90c5e-136">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="90c5e-136">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="90c5e-137">W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon szczegółów zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="90c5e-138">W sekcji **Nazwa strony** przejdź do **Strona szczegółów zamówienia**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-138">Under **Page name**, enter **Order details page**, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-139">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-139">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="90c5e-140">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Szczegółóy zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-141">W okienku właściwości modułu szczegółów zamówienia wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="90c5e-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="90c5e-142">W polu **Tekst nagłówka** okna dialogowego **Nagłówek** wpisz tekst **Szczegóły zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c5e-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details**, and then select **OK**.</span></span>
1. <span data-ttu-id="90c5e-143">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="90c5e-143">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="90c5e-144">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="90c5e-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="90c5e-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="90c5e-145">Additional resources</span></span>

[<span data-ttu-id="90c5e-146">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="90c5e-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="90c5e-147">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="90c5e-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="90c5e-148">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="90c5e-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="90c5e-149">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="90c5e-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="90c5e-150">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="90c5e-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="90c5e-151">Moduł Opcje dostawy</span><span class="sxs-lookup"><span data-stu-id="90c5e-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="90c5e-152">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="90c5e-152">Gift card module</span></span>](add-giftcard.md)
