---
title: Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego
description: W tym temacie opisano, jak ustawić limity ilości produktów w witrynach handlu elektronicznego typu business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1208b968e476ccbc7a726facf1db896c7bf3c36f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211184"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="1e0d5-103">Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="1e0d5-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e0d5-104">W tym temacie opisano, jak ustawić limity ilości produktów w witrynach handlu elektronicznego typu business-to-business (B2B).</span><span class="sxs-lookup"><span data-stu-id="1e0d5-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="1e0d5-105">Większość produktów ma jednostkę miary, która definiuje ich grupowanie.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="1e0d5-106">Grupowanie wpływa na sposób sprzedaży produktów.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="1e0d5-107">Niektóre produkty mogą mieć dodatkowe grupowanie według ilości.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="1e0d5-108">To grupowanie określa, czy produkty mogą być sprzedawane jako pojedyncze jednostki, czy jako wielokrotności oraz czy istnieje minimalny lub maksymalny limit ilości zamówienia, którego należy przestrzegać.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="1e0d5-109">Funkcja ograniczania ilości zapewnia, że minimalne, maksymalne, wielokrotne i standardowe ilości skonfigurowane w Microsoft Dynamics 365 Commerce (w domyślnych ustawieniach zamówienia lub w ustawieniach witryny do tworzenia witryn handlowych) są stosowane do zamówień klientów składanych na witryna handlowa.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="1e0d5-110">Limity ilości produktów nie są obecnie obsługiwane w punkcie sprzedaży (POS) i centrach obsługi telefonicznej.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="1e0d5-111">Wielu sprzedawców detalicznych oferuje możliwość składania zamówień klientów (zwanych również zamówieniami specjalnymi) w celu spełnienia różnych wymagań dotyczących produktów i spełnienia.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="1e0d5-112">Poniżej przedstawiono niektóre typowe scenariusze:</span><span class="sxs-lookup"><span data-stu-id="1e0d5-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="1e0d5-113">Klient chce, aby produkty w określonych wariantach były sprzedawane w wielokrotności kilku.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="1e0d5-114">Klient chce odebrać produkty ze sklepu lub lokalizacji innej niż ta, w której kupił produkty.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="1e0d5-115">Jednak standardy pakowania w sklepach różnią się od standardów pakowania w przypadku dystrybucji sprzedaży internetowej.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="1e0d5-116">Klient chce kupić produkt w limitowanej edycji, w którym obowiązuje maksymalny limit ilościowy dla przedmiotów, które można kupić.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="1e0d5-117">Włącz funkcję domyślnych ustawień zamówień w Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="1e0d5-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="1e0d5-118">Aby można było ustawić limity ilości produktów, w Commerce headquarters musi być włączona funkcja domyślnych ustawień zamówienia.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="1e0d5-119">Aby włączyć funkcję domyślnych ustawień kolejności, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="1e0d5-120">Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="1e0d5-121">Znajdź i wybierz opcję **Obsługuj witrynę i domyślne ustawienia zamówienia w zamówieniu klienta**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="1e0d5-122">W dolnej części prawego okienka wybierz opcję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="1e0d5-123">Określ ustawienia ilości</span><span class="sxs-lookup"><span data-stu-id="1e0d5-123">Define quantity settings</span></span> 

<span data-ttu-id="1e0d5-124">Na stronie **Ustawienia domyślne zamówień** można wprowadzić parametry zamówień.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="1e0d5-125">Aby zdefiniować ustawienia ilości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="1e0d5-126">Wybierz Produkt **Retail i Commerce \> Produkty i kategorie \> Zwolnione produkty według kategorii**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="1e0d5-127">Wybór zwalnianego produktu.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-127">Select a released product.</span></span>
1. <span data-ttu-id="1e0d5-128">W okienku akcji na karcie **Zarządzaj zapasami** w grupie **Ustawienia zamówienia** wybierz opcję **Ustawienia domyślne zamówień**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="1e0d5-129">Na stronie **Ustawienia domyślne zamówień**, na skróconej karcie **Zamówienie sprzedaży**, w sekcji **Ilość sprzedaży** skonfiguruj ilości sprzedaży produktów:</span><span class="sxs-lookup"><span data-stu-id="1e0d5-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="1e0d5-130">**Wielokrotność** — ilość, w wielokrotnościach, w których produkt może być kupowany.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="1e0d5-131">**Minimalna ilość zamówienia** — minimalna liczba produktów, które muszą zostać zakupione.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="1e0d5-132">**Maksymalna ilość zamówienia** — maksymalna liczba produktów, które mogą zostać zakupione.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="1e0d5-133">**Standardowa ilość zamówienia** — domyślna ilość wprowadzana automatycznie po wybraniu produktu.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="1e0d5-134">Włącz funkcję limitów ilości zamówienia B2B w Konstruktorze witryn Commerce</span><span class="sxs-lookup"><span data-stu-id="1e0d5-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="1e0d5-135">Aby włączyć funkcję limitów ilości zamówień B2B w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1e0d5-136">Przejdź do **Ustawień witryny \> Rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="1e0d5-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="1e0d5-137">W obszarze **Włącz limity ilości zamówienia** wybierz z menu rozwijanego opcję **Włącz dla odbiorców B2B**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1e0d5-138">Zaktualizowane ustawienia narzędzia do tworzenia witryn zaczną obowiązywać dopiero po zaktualizowaniu pliku app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="1e0d5-139">Aby uzyskać więcej informacji, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="1e0d5-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e0d5-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1e0d5-140">Additional resources</span></span>

[<span data-ttu-id="1e0d5-141">Konfigurowanie witryny handlu elektornicznego B2B</span><span class="sxs-lookup"><span data-stu-id="1e0d5-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="1e0d5-142">Tworzenie hierarchii modelowania organizacji dla organizacji B2B</span><span class="sxs-lookup"><span data-stu-id="1e0d5-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="1e0d5-143">Zarządzanie użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="1e0d5-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="1e0d5-144">Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B</span><span class="sxs-lookup"><span data-stu-id="1e0d5-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]