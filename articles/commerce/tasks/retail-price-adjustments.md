---
title: Korekty ceny detalicznej
description: Ta procedura prowadzi przez proces tworzenia korekty cen sprzedaży.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbd2f818930424313e1d76aea4a257efa7c7b3be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232792"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="30a4d-103">Korekty ceny detalicznej</span><span class="sxs-lookup"><span data-stu-id="30a4d-103">Retail price adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30a4d-104">Ta procedura prowadzi przez proces tworzenia korekty cen sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="30a4d-104">This procedure will walk through creating a commerce price adjustment.</span></span> <span data-ttu-id="30a4d-105">Korekta ceny sprzedaży może ustawiać cenę sprzedaży bezpośrednio lub modyfikować jej bazową cenę sprzedaży albo cenę sprzedaży z umowy handlowej.</span><span class="sxs-lookup"><span data-stu-id="30a4d-105">A price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="30a4d-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="30a4d-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="30a4d-107">Kliknij opcję Zarządzanie cenami i rabatami.</span><span class="sxs-lookup"><span data-stu-id="30a4d-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="30a4d-108">Kliknij kartę Korekta ceny.</span><span class="sxs-lookup"><span data-stu-id="30a4d-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="30a4d-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="30a4d-109">Click New.</span></span>
    * <span data-ttu-id="30a4d-110">W tym miejscu można tworzyć wszystkie najczęściej używane reguły cen i rabatów, w tym rabaty, korekty cen, arkusze umów handlowych i reguły cen dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="30a4d-110">From here you can create all of the most commonly used price and discount rules, including discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="30a4d-111">Kliknij opcję Korekta ceny.</span><span class="sxs-lookup"><span data-stu-id="30a4d-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="30a4d-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="30a4d-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="30a4d-113">Rozwiń sekcję Wiersze.</span><span class="sxs-lookup"><span data-stu-id="30a4d-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="30a4d-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="30a4d-114">Click Add.</span></span>
    * <span data-ttu-id="30a4d-115">W tym przykładzie w polu Produkt wpisz „81126”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-115">For this example, enter '81126' in the Product field.</span></span> <span data-ttu-id="30a4d-116">Następnie w polu Procent rabatu wpisz „10,0”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="30a4d-117">Korekta ceny typu „procent rabatu” zmniejsza bazową cenę sprzedaży lub cenę sprzedaży z umowy handlowej.</span><span class="sxs-lookup"><span data-stu-id="30a4d-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="30a4d-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="30a4d-118">Click Add.</span></span>
    * <span data-ttu-id="30a4d-119">W tym przykładzie w polu Produkt wpisz „81125”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-119">For this example, enter '81125' in the Product field.</span></span> <span data-ttu-id="30a4d-120">Następnie w polu Metoda rabatowania wybierz opcję „Kwota rabatu gotówkowego”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="30a4d-121">Na koniec w polu Kwota rabatu gotówkowego wpisz „5,0”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="30a4d-122">Typ rabatu Kwota rabatu gotówkowego jest kwotą odjętą od ceny bazowej lub ceny w umowie handlowej.</span><span class="sxs-lookup"><span data-stu-id="30a4d-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="30a4d-123">Kliknij opcję Grupy cenowe.</span><span class="sxs-lookup"><span data-stu-id="30a4d-123">Click Price groups.</span></span>
    * <span data-ttu-id="30a4d-124">W polu Grupa cenowa wybierz opcję „RP-Houston”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="30a4d-125">Spowoduje to skojarzenie korekty ceny ze sklepem w Houston.</span><span class="sxs-lookup"><span data-stu-id="30a4d-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="30a4d-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="30a4d-126">Click Save.</span></span>
11. <span data-ttu-id="30a4d-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="30a4d-127">Close the page.</span></span>
12. <span data-ttu-id="30a4d-128">W polu Stan wybierz wartość „Włączone”.</span><span class="sxs-lookup"><span data-stu-id="30a4d-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="30a4d-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="30a4d-129">Click Save.</span></span>
14. <span data-ttu-id="30a4d-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="30a4d-130">Close the page.</span></span>
15. <span data-ttu-id="30a4d-131">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="30a4d-131">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]