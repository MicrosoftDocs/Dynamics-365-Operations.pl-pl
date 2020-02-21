---
title: Ulepszona obsługa towarów śledzonych w partii
description: W tym temacie opisano ulepszenia dotyczące obsługi partii (w zakresie pozycji śledzonych w partii) podczas procesu księgowania zestawień.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: ecff18f0a34d22ef359f473fa6aaaff16c811bb6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004212"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="ef31f-103">Ulepszona obsługa pozycji śledzonych w partii</span><span class="sxs-lookup"><span data-stu-id="ef31f-103">Improved handling of batch-tracked items</span></span>


[!include [banner](includes/banner.md)]


<span data-ttu-id="ef31f-104">W punkcie sprzedaży (POS) nie można w momencie sprzedaży przechwytywać identyfikatorów partii dla pozycji śledzonych w partii.</span><span class="sxs-lookup"><span data-stu-id="ef31f-104">In Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="ef31f-105">Jednak w przypadku określonych konfiguracji, gdy sprzedaż jest księgowana w centrali w ramach procesu księgowania zamówień odbiorcy lub zestawień, system Microsoft Dynamics oczekuje, że istnieją prawidłowe numery partii dla towarów śledzonych w partii oraz że będą one używane w procesie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="ef31f-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="ef31f-106">Jeśli dla produktów są dostępne prawidłowe numery partii, będą one używane w procesie fakturowania zamówień odbiorcy oraz procesie fakturowania zamówień sprzedaży na podstawie księgowania zestawienia.</span><span class="sxs-lookup"><span data-stu-id="ef31f-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="ef31f-107">W przeciwnym razie nie będzie można wykonać księgowania w ramach procesu fakturowania zamówień odbiorcy, a użytkownik w punkcie sprzedaży zobaczy komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ef31f-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="ef31f-108">Następnie proces księgowania zestawienia przejdzie do stanu błędu.</span><span class="sxs-lookup"><span data-stu-id="ef31f-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="ef31f-109">Ten stan błędu występuje nawet wtedy, gdy dla produktów został włączony ujemny poziom zapasów.</span><span class="sxs-lookup"><span data-stu-id="ef31f-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="ef31f-110">Ulepszenia wprowadzone w rozwiązaniu Retail w wersji 10.0.4 i nowszych umożliwiają zagwarantowanie, że w sytuacji, gdy dla towarów śledzonych w partii włączono ujemny poziom zapasów, fakturowanie zamówień odbiorców i fakturowanie zamówień sprzedaży za pośrednictwem księgowania zestawienia nie będzie blokowane dla tych towarów, gdy ilość zapasów będzie równa 0 (zero) lub gdy numer partii będzie niedostępny.</span><span class="sxs-lookup"><span data-stu-id="ef31f-110">Improvements that have been made in Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="ef31f-111">Gdy numery partii są niedostępne, ta nowa funkcjonalność używa dla wierszy sprzedaży domyślnego identyfikatora partii.</span><span class="sxs-lookup"><span data-stu-id="ef31f-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="ef31f-112">Aby zdefiniować domyślny identyfikator partii, który będzie używany dla zamówień odbiorców, na skróconej karcie **Zamówienie** na karcie **Zamówienia odbiorców** na stronie **Parametry handlowe** ustaw wartość pola **Domyślny identyfikator partii**.</span><span class="sxs-lookup"><span data-stu-id="ef31f-112">To define the default batch ID that is used for customer orders, on the **Commerce parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="ef31f-113">Aby zdefiniować domyślny identyfikator partii, który będzie używany podczas fakturowania zamówień sprzedaży za pośrednictwem fakturowania zestawienia, na skróconej karcie **Aktualizacja zapasów** na karcie **Księgowanie** na stronie **Parametry handlowe** ustaw wartość pola **Domyślny identyfikator partii**.</span><span class="sxs-lookup"><span data-stu-id="ef31f-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Commerce parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="ef31f-114">Ta funkcjonalność jest dostępna tylko wtedy, gdy dla konkretnego magazynu sklepu i towarów jest włączona funkcja zaawansowanego magazynowania.</span><span class="sxs-lookup"><span data-stu-id="ef31f-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="ef31f-115">W późniejszym wydaniu ta funkcjonalność będzie również obsługiwana w scenariuszach, w których nie jest używana funkcja zaawansowanego zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="ef31f-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="ef31f-116">W wersji 10.0.5 rozwiązania Retail została wprowadzona pomoc techniczna do ulepszonej obsługi towarów śledzonych w partii podczas księgowania zestawienia dla scenariuszy niezaawansowanego zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="ef31f-116">Support for improved handling of batch-tracked items during statement posting for non-advanced warehouse management scenarios was introduced in Retail version 10.0.5.</span></span>
