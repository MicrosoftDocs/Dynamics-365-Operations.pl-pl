---
title: Konfigurowanie kodów kreskowych
description: W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.
author: jblucher
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1c395caedfce7efa0a087ff6944052958c72327e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804192"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="6e5ae-103">Konfigurowanie kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="6e5ae-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6e5ae-104">W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6e5ae-105">Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="6e5ae-106">Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="6e5ae-107">Towary można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-107">You can set up products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="6e5ae-108">Produkt może mieć więcej niż jeden kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-108">Products can have more than one bar code.</span></span> <span data-ttu-id="6e5ae-109">Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="6e5ae-110">Kody kreskowe mogą uwzględniać wagę lub cenę produktu.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="6e5ae-111">Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="6e5ae-112">Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="6e5ae-113">Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="6e5ae-114">Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="6e5ae-115">Usługa Commerce używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-115">Commerce uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="6e5ae-116">Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="6e5ae-117">W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="6e5ae-118">Kody kreskowe można tworzyć ręcznie lub automatycznie.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="6e5ae-119">Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="6e5ae-120">[Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="6e5ae-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="6e5ae-121">[Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="6e5ae-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="6e5ae-122">Konfigurowanie ustawień kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="6e5ae-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="6e5ae-123">[Tworzenie kodów kreskowych dla produktów](../supply-chain/pim/tasks/create-bar-code-product.md).</span><span class="sxs-lookup"><span data-stu-id="6e5ae-123">[Create bar codes for products](../supply-chain/pim/tasks/create-bar-code-product.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e5ae-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6e5ae-124">Additional resources</span></span>

[<span data-ttu-id="6e5ae-125">Konfigurowanie masek kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="6e5ae-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]