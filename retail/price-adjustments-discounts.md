---
title: Korekty ceny i rabaty
description: "Ten artykuł zawiera informacje o korektach ceny i rabatach w programie Microsoft Dynamics 365 for Retail."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c96f7afdb095fd45b5dd88c7760a24226518f61c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="16f1f-103">Korekty ceny i rabaty</span><span class="sxs-lookup"><span data-stu-id="16f1f-103">Price adjustments and discounts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="16f1f-104">Ten artykuł zawiera informacje o korektach ceny i rabatach w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="16f1f-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="16f1f-105">W module Dynamics 365 for Retail użytkownik może dokonywać korygowania cen na produkty, a także konfigurowania rabatów, które są stosowane do wiersza towaru lub transakcji w punkcie sprzedaży, w zamówieniu sprzedaży biura obsługi lub w zamówieniu online.</span><span class="sxs-lookup"><span data-stu-id="16f1f-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="16f1f-106">Do grup cen mogą być podłączone zarówno korekty ceny i rabaty.</span><span class="sxs-lookup"><span data-stu-id="16f1f-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="16f1f-107">Zarówno w przypadku korekty ceny, jak i rabatów, można określić pojedynczy datę rozpoczęcia i datę zakończenia lub okres cykliczny, kod rabatu i kilka dodatkowych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="16f1f-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="16f1f-108">Korekty ceny i rabaty mogą dotyczyć produktów, wariantów lub kategorii.</span><span class="sxs-lookup"><span data-stu-id="16f1f-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="16f1f-109">W przypadku zastosowania więcej niż jednego rabatu do produktu odbiorca może otrzymać jeden rabat lub rabat połączony.</span><span class="sxs-lookup"><span data-stu-id="16f1f-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="16f1f-110">Program Dynamics 365 for Retail automatycznie zastosuje rabat lub kombinację rabatów oferującą odbiorcy najlepszą cenę.</span><span class="sxs-lookup"><span data-stu-id="16f1f-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="16f1f-111">Podczas ustawiania korekty ceny lub rabatu należy sprawdzić, czy grupy cen są przypisane do właściwych kanałów, katalogów, przynależności lub programów lojalnościowych, do których ma mieć zastosowanie rabat.</span><span class="sxs-lookup"><span data-stu-id="16f1f-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="16f1f-112">Ponadto jeśli chcesz automatycznie wygenerować identyfikator rabatu, możesz ustawić sekwencje numerów na stronie **Parametry handlu detalicznego** zanim zdefiniujesz nowy rabat lub korektę ceny lub rabat.</span><span class="sxs-lookup"><span data-stu-id="16f1f-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span> <span data-ttu-id="16f1f-113">**Uwaga:** Korekty ceny lub rabaty można usunąć.</span><span class="sxs-lookup"><span data-stu-id="16f1f-113">**Note:** You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="16f1f-114">Jednak informacje statystyczne zostaną utracone.</span><span class="sxs-lookup"><span data-stu-id="16f1f-114">However, statistical information will be lost.</span></span>

### <a name="types-of-discounts"></a><span data-ttu-id="16f1f-115">Typy rabatów</span><span class="sxs-lookup"><span data-stu-id="16f1f-115">Types of discounts</span></span>

<span data-ttu-id="16f1f-116">Istnieją cztery typy rabatów sieci sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="16f1f-116">There are four types of retail discounts:</span></span>

-   <span data-ttu-id="16f1f-117">**Prosty rabat** — pojedynczy procent lub kwota.</span><span class="sxs-lookup"><span data-stu-id="16f1f-117">**Simple discount** – A single percentage or amount.</span></span>
-   <span data-ttu-id="16f1f-118">**Rabat ilościowy** — stosowany przy zakupie co najmniej dwóch produktów.</span><span class="sxs-lookup"><span data-stu-id="16f1f-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
-   <span data-ttu-id="16f1f-119">**Rabat łączony** — stosowany przy zakupie określonej kombinacji produktów.</span><span class="sxs-lookup"><span data-stu-id="16f1f-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
-   <span data-ttu-id="16f1f-120">**Rabat progowy** — stosowany przy sumie transakcji powyżej określonej kwoty.</span><span class="sxs-lookup"><span data-stu-id="16f1f-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="16f1f-121">Z grupami cen mogą być skojarzone zarówno korekty ceny i rabaty.</span><span class="sxs-lookup"><span data-stu-id="16f1f-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="16f1f-122">Grupy cen mogą być następnie skojarzone z kanałami, katalogami, przynależnościami i programami lojalnościowymi.</span><span class="sxs-lookup"><span data-stu-id="16f1f-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>




