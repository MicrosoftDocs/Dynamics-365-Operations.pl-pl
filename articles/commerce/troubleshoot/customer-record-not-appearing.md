---
title: Rekordy odbiorcy nie są wyświetlane w programie Commerce Headquarters
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy rekordy klientów nie są natychmiast wyświetlane w programie Commerce Headquarters.
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
ms.openlocfilehash: 5499e3c059c9e735df87ef8b462d446e0710d90c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801802"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="dd18a-103">Rekordy odbiorcy nie są wyświetlane w programie Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="dd18a-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd18a-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy rekordy klientów nie są natychmiast wyświetlane w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dd18a-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="dd18a-105">opis</span><span class="sxs-lookup"><span data-stu-id="dd18a-105">Description</span></span>

<span data-ttu-id="dd18a-106">Gdy tworzysz nowy rekord odbiorcy za pomocą przepływu rejestracji w sklepie e-commerce, odpowiadający mu rekord odbiorcy nie zostanie natychmiast wyświetlony w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dd18a-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="dd18a-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="dd18a-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="dd18a-108">Wyłącz tworzenie odbiorcy w trybie asynchronicznym</span><span class="sxs-lookup"><span data-stu-id="dd18a-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd18a-109">Wyłączenie asynchronicznego tworzenia odbiorcy może mieć wpływ na wydajność systemu, ponieważ utworzenie każdego rekordu spowoduje utworzenie żądania w czasie rzeczywistym do programu Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dd18a-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="dd18a-110">Ponadto jeśli w programie Commerce Headquarters zostanie u dołu (na przykład podczas przepływów obsługi), wszelkie nowe przepływy tworzenia odbiorcy będą powodować błędy.</span><span class="sxs-lookup"><span data-stu-id="dd18a-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="dd18a-111">Aby wyłączyć tworzenie odbiorcy w trybie asynchronicznym w programie Commerce Headquarters, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dd18a-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="dd18a-112">Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="dd18a-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="dd18a-113">Jeśli nie używasz jeszcze profilu funkcji kanału online, utwórz go.</span><span class="sxs-lookup"><span data-stu-id="dd18a-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="dd18a-114">Upewnij się, że opcja **Utwórz klienta w trybie asynchronicznym** ma wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="dd18a-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="dd18a-115">Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.</span><span class="sxs-lookup"><span data-stu-id="dd18a-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="dd18a-116">Wybierz sklep internetowy, dla których chcesz wyłączyć asynchroniczne tworzenie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dd18a-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="dd18a-117">Na karcie **Ogólne** upewnij się, że w polu **Profil funkcji** jest ustawiony profil funkcji, który jest ustawiony dla kanału online.</span><span class="sxs-lookup"><span data-stu-id="dd18a-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd18a-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="dd18a-118">Additional resources</span></span>

[<span data-ttu-id="dd18a-119">Konfigurowanie dzierżawy B2C w module Commerce</span><span class="sxs-lookup"><span data-stu-id="dd18a-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
