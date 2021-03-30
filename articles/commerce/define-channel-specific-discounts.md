---
title: Definiowanie rabatów właściwych dla kanału
description: Sprzedawcy detaliczni często ustawiają różne rabaty w różnych kanałach. W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 36b2d8f96f8545f9fa792e42c639b03e1e14e8ee
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213753"
---
# <a name="define-channel-specific-discounts"></a><span data-ttu-id="05111-104">Definiowanie rabatów specyficznych dla kanału</span><span class="sxs-lookup"><span data-stu-id="05111-104">Define channel-specific discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="05111-105">W tym temacie opisano pojęcia, które należy znać, aby tworzyć rabaty dla konkretnych kanałów.</span><span class="sxs-lookup"><span data-stu-id="05111-105">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span>

## <a name="channel-specific-discounts"></a><span data-ttu-id="05111-106">Rabaty właściwe dla kanału</span><span class="sxs-lookup"><span data-stu-id="05111-106">Channel-specific discounts</span></span>

<span data-ttu-id="05111-107">Sprzedawcy detaliczni często oferują różne rabaty w różnych kanałach.</span><span class="sxs-lookup"><span data-stu-id="05111-107">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="05111-108">To może zależeć od lokalnych uwarunkowań rynku lub być elementem konkurencji z innymi sprzedawcami detalicznymi.</span><span class="sxs-lookup"><span data-stu-id="05111-108">This may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="05111-109">Commerce używa grup cenowych do definiowania rabatów właściwych dla kanału.</span><span class="sxs-lookup"><span data-stu-id="05111-109">Commerce uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="05111-110">Grup cenowe mogą być skojarzone z jednym lub kilkoma następującymi elementami: kanały, katalogi, przynależności i programy lojalnościowe.</span><span class="sxs-lookup"><span data-stu-id="05111-110">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="05111-111">Ten artykuł dotyczy kanałów, ale te same pojęcia dotyczą rabatów katalogu, przynależności i programów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="05111-111">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="05111-112">Grupy cenowe</span><span class="sxs-lookup"><span data-stu-id="05111-112">Price groups</span></span>

<span data-ttu-id="05111-113">[![Grupy cenowe](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="05111-113">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="05111-114">Powyższy wykres ilustruje relację między jednostkami, które mogą znajdować się w transakcji (kanał, katalog, przynależność, odbiorca, karta lojalnościowa), a różnymi typami rabatów, które można skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="05111-114">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="05111-115">Wszystkie transakcje odbywają się w kanale, więc kanał na pewno będzie ujęty w transakcji.</span><span class="sxs-lookup"><span data-stu-id="05111-115">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="05111-116">Pozostałe elementy są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="05111-116">The remaining entities are optional.</span></span> <span data-ttu-id="05111-117">Na poszczególnych stronach danych głównych są łącza do powiązanej grupy cenowej, na której można wyświetlać i dodawać grupy cenowe w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="05111-117">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="05111-118">Grupa cenowa służy do tworzenia relacji czterech różnych typów elementów z rabatami, korektami cen i umowami handlowymi.</span><span class="sxs-lookup"><span data-stu-id="05111-118">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="05111-119">Dobrze jest zaplanować strategię nazywania grup cenowych, która pozwoli lepiej je uporządkować.</span><span class="sxs-lookup"><span data-stu-id="05111-119">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="05111-120">Jedną z możliwości jest używanie litery i cyfry na początku lub na końcu nazwy dla rozróżnienia typów.</span><span class="sxs-lookup"><span data-stu-id="05111-120">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="05111-121">Np. 1-xxxxx dla grup cenowych kanału i 2-xxxxx dla grup cenowych katalogu.</span><span class="sxs-lookup"><span data-stu-id="05111-121">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="05111-122">Dostępne są cztery strony zapytań, które koncentrują się na poszczególnych podmiotach handlowych, dla których są skojarzone rabaty.</span><span class="sxs-lookup"><span data-stu-id="05111-122">There are four inquiry pages that focus on each of the commerce entities that can have discounts associated to them.</span></span>

- <span data-ttu-id="05111-123">**Grupy cenowe kanału** — ta strona zawiera listę kanałów i rabatów połączonych ze sobą dla każdej grupy cenowej.</span><span class="sxs-lookup"><span data-stu-id="05111-123">**Channel channel price groups** – This page shows a list of channels and discounts linked together for each price group.</span></span>
- <span data-ttu-id="05111-124">**Grupy cenowe katalogu** — ta strona zawiera listę katalogów i rabatów połączonych ze sobą dla każdej grupy cenowej.</span><span class="sxs-lookup"><span data-stu-id="05111-124">**Catalog price groups** – This page shows a list of catalogs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="05111-125">**Grupy cenowe programów lojalnościowych** — ta strona zawiera listę programów lojalnościowych i rabatów połączonych ze sobą dla każdej grupy cenowej.</span><span class="sxs-lookup"><span data-stu-id="05111-125">**Loyalty price groups** – This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="05111-126">**Grupy cenowe przynależności** — ta strona zawiera listę przynależności i rabatów połączonych ze sobą dla każdej grupy cenowej.</span><span class="sxs-lookup"><span data-stu-id="05111-126">**Affiliation price groups** – This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="05111-127">Przykładowa konfiguracja rabatu kanału</span><span class="sxs-lookup"><span data-stu-id="05111-127">Example channel discount set up</span></span>

<span data-ttu-id="05111-128">Przykład poniżej ilustruje zadania niezbędne do skonfigurowania rabatu kanału.</span><span class="sxs-lookup"><span data-stu-id="05111-128">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1. <span data-ttu-id="05111-129">W tym przykładzie masz kanał **Houston** i chcesz utworzyć nowy rabat o nazwie **Powrót-do-szkoły**.</span><span class="sxs-lookup"><span data-stu-id="05111-129">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School**.</span></span>
2. <span data-ttu-id="05111-130">Ponieważ strategie cenowa i rabatów dają możliwość tworzenia rabatów kanału, to tworząc kanał, zawsze tworzysz grupę cenową właściwą dla kanału.</span><span class="sxs-lookup"><span data-stu-id="05111-130">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3. <span data-ttu-id="05111-131">Masz grupę cenową **Houston-GC**, która jest skojarzona z kanałem **Houston**.</span><span class="sxs-lookup"><span data-stu-id="05111-131">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4. <span data-ttu-id="05111-132">Po utworzeniu nowego rabatu **Powrót-do-szkoły** musisz kliknąć **Grupy cenowe** na górze strony **Rabat**.</span><span class="sxs-lookup"><span data-stu-id="05111-132">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="05111-133">Otworzy się strona **Grupy cenowe rabatów**.</span><span class="sxs-lookup"><span data-stu-id="05111-133">The **Discount price groups** page will open.</span></span> <span data-ttu-id="05111-134">Następnie kliknij **Nowa** i wybierz grupę cenową **Houston-GC**.</span><span class="sxs-lookup"><span data-stu-id="05111-134">Next, click **New** and select the **Houston-PG** price group.</span></span>
5. <span data-ttu-id="05111-135">Teraz można włączyć rabatu i przesunąć go do kanału.</span><span class="sxs-lookup"><span data-stu-id="05111-135">Now you can enable the discount and push it to the channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05111-136">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="05111-136">Additional resources</span></span>

[<span data-ttu-id="05111-137">Korekty cen i rabaty</span><span class="sxs-lookup"><span data-stu-id="05111-137">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]