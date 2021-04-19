---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5ff514f07e8b31abe79775e5011bd3f1b24b2935
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793088"
---
# <a name="cart-icon-module"></a><span data-ttu-id="f0f1f-103">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="f0f1f-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0f1f-104">W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f0f1f-105">Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-105">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="f0f1f-106">Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-106">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="f0f1f-107">Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-107">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="f0f1f-108">Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-108">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="f0f1f-109">Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-109">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="f0f1f-110">Obsługa korzystania z modułu ikon koszyka w Dynamics 365 Commerce w wydaniu 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-110">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="f0f1f-111">Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Przykład modułu na ikonie koszyka](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="f0f1f-113">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="f0f1f-113">Module properties</span></span>

- <span data-ttu-id="f0f1f-114">**Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="f0f1f-115">Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.</span><span class="sxs-lookup"><span data-stu-id="f0f1f-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="f0f1f-116">Dodawanie modułu ikonu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="f0f1f-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="f0f1f-117">Aby dodać moduł ikony koszyka, zobacz [Moduł nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="f0f1f-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0f1f-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f0f1f-118">Additional resources</span></span>

[<span data-ttu-id="f0f1f-119">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="f0f1f-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f0f1f-120">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="f0f1f-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f0f1f-121">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="f0f1f-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="f0f1f-122">Moduł adresu wysyłki</span><span class="sxs-lookup"><span data-stu-id="f0f1f-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="f0f1f-123">Moduł opcji dostawy</span><span class="sxs-lookup"><span data-stu-id="f0f1f-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="f0f1f-124">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="f0f1f-124">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="f0f1f-125">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="f0f1f-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f0f1f-126">Moduł karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="f0f1f-126">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]