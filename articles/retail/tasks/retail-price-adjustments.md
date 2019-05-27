---
title: Korekty ceny detalicznej
description: Ta procedura prowadzi przez proces tworzenia korekty ceny detalicznej.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9427d3955e5442e301c416e2960e071ca5d85a3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550043"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="14208-103">Korekty ceny detalicznej</span><span class="sxs-lookup"><span data-stu-id="14208-103">Retail price adjustments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="14208-104">Ta procedura prowadzi przez proces tworzenia korekty ceny detalicznej.</span><span class="sxs-lookup"><span data-stu-id="14208-104">This procedure will walk through creating a retail price adjustment.</span></span> <span data-ttu-id="14208-105">Korekta ceny sprzedaży detalicznej może ustawiać cenę sprzedaży bezpośrednio lub modyfikować jej bazową cenę sprzedaży albo cenę sprzedaży z umowy handlowej.</span><span class="sxs-lookup"><span data-stu-id="14208-105">A retail price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="14208-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="14208-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="14208-107">Kliknij opcję Zarządzanie cenami i rabatami.</span><span class="sxs-lookup"><span data-stu-id="14208-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="14208-108">Kliknij kartę Korekta ceny.</span><span class="sxs-lookup"><span data-stu-id="14208-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="14208-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="14208-109">Click New.</span></span>
    * <span data-ttu-id="14208-110">W tym miejscu można tworzyć wszystkie najczęściej używane reguły cen i rabatów, w tym rabaty detaliczne, korekty cen, arkusze umów handlowych i reguły cen dla kategorii.</span><span class="sxs-lookup"><span data-stu-id="14208-110">From here you can create all of the most commonly used price and discount rules, including retail discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="14208-111">Kliknij opcję Korekta ceny.</span><span class="sxs-lookup"><span data-stu-id="14208-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="14208-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="14208-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="14208-113">Rozwiń sekcję Wiersze.</span><span class="sxs-lookup"><span data-stu-id="14208-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="14208-114">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="14208-114">Click Add.</span></span>
    * <span data-ttu-id="14208-115">W tym przykładzie w polu Produkt wpisz „81126”.</span><span class="sxs-lookup"><span data-stu-id="14208-115">For this example, enter '81126' in the Product field.</span></span>    <span data-ttu-id="14208-116">Następnie w polu Procent rabatu wpisz „10,0”.</span><span class="sxs-lookup"><span data-stu-id="14208-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="14208-117">Korekta ceny typu „procent rabatu” zmniejsza bazową cenę sprzedaży lub cenę sprzedaży z umowy handlowej.</span><span class="sxs-lookup"><span data-stu-id="14208-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="14208-118">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="14208-118">Click Add.</span></span>
    * <span data-ttu-id="14208-119">W tym przykładzie w polu Produkt wpisz „81125”.</span><span class="sxs-lookup"><span data-stu-id="14208-119">For this example, enter '81125' in the Product field.</span></span>    <span data-ttu-id="14208-120">Następnie w polu Metoda rabatowania wybierz opcję „Kwota rabatu gotówkowego”.</span><span class="sxs-lookup"><span data-stu-id="14208-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="14208-121">Na koniec w polu Kwota rabatu gotówkowego wpisz „5,0”.</span><span class="sxs-lookup"><span data-stu-id="14208-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="14208-122">Typ rabatu Kwota rabatu gotówkowego jest kwotą odjętą od ceny bazowej lub ceny w umowie handlowej.</span><span class="sxs-lookup"><span data-stu-id="14208-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="14208-123">Kliknij opcję Grupy cenowe.</span><span class="sxs-lookup"><span data-stu-id="14208-123">Click Price groups.</span></span>
    * <span data-ttu-id="14208-124">W polu Grupa cenowa wybierz opcję „RP-Houston”.</span><span class="sxs-lookup"><span data-stu-id="14208-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="14208-125">Spowoduje to skojarzenie korekty ceny ze sklepem w Houston.</span><span class="sxs-lookup"><span data-stu-id="14208-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="14208-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="14208-126">Click Save.</span></span>
11. <span data-ttu-id="14208-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="14208-127">Close the page.</span></span>
12. <span data-ttu-id="14208-128">W polu Stan wybierz wartość „Włączone”.</span><span class="sxs-lookup"><span data-stu-id="14208-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="14208-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="14208-129">Click Save.</span></span>
14. <span data-ttu-id="14208-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="14208-130">Close the page.</span></span>
15. <span data-ttu-id="14208-131">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="14208-131">Refresh the page.</span></span>

