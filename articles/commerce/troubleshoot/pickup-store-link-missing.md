---
title: Opcja pobrania nie jest wyświetlana na stronach szczegółów koszyka lub produktu
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020820"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="687e2-103">Opcja „Odbierz” nie pojawia się na stronach koszyka ani szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="687e2-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="687e2-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="687e2-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="687e2-105">opis</span><span class="sxs-lookup"><span data-stu-id="687e2-105">Description</span></span>

<span data-ttu-id="687e2-106">Opcja **Odbierz** nie pojawia się na stronach koszyka ani szczegółów produktu.</span><span class="sxs-lookup"><span data-stu-id="687e2-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="687e2-107">Na poniższej ilustracji pokazano przykład strony, która zawiera przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="687e2-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Pobierz ten przycisk](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="687e2-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="687e2-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="687e2-110">Włączanie rozszerzenia BOPIS w konstruktorze witryn portalu Commerce</span><span class="sxs-lookup"><span data-stu-id="687e2-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="687e2-111">Aby włączyć rozszerzenie „zakup online, odbiór w sklepie” (BOPIS) w Konstruktorze witryn commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="687e2-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="687e2-112">Wybieranie witryny.</span><span class="sxs-lookup"><span data-stu-id="687e2-112">Select your site.</span></span>
1. <span data-ttu-id="687e2-113">Wybierz **Ustawienia witryny**, a następnie wybierz **Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="687e2-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="687e2-114">Upewnij się, że opcja **Wyłącz BOPIS** jest wyczyszczona.</span><span class="sxs-lookup"><span data-stu-id="687e2-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="687e2-115">Konfigurowanie trybów dostawy w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="687e2-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="687e2-116">Aby skonfigurować funkcję metod dostawy w siedzibie firmy Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="687e2-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="687e2-117">Przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="687e2-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="687e2-118">Upewnij się, że został utworzony tryb dostawy **Odbioru Klienta** oraz że są do niego przypisane produkty i adresy.</span><span class="sxs-lookup"><span data-stu-id="687e2-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="687e2-119">Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.</span><span class="sxs-lookup"><span data-stu-id="687e2-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="687e2-120">W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.</span><span class="sxs-lookup"><span data-stu-id="687e2-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="687e2-121">Upewnij się, że tryb **Metoda dostawy: odbiór** jest poprawnie skonfigurowany.</span><span class="sxs-lookup"><span data-stu-id="687e2-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="687e2-122">Konfigurowanie płatności zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="687e2-122">Configure customer orders payments</span></span>

<span data-ttu-id="687e2-123">Aby skonfigurować płatności za zamówienia klientów w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="687e2-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="687e2-124">Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.</span><span class="sxs-lookup"><span data-stu-id="687e2-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="687e2-125">W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.</span><span class="sxs-lookup"><span data-stu-id="687e2-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="687e2-126">Na skróconej karcie **Płatności** upewnij się, że pola **Warunki płatności** i **Metoda płatności** są poprawnie skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="687e2-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="687e2-127">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="687e2-127">Additional resources</span></span>

[<span data-ttu-id="687e2-128">Konfiguruj BOPIS</span><span class="sxs-lookup"><span data-stu-id="687e2-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="687e2-129">Włączanie wielu metod dostawy dla zamówień klientów</span><span class="sxs-lookup"><span data-stu-id="687e2-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="687e2-130">Płatności zamówień wielokanałowych rozwiązania Commerce</span><span class="sxs-lookup"><span data-stu-id="687e2-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="687e2-131">Moduł wyboru sklepu</span><span class="sxs-lookup"><span data-stu-id="687e2-131">Store selector module</span></span>](../store-selector.md)
