---
title: Konfigurowanie kodów kreskowych
description: W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b7a668f8b44c5f573957a91ab19a8b7fac7a95ba
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024897"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="487b4-103">Konfigurowanie kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="487b4-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="487b4-104">W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="487b4-104">This article describes how to use bar codes in Dynamics 365 Retail.</span></span>

<span data-ttu-id="487b4-105">Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników.</span><span class="sxs-lookup"><span data-stu-id="487b4-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="487b4-106">Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych.</span><span class="sxs-lookup"><span data-stu-id="487b4-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="487b4-107">Towary detaliczne można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="487b4-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="487b4-108">Produkt może mieć więcej niż jeden kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="487b4-108">Products can have more than one bar code.</span></span> <span data-ttu-id="487b4-109">Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu.</span><span class="sxs-lookup"><span data-stu-id="487b4-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="487b4-110">Kody kreskowe mogą uwzględniać wagę lub cenę produktu.</span><span class="sxs-lookup"><span data-stu-id="487b4-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="487b4-111">Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="487b4-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="487b4-112">Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany.</span><span class="sxs-lookup"><span data-stu-id="487b4-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="487b4-113">Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu.</span><span class="sxs-lookup"><span data-stu-id="487b4-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="487b4-114">Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym.</span><span class="sxs-lookup"><span data-stu-id="487b4-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="487b4-115">Aplikacja Retail używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów.</span><span class="sxs-lookup"><span data-stu-id="487b4-115">Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="487b4-116">Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów.</span><span class="sxs-lookup"><span data-stu-id="487b4-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="487b4-117">W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="487b4-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="487b4-118">Kody kreskowe można tworzyć ręcznie lub automatycznie.</span><span class="sxs-lookup"><span data-stu-id="487b4-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="487b4-119">Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.</span><span class="sxs-lookup"><span data-stu-id="487b4-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="487b4-120">[Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="487b4-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="487b4-121">[Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="487b4-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="487b4-122">Konfigurowanie ustawień kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="487b4-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="487b4-123">Tworzenie kodów kreskowych dla produktów.</span><span class="sxs-lookup"><span data-stu-id="487b4-123">Create bar codes for products.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="487b4-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="487b4-124">Additional resources</span></span>

[<span data-ttu-id="487b4-125">Konfigurowanie masek kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="487b4-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
