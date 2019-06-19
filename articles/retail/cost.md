---
title: Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)
description: W tym temacie opisano konfigurację kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 80e7a033467c3d94d55f06daa05f99bd27e19a29
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606786"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="c75ea-103">Konfiguracja kosztów dla funkcji zarządzania zamówieniami rozdzielonymi (DOM)</span><span class="sxs-lookup"><span data-stu-id="c75ea-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c75ea-104">Organizacje używają wielu składników kosztów w celu ustalenia optymalnej lokalizacji, z której ma zostać zrealizowane zamówienie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="c75ea-105">Niektóre z tych składników kosztów to koszty wysyłki, koszty obsługi i koszty pakowania.</span><span class="sxs-lookup"><span data-stu-id="c75ea-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="c75ea-106">Kombinacja tych kosztów jest obliczana w celu ustalenia lokalizacji realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="c75ea-107">Gdy w wyniku pierwszej iteracji zarządzania zamówieniami rozdzielonymi (DOM) w rozwiązaniu Microsoft Dynamics 365 for Retail byłą wykonywana optymalizacja przypisań zamówień do lokalizacji realizacji, była brana pod uwagę tylko odległość.</span><span class="sxs-lookup"><span data-stu-id="c75ea-107">When the first iteration of distributed order management (DOM) in Microsoft Dynamics 365 for Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="c75ea-108">Mimo że odległość może być skorelowana z kosztami, nie jest tym samym, co koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="c75ea-109">Na przykład wysyłka w ciągu jednej nocy kosztuje więcej niż wysyłka w ciągu trzech lub siedmiu dni na tę samą odległość.</span><span class="sxs-lookup"><span data-stu-id="c75ea-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="c75ea-110">Funkcja konfiguracji kosztów umożliwia sprzedawcom detalicznym definiowanie i konfigurowanie dodatkowych składników kosztów, które będą obliczane i uwzględniane w celu ustalenia optymalnej lokalizacji, z której mają być realizowane wiersze zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c75ea-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="c75ea-111">W przypadku skonfigurowania składników kosztów moduł obliczeniowy DOM używa tylko tych definicji kosztów w celu ustalenia optymalnej lokalizacji realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c75ea-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="c75ea-112">Ten moduł nie traktuje składnika odległości jako kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="c75ea-113">Jeśli jednak składniki kosztów nie zostaną skonfigurowane, moduł obliczeniowy DOM będzie używał składnika odległości jako kosztu w celu ustalenia optymalnej lokalizacji realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c75ea-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="c75ea-114">Konfigurowanie składników kosztów</span><span class="sxs-lookup"><span data-stu-id="c75ea-114">Set up cost components</span></span>

<span data-ttu-id="c75ea-115">W systemie można zdefiniować dwa główne typy składników kosztów: **Wysyłka** i **Inne**.</span><span class="sxs-lookup"><span data-stu-id="c75ea-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="c75ea-116">Oba typy składników kosztów obsługują wiele podstaw obliczania, tak jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c75ea-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c75ea-117">Typ składnika kosztów</span><span class="sxs-lookup"><span data-stu-id="c75ea-117">Cost component type</span></span></th>
<th><span data-ttu-id="c75ea-118">Podstawa obliczania</span><span class="sxs-lookup"><span data-stu-id="c75ea-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c75ea-119">Wysyłka</span><span class="sxs-lookup"><span data-stu-id="c75ea-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c75ea-120">Proste</span><span class="sxs-lookup"><span data-stu-id="c75ea-120">Simple</span></span></li>
<li><span data-ttu-id="c75ea-121">Wielopoziomowe</span><span class="sxs-lookup"><span data-stu-id="c75ea-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="c75ea-122">Inne</span><span class="sxs-lookup"><span data-stu-id="c75ea-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c75ea-123">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c75ea-123">Sales order</span></span></li>
<li><span data-ttu-id="c75ea-124">Wiersz sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c75ea-124">Sales line</span></span></li>
<li><span data-ttu-id="c75ea-125">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="c75ea-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="c75ea-126">Typ składnika kosztów Wysyłka</span><span class="sxs-lookup"><span data-stu-id="c75ea-126">Shipping cost component type</span></span>

<span data-ttu-id="c75ea-127">W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów **Wysyłka** oraz podstawy obliczania kosztów wysyłki.</span><span class="sxs-lookup"><span data-stu-id="c75ea-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="c75ea-128">Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="c75ea-129">Typ składnika kosztów = Wysyłka; Podstawa obliczania = Proste</span><span class="sxs-lookup"><span data-stu-id="c75ea-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="c75ea-130">Jeśli jest używana kombinacja typu składnika kosztów **Wysyłka** i podstawa obliczania **Proste**, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości.</span><span class="sxs-lookup"><span data-stu-id="c75ea-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="c75ea-131">Dla tej kombinacji musisz skonfigurować następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c75ea-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="c75ea-132">**Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="c75ea-133">**Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="c75ea-134">**Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="c75ea-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="c75ea-135">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="c75ea-136">**Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="c75ea-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="c75ea-137">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="c75ea-138">**Firma** — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="c75ea-139">Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="c75ea-140">**Metody dostawy** — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="c75ea-141">**Typ obliczania** — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="c75ea-142">Obsługiwane są dwa typy obliczania:</span><span class="sxs-lookup"><span data-stu-id="c75ea-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="c75ea-143">**Stały** — dla metody dostawy jest używany ustalony koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="c75ea-144">W przypadku wybrania tego typu obliczania w polu **Koszt** należy zdefiniować ustalony koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="c75ea-145">**Na jednostkę odległości** — koszt dla metody dostawy jest obliczany jako iloczyn wartość kosztu określonej w polu **Koszt** i odległości między adresem dostawy a lokalizacjami.</span><span class="sxs-lookup"><span data-stu-id="c75ea-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="c75ea-146">**Koszt** — umożliwia określenie wartości kosztu używanej w połączeniu z polem **Typ obliczania** w celu obliczenia kosztu dla metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="c75ea-147">Typ składnika kosztów = Wysyłka; Podstawa obliczania = Wielopoziomowe</span><span class="sxs-lookup"><span data-stu-id="c75ea-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="c75ea-148">Jeśli jest używana kombinacja typu składnika kosztów **Wysyłka** i podstawa obliczania **Wielopoziomowe**, koszt wysyłki dla metody dostawy jest oparty na ustalonym koszcie lub odległości.</span><span class="sxs-lookup"><span data-stu-id="c75ea-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="c75ea-149">Jednak w przypadku tej kombinacji odległość jest oparta na wielopoziomowym zakresie odległości.</span><span class="sxs-lookup"><span data-stu-id="c75ea-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="c75ea-150">Dla tej kombinacji musisz skonfigurować następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c75ea-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="c75ea-151">**Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="c75ea-152">**Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="c75ea-153">**Koszt domyślny** — umożliwia określenie kosztu, który ma być używany dla metody dostawy, jeśli odległość między adresem dostawy a lokalizacją nie należy do żadnej wielopoziomowej odległości ustalonej dla metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="c75ea-154">**Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="c75ea-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="c75ea-155">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="c75ea-156">**Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="c75ea-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="c75ea-157">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="c75ea-158">**Firma** — umożliwia określenie firmy, dla której jest konfigurowany współczynnik kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="c75ea-159">Wszystkie wiersze kryteriów obliczania muszą dotyczyć tej samej firmy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="c75ea-160">**Metody dostawy** — umożliwia określenie metod dostawy, dla których jest konfigurowany koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="c75ea-161">**Typ odległości** — umożliwia określenie, czy definicja odległości wielopoziomowej to odległość lotnicza, czy drogowa.</span><span class="sxs-lookup"><span data-stu-id="c75ea-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="c75ea-162">**Jednostki odległości** — umożliwia określenie jednostki, w której będzie mierzona odległość wielopoziomowa.</span><span class="sxs-lookup"><span data-stu-id="c75ea-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="c75ea-163">**Odległość od** — określa zakres początkowy dla odległości wielopoziomowej.</span><span class="sxs-lookup"><span data-stu-id="c75ea-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="c75ea-164">**Odległość do** — określa zakres końcowy dla odległości wielopoziomowej.</span><span class="sxs-lookup"><span data-stu-id="c75ea-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="c75ea-165">**Typ obliczania** — umożliwia określenie sposobu obliczania kosztu dla określonej metody dostawy i odległości wielopoziomowej.</span><span class="sxs-lookup"><span data-stu-id="c75ea-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="c75ea-166">Obsługiwane są dwa typy obliczania:</span><span class="sxs-lookup"><span data-stu-id="c75ea-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="c75ea-167">**Stały** — dla metody dostawy jest używany ustalony koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="c75ea-168">W przypadku wybrania tego typu obliczania w polu **Koszt** należy zdefiniować ustalony koszt.</span><span class="sxs-lookup"><span data-stu-id="c75ea-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="c75ea-169">**Na jednostkę odległości** — koszt dla metody dostawy i odległości wielopoziomowej jest obliczany jako iloczyn wartość kosztu określonej w polu **Koszt** i odległości między adresem dostawy a lokalizacjami.</span><span class="sxs-lookup"><span data-stu-id="c75ea-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="c75ea-170">**Koszt** — umożliwia określenie wartości kosztu używanej w połączeniu z polem **Typ obliczania** w celu obliczenia kosztu dla metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="c75ea-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="c75ea-171">Podczas definiowania odległości wielopoziomowych system sprawdza, czy nie brakuje żadnych odległości i czy jakiekolwiek odległości nie nakładają się na siebie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="c75ea-172">Typ odległości używany dla metody dostawy musi być taki sam dla wszystkich odległości wielopoziomowych.</span><span class="sxs-lookup"><span data-stu-id="c75ea-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="c75ea-173">Typ składnika kosztów Inny</span><span class="sxs-lookup"><span data-stu-id="c75ea-173">Other cost component type</span></span>

<span data-ttu-id="c75ea-174">W tej sekcji opisano sposób konfigurowania poszczególnych kombinacji typu składnika kosztów **Inny** oraz innego typu koszu dla kosztów niezwiązanych z wysyłką.</span><span class="sxs-lookup"><span data-stu-id="c75ea-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="c75ea-175">Wyjaśniono również, w jaki sposób moduł obliczeniowy DOM używa każdej kombinacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="c75ea-176">Typ składnika kosztów = Inny; Inny typ kosztu = Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c75ea-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="c75ea-177">Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Zamówienie sprzedaży** służy do definiowania kosztów niezwiązanych z wysyłką na poziomie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c75ea-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="c75ea-178">Dla tej kombinacji musisz skonfigurować następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c75ea-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="c75ea-179">**Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="c75ea-180">**Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="c75ea-181">**Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="c75ea-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="c75ea-182">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="c75ea-183">**Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="c75ea-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="c75ea-184">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="c75ea-185">**Koszt** — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c75ea-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="c75ea-186">Typ składnika kosztów = Inny; Inny typ kosztu = Wiersz sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c75ea-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="c75ea-187">Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Wiersz sprzedaży** służy do definiowania kosztów niezwiązanych z wysyłką na poziomie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c75ea-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="c75ea-188">Dla tej kombinacji musisz skonfigurować następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c75ea-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="c75ea-189">**Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="c75ea-190">**Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="c75ea-191">**Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="c75ea-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="c75ea-192">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="c75ea-193">**Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="c75ea-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="c75ea-194">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="c75ea-195">**Koszt** — umożliwia określenie wartości kosztu niezwiązanego z wysyłką na poziomie wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c75ea-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="c75ea-196">Typ składnika kosztów = Inny; Inny typ kosztu = Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="c75ea-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="c75ea-197">Kombinacja typu składnika kosztów **Inny** oraz innego typu kosztu **Lokalizacja** służy do definiowania kosztów niezwiązanych z wysyłką dla grupy lokalizacji lub pojedynczej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="c75ea-198">Dla tej kombinacji musisz skonfigurować następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c75ea-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="c75ea-199">**Współczynnik kosztu** — umożliwia wprowadzenie unikatowego identyfikatora współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="c75ea-200">**Opis** — umożliwia wprowadzenie nazwy i opisu współczynnika kosztu.</span><span class="sxs-lookup"><span data-stu-id="c75ea-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="c75ea-201">**Data rozpoczęcia** i **Data zakończenia** — za pomocą tych pól możesz ograniczyć współczynnik kosztu do określonego zakresu dat.</span><span class="sxs-lookup"><span data-stu-id="c75ea-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="c75ea-202">Jeśli zostawisz te pola puste, współczynnik kosztu będzie prawidłowy w nieskończonym okresie.</span><span class="sxs-lookup"><span data-stu-id="c75ea-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="c75ea-203">**Aktywny** — umożliwia wskazanie, czy dany współczynnik kosztu jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="c75ea-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="c75ea-204">Funkcja zarządzania zamówieniami rozdzielonymi uwzględnia tylko aktywne współczynniki kosztów, które są skojarzone z profilem realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="c75ea-205">**Grupa realizacji** — umożliwia określenie grupy lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.</span><span class="sxs-lookup"><span data-stu-id="c75ea-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="c75ea-206">**Lokalizacja realizacji** — umożliwia określenie lokalizacji, dla której jest definiowany koszt niezwiązany z wysyłką.</span><span class="sxs-lookup"><span data-stu-id="c75ea-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c75ea-207">W przypadku kryteriów obliczania opartych na lokalizacji nie możesz określić w tym samym wierszu grupy realizacji i lokalizacji realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="c75ea-208">**Koszt** — umożliwia określenie wartości kosztu dla kosztu niezwiązanego z wysyłką na poziomie grupy realizacji lub lokalizacji realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c75ea-209">Aby funkcja zarządzania zamówieniami rozdzielonymi mogła uwzględniać te koszty, gdy zostanie uruchomiona, musisz dodać współczynnik kosztu do odpowiedniego profilu realizacji.</span><span class="sxs-lookup"><span data-stu-id="c75ea-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>
