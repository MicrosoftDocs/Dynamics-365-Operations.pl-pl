---
title: Konfigurowanie podatku dla zamówień online
description: Ten temat stanowi przegląd wyboru grupy podatków dla różnych typów zamówień w trybie online w Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 36dd3e8a3d47f02eed5b9c8bb79d773d98069376
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254848"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="de37d-103">Konfigurowanie podatku dla zamówień online</span><span class="sxs-lookup"><span data-stu-id="de37d-103">Configure sales tax for online orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="de37d-104">Ten temat stanowi przegląd wyboru grupy podatków dla różnych typów zamówień w trybie online.</span><span class="sxs-lookup"><span data-stu-id="de37d-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="de37d-105">Twój kanał handlu elektronicznego może chcieć obsługiwać takie opcje, jak dostawa lub odbiór zamówień online.</span><span class="sxs-lookup"><span data-stu-id="de37d-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="de37d-106">Stosowanie podatku jest oparte na opcji wybranej przez użytkowników w trybie online.</span><span class="sxs-lookup"><span data-stu-id="de37d-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="de37d-107">Jeśli klient witryny zdecyduje się kupić towar w trybie online i otrzymuje go na adres, podatek jest ustalany na podstawie ustawienia grupy podatków dla adresu wysyłkowego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="de37d-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="de37d-108">Jeśli odbiorca zdecyduje się na odebranie zakupionego towaru w sklepie, podatek jest ustalany na podstawie ustawienia grupy podatków dla sklepu odbioru.</span><span class="sxs-lookup"><span data-stu-id="de37d-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="de37d-109">Zamówienia wysłane na adres odbiorcy</span><span class="sxs-lookup"><span data-stu-id="de37d-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="de37d-110">Na ogół podatki dla zamówień w trybie online, które są wysyłane na adresy odbiorców, są definiowane przez miejsce docelowe.</span><span class="sxs-lookup"><span data-stu-id="de37d-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="de37d-111">Każda grupa podatków ma konfigurację podatku według lokalizacji docelowej sieci sprzedaży, w której firma może definiować szczegóły docelowe, takie jak powiat/region, województwo i miasto w postaci hierarchicznej.</span><span class="sxs-lookup"><span data-stu-id="de37d-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="de37d-112">Po złożeniu zamówienia online aparat podatkowy Commerce używa adresu dostawy każdego elementu zamówienia w zamówieniu i znajduje grupy podatków z pasującymi kryteriami podatkowymi opartymi na miejscu docelowym.</span><span class="sxs-lookup"><span data-stu-id="de37d-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="de37d-113">Na przykład w przypadku zamówienia online z adresem dostawy elementu zamówienia do San Francisco w Kalifornii aparat podatkowy znajdzie grupę podatków i kod podatku dla Kalifornii, a następnie odpowiednio obliczy podatek dla każdego elementu zamówienia.</span><span class="sxs-lookup"><span data-stu-id="de37d-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="de37d-114">Grupy podatków oparte na odbiorcach</span><span class="sxs-lookup"><span data-stu-id="de37d-114">Customer-based tax groups</span></span>

<span data-ttu-id="de37d-115">W centrali Commerce istnieją dwa miejsca, w których skonfigurowano grupy podatków dla odbiorców:</span><span class="sxs-lookup"><span data-stu-id="de37d-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="de37d-116">**Profil odbiorcy**</span><span class="sxs-lookup"><span data-stu-id="de37d-116">**Customer's profile**</span></span>
- <span data-ttu-id="de37d-117">**Adres wysyłkowy odbiorcy**</span><span class="sxs-lookup"><span data-stu-id="de37d-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="de37d-118">Jeśli profil odbiorcy ma skonfigurowaną grupę podatków</span><span class="sxs-lookup"><span data-stu-id="de37d-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="de37d-119">Rekord profilu odbiorcy w centrali może mieć skonfigurowaną grupę podatków, jednak w przypadku zamówień w trybie online grupa podatków skonfigurowana w profilu odbiorcy nie będzie używana przez aparat podatkowy.</span><span class="sxs-lookup"><span data-stu-id="de37d-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="de37d-120">Jeśli adres wysyłkowy odbiorcy ma skonfigurowaną grupę podatków</span><span class="sxs-lookup"><span data-stu-id="de37d-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="de37d-121">Jeśli rekord adresu wysyłkowego odbiorcy ma skonfigurowaną grupę podatków i zamówienie online (lub towar w wierszu) jest wysyłane na adres wysyłkowy odbiorcy, grupa podatków skonfigurowana w rekordzie adresu odbiorcy będzie używana przez aparat podatków do obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="de37d-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="de37d-122">Skonfiguruj grupę podatkową dla rekordu adresu wysyłkowego klienta</span><span class="sxs-lookup"><span data-stu-id="de37d-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="de37d-123">Aby skonfigurować grupę podatków dla rekordu adresu wysyłkowego odbiorcy w centrali Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="de37d-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="de37d-124">Przejdź do **Wszyscy odbiorcy**, a następnie wybierz żądanego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="de37d-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="de37d-125">Na skróconej karcie **Adresy** wybierz żądany adres, a następnie wybierz **Więcej opcji \> Zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="de37d-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="de37d-126">Na karcie **Ogólne**, na stronie **Zarządzanie adresami** ustaw wartość podatku zgodnie z potrzebą.</span><span class="sxs-lookup"><span data-stu-id="de37d-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="de37d-127">Grupa podatków jest definiowana przy użyciu adresu wysyłkowego wiersza zamówienia, a podatki oparte na miejscu docelowym są konfigurowane dla grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="de37d-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="de37d-128">Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="de37d-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="de37d-129">Odbiór zamówienia w sklepie</span><span class="sxs-lookup"><span data-stu-id="de37d-129">Order pickup in store</span></span>

<span data-ttu-id="de37d-130">W przypadku wierszy zamówienia z określonym odbiorem w sklepie lub przy krawężniku zostanie zastosowana grupa podatkowa z wybranego punktu odbioru.</span><span class="sxs-lookup"><span data-stu-id="de37d-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="de37d-131">Aby uzyskać szczegółowe informacje dotyczące konfigurowania grupy podatków dla danego sklepu, zapoznaj się z tematem [Konfigurowanie innych opcji podatków dla sklepów](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="de37d-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="de37d-132">Gdy wiersz zamówienia zostanie odebrany w sklepie, ustawienia podatkowe dotyczące adresu klienta (jeśli zostały skonfigurowane) zostaną zignorowane przez aparat podatkowy i zastosowana zostanie konfiguracja podatku sklepu odbioru.</span><span class="sxs-lookup"><span data-stu-id="de37d-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="de37d-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="de37d-133">Additional resources</span></span>

[<span data-ttu-id="de37d-134">Omówienie podatku</span><span class="sxs-lookup"><span data-stu-id="de37d-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="de37d-135">Wybieranie metody obliczania podatku w polu Źródło</span><span class="sxs-lookup"><span data-stu-id="de37d-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="de37d-136"> Przypisanie i zastąpienia podatku</span><span class="sxs-lookup"><span data-stu-id="de37d-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="de37d-137">Opcje Cała kwota i Obliczanie interwału dla kodów podatku</span><span class="sxs-lookup"><span data-stu-id="de37d-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="de37d-138">Obliczanie zwolnienia z podatku</span><span class="sxs-lookup"><span data-stu-id="de37d-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]