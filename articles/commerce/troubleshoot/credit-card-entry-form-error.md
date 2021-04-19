---
title: Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja Metoda płatności nie jest załadowana i wyświetlany jest komunikat o błędzie.
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
ms.openlocfilehash: d2c5f01d17df79c9b23fd513aaeb5c0605d657e9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801778"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="98636-103">Strona wprowadzania karty kredytowej pokazuje błąd podczas realizacji zamówienia</span><span class="sxs-lookup"><span data-stu-id="98636-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98636-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc, gdy sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="98636-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="98636-105">opis</span><span class="sxs-lookup"><span data-stu-id="98636-105">Description</span></span>

<span data-ttu-id="98636-106">Po otwarciu strony realizacji zamówienia dla sklepu internetowego sekcja **Metoda płatności** nie jest załadowana i wyświetlany jest następujący komunikat o błędzie: „Wystąpił błąd.</span><span class="sxs-lookup"><span data-stu-id="98636-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="98636-107">Spróbuj ponownie później”.</span><span class="sxs-lookup"><span data-stu-id="98636-107">Please try again later."</span></span>

![Błąd Moduł płatności](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="98636-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="98636-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="98636-110">Oczekiwanie na wygaśnięcie pamięci podręcznej jednostki Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="98636-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="98636-111">Ustawienia usługi płatności na stronie realizacji zamówienia sklepu internetowego są buforowane w jednostce skalowania Commerce Scale Unit i mogą potrwać do 15 minut, aby pojawić się w witrynie e-commerce.</span><span class="sxs-lookup"><span data-stu-id="98636-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="98636-112">Te ustawienia usługi płatności obejmują zmiany identyfikatora konta handlowca, klucza interfejsu API w chmurze oraz różne ustawienia konfiguracji związane z metodą płatności.</span><span class="sxs-lookup"><span data-stu-id="98636-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98636-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="98636-113">Additional resources</span></span>

[<span data-ttu-id="98636-114">Konfigurowanie kanału online</span><span class="sxs-lookup"><span data-stu-id="98636-114">Set up an online channel</span></span>](../channel-setup-online.md)
