---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 138c256b56593c4fafb20050a97e614fa584597c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997833"
---
# <a name="cart-icon-module"></a><span data-ttu-id="a9033-103">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="a9033-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a9033-104">W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9033-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a9033-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a9033-105">Overview</span></span>

<span data-ttu-id="a9033-106">Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="a9033-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="a9033-107">Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem.</span><span class="sxs-lookup"><span data-stu-id="a9033-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="a9033-108">Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka.</span><span class="sxs-lookup"><span data-stu-id="a9033-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="a9033-109">Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania.</span><span class="sxs-lookup"><span data-stu-id="a9033-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="a9033-110">Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji.</span><span class="sxs-lookup"><span data-stu-id="a9033-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="a9033-111">Obsługa korzystania z modułu ikon koszyka w Dynamics 365 Commerce w wydaniu 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="a9033-111">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="a9033-112">Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="a9033-112">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Przykład modułu na ikonie koszyka](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="a9033-114">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="a9033-114">Module properties</span></span>

- <span data-ttu-id="a9033-115">**Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="a9033-115">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="a9033-116">Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.</span><span class="sxs-lookup"><span data-stu-id="a9033-116">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="a9033-117">Dodawanie modułu ikonu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="a9033-117">Add a cart icon module to a page</span></span>

<span data-ttu-id="a9033-118">Aby dodać moduł ikony koszyka, zobacz [Moduł nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="a9033-118">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9033-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a9033-119">Additional resources</span></span>

[<span data-ttu-id="a9033-120">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="a9033-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a9033-121">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="a9033-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a9033-122">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="a9033-122">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="a9033-123">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="a9033-123">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="a9033-124">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="a9033-124">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="a9033-125">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="a9033-125">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="a9033-126">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="a9033-126">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a9033-127">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="a9033-127">Gift card module</span></span>](add-giftcard.md)
