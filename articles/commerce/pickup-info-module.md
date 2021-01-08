---
title: Moduł informacji o odbiorze
description: W tym temacie omówiono moduł informacji o odbiorze i opisano, jak dodać go do stron realizacji transakcji w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 61b97d72b6a397737c10476cd6c02764e60f10b1
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665355"
---
# <a name="pickup-information-module"></a><span data-ttu-id="f4f49-103">Moduł informacji o odbiorze</span><span class="sxs-lookup"><span data-stu-id="f4f49-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f4f49-104">W tym temacie omówiono moduł informacji o odbiorze i opisano, jak dodać go do stron realizacji transakcji w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4f49-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f4f49-105">Moduł informacji o odbiorze może być używany w module realizacji transakcji do wyświetlania informacji o odbiorze zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f4f49-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="f4f49-106">Klienci mogą przeglądać dostępne daty odbioru i przedziały czasowe, a następnie wybrać odpowiedni czas na odebranie zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f4f49-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="f4f49-107">Na przykład klient może odebrać zamówienie o godzinie 15:00 21 marca ze sklepu w San Francisco.</span><span class="sxs-lookup"><span data-stu-id="f4f49-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="f4f49-108">Przedziały czasowe odbioru dla odpowiednich sklepów muszą być skonfigurowane w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4f49-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="f4f49-109">Aby uzyskać więcej informacji, zobacz [Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="f4f49-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="f4f49-110">Jeśli moduł informacji o odbiorze jest utworzony na stronie kasy, ale dla sklepu wybranego do odbioru nie zdefiniowano żadnych przedziałów czasowych, moduł wyświetli informacje, ale użytkownik nie będzie mógł wybrać żadnych przedziałów czasowych.</span><span class="sxs-lookup"><span data-stu-id="f4f49-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="f4f49-111">Przedziały czasu są opcjonalne i nie są wymagane do złożenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f4f49-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="f4f49-112">Jeśli do odbioru w wielu sklepach wybrano wiele pozycji, moduł informacji o odbiorze pozwoli użytkownikowi wybrać przedział czasowy dla każdego sklepu, pod warunkiem, że dostępne są dla niego przedziały czasowe.</span><span class="sxs-lookup"><span data-stu-id="f4f49-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="f4f49-113">Obsługa przedziałów czasu i modułu informacji o odbiorze zamówienia jest dostępna w Dynamics 365 Commerce w wersji 10.0.15 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="f4f49-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="f4f49-114">Poniższa ilustracja przedstawia przykład wyboru przedziału czasu za pośrednictwem modułu informacji o odbiorze, znajdującego się na stronie realizacja transakcji.</span><span class="sxs-lookup"><span data-stu-id="f4f49-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Przykład modułu informacji o odbiorze na stronie realizacja zamówienia](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="f4f49-116">Właściwości modułu</span><span class="sxs-lookup"><span data-stu-id="f4f49-116">Module properties</span></span>

- <span data-ttu-id="f4f49-117">**Nagłówek** – Wprowadź nagłówek modułu.</span><span class="sxs-lookup"><span data-stu-id="f4f49-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="f4f49-118">Pokaż informacje o przedziale czasowym po złożeniu zamówienia</span><span class="sxs-lookup"><span data-stu-id="f4f49-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="f4f49-119">Po umieszczeniu zamówienia informacje o wybranym przedziale czasu można przejrzeć w [module potwierdzenia zamówienia](order-confirmation-module.md) oraz w [module szczegóły zamówienia](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="f4f49-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="f4f49-120">Oba moduły mają właściwość **Pokaż informacje o przedziale czasu**.</span><span class="sxs-lookup"><span data-stu-id="f4f49-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="f4f49-121">Aby można było wyświetlić wybrany przedział czasu w procesie przetwarzania, ta właściwość musi mieć ustawioną wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="f4f49-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="f4f49-122">Dodaj do strony moduł informacji o odbiorze kasy</span><span class="sxs-lookup"><span data-stu-id="f4f49-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="f4f49-123">Aby uzyskać instrukcje dotyczące dodawania modułu informacji o odbiorze do strony kasy i ustawiania wymaganych właściwości, należy zapoznać się z [Moduł realizacji transakcji](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="f4f49-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="f4f49-124">Na poniższej ilustracji przedstawiono przykład strony płatności handlu elektronicznego, która zawiera przedziały czasowe dla elementów zamówienia odbioru.</span><span class="sxs-lookup"><span data-stu-id="f4f49-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Przykład strony płatności handlu elektronicznego, która zawiera przedziały czasowe dla elementów zamówienia odbioru](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="f4f49-126">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f4f49-126">Additional resources</span></span>

[<span data-ttu-id="f4f49-127">Tworzenie i aktualizowanie przedziałów czasu na potrzeby odbiorów przez odbiorcę</span><span class="sxs-lookup"><span data-stu-id="f4f49-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="f4f49-128">Moduł realizacji transakcji</span><span class="sxs-lookup"><span data-stu-id="f4f49-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f4f49-129">Moduł potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="f4f49-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f4f49-130">Moduł szczegółów zamówienia</span><span class="sxs-lookup"><span data-stu-id="f4f49-130">Order details module</span></span>](account-management.md)
