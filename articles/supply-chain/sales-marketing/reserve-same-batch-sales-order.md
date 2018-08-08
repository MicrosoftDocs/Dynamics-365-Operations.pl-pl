---
title: "Rezerwowanie takiej samej partii na potrzeby zamówienia sprzedaży"
description: "Ten artykuł przedstawia sposób konfigurowania produktu w celu umożliwienia rezerwacji zapasów z jednej partii zapasów."
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2d6089d07b0f8bc1a36703b5b1c2f24af72770d5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="40ab5-103">Rezerwowanie takiej samej partii na potrzeby zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="40ab5-103">Reserve the same batch for a sales order</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40ab5-104">Ten artykuł przedstawia sposób konfigurowania produktu w celu umożliwienia rezerwacji zapasów z jednej partii zapasów.</span><span class="sxs-lookup"><span data-stu-id="40ab5-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="40ab5-105">Rezerwacja tej samej partii umożliwia rezerwowanie zapasu dla wiersza zamówienia sprzedaży z jednej partii zapasów.</span><span class="sxs-lookup"><span data-stu-id="40ab5-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="40ab5-106">Na przykład klient zamawiający tapety może zażądać, by całe zamówienie zawierało towar z jednej partii, aby uniknąć różnic między rolkami.</span><span class="sxs-lookup"><span data-stu-id="40ab5-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="40ab5-107">Aby skonfigurować produktu do użycia rezerwacji tej samej partii, w grupie modeli towaru, grupie wymiarów śledzenia i grupie wymiarów magazynowania muszą być aktywne następujące ustawienia przypisane do produktu:</span><span class="sxs-lookup"><span data-stu-id="40ab5-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="40ab5-108">**Grupy modeli towarów** — grupa musi mieć zaznaczone pola **Wybór tej samej partii** i **Konsoliduj zapotrzebowanie** w grupie pól **rezerwacji** dla zasad zapasów.</span><span class="sxs-lookup"><span data-stu-id="40ab5-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="40ab5-109">**Grupy wymiarów śledzenia** — grupa mieć zaznaczone pole **plan zapotrzebowania wg wymiaru** dla numeru partii.</span><span class="sxs-lookup"><span data-stu-id="40ab5-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="40ab5-110">**Grupy wymiarów magazynowania** — grupa musi mieć zaznaczone pole **plan zapotrzebowania wg wymiaru** dla opcji **Oddział** i **Magazyn**.</span><span class="sxs-lookup"><span data-stu-id="40ab5-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="40ab5-111">Podczas rezerwowania zapasów produktu w wierszu zamówienia sprzedaży, dla którego zdefiniowano dla wybór tej samej partii, program Microsoft Dynamics 365 for Finance and Operations próbuje zarezerwować zamówioną ilość z jednej partii zapasów.</span><span class="sxs-lookup"><span data-stu-id="40ab5-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="40ab5-112">Uwzględnione są również wszelkie specyficzne wymagania atrybutów partii.</span><span class="sxs-lookup"><span data-stu-id="40ab5-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="40ab5-113">Jeśli w pojedynczej partii nie ma wystarczającej ilości towaru, zostanie wyświetlona strona **Konflikt rezerwacji tej samej partii**.</span><span class="sxs-lookup"><span data-stu-id="40ab5-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="40ab5-114">Na tej stronie opisano problemy, a także akcje, które należy wykonać, aby kontynuować wykonywanie rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="40ab5-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="40ab5-115">Następujące warunki mogą uniemożliwić zarezerwowane partii:</span><span class="sxs-lookup"><span data-stu-id="40ab5-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="40ab5-116">Dla kodu dyspozycji partii jest zaznaczona opcja **Blokuj rezerwację** dla sprzedaży oznaczonych jako **zablokowano**.</span><span class="sxs-lookup"><span data-stu-id="40ab5-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="40ab5-117">Partia wygasła, na podstawie daty ważności oraz jakiekolwiek dni możliwej sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="40ab5-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="40ab5-118">Element nadal można uznać za do rezerwacji, jeśli grupa modeli pozycji dla towaru jest ewidencjonowana według zasady FEFO, a okres przydatności jest kryterium pobrania.</span><span class="sxs-lookup"><span data-stu-id="40ab5-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="40ab5-119">Partia nie ma wystarczającej liczby pozostałych dni przydatności (według daty ważności, daty przydatności i liczby dni możliwej sprzedaży u odbiorcy).</span><span class="sxs-lookup"><span data-stu-id="40ab5-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>





