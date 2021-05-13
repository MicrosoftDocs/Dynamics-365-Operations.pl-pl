---
title: Błąd synchronizacji zamówienia związany z domyślną usługą płatności
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.
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
ms.openlocfilehash: 45eeae751051b58e1c9e725eb4ed4b5240026e7f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801442"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="a3ca1-103">Błąd synchronizacji zamówienia związany z domyślną usługą płatności</span><span class="sxs-lookup"><span data-stu-id="a3ca1-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a3ca1-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="a3ca1-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="a3ca1-105">opis</span><span class="sxs-lookup"><span data-stu-id="a3ca1-105">Description</span></span>

<span data-ttu-id="a3ca1-106">Podczas synchronizowania zamówienia online wyświetlany jest następujący komunikat o błędzie: „Do przetwarzania transakcji kartami kredytowymi musi być domyślna usługa płatności”.</span><span class="sxs-lookup"><span data-stu-id="a3ca1-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Brak domyślnego błędu usługi płatności](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="a3ca1-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="a3ca1-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="a3ca1-109">Potwierdź lub ustaw domyślną usługę płatności w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a3ca1-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="a3ca1-110">Aby potwierdzić lub ustawić domyślną usługę płatności w Commerce headquarters, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a3ca1-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a3ca1-111">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Usługi płatności**.</span><span class="sxs-lookup"><span data-stu-id="a3ca1-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="a3ca1-112">Upewnij się, że w ustawieniach **domyślnego procesora dla nowych kart kredytowych** jest ustawiona wartość **Tak** dla jednej usługi płatności.</span><span class="sxs-lookup"><span data-stu-id="a3ca1-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3ca1-113">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3ca1-113">Additional resources</span></span>

[<span data-ttu-id="a3ca1-114">Konfiguracja, autoryzacja i przechwytywanie karty kredytowej</span><span class="sxs-lookup"><span data-stu-id="a3ca1-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)