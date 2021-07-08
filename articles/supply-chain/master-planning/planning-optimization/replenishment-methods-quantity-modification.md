---
title: Metody uzupełniania zapasów i modyfikacja ilości
description: Ten temat zawiera informacje na temat metod uzupełniania zapasów w optymalizacji planowania. Wyjaśnia również, w jaki sposób wielokrotność zamówienia dla produktu wpływa na wynik.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e0e671e624de2646a47647ef08d3567599b884
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261703"
---
# <a name="replenishment-methods-and-quantity-modification"></a><span data-ttu-id="0852a-104">Metody uzupełniania zapasów i modyfikacja ilości</span><span class="sxs-lookup"><span data-stu-id="0852a-104">Replenishment methods and quantity modification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0852a-105">Ten temat zawiera informacje na temat metod uzupełniania zapasów w optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="0852a-105">This topic provides information about replenishment methods in Planning Optimization.</span></span> <span data-ttu-id="0852a-106">Wyjaśnia również, w jaki sposób wielokrotność zamówienia dla produktu wpływa na wynik.</span><span class="sxs-lookup"><span data-stu-id="0852a-106">It also explains how the multiple order quantity for a product affects the result.</span></span>

<span data-ttu-id="0852a-107">Metody uzupełniania zapasów są również znane jako metody pokrycia i metody wielkości partii.</span><span class="sxs-lookup"><span data-stu-id="0852a-107">Replenishment methods are also known as coverage methods and lot-sizing methods.</span></span>

## <a name="coverage-codes"></a><span data-ttu-id="0852a-108">Kody zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="0852a-108">Coverage codes</span></span>

<span data-ttu-id="0852a-109">Planowanie optymalizacji można skonfigurować w taki sposób, aby korzystało z różnych metod uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="0852a-109">Planning Optimization can be configured to use different replenishment methods.</span></span> <span data-ttu-id="0852a-110">Metody uzupełniania zapasów są technikami, które system wykorzystuje do obliczania zapotrzebowania na dany produkt.</span><span class="sxs-lookup"><span data-stu-id="0852a-110">The replenishment methods are the techniques that the system uses to calculate requirements for a product.</span></span> <span data-ttu-id="0852a-111">Metody uzupełniania są zdefiniowane przez kody zakresu, które można ustawić na grupie zakresu lub na produkcie.</span><span class="sxs-lookup"><span data-stu-id="0852a-111">Replenishment methods are defined by coverage codes that you can set up on either the coverage group or the product.</span></span>

<span data-ttu-id="0852a-112">Następujące kody pokrycia mogą być użyte w optymalizacji planowania:</span><span class="sxs-lookup"><span data-stu-id="0852a-112">The following coverage codes can be used in Planning Optimization:</span></span>

- <span data-ttu-id="0852a-113">**Na okres** — metoda uzupełniania zapasów łączy całe zapotrzebowanie na dany okres w jedno zamówienie na dany produkt.</span><span class="sxs-lookup"><span data-stu-id="0852a-113">**Period** – The replenishment method combines all the demand for a period into one order for the product.</span></span> <span data-ttu-id="0852a-114">Zamówienie zostanie zaplanowane na pierwszy dzień okresu, a jego ilość będzie spełniać zapotrzebowania netto w ustalonym okresie.</span><span class="sxs-lookup"><span data-stu-id="0852a-114">The order will be planned for the first day of the period, and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="0852a-115">Okres rozpoczyna się od pierwszego zapotrzebowania na produkt i obejmuje zdefiniowany okres w czasie.</span><span class="sxs-lookup"><span data-stu-id="0852a-115">The period starts with the first demand of the product and covers the defined length of time.</span></span> <span data-ttu-id="0852a-116">Następny okres rozpocznie się od kolejnych wymagań dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="0852a-116">The next period will start with the next requirements of the product.</span></span> <span data-ttu-id="0852a-117">Kod pokrycia *Okres* jest często stosowany w przypadku nieprzewidywalnych losowań zapasów, produktów uzależnionych od pory roku lub produktów o wysokich kosztach.</span><span class="sxs-lookup"><span data-stu-id="0852a-117">The *Period* coverage code is often used for non-predictable inventory draw, season-influenced products, or high-cost products.</span></span> <span data-ttu-id="0852a-118">Na poniższej ilustracji pokazano przykład.</span><span class="sxs-lookup"><span data-stu-id="0852a-118">The following illustration shows an example.</span></span>

    <span data-ttu-id="0852a-119">![Przykład użycia kodu zapotrzebowania okresowego](./media/coverage-code-period.png "Przykład użycia kodu zapotrzebowania okresowego")</span><span class="sxs-lookup"><span data-stu-id="0852a-119">![Example of Period coverage code use](./media/coverage-code-period.png "Example of Period coverage code use")</span></span>

- <span data-ttu-id="0852a-120">**Wymaganie** — w metodzie uzupełniania zapasów system tworzy planowane zlecenie zakupu, przesunięcia lub produkcji na zapotrzebowanie na dany produkt.</span><span class="sxs-lookup"><span data-stu-id="0852a-120">**Requirement** – In the replenishment method, the system creates a planned purchase, transfer, or production order per requirement for the product.</span></span> <span data-ttu-id="0852a-121">Ta metoda jest używana dla drogich produktów, które mają nieregularny popyt.</span><span class="sxs-lookup"><span data-stu-id="0852a-121">This method is used for expensive products that have intermittent demand.</span></span> <span data-ttu-id="0852a-122">Kod *Zapotrzebowania* jest często używany w przypadku produktów konfigurowalnych lub scenariuszy produkcji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="0852a-122">The *Requirement* coverage code is often used for configurable products or make-to-order scenarios.</span></span> <span data-ttu-id="0852a-123">Na poniższej ilustracji pokazano przykład.</span><span class="sxs-lookup"><span data-stu-id="0852a-123">The following illustration shows an example.</span></span>

    <span data-ttu-id="0852a-124">![Przykład użycia kodu zapotrzebowania wymagania](./media/coverage-code-requirement.png "Przykład użycia kodu zapotrzebowania wymagania")</span><span class="sxs-lookup"><span data-stu-id="0852a-124">![Example of Requirement coverage code use](./media/coverage-code-requirement.png "Example of Requirement coverage code use")</span></span>

- <span data-ttu-id="0852a-125">**Minimum/Maksimum**</span><span class="sxs-lookup"><span data-stu-id="0852a-125">**Min./Max.**</span></span> <span data-ttu-id="0852a-126">— metoda uzupełniania zapasów jest oparta na poziomie zapasów.</span><span class="sxs-lookup"><span data-stu-id="0852a-126">– The replenishment method is based on the inventory level.</span></span> <span data-ttu-id="0852a-127">Określa uzupełnianie zapasów do określonego poziomu, gdy przewidywany poziom zapasów na stanie jest poniżej określonego progu.</span><span class="sxs-lookup"><span data-stu-id="0852a-127">It defines the replenishment of inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span> <span data-ttu-id="0852a-128">Ilość uzupełniania zapasów będzie różnicą między maksymalnym poziomem i przewidywanym poziomem zapasów.</span><span class="sxs-lookup"><span data-stu-id="0852a-128">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span> <span data-ttu-id="0852a-129">Kod zapotrzebowania *minimum/maksimum*</span><span class="sxs-lookup"><span data-stu-id="0852a-129">The *Min./Max.*</span></span> <span data-ttu-id="0852a-130">jest często używany dla przewidywalnego rysunku zapasów, wysokich biegaczy, lub tańszych produktów.</span><span class="sxs-lookup"><span data-stu-id="0852a-130">coverage code is often used for predictable inventory draw, high runners, or less expensive products.</span></span> <span data-ttu-id="0852a-131">Na poniższej ilustracji pokazano przykład.</span><span class="sxs-lookup"><span data-stu-id="0852a-131">The following illustration shows an example.</span></span>

    <span data-ttu-id="0852a-132">![Przykład użycia kodu pokrycia min./max.](./media/coverage-code-min-max.png "Przykład użycia kodu pokrycia min./max.")</span><span class="sxs-lookup"><span data-stu-id="0852a-132">![Example of Min./Max. coverage code use](./media/coverage-code-min-max.png "Example of Min./Max. coverage code use")</span></span>

- <span data-ttu-id="0852a-133">**Ręczna** — w metodzie uzupełniania system nie sugeruje zleceń zakupu, przesunięcia, czy produkcji produktu.</span><span class="sxs-lookup"><span data-stu-id="0852a-133">**Manual** – In the replenishment method, the system doesn't suggest purchase, transfer, or production orders for the product.</span></span> <span data-ttu-id="0852a-134">Zamiast tego, planista produktu jest odpowiedzialny za tworzenie wymaganych zamówień w celu uzupełnienia produktu.</span><span class="sxs-lookup"><span data-stu-id="0852a-134">Instead, the planner for the product is responsible for creating the required orders for the replenishment of the product.</span></span> <span data-ttu-id="0852a-135">Kod zapotrzebowania *ręcznego* jest często używany w przypadku produktów, których nie chce używać wygenerowane przez system planowane zamówienia.</span><span class="sxs-lookup"><span data-stu-id="0852a-135">The *Manual* coverage code is often used for products that system-generated planned orders aren't wanted for.</span></span>

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a><span data-ttu-id="0852a-136">Wpływ ilości zamówienia z domyślnych ustawień zamówienia</span><span class="sxs-lookup"><span data-stu-id="0852a-136">Impact of the order quantity from default order settings</span></span>

<span data-ttu-id="0852a-137">Na stronie **Domyślne ustawienie zamówienia** dla wydanego produktu można określić każde z następujących ustawień ilości na szybkich kartach **Zamówienie**, **Zapasy** i **Zamówienie sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="0852a-137">On the **Default order setting** page for a released product, you can specify each of following quantity settings on the **Purchase order**, **Inventory**, and **Sales order** FastTabs.</span></span> <span data-ttu-id="0852a-138">(Skrócona karta **Inwentaryzacja** jest używana zarówno dla zleceń transferowych jak i zleceń produkcyjnych.)</span><span class="sxs-lookup"><span data-stu-id="0852a-138">(The **Inventory** FastTab is used for both transfer orders and production orders.)</span></span>

- <span data-ttu-id="0852a-139">**Wiele** — planowane zamówienia będą wielokrotnością tej ilości.</span><span class="sxs-lookup"><span data-stu-id="0852a-139">**Multiple** – Planned orders will be a multiple of this quantity.</span></span>

    <span data-ttu-id="0852a-140">Na przykład, jeśli pole **Wielokrotność** jest ustawione na *5*, zamówienie może dotyczyć ilości 5, 10, 15, 20 itd.</span><span class="sxs-lookup"><span data-stu-id="0852a-140">For example, if the **Multiple** field is set to *5*, an order can be for a quantity of 5, 10, 15, 20, and so on.</span></span>

- <span data-ttu-id="0852a-141">**Minimalna ilość zamówienia** — zamówienia planowane nie będą mniejsze niż określona wartość.</span><span class="sxs-lookup"><span data-stu-id="0852a-141">**Min. order quantity** – Planned orders won't be less than the specified value.</span></span>

    <span data-ttu-id="0852a-142">Na przykład, jeśli w polu **Minimalna ilość zamówienia** jest ustawiona wartość *10*, zostanie utworzone zamówienie planowane na ilość 10, nawet jeśli do spełnienia popytu są wymagane tylko cztery.</span><span class="sxs-lookup"><span data-stu-id="0852a-142">For example, if the **Min. order quantity** field is set to *10*, a planned order for a quantity of 10 will be created, even if only four are required to fulfill the demand.</span></span>

- <span data-ttu-id="0852a-143">**maksymalna ilość zamówienia** — zamówienia planowane nie będą większe niż określona wartość.</span><span class="sxs-lookup"><span data-stu-id="0852a-143">**Max. order quantity** – Planned orders won't exceed the specified value.</span></span> <span data-ttu-id="0852a-144">Jeśli zapotrzebowanie jest większe niż wartość **Max. ilość zamówienia**, zostanie utworzonych wiele planowanych zamówień, aby je pokryć.</span><span class="sxs-lookup"><span data-stu-id="0852a-144">If the demand is more than the **Max. order quantity** value, multiple planned orders will be created to cover it.</span></span>

    <span data-ttu-id="0852a-145">Jeśli np. w polu **Maks. ilość zamówienia** ustawiono wartość *100*, a zapotrzebowanie wynosi 450, to zostaną utworzone cztery planowane zamówienia na ilość 100 i jedno planowane zamówienie na ilość 50.</span><span class="sxs-lookup"><span data-stu-id="0852a-145">For example, if the **Max. order quantity** field is set to *100*, and the demand is 450, four planned orders for a quantity of 100 and one planned order for a quantity of 50 will be created.</span></span>

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a><span data-ttu-id="0852a-146">Przykłady uzupełniania zapasów z wykorzystaniem kodu</span><span class="sxs-lookup"><span data-stu-id="0852a-146">Examples of replenishment that use the Min./Max.</span></span> <span data-ttu-id="0852a-147">min./maks.</span><span class="sxs-lookup"><span data-stu-id="0852a-147">coverage code</span></span>

<span data-ttu-id="0852a-148">Jeśli nie podasz wartości w polu **Wielokrotność** dla produktu na stronie **Domyślne ustawienia zamówienia** i jeśli korzystasz z metody uzupełniania *Min./Max*.</span><span class="sxs-lookup"><span data-stu-id="0852a-148">If you don't specify a value in the **Multiple** field for a product on the **Default order setting** page, and if you're using the *Min./Max.*</span></span> <span data-ttu-id="0852a-149">, wtedy optymalizacja planowania uzupełni zapas do określonego poziomu, gdy przewidywany poziom na rękę jest poniżej określonego progu.</span><span class="sxs-lookup"><span data-stu-id="0852a-149">replenishment method, Planning Optimization will replenish the inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span>

<span data-ttu-id="0852a-150">W przypadku zdefiniowania ilości wielokrotności, wartość metody odnawiania *min./maks.*</span><span class="sxs-lookup"><span data-stu-id="0852a-150">If you define a multiple quantity for a product, the *Min./Max.*</span></span> <span data-ttu-id="0852a-151">zmienia swoje zachowanie i bierze pod uwagę wartość **Wielokrotność**.</span><span class="sxs-lookup"><span data-stu-id="0852a-151">replenishment method changes its behavior and considers the **Multiple** value.</span></span>

<span data-ttu-id="0852a-152">Innymi słowy, optymalizacja planowania będzie nadal uzupełniać zapasy do zdefiniowanego maksymalnego poziomu, gdy przewidywany poziom na rękę jest mniejszy niż zdefiniowany poziom minimalny.</span><span class="sxs-lookup"><span data-stu-id="0852a-152">In other words, Planning Optimization will still replenish the inventory up to the defined maximum level when the predicted on-hand level is less than the defined minimum level.</span></span> <span data-ttu-id="0852a-153">Ilość uzupełnienia musi być jednak wielokrotnością wartości **Wielokrotność**.</span><span class="sxs-lookup"><span data-stu-id="0852a-153">However, the replenishment quantity must be a multiple of the **Multiple** value.</span></span>

<span data-ttu-id="0852a-154">Jeśli ilość uzupełnienia (różnica pomiędzy poziomem maksymalnym a przewidywanym poziomem na stanie) nie jest wielokrotnością zdefiniowanej ilości wielokrotnej, optymalizacja planowania używa pierwszej możliwej wartości, która wraz z przewidywanym poziomem na stanie będzie poniżej poziomu maksymalnego.</span><span class="sxs-lookup"><span data-stu-id="0852a-154">If the replenishment quantity (the difference between the maximum level and the predicted on-hand level) isn't a multiple of the defined multiple quantity, Planning Optimization uses the first possible value that, together with predicted on-hand level, will be below the maximum level.</span></span> <span data-ttu-id="0852a-155">Jeśli suma jest mniejsza niż poziom minimalny, optymalizacja planowania wykorzystuje pierwszą wartość, która wraz z przewidywanym stanem magazynowym będzie powyżej poziomu maksymalnego.</span><span class="sxs-lookup"><span data-stu-id="0852a-155">If the sum is less than the minimum level, Planning Optimization uses the first value that, together with predicted on-hand, will be above the maximum level.</span></span>

<span data-ttu-id="0852a-156">Poniższe podrozdziały zawierają kilka przykładów, które pokazują, jak wielokrotne zamawianie produktu wpływa na wynik metody uzupełniania zapasów *min./maks.*</span><span class="sxs-lookup"><span data-stu-id="0852a-156">The following subsections provide some examples that show how the multiple order quantity for a product affects the result of the *Min./Max.*</span></span> <span data-ttu-id="0852a-157">.</span><span class="sxs-lookup"><span data-stu-id="0852a-157">replenishment method.</span></span>

### <a name="example-1"></a><span data-ttu-id="0852a-158">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="0852a-158">Example 1</span></span>

<span data-ttu-id="0852a-159">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="0852a-159">A product has the following configuration:</span></span>

- <span data-ttu-id="0852a-160">**Kod objęcia świadczeniem:** *Minimum/Maksimum*.</span><span class="sxs-lookup"><span data-stu-id="0852a-160">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="0852a-161">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="0852a-161">**Minimum:** *15*</span></span>
- <span data-ttu-id="0852a-162">**Maksimum:** *22*</span><span class="sxs-lookup"><span data-stu-id="0852a-162">**Maximum:** *22*</span></span>
- <span data-ttu-id="0852a-163">**Wielokrotność:** *0*</span><span class="sxs-lookup"><span data-stu-id="0852a-163">**Multiple:** *0*</span></span>

<span data-ttu-id="0852a-164">Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.</span><span class="sxs-lookup"><span data-stu-id="0852a-164">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="0852a-165">Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 12 sztuk w celu uzupełnienia zapasów do maksymalnej ilości.</span><span class="sxs-lookup"><span data-stu-id="0852a-165">When master planning runs, a planned order for 12 pieces is created to replenish inventory to the maximum quantity.</span></span>

### <a name="example-2"></a><span data-ttu-id="0852a-166">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="0852a-166">Example 2</span></span>

<span data-ttu-id="0852a-167">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="0852a-167">A product has the following configuration:</span></span>

- <span data-ttu-id="0852a-168">**Kod objęcia świadczeniem:** *Minimum/Maksimum*.</span><span class="sxs-lookup"><span data-stu-id="0852a-168">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="0852a-169">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="0852a-169">**Minimum:** *15*</span></span>
- <span data-ttu-id="0852a-170">**Maksimum:** *22*</span><span class="sxs-lookup"><span data-stu-id="0852a-170">**Maximum:** *22*</span></span>
- <span data-ttu-id="0852a-171">**Wielokrotność:** *5*</span><span class="sxs-lookup"><span data-stu-id="0852a-171">**Multiple:** *5*</span></span>

<span data-ttu-id="0852a-172">Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.</span><span class="sxs-lookup"><span data-stu-id="0852a-172">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="0852a-173">Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 10 sztuk (ponieważ 15 sztuk z uzupełnienia plus 10 sztuk z zapasów na stanie przekroczy ilość maksymalną).</span><span class="sxs-lookup"><span data-stu-id="0852a-173">When master planning runs, a planned order for 10 pieces is created (because 15 pieces of replenishment plus 10 pieces of on-hand inventory will exceed the maximum quantity).</span></span>

### <a name="example-3"></a><span data-ttu-id="0852a-174">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="0852a-174">Example 3</span></span>

<span data-ttu-id="0852a-175">Produkt ma następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="0852a-175">A product has the following configuration:</span></span>

- <span data-ttu-id="0852a-176">**Kod objęcia świadczeniem:** *Minimum/Maksimum*.</span><span class="sxs-lookup"><span data-stu-id="0852a-176">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="0852a-177">**Minimum:** *21*</span><span class="sxs-lookup"><span data-stu-id="0852a-177">**Minimum:** *21*</span></span>
- <span data-ttu-id="0852a-178">**Maksimum:** *24*</span><span class="sxs-lookup"><span data-stu-id="0852a-178">**Maximum:** *24*</span></span>
- <span data-ttu-id="0852a-179">**Wielokrotność:** *5*</span><span class="sxs-lookup"><span data-stu-id="0852a-179">**Multiple:** *5*</span></span>

<span data-ttu-id="0852a-180">Istnieje 10 sztuk zapasów na rękę dla produktu, a nie ma innego popytu lub podaży.</span><span class="sxs-lookup"><span data-stu-id="0852a-180">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="0852a-181">Po uruchomieniu planowania głównego tworzone jest planowane zamówienie na 15 sztuk (ponieważ 10 sztuk z uzupełnienia plus 10 sztuk z zapasów na stanie będzie mniejsze od ilości minimalnej).</span><span class="sxs-lookup"><span data-stu-id="0852a-181">When master planning runs, the planned order for 15 pieces is created (because 10 pieces of replenishment plus 10 pieces of on-hand inventory will be less than the minimum quantity).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
