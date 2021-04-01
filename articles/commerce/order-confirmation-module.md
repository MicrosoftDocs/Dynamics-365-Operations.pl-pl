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
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257154"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="c34af-103">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="c34af-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c34af-104">W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c34af-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c34af-105">Moduł potwierdzenia zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu.</span><span class="sxs-lookup"><span data-stu-id="c34af-105">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="c34af-106">Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności, opcje odbioru oraz metodę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="c34af-106">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="c34af-107">Właściwości modułu potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="c34af-107">Order confirmation module properties</span></span>

| <span data-ttu-id="c34af-108">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="c34af-108">Property name</span></span>  | <span data-ttu-id="c34af-109">Wartości</span><span class="sxs-lookup"><span data-stu-id="c34af-109">Values</span></span> | <span data-ttu-id="c34af-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c34af-110">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="c34af-111">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="c34af-111">Heading</span></span>        | <span data-ttu-id="c34af-112">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="c34af-112">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c34af-113">Moduł potwierdzający zamówienie może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="c34af-113">The order confirmation module can have a heading.</span></span> <span data-ttu-id="c34af-114">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="c34af-114">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="c34af-115">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="c34af-115">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="c34af-116">Numer osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="c34af-116">Contact number</span></span> | <span data-ttu-id="c34af-117">Tekst</span><span class="sxs-lookup"><span data-stu-id="c34af-117">Text</span></span> | <span data-ttu-id="c34af-118">Numer kontaktowy może być podawany dla pytań związanych z zamówieniami.</span><span class="sxs-lookup"><span data-stu-id="c34af-118">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="c34af-119">Wyświetlanie informacji o przedziałach czasu na potrzeby odbiorów</span><span class="sxs-lookup"><span data-stu-id="c34af-119">Show pickup timeslot information</span></span> | <span data-ttu-id="c34af-120">Prawda lub Fałsz</span><span class="sxs-lookup"><span data-stu-id="c34af-120">True or False</span></span> | <span data-ttu-id="c34af-121">Ta właściwość jest dostępna w Dynamics 365 Commerce w wersji 10.0.15 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="c34af-121">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="c34af-122">Gdy wartość wynosi prawda, wyświetla informacje o przedziale czasu odbioru, jeśli jest podany dla przedmiotu do odbioru</span><span class="sxs-lookup"><span data-stu-id="c34af-122">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="c34af-123">Moduły, których można używać na stronie potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="c34af-123">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="c34af-124">Podczas tworzenia strony potwierdzenia zamówienia można dodać także inne odpowiednie moduły oprócz modułu potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c34af-124">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="c34af-125">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="c34af-125">Here are some examples:</span></span>

- <span data-ttu-id="c34af-126">**Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony potwierdzenia zamówienia w celu zaproponowania odbiorcy innych produktów.</span><span class="sxs-lookup"><span data-stu-id="c34af-126">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="c34af-127">**Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony potwierdzenia zamówień, aby wyświetlić zawartość marketingową.</span><span class="sxs-lookup"><span data-stu-id="c34af-127">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="c34af-128">Dodawanie modułu potwierdzenia zamówienia do strony</span><span class="sxs-lookup"><span data-stu-id="c34af-128">Add an order confirmation module to a page</span></span>

<span data-ttu-id="c34af-129">Aby dodać moduł potwierdzenia zamówienia do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c34af-129">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c34af-130">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="c34af-130">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c34af-131">W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon potwierdzenia zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-131">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-132">W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c34af-132">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c34af-133">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-133">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-134">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c34af-134">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c34af-135">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-135">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-136">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd szablonu.</span><span class="sxs-lookup"><span data-stu-id="c34af-136">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="c34af-137">Moduł potwierdzenia zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c34af-137">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="c34af-138">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="c34af-138">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="c34af-139">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="c34af-139">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="c34af-140">W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon potwierdzenia zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="c34af-140">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="c34af-141">W sekcji **Nazwa strony** przejdź do **Strona potwierdzenia zamówienia**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-141">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-142">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="c34af-142">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c34af-143">W oknie dialogowym **Dodawanie modułu** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-143">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-144">W okienku właściwości modułu potwierdzenia zamówienia wybierz pozycję **Nagłówek** obok symbolu ołówka.</span><span class="sxs-lookup"><span data-stu-id="c34af-144">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="c34af-145">W polu **Tekst nagłówka** okna dialogowego **Nagłówek** wpisz tekst **Potwierdzenie zamówienia**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="c34af-145">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="c34af-146">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="c34af-146">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="c34af-147">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="c34af-147">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c34af-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c34af-148">Additional resources</span></span>

[<span data-ttu-id="c34af-149">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="c34af-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c34af-150">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="c34af-150">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="c34af-151">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="c34af-151">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c34af-152">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="c34af-152">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c34af-153">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="c34af-153">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c34af-154">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="c34af-154">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c34af-155">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="c34af-155">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c34af-156">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="c34af-156">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]