---
title: Wykluczanie produktów z określonymi stanami cyklu życia produktu
description: W tym temacie wyjaśniono, jak wykluczyć produkty na podstawie ich stanu cyklu życia, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645099"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="e7b52-103">Wykluczanie produktów z określonymi stanami cyklu życia produktu</span><span class="sxs-lookup"><span data-stu-id="e7b52-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7b52-104">Zwolnione produkty i zwolnione wersje produktu zawierają pole **Stan cyklu życia produktu**.</span><span class="sxs-lookup"><span data-stu-id="e7b52-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="e7b52-105">To pole umożliwia między innymi kontrolowanie, które produkty są uwzględniane podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e7b52-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="e7b52-106">Istnieje możliwość dodawania, usuwania i edytowania stanów cyklu zgodnie z potrzebami, przechodząc do **Zarządzanie informacjami o produktach \> Konfiguracja \> Stan cyklu życia produktu**.</span><span class="sxs-lookup"><span data-stu-id="e7b52-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="e7b52-107">Dla każdego stanu cyklu życia produktu ustaw opcję **Jest aktywna dla planowania** na *Tak*, jeśli produkty, które mają ten stan, powinny być uwzględnione podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e7b52-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="e7b52-108">Jeśli opcja jest ustawiona na wartość *Nie*, skojarzone produkty i warianty będą wykluczone ze wszystkich planów głównych i wszystkich obliczeń na poziomie BOM.</span><span class="sxs-lookup"><span data-stu-id="e7b52-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="e7b52-109">Zwolnione produkty i warianty, w których pole **Stan cyklu życia produktu** pozostaje puste, są traktowane tak, jakby miały stan cyklu życia produktu, w którym opcja **Jest aktywna dla planowania** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="e7b52-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="e7b52-110">Innymi słowy, zostaną one uwzględnione podczas planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="e7b52-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="e7b52-111">Aby uniknąć niepotrzebnych sugestii dotyczących dostaw, zdecydowanie zaleca się, aby skojarzyć wszystkie przestarzałe zwolnione produkty i warianty z stanem cyklu życia produktu, w którym opcja **Jest aktywna dla planowania** jest ustawiona na wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="e7b52-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="e7b52-112">Ta metoda jest szczególnie ważna podczas pracy z wariantami konfiguracji produktu, które nie są ponownie używane, ponieważ ułatwiają one zapobieganie powstawania odpadów.</span><span class="sxs-lookup"><span data-stu-id="e7b52-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e7b52-113">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="e7b52-113">Related resources</span></span>

<span data-ttu-id="e7b52-114">Aby uzyskać więcej informacji na temat stanów cyklu życia produktów, zapoznaj się z [Omówienie stanów cyklu życia produktu](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="e7b52-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="e7b52-115">Aby uzyskać szczegółowe informacje, które obejmują kroki korzystania ze stanów cyklu życia produktu w celu wykluczenia produktów z planowania głównego i obliczeń na poziomie BOM, zobacz [Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="e7b52-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>
