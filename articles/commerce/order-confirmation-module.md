---
title: Moduł szczegółów zamówienia
description: W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026024"
---
# <a name="order-details-module"></a><span data-ttu-id="38dbb-103">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="38dbb-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="38dbb-104">W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="38dbb-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="38dbb-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="38dbb-105">Overview</span></span>

<span data-ttu-id="38dbb-106">Moduł szczegółów zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu.</span><span class="sxs-lookup"><span data-stu-id="38dbb-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="38dbb-107">Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności oraz metodę wysyłki.</span><span class="sxs-lookup"><span data-stu-id="38dbb-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="38dbb-108">Właściwości modułu potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="38dbb-108">Order confirmation module properties</span></span>

| <span data-ttu-id="38dbb-109">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="38dbb-109">Property name</span></span>  | <span data-ttu-id="38dbb-110">Wartości</span><span class="sxs-lookup"><span data-stu-id="38dbb-110">Values</span></span> | <span data-ttu-id="38dbb-111">Opis</span><span class="sxs-lookup"><span data-stu-id="38dbb-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="38dbb-112">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="38dbb-112">Heading</span></span>        | <span data-ttu-id="38dbb-113">Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**)</span><span class="sxs-lookup"><span data-stu-id="38dbb-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="38dbb-114">Moduł potwierdzający zamówienie może mieć nagłówek.</span><span class="sxs-lookup"><span data-stu-id="38dbb-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="38dbb-115">Domyślnie w nagłówku jest używany znacznik nagłówka **H2**.</span><span class="sxs-lookup"><span data-stu-id="38dbb-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="38dbb-116">Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności.</span><span class="sxs-lookup"><span data-stu-id="38dbb-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="38dbb-117">Numer osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="38dbb-117">Contact number</span></span> | <span data-ttu-id="38dbb-118">Tekst</span><span class="sxs-lookup"><span data-stu-id="38dbb-118">Text</span></span> | <span data-ttu-id="38dbb-119">Numer kontaktowy może być podawany dla pytań związanych z zamówieniami.</span><span class="sxs-lookup"><span data-stu-id="38dbb-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="38dbb-120">Moduły, których można używać na stronie szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="38dbb-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="38dbb-121">Podczas tworzenia strony szczegóły zamówienia można dodać także inne odpowiednie moduły oprócz modułu szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="38dbb-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="38dbb-122">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="38dbb-122">Here are some examples:</span></span>

- <span data-ttu-id="38dbb-123">**Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony szczegółów zamówienia w celu zaproponowania odbiorcy innych produktów.</span><span class="sxs-lookup"><span data-stu-id="38dbb-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="38dbb-124">**Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony Szczegóły zamówień, aby wyświetlić zawartość marketingową.</span><span class="sxs-lookup"><span data-stu-id="38dbb-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="38dbb-125">Tworzenie modułu strony szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="38dbb-125">Create an order details page module</span></span>

1. <span data-ttu-id="38dbb-126">Utwórz szablon strony o nazwie nazwa **szablon szczegółów zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="38dbb-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="38dbb-127">W gnieździe **Główne** na stronie domyślnej dodaj moduł szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="38dbb-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="38dbb-128">W module szczegóły zamówienia dodaj moduł rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="38dbb-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="38dbb-129">Zapisz i zobacz podgląd szablonu.</span><span class="sxs-lookup"><span data-stu-id="38dbb-129">Save and preview the template.</span></span> <span data-ttu-id="38dbb-130">Moduł szczegółów zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="38dbb-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="38dbb-131">Zakończ edytowanie szablonu i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="38dbb-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="38dbb-132">Za pomocą utworzonego właśnie szablonu szczegółów zamówienia utwórz stronę o nazwie **strona szczegółów zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="38dbb-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="38dbb-133">Dodaj stronę domyślną do konspektu strony.</span><span class="sxs-lookup"><span data-stu-id="38dbb-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="38dbb-134">W gnieździe **nagłówka** w dodaj fragment nagłówka.</span><span class="sxs-lookup"><span data-stu-id="38dbb-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="38dbb-135">W gnieździe **stopki** w dodaj fragment stopki.</span><span class="sxs-lookup"><span data-stu-id="38dbb-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="38dbb-136">W gnieździe **Główne** dodaj moduł szczegółów zamówienia.</span><span class="sxs-lookup"><span data-stu-id="38dbb-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="38dbb-137">W okienku właściwości dla modułu szczegółów zamówienia dodaj nagłówek **Szczegóły zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="38dbb-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="38dbb-138">Poniżej modułu szczegółów zamówienia dodaj moduł rekomendacji i skonfiguruj go tak, aby korzystał z ustawień list **Nowości** i **Bestsellery**.</span><span class="sxs-lookup"><span data-stu-id="38dbb-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="38dbb-139">Zapisz i zobacz podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="38dbb-139">Save and preview the page.</span></span>
1. <span data-ttu-id="38dbb-140">Zakończ edytowanie strony i opublikuj go.</span><span class="sxs-lookup"><span data-stu-id="38dbb-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38dbb-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="38dbb-141">Additional resources</span></span>

[<span data-ttu-id="38dbb-142">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="38dbb-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="38dbb-143">Moduł kontenera</span><span class="sxs-lookup"><span data-stu-id="38dbb-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="38dbb-144">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="38dbb-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="38dbb-145">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="38dbb-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="38dbb-146">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="38dbb-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="38dbb-147">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="38dbb-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="38dbb-148">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="38dbb-148">Footer module</span></span>](author-footer-module.md)
