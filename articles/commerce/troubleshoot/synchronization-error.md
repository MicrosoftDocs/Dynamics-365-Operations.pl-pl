---
title: Błąd synchronizacji zamówienia związany z domyślną usługą płatności
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021134"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="8d1d8-103">Błąd synchronizacji zamówienia związany z domyślną usługą płatności</span><span class="sxs-lookup"><span data-stu-id="8d1d8-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d1d8-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="8d1d8-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="8d1d8-105">opis</span><span class="sxs-lookup"><span data-stu-id="8d1d8-105">Description</span></span>

<span data-ttu-id="8d1d8-106">Podczas synchronizowania zamówienia online wyświetlany jest następujący komunikat o błędzie: „Do przetwarzania transakcji kartami kredytowymi musi być domyślna usługa płatności”.</span><span class="sxs-lookup"><span data-stu-id="8d1d8-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Brak domyślnego błędu usługi płatności](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="8d1d8-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="8d1d8-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="8d1d8-109">Potwierdź lub ustaw domyślną usługę płatności w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="8d1d8-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="8d1d8-110">Aby potwierdzić lub ustawić domyślną usługę płatności w Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8d1d8-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8d1d8-111">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Usługi płatności**.</span><span class="sxs-lookup"><span data-stu-id="8d1d8-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="8d1d8-112">Upewnij się, że w ustawieniach **domyślnego procesora dla nowych kart kredytowych** jest ustawiona wartość **Tak** dla jednej usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="8d1d8-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d1d8-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8d1d8-113">Additional resources</span></span>

[<span data-ttu-id="8d1d8-114">Konfiguracja, autoryzacja i przechwytywanie karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="8d1d8-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)