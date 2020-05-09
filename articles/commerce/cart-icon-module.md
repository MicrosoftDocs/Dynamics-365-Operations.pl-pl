---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8cc96e0476a9d8a46aed7011359dc65fbc678fbf
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261584"
---
# <a name="cart-icon-module"></a><span data-ttu-id="6c019-103">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="6c019-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6c019-104">W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c019-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6c019-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6c019-105">Overview</span></span>

<span data-ttu-id="6c019-106">Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="6c019-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="6c019-107">Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem.</span><span class="sxs-lookup"><span data-stu-id="6c019-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="6c019-108">Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka.</span><span class="sxs-lookup"><span data-stu-id="6c019-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="6c019-109">Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania.</span><span class="sxs-lookup"><span data-stu-id="6c019-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="6c019-110">Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji.</span><span class="sxs-lookup"><span data-stu-id="6c019-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

## <a name="module-properties"></a><span data-ttu-id="6c019-111">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="6c019-111">Module properties</span></span>

- <span data-ttu-id="6c019-112">**Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="6c019-112">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="6c019-113">Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.</span><span class="sxs-lookup"><span data-stu-id="6c019-113">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="6c019-114">Dodawanie modułu ikonu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="6c019-114">Add a cart icon module to a page</span></span>

<span data-ttu-id="6c019-115">Aby dodać moduł ikony koszyka, zobacz [Moduł nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="6c019-115">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="6c019-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6c019-116">Additional resources</span></span>

[<span data-ttu-id="6c019-117">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="6c019-117">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6c019-118">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="6c019-118">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6c019-119">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="6c019-119">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="6c019-120">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="6c019-120">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="6c019-121">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="6c019-121">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="6c019-122">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="6c019-122">Footer module</span></span>](author-footer-module.md)