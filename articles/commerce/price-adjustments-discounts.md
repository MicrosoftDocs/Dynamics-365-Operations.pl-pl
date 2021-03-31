---
title: Korekty ceny i rabaty
description: Ten artykuł zawiera informacje dotyczące korekt cen i rabatów w Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d64632d7726fa5093bd04232790cae3f75938ae5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231231"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="be333-103">Korekty ceny i rabaty</span><span class="sxs-lookup"><span data-stu-id="be333-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="be333-104">Ten artykuł zawiera informacje dotyczące korekt cen i rabatów w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="be333-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="be333-105">W Commerce możesz korygować ceny produktów, a także skonfigurować rabaty stosowane do towaru lub transakcji w punkcie sprzedaży, zamówienia sprzedaży (POS) w biurze obsługi lub zamówienia online.</span><span class="sxs-lookup"><span data-stu-id="be333-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="be333-106">Do grup cen mogą być podłączone zarówno korekty ceny i rabaty.</span><span class="sxs-lookup"><span data-stu-id="be333-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="be333-107">Zarówno w przypadku korekty ceny, jak i rabatów, można określić pojedynczy datę rozpoczęcia i datę zakończenia lub okres cykliczny, kod rabatu i kilka dodatkowych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="be333-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="be333-108">Korekty ceny i rabaty mogą dotyczyć produktów, wariantów lub kategorii.</span><span class="sxs-lookup"><span data-stu-id="be333-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="be333-109">W przypadku zastosowania więcej niż jednego rabatu do produktu odbiorca może otrzymać jeden rabat lub rabat połączony.</span><span class="sxs-lookup"><span data-stu-id="be333-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="be333-110">Commerce automatycznie zastosuje rabat lub kombinację rabatów oferującą odbiorcy najlepszą cenę.</span><span class="sxs-lookup"><span data-stu-id="be333-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="be333-111">Podczas ustawiania korekty ceny lub rabatu należy sprawdzić, czy grupy cen są przypisane do właściwych kanałów, katalogów, przynależności lub programów lojalnościowych, do których ma mieć zastosowanie rabat.</span><span class="sxs-lookup"><span data-stu-id="be333-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="be333-112">Ponadto jeśli chcesz automatycznie wygenerować identyfikator rabatu, możesz ustawić sekwencje numerów na stronie **Parametry handlu** zanim zdefiniujesz nowy rabat lub korektę ceny lub rabat.</span><span class="sxs-lookup"><span data-stu-id="be333-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="be333-113">Korekty ceny lub rabaty można usunąć.</span><span class="sxs-lookup"><span data-stu-id="be333-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="be333-114">Jednak informacje statystyczne zostaną utracone.</span><span class="sxs-lookup"><span data-stu-id="be333-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="be333-115">Typy rabatów</span><span class="sxs-lookup"><span data-stu-id="be333-115">Types of discounts</span></span>

<span data-ttu-id="be333-116">Istnieje wiele typów rabatów:</span><span class="sxs-lookup"><span data-stu-id="be333-116">There are many types of discounts:</span></span>

- <span data-ttu-id="be333-117">**Prosty rabat** — pojedynczy procent lub kwota.</span><span class="sxs-lookup"><span data-stu-id="be333-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="be333-118">**Rabat ilościowy** — stosowany przy zakupie co najmniej dwóch produktów.</span><span class="sxs-lookup"><span data-stu-id="be333-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="be333-119">**Rabat łączony** — stosowany przy zakupie określonej kombinacji produktów.</span><span class="sxs-lookup"><span data-stu-id="be333-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="be333-120">**Rabat progowy** — stosowany przy sumie transakcji powyżej określonej kwoty.</span><span class="sxs-lookup"><span data-stu-id="be333-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="be333-121">**Rabat oparty na metodach płatności** — Rabat stosowany w przypadku, gdy suma transakcji jest większa niż określona kwota i określony typ płatności (na przykład gotówka, karta kredytowa lub debetowa) jest używany do celów płatności.</span><span class="sxs-lookup"><span data-stu-id="be333-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="be333-122">**Rabat wysyłkowy** — Rabat stosowany, gdy suma transakcji przekracza określoną kwotę, a zamówienie jest objęte określonym sposobem dostawy (na przykład dostawa w ciągu dwóch dni lub dostawa z dnia na dzień).</span><span class="sxs-lookup"><span data-stu-id="be333-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="be333-123">Z grupami cen mogą być skojarzone zarówno korekty ceny i rabaty.</span><span class="sxs-lookup"><span data-stu-id="be333-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="be333-124">Grupy cen mogą być następnie skojarzone z kanałami, katalogami, przynależnościami i programami lojalnościowymi.</span><span class="sxs-lookup"><span data-stu-id="be333-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]