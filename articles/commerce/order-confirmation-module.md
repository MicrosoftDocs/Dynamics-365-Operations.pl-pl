---
title: Moduł potwierdzenia zamówienia
description: W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698333"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="3e51b-103">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="3e51b-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3e51b-104">W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e51b-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e51b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="3e51b-105">Overview</span></span>

<span data-ttu-id="3e51b-106">Moduł potwierdzenia zamówienia służy do wyświetlania komunikatu potwierdzającego na stronie potwierdzenia zamówienia po złożeniu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="3e51b-107">W module potwierdzenia zamówienia wyświetlany jest numer potwierdzenia zamówienia oraz adres e-mail odbiorcy dostarczony podczas realizacji transakcji.</span><span class="sxs-lookup"><span data-stu-id="3e51b-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="3e51b-108">Jeśli zamówienie zostanie wykonane podczas procesu realizacji transakcji, numer potwierdzenia zamówienia i adres e-mail odbiorcy są przekazywane do strony potwierdzenia zamówienia jako ciąg kwerendy w adresie URL strony.</span><span class="sxs-lookup"><span data-stu-id="3e51b-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="3e51b-109">Moduł potwierdzenie zamówienia odbiera te informacje i renderuje stan zamówienia na stronie potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="3e51b-110">W module potwierdzenia zamówienia do podania stanu zamówienia wymagany jest kontekst strony.</span><span class="sxs-lookup"><span data-stu-id="3e51b-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="3e51b-111">Właściwości modułu potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="3e51b-111">Order confirmation module properties</span></span>

| <span data-ttu-id="3e51b-112">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="3e51b-112">Property name</span></span> | <span data-ttu-id="3e51b-113">Wartości</span><span class="sxs-lookup"><span data-stu-id="3e51b-113">Values</span></span> | <span data-ttu-id="3e51b-114">Opis</span><span class="sxs-lookup"><span data-stu-id="3e51b-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="3e51b-115">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="3e51b-115">Heading</span></span>       | <span data-ttu-id="3e51b-116">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="3e51b-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="3e51b-117">Moduł potwierdzający zamówienie może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="3e51b-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="3e51b-118">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="3e51b-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="3e51b-119">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="3e51b-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="3e51b-120">Moduły, których można używać w module strony potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="3e51b-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="3e51b-121">**Rekomendacje** — moduł rekomendacji może zostać umieszczony na stronie potwierdzenia zamówienia w celu zaproponowania innym produktom odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3e51b-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="3e51b-122">**Marketing** — moduł marketingowy umożliwia dodanie zawartości marketingowej do strony potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="3e51b-123">Tworzenie strony modułu potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="3e51b-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="3e51b-124">Utwórz szablon strony o nazwie nazwa **szablon potwierdzenia zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="3e51b-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="3e51b-125">W **Głównym** gnieździe na stronie domyślnej dodaj moduł potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="3e51b-126">W module potwierdzenia zamówienia dodaj moduł rekomendacji</span><span class="sxs-lookup"><span data-stu-id="3e51b-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="3e51b-127">Zapisz i zobacz podgląd szablonu.</span><span class="sxs-lookup"><span data-stu-id="3e51b-127">Save and preview the template.</span></span> <span data-ttu-id="3e51b-128">Moduł potwierdzenia zamówienia nie powinien być renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="3e51b-129">Zaewidencjonuj szablon i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="3e51b-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="3e51b-130">Za pomocą utworzonego właśnie szablonu potwierdzenia zamówienia utwórz stronę o nazwie **strona potwierdzenia zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="3e51b-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="3e51b-131">Dodaj stronę domyślną do konspektu strony.</span><span class="sxs-lookup"><span data-stu-id="3e51b-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="3e51b-132">W gnieździe **nagłówka** w dodaj fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="3e51b-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="3e51b-133">W gnieździe **stopki** w dodaj fragment stopki.</span><span class="sxs-lookup"><span data-stu-id="3e51b-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="3e51b-134">W **Głównym** gnieździe dodaj moduł potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3e51b-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="3e51b-135">W okienku właściwości modułu potwierdzenie zamówienia dodaj nagłówek **potwierdzenie zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="3e51b-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="3e51b-136">Poniżej modułu potwierdzenia zamówienia Dodaj moduł rekomendacji i skonfiguruj go tak, aby korzystał z ustawień list **Nowości** i **Bestsellery**.</span><span class="sxs-lookup"><span data-stu-id="3e51b-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="3e51b-137">Zapisz i zobacz podgląd strony, zaewidencjonuj ją i opublikuj.</span><span class="sxs-lookup"><span data-stu-id="3e51b-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e51b-138">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3e51b-138">Additional resources</span></span>

[<span data-ttu-id="3e51b-139">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="3e51b-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3e51b-140">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="3e51b-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3e51b-141">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="3e51b-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="3e51b-142">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="3e51b-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3e51b-143">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="3e51b-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3e51b-144">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="3e51b-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="3e51b-145">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="3e51b-145">Footer module</span></span>](author-footer-module.md)
