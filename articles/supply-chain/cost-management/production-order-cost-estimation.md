---
title: Szacowanie kosztu zlecenia produkcyjnego
description: "Ten artykuł zawiera informacje o szacowaniu kosztów produkcji. Szacowanie kosztów produkcji pokazuje prognozowane koszty zużycia materiałów i zdolności produkcyjnych w celu wytworzenia towaru w ilości określonej w planowanym zleceniu produkcyjnym."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3ea3998014eb9ac2fd4610b5d52bd792d4f73869
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="production-order-cost-estimation"></a><span data-ttu-id="bc772-104">Szacowanie kosztu zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="bc772-104">Production order cost estimation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bc772-105">Ten artykuł zawiera informacje o szacowaniu kosztów produkcji.</span><span class="sxs-lookup"><span data-stu-id="bc772-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="bc772-106">Szacowanie kosztów produkcji pokazuje prognozowane koszty zużycia materiałów i zdolności produkcyjnych w celu wytworzenia towaru w ilości określonej w planowanym zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="bc772-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="bc772-107">Po utworzeniu zlecenia produkcyjnego należy oszacować koszty produkcji.</span><span class="sxs-lookup"><span data-stu-id="bc772-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="bc772-108">Celem jest oszacowanie zużycia towaru i marszruty w procesie produkcji, ponieważ te szacunki są używane jako podstawa dla kolejnych procesów planowania i produkcji.</span><span class="sxs-lookup"><span data-stu-id="bc772-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="bc772-109">Szacowanie kosztu produkcji</span><span class="sxs-lookup"><span data-stu-id="bc772-109">Production cost estimation</span></span>
<span data-ttu-id="bc772-110">Szacunki kosztów produkcji bazują na następujących informacjach:</span><span class="sxs-lookup"><span data-stu-id="bc772-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="bc772-111">Ilość w zleceniu produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="bc772-111">The quantity on the production order</span></span>
-   <span data-ttu-id="bc772-112">Składniki w listach składowych (BOM)</span><span class="sxs-lookup"><span data-stu-id="bc772-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="bc772-113">Operacje marszruty w marszrucie produkcji</span><span class="sxs-lookup"><span data-stu-id="bc772-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="bc772-114">Koszty pośrednie dotyczące składników i operacji</span><span class="sxs-lookup"><span data-stu-id="bc772-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="bc772-115">Dane aktywnych kosztów na dzień obliczania</span><span class="sxs-lookup"><span data-stu-id="bc772-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="bc772-116">Jeśli listy BOM produkcji zawierają wiersze fantomowe, obliczenia odzwierciedlają składniki i operacje marszruty istniejące w tych fantomach.</span><span class="sxs-lookup"><span data-stu-id="bc772-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="bc772-117">Zadanie szacowania umożliwia ponowne obliczanie szacowanych kosztów, tak aby odzwierciedlały zaktualizowane informacje.</span><span class="sxs-lookup"><span data-stu-id="bc772-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="bc772-118">Na przykład zaktualizowanymi informacjami mogą być zmiany ilości w zleceniu produkcyjnym, składników w BOM produkcji, operacji marszruty w marszrucie produkcji, kosztów pośrednich dotyczących tych składników i operacji albo aktywnych kosztów na dzień ponownego obliczania.</span><span class="sxs-lookup"><span data-stu-id="bc772-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="bc772-119">Obliczanie szacowanych kosztów umożliwia również zaproponowanie ceny sprzedaży wytwarzanego towaru na podstawie metody „koszt plus narzut”.</span><span class="sxs-lookup"><span data-stu-id="bc772-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="bc772-120">Obliczenia szacowanych kosztów mogą opcjonalnie dotyczyć zamówień odniesienia odzwierciedlających inne zlecenia produkcyjne powiązane ze zleceniem produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="bc772-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="bc772-121">Wyświetlanie szacowanych kosztów</span><span class="sxs-lookup"><span data-stu-id="bc772-121">View the estimated costs</span></span>
<span data-ttu-id="bc772-122">Po wykonaniu szacowania wyniki można obejrzeć na stronie **Obliczanie ceny**.</span><span class="sxs-lookup"><span data-stu-id="bc772-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="bc772-123">Szacowanie powoduje obliczenie następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="bc772-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="bc772-124">**Koszt produkcji** — Koszt produkcji to górny wiersz szacowania.</span><span class="sxs-lookup"><span data-stu-id="bc772-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="bc772-125">Pokazuje on całkowity koszt realizacji zlecenia produkcyjnego oraz łączną cenę sprzedaży produkcji.</span><span class="sxs-lookup"><span data-stu-id="bc772-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="bc772-126">Jest to suma wszystkich wierszy kosztów w szacowaniu.</span><span class="sxs-lookup"><span data-stu-id="bc772-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="bc772-127">**Koszty marszrut lub zasobów** — Koszty marszrut lub zasobów to koszty operacji produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="bc772-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="bc772-128">Obejmują koszty elementów takich jak czas przezbrajania i czas procesu oraz koszty ogólne.</span><span class="sxs-lookup"><span data-stu-id="bc772-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="bc772-129">**Koszty materiałów** — Koszty materiałów to koszty i ceny składników BOM potrzebnych do wyprodukowania towaru.</span><span class="sxs-lookup"><span data-stu-id="bc772-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="bc772-130">Koszty te zostały uprzednio określone i wprowadzone w systemie.</span><span class="sxs-lookup"><span data-stu-id="bc772-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="bc772-131">Inne zastosowania szacowania kosztów</span><span class="sxs-lookup"><span data-stu-id="bc772-131">Other uses of cost estimation</span></span>
<span data-ttu-id="bc772-132">Szacowanie kosztów może także dostarczać następujących informacji:</span><span class="sxs-lookup"><span data-stu-id="bc772-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="bc772-133">Sensowne oferty cenowe.</span><span class="sxs-lookup"><span data-stu-id="bc772-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="bc772-134">Oszacowania zyskowności zamówienia.</span><span class="sxs-lookup"><span data-stu-id="bc772-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="bc772-135">Oszacowania wykorzystania surowców.</span><span class="sxs-lookup"><span data-stu-id="bc772-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="bc772-136">Porównania z informacjami o kosztach wcześniejszych produkcji.</span><span class="sxs-lookup"><span data-stu-id="bc772-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="bc772-137">Informacje o budżecie i prognozach.</span><span class="sxs-lookup"><span data-stu-id="bc772-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="bc772-138">Oszacowania rozmiaru produkcji wymaganego do utrzymania określonego kosztu.</span><span class="sxs-lookup"><span data-stu-id="bc772-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>





