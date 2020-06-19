---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411096"
---
# <a name="cart-icon-module"></a><span data-ttu-id="23b7f-103">Moduł ikony koszyka</span><span class="sxs-lookup"><span data-stu-id="23b7f-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="23b7f-104">W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="23b7f-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="23b7f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="23b7f-105">Overview</span></span>

<span data-ttu-id="23b7f-106">Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku.</span><span class="sxs-lookup"><span data-stu-id="23b7f-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="23b7f-107">Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem.</span><span class="sxs-lookup"><span data-stu-id="23b7f-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="23b7f-108">Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka.</span><span class="sxs-lookup"><span data-stu-id="23b7f-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="23b7f-109">Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania.</span><span class="sxs-lookup"><span data-stu-id="23b7f-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="23b7f-110">Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji.</span><span class="sxs-lookup"><span data-stu-id="23b7f-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="23b7f-111">Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="23b7f-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Przykład modułu na ikonie koszyka](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="23b7f-113">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="23b7f-113">Module properties</span></span>

- <span data-ttu-id="23b7f-114">**Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka.</span><span class="sxs-lookup"><span data-stu-id="23b7f-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="23b7f-115">Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.</span><span class="sxs-lookup"><span data-stu-id="23b7f-115">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="23b7f-116">Dodawanie modułu ikonu koszyka do strony</span><span class="sxs-lookup"><span data-stu-id="23b7f-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="23b7f-117">Aby dodać moduł ikony koszyka, zobacz [Moduł nagłówka](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="23b7f-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="23b7f-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="23b7f-118">Additional resources</span></span>

[<span data-ttu-id="23b7f-119">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="23b7f-119">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="23b7f-120">Moduł koszyka</span><span class="sxs-lookup"><span data-stu-id="23b7f-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="23b7f-121">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="23b7f-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="23b7f-122">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="23b7f-122">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="23b7f-123">Moduł nagłówka</span><span class="sxs-lookup"><span data-stu-id="23b7f-123">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="23b7f-124">Moduł stopki</span><span class="sxs-lookup"><span data-stu-id="23b7f-124">Footer module</span></span>](author-footer-module.md)
