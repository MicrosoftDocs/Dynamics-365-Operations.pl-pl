---
title: Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.
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
ms.openlocfilehash: b4fd37a3c45f2559c9659f072ca0b6f02e712f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018267"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="b64b0-103">Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień</span><span class="sxs-lookup"><span data-stu-id="b64b0-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b64b0-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.</span><span class="sxs-lookup"><span data-stu-id="b64b0-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="b64b0-105">opis</span><span class="sxs-lookup"><span data-stu-id="b64b0-105">Description</span></span>

<span data-ttu-id="b64b0-106">Po złożeniu zamówienia płatność jest natychmiast rozliczana w portalu Adyen, mimo że zamówienie sprzedaży nie zostało zafakturowane ani wysłane.</span><span class="sxs-lookup"><span data-stu-id="b64b0-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="b64b0-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="b64b0-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="b64b0-108">Konfigurowanie ręcznego przechwytywania płatności handlu elektronicznego w portalu Adyen</span><span class="sxs-lookup"><span data-stu-id="b64b0-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="b64b0-109">Aby skonfigurować ręczne przechwytywanie dla płatności handlu elektronicznego w portalu Adyen, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b64b0-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="b64b0-110">Zaloguj się do portalu usługi Adyen.</span><span class="sxs-lookup"><span data-stu-id="b64b0-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="b64b0-111">W prawym górnym rogu wybierz konto handlowca dla kanału handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="b64b0-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="b64b0-112">Na górnym pasku nawigacyjnym wybierz opcję **Konto**, a następnie wybierz opcję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="b64b0-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="b64b0-113">W polu **Przechwyć opóźnienie** wybierz opcję **ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="b64b0-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Ustawienie przechwycenia opóźnienia w portalu Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="b64b0-115">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b64b0-115">Additional resources</span></span>

[<span data-ttu-id="b64b0-116">Przechwycenie płatności Adyen</span><span class="sxs-lookup"><span data-stu-id="b64b0-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="b64b0-117">Łącznik płatności usługi Dynamics 365 dla Adyen</span><span class="sxs-lookup"><span data-stu-id="b64b0-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="b64b0-118">Skonfiguruj łącznik płatności Adyen dla Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b64b0-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
