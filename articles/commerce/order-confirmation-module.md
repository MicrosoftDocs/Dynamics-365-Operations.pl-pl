---
title: Moduł potwierdzenia zamówienia
description: W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9d916d2687777403f2b0df7c35171948ad2fb7db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972757"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="1a01a-103">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="1a01a-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1a01a-104">W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a01a-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1a01a-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1a01a-105">Overview</span></span>

<span data-ttu-id="1a01a-106">Moduł potwierdzenia zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu.</span><span class="sxs-lookup"><span data-stu-id="1a01a-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="1a01a-107">Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności, opcje odbioru oraz metodę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="1a01a-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="1a01a-108">Właściwości modułu potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="1a01a-108">Order confirmation module properties</span></span>

| <span data-ttu-id="1a01a-109">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="1a01a-109">Property name</span></span>  | <span data-ttu-id="1a01a-110">Wartości</span><span class="sxs-lookup"><span data-stu-id="1a01a-110">Values</span></span> | <span data-ttu-id="1a01a-111">Opis</span><span class="sxs-lookup"><span data-stu-id="1a01a-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="1a01a-112">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="1a01a-112">Heading</span></span>        | <span data-ttu-id="1a01a-113">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="1a01a-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="1a01a-114">Moduł potwierdzający zamówienie może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="1a01a-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="1a01a-115">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="1a01a-116">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="1a01a-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="1a01a-117">Numer osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="1a01a-117">Contact number</span></span> | <span data-ttu-id="1a01a-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="1a01a-118">Text</span></span> | <span data-ttu-id="1a01a-119">Numer kontaktowy może być podawany dla pytań związanych z zamówieniami.</span><span class="sxs-lookup"><span data-stu-id="1a01a-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="1a01a-120">Wyświetlanie informacji o przedziałach czasu na potrzeby odbiorów</span><span class="sxs-lookup"><span data-stu-id="1a01a-120">Show pickup timeslot information</span></span> | <span data-ttu-id="1a01a-121">Prawda lub Fałsz</span><span class="sxs-lookup"><span data-stu-id="1a01a-121">True or False</span></span> | <span data-ttu-id="1a01a-122">Ta właściwość jest dostępna w Dynamics 365 Commerce w wersji 10.0.15 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="1a01a-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="1a01a-123">Gdy wartość wynosi prawda, wyświetla informacje o przedziale czasu odbioru, jeśli jest podany dla przedmiotu do odbioru</span><span class="sxs-lookup"><span data-stu-id="1a01a-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="1a01a-124">Moduły, których można używać na stronie potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="1a01a-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="1a01a-125">Podczas tworzenia strony potwierdzenia zamówienia można dodać także inne odpowiednie moduły oprócz modułu potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1a01a-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="1a01a-126">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="1a01a-126">Here are some examples:</span></span>

- <span data-ttu-id="1a01a-127">**Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony potwierdzenia zamówienia w celu zaproponowania odbiorcy innych produktów.</span><span class="sxs-lookup"><span data-stu-id="1a01a-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="1a01a-128">**Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony potwierdzenia zamówień, aby wyświetlić zawartość marketingową.</span><span class="sxs-lookup"><span data-stu-id="1a01a-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="1a01a-129">Dodawanie modułu potwierdzenia zamówienia do strony</span><span class="sxs-lookup"><span data-stu-id="1a01a-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="1a01a-130">Aby dodać moduł potwierdzenia zamówienia do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1a01a-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="1a01a-131">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="1a01a-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="1a01a-132">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon potwierdzenia zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-133">W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1a01a-134">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-135">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1a01a-136">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-137">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd szablonu.</span><span class="sxs-lookup"><span data-stu-id="1a01a-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="1a01a-138">Moduł potwierdzenia zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1a01a-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="1a01a-139">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1a01a-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="1a01a-140">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="1a01a-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="1a01a-141">W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon potwierdzenia zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="1a01a-142">W sekcji **Nazwa strony** przejdź do **Strona potwierdzenia zamówienia**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-143">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1a01a-144">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-145">W okienku właściwości modułu potwierdzenia zamówienia wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="1a01a-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="1a01a-146">W polu **Tekst nagłówka** okna dialogowego **Nagłówek** wpisz tekst **Potwierdzenie zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a01a-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="1a01a-147">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="1a01a-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="1a01a-148">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="1a01a-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a01a-149">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1a01a-149">Additional resources</span></span>

[<span data-ttu-id="1a01a-150">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="1a01a-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1a01a-151">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="1a01a-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="1a01a-152">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="1a01a-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1a01a-153">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="1a01a-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="1a01a-154">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="1a01a-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="1a01a-155">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="1a01a-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="1a01a-156">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="1a01a-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="1a01a-157">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="1a01a-157">Gift card module</span></span>](add-giftcard.md)
