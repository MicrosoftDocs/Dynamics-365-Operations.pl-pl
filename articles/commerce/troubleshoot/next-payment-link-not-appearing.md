---
title: Zapisz dla mojej następnej opcji płatności nie jest wyświetlany
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy pole wyboru Zapisz dla mojej następnej płatności nie jest wyświetlane w obszarze Metoda płatności na stronie realizacji zamówienia w witrynie e-commerce.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 3a4fbcd522651ed1b82b72b751ff6ead44c94a71
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585485"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="70245-103">Opcja „Zapisz do następnej płatności” nie pojawia się</span><span class="sxs-lookup"><span data-stu-id="70245-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="70245-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy pole wyboru **Zapisz dla mojej następnej płatności** nie jest wyświetlane w obszarze **Metoda płatności na stronie realizacji zamówienia** w witrynie e-commerce.</span><span class="sxs-lookup"><span data-stu-id="70245-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="70245-105">opis</span><span class="sxs-lookup"><span data-stu-id="70245-105">Description</span></span>

<span data-ttu-id="70245-106">Pole wyboru **Zapisz dla mojej następnej płatności** nie jest widoczne w sekcji **Metoda płatności** na stronie realizacji zamówienia w witrynie e-commerce.</span><span class="sxs-lookup"><span data-stu-id="70245-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="70245-107">Na poniższej ilustracji pokazano przykład strony realizacji zamówienia, która zawiera pole wyboru **Zapisz dla następnej płatności**.</span><span class="sxs-lookup"><span data-stu-id="70245-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Zapisz dla pola wyboru Następna płatność w module Płatność](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="70245-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="70245-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="70245-110">Sprawdź, czy program Dynamics 365 Payment Connector dla Adyen jest poprawnie skonfigurowany w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="70245-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="70245-111">Aby sprawdzić, czy Dynamics 365 Payment Connector dla Adyen jest poprawnie skonfigurowany w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="70245-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="70245-112">Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.</span><span class="sxs-lookup"><span data-stu-id="70245-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="70245-113">Wybierz sklep internetowy.</span><span class="sxs-lookup"><span data-stu-id="70245-113">Select the online store.</span></span>
1. <span data-ttu-id="70245-114">Na skróconej karcie **Konta płatności** upewnij się, że ustawienie **Zezwalaj na zapisywanie informacji o płatności w polu e-commerce** ma wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="70245-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Zezwalaj na zapisywanie informacji o płatności w polu e-commerce w programie Commerce Headquarters](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="70245-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="70245-116">Additional resources</span></span>

[<span data-ttu-id="70245-117">Moduł płatności</span><span class="sxs-lookup"><span data-stu-id="70245-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="70245-118">Zapisywanie instrumentów płatniczych online za pomocą łącznika Adyen</span><span class="sxs-lookup"><span data-stu-id="70245-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
