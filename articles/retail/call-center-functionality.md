---
title: "Funkcja Biuro obsługi"
description: "Ten artykuł zawiera omówienie funkcji biura obsługi dostępnych w programie Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2c58f71230a0781ee957632b453ced86ca03b15a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="call-center-functionality"></a><span data-ttu-id="ca38d-103">Funkcje biura obsługi</span><span class="sxs-lookup"><span data-stu-id="ca38d-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ca38d-104">Ten artykuł zawiera omówienie funkcji biura obsługi dostępnych w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ca38d-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="ca38d-105">Program Dynamics 365 for Retail obsługuje też biura obsługi jako typ kanału sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ca38d-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="ca38d-106">W biurze obsługi pracownicy przyjmują zamówienia od odbiorców przez telefon i tworzą zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ca38d-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="ca38d-107">Funkcja centrum obsługi zawiera funkcje, które zostały zaprojektowane z myślą o ułatwieniu zbierania zamówień teleficznych i obsługi klienta w trakcie procesu realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ca38d-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="ca38d-108">Na przykład pracownicy biura obsługi mogą wprowadzać informacje o płatności bezpośrednio do zamówienia sprzedaży i mogą wyświetlać szczegółowe podsumowanie opłat i płatności przed przesłaniem zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ca38d-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="ca38d-109">Pracownicy mogą też kontrolować proces wyceny i mają dostęp do różnych danych o odbiorcach, produktach oraz cenach ze strony **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="ca38d-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="ca38d-110">Oprócz tego biura obsługi mają też rozszerzoną funkcję śledzenia historii i stanu zamówień odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ca38d-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="ca38d-111">Każde biuro obsługi może mieć własnych użytkowników, metody płatności, grupy cenowe, wymiary finansowe oraz metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="ca38d-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="ca38d-112">Opcje te można konfigurować podczas tworzenia biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="ca38d-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="ca38d-113">Dodatkowo na stronie **Biuro obsługi** można włączyć lub wyłączyć następujące grupy funkcji, które są unikatowe dla biur obsługi:</span><span class="sxs-lookup"><span data-stu-id="ca38d-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="ca38d-114">**Kończenie zamówienia** — Ta grupa zawiera funkcje, które odnoszą się do płatności i kończenia zamówienia na stronie **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="ca38d-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="ca38d-115">**Sprzedaż sterowana** — Ta grupa zawiera funkcje, które są powiązane z kodami źródłowymi, skryptami i żądaniami katalogu.</span><span class="sxs-lookup"><span data-stu-id="ca38d-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="ca38d-116">Jeśli włączysz te funkcje w ustawieniach biura obsługi, są one dostępne na stronie **Zamówienie sprzedaży** dla użytkowników, którzy są skojarzeni z biurem obsługi.</span><span class="sxs-lookup"><span data-stu-id="ca38d-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="ca38d-117">Większość tych funkcji wymaga dodatkowych ustawień przed użyciem.</span><span class="sxs-lookup"><span data-stu-id="ca38d-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="ca38d-118">Aby użytkownicy mogli tworzyć biura obsługi, trzeba ich dodać do biura obsługi jako użytkowników biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="ca38d-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="ca38d-119">Ten krok umożliwia obsługę konfiguracji i funkcji właściwych dla kanału biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="ca38d-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="ca38d-120">Oto kilka przykładów funkcji, które stają się dostępne:</span><span class="sxs-lookup"><span data-stu-id="ca38d-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="ca38d-121">Sprzedaż sterowana oferuje opcje konfiguracji dla skryptów telesprzedaży i obrazów produktów, ułatwiających pracę i wyświetlających wskazówki pracownikom sprzedaży przyjmujących zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ca38d-121">Guided selling provides configuration options for telesales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="ca38d-122">Nie można ukończyć zamówień dopóki pracownik sprzedaży nie zarejestruje co najmniej jednej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="ca38d-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="ca38d-123">Można skonfigurować reguły sprzedaży dodatkowej i wiązanej, aby sprzedawcy widzieli monity dotyczące promocji określonych produktów.</span><span class="sxs-lookup"><span data-stu-id="ca38d-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="ca38d-124">Pracownicy sprzedaży mogą rejestrować kod źródłowy dla katalogu, z którego odbiorca zamawia.</span><span class="sxs-lookup"><span data-stu-id="ca38d-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="ca38d-125">Pracownicy sprzedaży mogą dodawać kupony sprzedawców detalicznych do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ca38d-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="ca38d-126">Pracownicy sprzedaży mogą sprzedawać programy ciągłości.</span><span class="sxs-lookup"><span data-stu-id="ca38d-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="ca38d-127">Zamówienia mogą być wstrzymywane ręcznie lub automatycznie, aby wskazać, że wymagane jest dodatkowe badanie, zanim będzie można przetworzyć zamówienie.</span><span class="sxs-lookup"><span data-stu-id="ca38d-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





