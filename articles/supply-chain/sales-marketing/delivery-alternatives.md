---
title: Dostawy alternatywne
description: "Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony Dostawy alternatywne wykrywać alternatywne opcje realizacji zamówień."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cbfbdf5f79ef557ea934505285b57562b0b289ba
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="delivery-alternatives"></a><span data-ttu-id="f562a-103">Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="f562a-103">Delivery alternatives</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f562a-104">Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony Dostawy alternatywne wykrywać alternatywne opcje realizacji zamówień.</span><span class="sxs-lookup"><span data-stu-id="f562a-104">Sales order takers can use the Delivery alternatives page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="f562a-105">W programie Microsoft Dynamics 365 for Operations w wersji 1611 (z listopada 2016 r.) osoby wypełniające zamówienia sprzedaży mogą za pomocą strony **Dostawy alternatywne** wykrywać alternatywne opcje realizacji zamówień.</span><span class="sxs-lookup"><span data-stu-id="f562a-105">In Microsoft Dynamics 365 for Operations version 1611 (November 2016), sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span> <span data-ttu-id="f562a-106">Przeprojektowany układ strony zapewnia lepszy przegląd wszystkich alternatywnych opcji.</span><span class="sxs-lookup"><span data-stu-id="f562a-106">The redesigned page layout gives a better overview of all alternative options.</span></span> <span data-ttu-id="f562a-107">Umożliwia również osobom wypełniającym zamówienia szukanie możliwości realizacji poza bieżącą firmą.</span><span class="sxs-lookup"><span data-stu-id="f562a-107">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="f562a-108">Teraz można wyświetlać możliwości zarówno międzyfirmowe, jak i u zewnętrznych dostawców.</span><span class="sxs-lookup"><span data-stu-id="f562a-108">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="f562a-109">Sortując opcje według dat dostawy, osoby wypełniające zamówienia sprzedaży mogą wyświetlić inteligentną listę alternatywnych możliwości realizacji dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-109">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="f562a-110">Ponadto parametry pozwalają lepiej zarządzać sugerowanymi dostawami.</span><span class="sxs-lookup"><span data-stu-id="f562a-110">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="f562a-111">Ponieważ czas transportu może wpływać na daty dostawy, osoby wypełniające zamówienia sprzedaży mogą sprawdzać różne opcje transportu oferowane przez przewoźników.</span><span class="sxs-lookup"><span data-stu-id="f562a-111">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="f562a-112">Dla każdej sugestii są wyświetlane szczegółowe informacje, dlatego osoby wypełniające zamówienia mogą podejmować optymalne decyzje bezpośrednio ze strony **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="f562a-112">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="f562a-113">Otwieranie strony Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="f562a-113">Open the Delivery alternatives page</span></span>
<span data-ttu-id="f562a-114">Stronę **Dostawy** **alternatywne** można otworzyć z wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-114">You can open the **Delivery** **alternatives** page from the sales order line.</span></span>

1.  <span data-ttu-id="f562a-115">Kliknij kolejno opcje **Produkty i dostawa** &gt; **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="f562a-115">Click **Products and supply** &gt; **Delivery alternatives**.</span></span>
2.  <span data-ttu-id="f562a-116">Kliknij kolejno opcje **Szczegóły wiersza** &gt; **Dostawa** &gt; **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="f562a-116">Click **Line details** &gt; **Delivery** &gt; **Delivery alternatives.**</span></span>

<span data-ttu-id="f562a-117">Inny sposób otwarcia strony **Dostawy alternatywne** to otwarcie obszaru roboczego **Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania**, a następnie kliknięcie kolejno opcji **Zamówienia i ulubione** &gt; **Wiersze opóźnionych zamówień** &gt; **Dostawy alternatywne**. **Uwaga:** Stronę **Dostawy alternatywne** można otworzyć tylko wtedy, gdy są spełnione oba poniższe warunki:</span><span class="sxs-lookup"><span data-stu-id="f562a-117">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then clicking **Orders and favorites** &gt; **Delayed order lines** &gt; **Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

-   <span data-ttu-id="f562a-118">Wszystkie wymagane informacje wiersza sprzedaży są wypełnione.</span><span class="sxs-lookup"><span data-stu-id="f562a-118">All mandatory sales line information is filled in.</span></span>
-   <span data-ttu-id="f562a-119">W polu **Kontrola daty dostawy** ustawiono wartość inną niż **Brak**.</span><span class="sxs-lookup"><span data-stu-id="f562a-119">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="f562a-120">Metody kontroli daty dostawy</span><span class="sxs-lookup"><span data-stu-id="f562a-120">Delivery date control methods</span></span>
<span data-ttu-id="f562a-121">Metoda kontroli daty dostawy określa, jak system ustala daty dostawy, jak są obliczane alternatywne opcje dostawy i które informacje są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="f562a-121">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="f562a-122">Należy zwrócić uwagę, że funkcja kontroli dat dostawy uwzględnia kalendarze.</span><span class="sxs-lookup"><span data-stu-id="f562a-122">Note that delivery data control takes calendars into consideration.</span></span> <span data-ttu-id="f562a-123">W związku z tym następujące kalendarze mogą mieć wpływ na sugerowaną datę przyjęcia: kalendarz magazynu, kalendarz transportu, kalendarz dostawcy i kalendarz odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f562a-123">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="f562a-124">W poniższej tabeli opisano każdą z metod kontroli daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-124">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f562a-125"><strong>Metoda</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-125"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="f562a-126"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-126"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f562a-127"><strong>Brak</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-127"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="f562a-128">Alternatywne opcje dostawy dla wierszy sprzedaży nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="f562a-128">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="f562a-129">Ta opcja powoduje wyłączenie funkcji kontroli daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-129">This option turns off delivery data control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f562a-130"><strong>Czas realizacji sprzedaży</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-130"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="f562a-131">Alternatywne opcje dostawy są obliczane na podstawie wstępnie zdefiniowanego czasu realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-131">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="f562a-132">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-132">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="f562a-133">Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</span><span class="sxs-lookup"><span data-stu-id="f562a-133">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f562a-134"><strong>Dostępność zapasów</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-134"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="f562a-135">Alternatywne opcje dostawy są obliczane na podstawie logiki dostępności zapasów (ATP).</span><span class="sxs-lookup"><span data-stu-id="f562a-135">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="f562a-136">Funkcja bierze pod uwagę bieżącą dostępność i oczekiwaną przyszłą dostępność.</span><span class="sxs-lookup"><span data-stu-id="f562a-136">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="f562a-137">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-137">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="f562a-138">Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</span><span class="sxs-lookup"><span data-stu-id="f562a-138">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f562a-139"><strong>Dostępność zapasów + Zapas czasu dla rozchodu</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-139"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="f562a-140">Alternatywne opcje dostawy są obliczane podobnie jak w metodzie ATP, ale dodatkowo jest uwzględniany zapas czasu dla rozchodu.</span><span class="sxs-lookup"><span data-stu-id="f562a-140">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f562a-141"><strong>Możliwe do zrealizowania</strong></span><span class="sxs-lookup"><span data-stu-id="f562a-141"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="f562a-142">Alternatywne opcje dostawy są obliczane na podstawie logiki ilości możliwej do zrealizowania (CTP).</span><span class="sxs-lookup"><span data-stu-id="f562a-142">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="f562a-143">Do określenia dostępności służy rozłożenie MRP.</span><span class="sxs-lookup"><span data-stu-id="f562a-143">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="f562a-144">Należy zauważyć, że w metodzie CTP następuje co najmniej kompensowanie dat dostawy o czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-144">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="f562a-145">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-145">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="f562a-146">Alternatywne opcje dostawy zawierają sugestie dotyczące następujących magazynów:</span><span class="sxs-lookup"><span data-stu-id="f562a-146">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="f562a-147">Bieżący magazyn</span><span class="sxs-lookup"><span data-stu-id="f562a-147">Current warehouse</span></span></li>
<li><span data-ttu-id="f562a-148">Magazyn domyślny</span><span class="sxs-lookup"><span data-stu-id="f562a-148">Default warehouse</span></span></li>
<li><span data-ttu-id="f562a-149">Wszystkie magazyny, w których istnieją dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="f562a-149">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="f562a-150">Wszystkie magazyny, które mają zamówienia podażowe</span><span class="sxs-lookup"><span data-stu-id="f562a-150">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="f562a-151">Wszystkie magazyny, które mają aktywne wersje list składowych (BOM)</span><span class="sxs-lookup"><span data-stu-id="f562a-151">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="f562a-152">Wyświetlanie informacji o alternatywnych opcjach dostawy</span><span class="sxs-lookup"><span data-stu-id="f562a-152">View information about delivery alternatives</span></span>
<span data-ttu-id="f562a-153">W tej sekcji opisano informacje o alternatywnych opcjach dostawy, które są dostępne na każdej karcie na stronie **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="f562a-153">This section describes the information about delivery alternatives that is available on each tab of the **Delivery alternatives** page.</span></span>

### <a name="products"></a><span data-ttu-id="f562a-154">Produkty</span><span class="sxs-lookup"><span data-stu-id="f562a-154">Products</span></span>

<span data-ttu-id="f562a-155">Ta karta zawiera podsumowanie produktu i szczegółów bieżącego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-155">This tab shows a summary of the product and details of the current sales line.</span></span>

### <a name="delivery-alternatives"></a><span data-ttu-id="f562a-156">Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="f562a-156">Delivery alternatives</span></span>

<span data-ttu-id="f562a-157">Ta karta zawiera listę alternatywnych opcji dostawy posortowanych według dat przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="f562a-157">This tab shows a list of delivery alternatives that is sorted by receipt data.</span></span> <span data-ttu-id="f562a-158">Nad listą można wybrać opcje, na których mają się opierać sugestie.</span><span class="sxs-lookup"><span data-stu-id="f562a-158">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="f562a-159">Można również wybrać metodę dostawy, co decyduje o liczbie dni transportu.</span><span class="sxs-lookup"><span data-stu-id="f562a-159">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="f562a-160">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="f562a-160">The following options are available:</span></span>

-   <span data-ttu-id="f562a-161">**Uwzględnij inne warianty produktu** — Ta opcja jest dostępna dla produktów mających warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="f562a-161">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="f562a-162">Spowoduje uwzględnienie alternatywnych opcji dostawy dla innych wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="f562a-162">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="f562a-163">Ta opcja jest niedostępna dla metody CTP.</span><span class="sxs-lookup"><span data-stu-id="f562a-163">This option isn't available for CTP.</span></span>
-   <span data-ttu-id="f562a-164">**Uwzględnij ilość częściową** — Domyślnie są uwzględniane tylko propozycje zaspokajające pełną ilość wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-164">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="f562a-165">Wybierz tę opcję, aby uwzględniać sugestie, które tylko częściowo zaspokajają wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="f562a-165">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="f562a-166">Ta opcja jest przydatna, gdy odbiorca prosi o wcześniejszą datę dostawy i akceptuje dostawę częściową.</span><span class="sxs-lookup"><span data-stu-id="f562a-166">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
-   <span data-ttu-id="f562a-167">**Uwzględnij późniejsze daty** — Domyślnie są wyświetlane tylko sugestie lepsze (wcześniejsze) niż bieżące daty w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-167">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="f562a-168">Wybierz tę opcję, aby uwzględniać późniejsze daty.</span><span class="sxs-lookup"><span data-stu-id="f562a-168">Select this option to include later dates.</span></span> <span data-ttu-id="f562a-169">Ta opcja może być przydatna w sytuacjach, gdy pierwszeństwo mają parametry inne niż data.</span><span class="sxs-lookup"><span data-stu-id="f562a-169">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="f562a-170">Na przykład może być preferowany określony dostawca lub magazyn.</span><span class="sxs-lookup"><span data-stu-id="f562a-170">For example, a specific vendor or warehouse might be preferred.</span></span>
-   <span data-ttu-id="f562a-171">**Metoda dostawy** — Umożliwia wybranie preferowanej metody dostawy w celu optymalizacji czasu i kosztów transportu.</span><span class="sxs-lookup"><span data-stu-id="f562a-171">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="f562a-172">Natychmiast zobaczysz wpływ na sugerowane alternatywne opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-172">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="f562a-173">Dzięki temu można łatwo porównywać alternatywne rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="f562a-173">Therefore, it's easy to compare the alternatives.</span></span>
-   <span data-ttu-id="f562a-174">**Uwzględnij zaopatrzenie** — Po wybraniu kryterium zaopatrzenia sugerowane alternatywne opcje dostawy obejmują opcje pozyskiwania od dostawców zewnętrznych i od innych firm w przedsiębiorstwie (dostawy międzyfirmowe).</span><span class="sxs-lookup"><span data-stu-id="f562a-174">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="f562a-175">Opcja **Uwzględnij zaopatrzenie** opcja jest obsługiwana dla metod kontroli dat dostawy Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu.</span><span class="sxs-lookup"><span data-stu-id="f562a-175">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="f562a-176">Propozycje uwzględniają opcje zaopatrzenia od domyślnego i wszystkich zatwierdzonych dostawców wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="f562a-176">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
-   <span data-ttu-id="f562a-177">W przypadku dostawców zewnętrznych obliczenie bazuje na czasie realizacji zakupu.</span><span class="sxs-lookup"><span data-stu-id="f562a-177">For external vendors, the calculation is based on the purchase lead time.</span></span>
-   <span data-ttu-id="f562a-178">W zaopatrzeniu międzyfirmowym aparat obliczania bierze pod uwagę ilości dostępne w firmie zaopatrującej, używając funkcji kontrolę daty dostawy w firmie zaopatrującej.</span><span class="sxs-lookup"><span data-stu-id="f562a-178">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
-   <span data-ttu-id="f562a-179">**Typ dostawy** (odpowiedni dla zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="f562a-179">**Delivery type** (Relevant for procurement)</span></span>
    -   <span data-ttu-id="f562a-180">**Zapasy** — Produkty są wysyłane z magazynu zaopatrującego do oddziału/magazynu określonego w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-180">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="f562a-181">Następnie są wysyłane z tego magazynu do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f562a-181">They are then shipped from that warehouse to the customer.</span></span>
    -   <span data-ttu-id="f562a-182">**Dostawa bezpośrednia** — Produkty są wysyłane bezpośrednio z magazynu zaopatrującego do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f562a-182">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="availability-information"></a><span data-ttu-id="f562a-183">Informacje o dostępności</span><span class="sxs-lookup"><span data-stu-id="f562a-183">Availability information</span></span>

<span data-ttu-id="f562a-184">Informacje na tej karcie dotyczą wybranego wiersza alternatywnych opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-184">Information on this tab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="f562a-185">Wyświetlane są następujące informacje, w zależności od ustawienia kontroli daty dostawy w wierszu sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="f562a-185">The following information is shown, depending on the delivery date control for the sales line:</span></span>

-   <span data-ttu-id="f562a-186">**Czas realizacji sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="f562a-186">**Sales lead time**</span></span>
    -   <span data-ttu-id="f562a-187">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="f562a-187">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="f562a-188">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-188">**Parameters** - Show the inventory unit and sales lead time.</span></span>

-   <span data-ttu-id="f562a-189">**Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu**</span><span class="sxs-lookup"><span data-stu-id="f562a-189">**ATP and ATP + Issue margin**</span></span>
    -   <span data-ttu-id="f562a-190">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="f562a-190">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="f562a-191">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-191">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="f562a-192">**Dostępność w przyszłości** — Pokazuje w sposób graficzny bieżącą i przyszłą dostępność w oddziale i magazynie wybranych w obszarze **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="f562a-192">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="f562a-193">Możesz klikać kolumny wykresu, aby zobaczyć więcej szczegółowych informacji o przyszłej dostępności produktu.</span><span class="sxs-lookup"><span data-stu-id="f562a-193">You can click the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="f562a-194">Suwak umożliwia wyświetlenie listy odnośnych zamówień popytowych i podażowych w granicach horyzontu czasowego dostępności zapasów.</span><span class="sxs-lookup"><span data-stu-id="f562a-194">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

-   <span data-ttu-id="f562a-195">**Możliwe do zrealizowania**</span><span class="sxs-lookup"><span data-stu-id="f562a-195">**CTP**</span></span>
    -   <span data-ttu-id="f562a-196">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="f562a-196">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="f562a-197">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f562a-197">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="f562a-198">**Rozłożenie** — Pokazuje rozłożenie podaży w wybranej alternatywnej opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-198">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="f562a-199">Można użyć przycisku **Ustawienia**, aby zmienić pola i wymiary magazynowe wyświetlane w rozłożeniu.</span><span class="sxs-lookup"><span data-stu-id="f562a-199">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="impact-of-selected-alternative"></a><span data-ttu-id="f562a-200">Wpływ wybranej alternatywy</span><span class="sxs-lookup"><span data-stu-id="f562a-200">Impact of selected alternative</span></span>

<span data-ttu-id="f562a-201">Na tej karcie są eksponowane skutki wybranej alternatywnej opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="f562a-201">This tab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="f562a-202">Kliknięcie przycisku **OK** spowoduje aktualizację wiersza sprzedaży o wyeksponowane wartości w kolumnach WYBRANE.</span><span class="sxs-lookup"><span data-stu-id="f562a-202">If you click **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="f562a-203">Należy zwrócić uwagę, że jeśli ilość w wybranej alternatywnej opcji dostawy jest mniejsza niż ilość w wierszu sprzedaży, jest utworzony harmonogram dostaw, a wiersz zamówienia jest dzielony na dwa wiersze: jeden wiersz dla wybranej ilości i jeden wiersz na pozostałej ilości.</span><span class="sxs-lookup"><span data-stu-id="f562a-203">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="f562a-204">Można także zaktualizować wiersz handlowy, aby pasował do wierszy harmonogramu i miał wpływ na ceny.</span><span class="sxs-lookup"><span data-stu-id="f562a-204">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

<a name="see-also"></a><span data-ttu-id="f562a-205">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f562a-205">See also</span></span>
--------

[<span data-ttu-id="f562a-206">Zobowiązanie do zamówienia</span><span class="sxs-lookup"><span data-stu-id="f562a-206">Order promising</span></span>](delivery-dates-available-promise-calculations.md)





