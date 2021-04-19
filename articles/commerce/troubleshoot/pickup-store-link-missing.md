---
title: Opcja pobrania nie jest wyświetlana na stronach szczegółów koszyka lub produktu
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 46eeed18bb547035603d7e9a01e8f131a2393f01
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801634"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="21f8a-103">Opcja „Odbierz” nie pojawia się na stronach koszyka ani szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="21f8a-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21f8a-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="21f8a-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="21f8a-105">opis</span><span class="sxs-lookup"><span data-stu-id="21f8a-105">Description</span></span>

<span data-ttu-id="21f8a-106">Opcja **Odbierz** nie pojawia się na stronach koszyka ani szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="21f8a-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="21f8a-107">Na poniższej ilustracji pokazano przykład strony, która zawiera przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Pobierz ten przycisk](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="21f8a-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="21f8a-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="21f8a-110">Włączanie rozszerzenia BOPIS w konstruktorze witryn portalu Commerce</span><span class="sxs-lookup"><span data-stu-id="21f8a-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="21f8a-111">Aby włączyć rozszerzenie „zakup online, odbiór w sklepie” (BOPIS) w Konstruktorze witryn commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="21f8a-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="21f8a-112">Wybieranie witryny.</span><span class="sxs-lookup"><span data-stu-id="21f8a-112">Select your site.</span></span>
1. <span data-ttu-id="21f8a-113">Wybierz **Ustawienia witryny**, a następnie wybierz **Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="21f8a-114">Upewnij się, że opcja **Wyłącz BOPIS** jest wyczyszczona.</span><span class="sxs-lookup"><span data-stu-id="21f8a-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="21f8a-115">Konfigurowanie trybów dostawy w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="21f8a-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="21f8a-116">Aby skonfigurować funkcję metod dostawy w siedzibie firmy Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="21f8a-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="21f8a-117">Przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="21f8a-118">Upewnij się, że został utworzony tryb dostawy **Odbioru Klienta** oraz że są do niego przypisane produkty i adresy.</span><span class="sxs-lookup"><span data-stu-id="21f8a-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="21f8a-119">Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="21f8a-120">W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="21f8a-121">Upewnij się, że tryb **Metoda dostawy: odbiór** jest poprawnie skonfigurowany.</span><span class="sxs-lookup"><span data-stu-id="21f8a-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="21f8a-122">Konfigurowanie płatności zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="21f8a-122">Configure customer orders payments</span></span>

<span data-ttu-id="21f8a-123">Aby skonfigurować płatności za zamówienia klientów w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="21f8a-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="21f8a-124">Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="21f8a-125">W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.</span><span class="sxs-lookup"><span data-stu-id="21f8a-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="21f8a-126">Na skróconej karcie **Płatności** upewnij się, że pola **Warunki płatności** i **Metoda płatności** są poprawnie skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="21f8a-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21f8a-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="21f8a-127">Additional resources</span></span>

[<span data-ttu-id="21f8a-128">Konfiguruj BOPIS</span><span class="sxs-lookup"><span data-stu-id="21f8a-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="21f8a-129">Włączanie wielu metod dostawy dla zamówień klientów</span><span class="sxs-lookup"><span data-stu-id="21f8a-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="21f8a-130">Płatności zamówień wielokanałowych rozwiązania Commerce</span><span class="sxs-lookup"><span data-stu-id="21f8a-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="21f8a-131">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="21f8a-131">Store selector module</span></span>](../store-selector.md)
