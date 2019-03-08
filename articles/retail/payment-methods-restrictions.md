---
title: Ograniczanie metod płatności dla zwrotów bez paragonu
description: W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "315919"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="50a9c-103">Ograniczanie metod płatności dla zwrotów bez paragonu</span><span class="sxs-lookup"><span data-stu-id="50a9c-103">Restrict payment methods for returns without a receipt</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="50a9c-104">Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany na etapie konfiguracji systemu.</span><span class="sxs-lookup"><span data-stu-id="50a9c-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="50a9c-105">W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.</span><span class="sxs-lookup"><span data-stu-id="50a9c-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="50a9c-106">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="50a9c-106">Set up payment methods</span></span>

<span data-ttu-id="50a9c-107">Aby skonfigurować metody płatności, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="50a9c-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="50a9c-108">Utwórz formy płatności akceptowane w całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="50a9c-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="50a9c-109">Utwórz typy i numery kart na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="50a9c-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="50a9c-110">Jeśli będą przyjmowane karty kredytowe lub debetowe, trzeba utworzyć jeden typ metody płatności kartami, a następnie utworzyć typy i numery kart na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="50a9c-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="50a9c-111">Konfigurowanie metod płatności sklepu.</span><span class="sxs-lookup"><span data-stu-id="50a9c-111">Set up store payment methods.</span></span> <span data-ttu-id="50a9c-112">Skojarz typy metod płatności z poszczególnymi sklepami, a następnie wprowadź dla każdego typu metody płatności ustawienia właściwe dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="50a9c-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="50a9c-113">Skonfiguruj metody płatności kartą dla sklepów.</span><span class="sxs-lookup"><span data-stu-id="50a9c-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="50a9c-114">Skonfiguruj karty dla każdej formy płatności akceptowanej w sklepie.</span><span class="sxs-lookup"><span data-stu-id="50a9c-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="50a9c-115">![Konfiguracja sklepu detalicznego](media/NoReceiptReturns1.png "Konfiguracja sklepu detalicznego")</span><span class="sxs-lookup"><span data-stu-id="50a9c-115">![Retail Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="50a9c-116">Ograniczanie metod płatności dla zwrotów bez paragonu</span><span class="sxs-lookup"><span data-stu-id="50a9c-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="50a9c-117">Dla każdej metody płatności na stronie **Zarządzanie sklepu detalicznym** w obszarze **Zwroty bez paragonu** wybierz dla ustawienia **Ogranicz dla zwrotów bez paragonu** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="50a9c-117">For each store payment method, on the **Retail store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="50a9c-118">Domyślną wartością tego ustawienia jest **Nie**, co zapewnia, że metoda płatności jest dozwolona dla zwrotów.</span><span class="sxs-lookup"><span data-stu-id="50a9c-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="50a9c-119">Po wybraniu dla ustawienia **Ogranicz zwroty bez paragonu** wartości **Tak**, dla wybranej metody płatności nie będą możliwe zwroty.</span><span class="sxs-lookup"><span data-stu-id="50a9c-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="50a9c-120">![Metoda płatności w sklepie detalicznym](media/NoReceiptReturns3.png "Metoda płatności w sklepie detalicznym")</span><span class="sxs-lookup"><span data-stu-id="50a9c-120">![Retail Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="50a9c-121">Kiedy kasjer wybiera metodę płatności, dla której obowiązuje ograniczenie zwrotów bez paragonu, pojawia się komunikat przypominający o sprawdzeniu dopuszczalnych metod płatności.</span><span class="sxs-lookup"><span data-stu-id="50a9c-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="50a9c-122">![Dopuszczalne metody płatności](media/NoReceiptReturns4.png "Dopuszczalne metody płatności")</span><span class="sxs-lookup"><span data-stu-id="50a9c-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="50a9c-123">Jeśli dla transakcji istnieją zarówno zwrot z dokumentem przyjęcia, jak i zwrot bez paragonu, warunek ograniczenia nie zostanie zastosowany, ponieważ transakcja będzie przepływem pracy zwrotu z dokumentem przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="50a9c-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

