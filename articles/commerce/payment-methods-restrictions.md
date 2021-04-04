---
title: Ograniczanie metod płatności dla zwrotów bez paragonu
description: W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: fc087ea24ebbebd5acd1cf37fdfd5c9422d44be8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257056"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="9e835-103">Ograniczanie metod płatności dla zwrotów bez paragonu</span><span class="sxs-lookup"><span data-stu-id="9e835-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9e835-104">Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany na etapie konfiguracji systemu.</span><span class="sxs-lookup"><span data-stu-id="9e835-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="9e835-105">W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.</span><span class="sxs-lookup"><span data-stu-id="9e835-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="9e835-106">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="9e835-106">Set up payment methods</span></span>

<span data-ttu-id="9e835-107">Aby skonfigurować metody płatności, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="9e835-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="9e835-108">Utwórz formy płatności akceptowane w całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="9e835-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="9e835-109">Utwórz typy i numery kart na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="9e835-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="9e835-110">Jeśli będą przyjmowane karty kredytowe lub debetowe, trzeba utworzyć jeden typ metody płatności kartami, a następnie utworzyć typy i numery kart na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="9e835-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="9e835-111">Konfigurowanie metod płatności sklepu.</span><span class="sxs-lookup"><span data-stu-id="9e835-111">Set up store payment methods.</span></span> <span data-ttu-id="9e835-112">Skojarz typy metod płatności z poszczególnymi sklepami, a następnie wprowadź dla każdego typu metody płatności ustawienia właściwe dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="9e835-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="9e835-113">Skonfiguruj metody płatności kartą dla sklepów.</span><span class="sxs-lookup"><span data-stu-id="9e835-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="9e835-114">Skonfiguruj karty dla każdej formy płatności akceptowanej w sklepie.</span><span class="sxs-lookup"><span data-stu-id="9e835-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="9e835-115">![Ustawienia sklepu](media/NoReceiptReturns1.png "Ustawienia sklepu detalicznego")</span><span class="sxs-lookup"><span data-stu-id="9e835-115">![Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="9e835-116">Ograniczanie metod płatności dla zwrotów bez paragonu</span><span class="sxs-lookup"><span data-stu-id="9e835-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="9e835-117">Dla każdej metody płatności na stronie **Zarządzanie sklepem detalicznym** w obszarze **Zwroty bez paragonu** wybierz dla ustawienia **Ogranicz dla zwrotów bez paragonu** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9e835-117">For each store payment method, on the **Store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="9e835-118">Domyślną wartością tego ustawienia jest **Nie**, co zapewnia, że metoda płatności jest dozwolona dla zwrotów.</span><span class="sxs-lookup"><span data-stu-id="9e835-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="9e835-119">Po wybraniu dla ustawienia **Ogranicz zwroty bez paragonu** wartości **Tak**, dla wybranej metody płatności nie będą możliwe zwroty.</span><span class="sxs-lookup"><span data-stu-id="9e835-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="9e835-120">![Metoda płatności sklepu](media/NoReceiptReturns3.png "Metoda płatności sklepu detalicznego")</span><span class="sxs-lookup"><span data-stu-id="9e835-120">![Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="9e835-121">Kiedy kasjer wybiera metodę płatności, dla której obowiązuje ograniczenie zwrotów bez paragonu, pojawia się komunikat przypominający o sprawdzeniu dopuszczalnych metod płatności.</span><span class="sxs-lookup"><span data-stu-id="9e835-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="9e835-122">![Dopuszczalne metody płatności](media/NoReceiptReturns4.png "Dopuszczalne metody płatności")</span><span class="sxs-lookup"><span data-stu-id="9e835-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="9e835-123">Jeśli dla transakcji istnieją zarówno zwrot z dokumentem przyjęcia, jak i zwrot bez paragonu, warunek ograniczenia nie zostanie zastosowany, ponieważ transakcja będzie przepływem pracy zwrotu z dokumentem przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="9e835-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 



[!INCLUDE[footer-include](../includes/footer-banner.md)]