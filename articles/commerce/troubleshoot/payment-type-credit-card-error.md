---
title: Typem płatności musi być błąd karty kredytowej na stronie zamówienia sprzedaży
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy po zsynchronizowaniu zamówienia na stronie zamówienia sprzedaży zostanie wyświetlony komunikat o błędzie.
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
ms.openlocfilehash: eabc64acc74645c7e6c7c4ab5794ed9fdb9dc997
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801682"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="9bcac-103">Błąd „Typ płatności musi być kartą kredytową” na stronie zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9bcac-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9bcac-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy po zsynchronizowaniu zamówienia na stronie zamówienia sprzedaży zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="9bcac-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="9bcac-105">opis</span><span class="sxs-lookup"><span data-stu-id="9bcac-105">Description</span></span>

<span data-ttu-id="9bcac-106">Po otwarciu strony zamówienia sprzedaży po zsynchronizowaniu zamówienia pojawia się następujący komunikat o błędzie: „Typ płatności musi być kartą kredytową, ponieważ określono numer karty kredytowej”.</span><span class="sxs-lookup"><span data-stu-id="9bcac-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Typem płatności musi być błąd karty kredytowej](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="9bcac-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="9bcac-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="9bcac-109">Ustawianie typu płatności w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="9bcac-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="9bcac-110">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Warunki płatności**.</span><span class="sxs-lookup"><span data-stu-id="9bcac-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="9bcac-111">W lewym okienku wybierz warunki płatności.</span><span class="sxs-lookup"><span data-stu-id="9bcac-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="9bcac-112">Upewnij się, że w polu **Typ płatności** wybrano **Kartę kredytową**.</span><span class="sxs-lookup"><span data-stu-id="9bcac-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bcac-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9bcac-113">Additional resources</span></span>

[<span data-ttu-id="9bcac-114">Księgowanie sprzedaży i płatności online</span><span class="sxs-lookup"><span data-stu-id="9bcac-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
