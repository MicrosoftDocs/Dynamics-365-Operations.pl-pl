---
title: Konfigurowanie kodów kreskowych
description: W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.
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
ms.openlocfilehash: 52801e0d09b1d7da50719966700ca45275d702f7
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057285"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="4ced9-103">Konfigurowanie kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="4ced9-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4ced9-104">W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ced9-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4ced9-105">Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników.</span><span class="sxs-lookup"><span data-stu-id="4ced9-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="4ced9-106">Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych.</span><span class="sxs-lookup"><span data-stu-id="4ced9-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="4ced9-107">Towary można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="4ced9-107">You can set up products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="4ced9-108">Produkt może mieć więcej niż jeden kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="4ced9-108">Products can have more than one bar code.</span></span> <span data-ttu-id="4ced9-109">Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu.</span><span class="sxs-lookup"><span data-stu-id="4ced9-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="4ced9-110">Kody kreskowe mogą uwzględniać wagę lub cenę produktu.</span><span class="sxs-lookup"><span data-stu-id="4ced9-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="4ced9-111">Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="4ced9-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="4ced9-112">Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany.</span><span class="sxs-lookup"><span data-stu-id="4ced9-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="4ced9-113">Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu.</span><span class="sxs-lookup"><span data-stu-id="4ced9-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="4ced9-114">Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym.</span><span class="sxs-lookup"><span data-stu-id="4ced9-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="4ced9-115">Usługa Commerce używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów.</span><span class="sxs-lookup"><span data-stu-id="4ced9-115">Commerce uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="4ced9-116">Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów.</span><span class="sxs-lookup"><span data-stu-id="4ced9-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="4ced9-117">W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="4ced9-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="4ced9-118">Kody kreskowe można tworzyć ręcznie lub automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4ced9-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="4ced9-119">Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.</span><span class="sxs-lookup"><span data-stu-id="4ced9-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="4ced9-120">[Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="4ced9-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="4ced9-121">[Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="4ced9-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="4ced9-122">Konfigurowanie ustawień kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="4ced9-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="4ced9-123">Tworzenie kodów kreskowych dla produktów.</span><span class="sxs-lookup"><span data-stu-id="4ced9-123">Create bar codes for products.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ced9-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4ced9-124">Additional resources</span></span>

[<span data-ttu-id="4ced9-125">Konfigurowanie masek kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="4ced9-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
