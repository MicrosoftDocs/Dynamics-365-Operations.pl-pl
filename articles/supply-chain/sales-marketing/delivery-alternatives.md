---
title: Dostawy alternatywne
description: Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony Dostawy alternatywne wykrywać alternatywne opcje realizacji zamówień.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 829775e36a2d49ebbab5c719436cff4c92984635
ms.sourcegitcommit: ca7fc46607ae9d07725e1486b43c66d39ec5cdb5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035273"
---
# <a name="delivery-alternatives"></a><span data-ttu-id="64627-103">Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="64627-103">Delivery alternatives</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64627-104">Osoby wypełniające zamówienia sprzedaży mogą za pomocą strony **Dostawy alternatywne** wykrywać alternatywne opcje realizacji zamówień.</span><span class="sxs-lookup"><span data-stu-id="64627-104">Sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="64627-105">Układ strony **Dostawy alternatywne** umożliwia przegląd wszystkich alternatywnych opcji.</span><span class="sxs-lookup"><span data-stu-id="64627-105">The **Delivery alternatives** page layout gives an overview of all alternative options.</span></span> <span data-ttu-id="64627-106">Umożliwia również osobom wypełniającym zamówienia szukanie możliwości realizacji poza bieżącą firmą.</span><span class="sxs-lookup"><span data-stu-id="64627-106">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="64627-107">Teraz można wyświetlać możliwości zarówno międzyfirmowe, jak i u zewnętrznych dostawców.</span><span class="sxs-lookup"><span data-stu-id="64627-107">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="64627-108">Sortując opcje według dat dostawy, osoby wypełniające zamówienia sprzedaży mogą wyświetlić inteligentną listę alternatywnych możliwości realizacji dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-108">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="64627-109">Ponadto parametry pozwalają lepiej zarządzać sugerowanymi dostawami.</span><span class="sxs-lookup"><span data-stu-id="64627-109">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="64627-110">Ponieważ czas transportu może wpływać na daty dostawy, osoby wypełniające zamówienia sprzedaży mogą sprawdzać różne opcje transportu oferowane przez przewoźników.</span><span class="sxs-lookup"><span data-stu-id="64627-110">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="64627-111">Dla każdej sugestii są wyświetlane szczegółowe informacje, dlatego osoby wypełniające zamówienia mogą podejmować optymalne decyzje bezpośrednio ze strony **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="64627-111">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="64627-112">Otwieranie strony Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="64627-112">Open the Delivery alternatives page</span></span>

<span data-ttu-id="64627-113">Stronę **Dostawy alternatywne** można otworzyć z wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-113">You can open the **Delivery alternatives** page from the sales order line.</span></span>

1. <span data-ttu-id="64627-114">Wybierz kolejno opcje **Produkty i dostawa \> Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="64627-114">Select **Products and supply \> Delivery alternatives**.</span></span>
1. <span data-ttu-id="64627-115">Wybierz kolejno opcje **Szczegóły wiersza \> Dostawa \> Dostawy alternatywne.**</span><span class="sxs-lookup"><span data-stu-id="64627-115">Select **Line details \> Delivery \> Delivery alternatives.**</span></span>

<span data-ttu-id="64627-116">Inny sposób otwarcia strony **Dostawy alternatywne** to otwarcie obszaru roboczego **Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania**, a następnie wybranie kolejno opcji **Zamówienia i ulubione \> Wiersze opóźnionych zamówień \> Dostawy alternatywne**. **Uwaga**: stronę **Dostawy alternatywne** można otworzyć tylko wtedy, gdy są spełnione oba poniższe warunki:</span><span class="sxs-lookup"><span data-stu-id="64627-116">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then selecting **Orders and favorites \> Delayed order lines \> Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

- <span data-ttu-id="64627-117">Wszystkie wymagane informacje wiersza sprzedaży są wypełnione.</span><span class="sxs-lookup"><span data-stu-id="64627-117">All mandatory sales line information is filled in.</span></span>
- <span data-ttu-id="64627-118">W polu **Kontrola daty dostawy** ustawiono wartość inną niż **Brak**.</span><span class="sxs-lookup"><span data-stu-id="64627-118">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="64627-119">Metody kontroli daty dostawy</span><span class="sxs-lookup"><span data-stu-id="64627-119">Delivery date control methods</span></span>

<span data-ttu-id="64627-120">Metoda kontroli daty dostawy określa, jak system ustala daty dostawy, jak są obliczane alternatywne opcje dostawy i które informacje są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="64627-120">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="64627-121">Należy zwrócić uwagę, że funkcja kontroli dat dostawy uwzględnia kalendarze.</span><span class="sxs-lookup"><span data-stu-id="64627-121">Note that delivery date control takes calendars into consideration.</span></span> <span data-ttu-id="64627-122">W związku z tym następujące kalendarze mogą mieć wpływ na sugerowaną datę przyjęcia: kalendarz magazynu, kalendarz transportu, kalendarz dostawcy i kalendarz odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="64627-122">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="64627-123">W poniższej tabeli opisano każdą z metod kontroli daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-123">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="64627-124"><strong>Metoda</strong></span><span class="sxs-lookup"><span data-stu-id="64627-124"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="64627-125"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="64627-125"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="64627-126"><strong>None</strong></span><span class="sxs-lookup"><span data-stu-id="64627-126"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="64627-127">Alternatywne opcje dostawy dla wierszy sprzedaży nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="64627-127">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="64627-128">Ta opcja powoduje wyłączenie funkcji kontroli daty dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-128">This option turns off delivery date control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="64627-129"><strong>Czas realizacji sprzedaży</strong></span><span class="sxs-lookup"><span data-stu-id="64627-129"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="64627-130">Alternatywne opcje dostawy są obliczane na podstawie wstępnie zdefiniowanego czasu realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-130">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="64627-131">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-131">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="64627-132">Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</span><span class="sxs-lookup"><span data-stu-id="64627-132">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="64627-133"><strong>Dostępność zapasów</strong></span><span class="sxs-lookup"><span data-stu-id="64627-133"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="64627-134">Alternatywne opcje dostawy są obliczane na podstawie logiki dostępności zapasów (ATP).</span><span class="sxs-lookup"><span data-stu-id="64627-134">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="64627-135">Funkcja bierze pod uwagę bieżącą dostępność i oczekiwaną przyszłą dostępność.</span><span class="sxs-lookup"><span data-stu-id="64627-135">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="64627-136">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-136">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="64627-137">Alternatywne opcje dostawy uwzględniają magazyny, w których istnieją dostępne zapasy, oraz zamówienia popytowe/podażowe.</span><span class="sxs-lookup"><span data-stu-id="64627-137">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="64627-138"><strong>Dostępność zapasów + Zapas czasu dla rozchodu</strong></span><span class="sxs-lookup"><span data-stu-id="64627-138"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="64627-139">Alternatywne opcje dostawy są obliczane podobnie jak w metodzie ATP, ale dodatkowo jest uwzględniany zapas czasu dla rozchodu.</span><span class="sxs-lookup"><span data-stu-id="64627-139">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="64627-140"><strong>Możliwe do zrealizowania</strong></span><span class="sxs-lookup"><span data-stu-id="64627-140"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="64627-141">Alternatywne opcje dostawy są obliczane na podstawie logiki ilości możliwej do zrealizowania (CTP).</span><span class="sxs-lookup"><span data-stu-id="64627-141">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="64627-142">Do określenia dostępności służy rozłożenie MRP.</span><span class="sxs-lookup"><span data-stu-id="64627-142">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="64627-143">Należy zauważyć, że w metodzie CTP następuje co najmniej kompensowanie dat dostawy o czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-143">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="64627-144">Liczba dni transportu jest obliczana na podstawie metody dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-144">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="64627-145">Alternatywne opcje dostawy zawierają sugestie dotyczące następujących magazynów:</span><span class="sxs-lookup"><span data-stu-id="64627-145">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="64627-146">Bieżący magazyn</span><span class="sxs-lookup"><span data-stu-id="64627-146">Current warehouse</span></span></li>
<li><span data-ttu-id="64627-147">Magazyn domyślny</span><span class="sxs-lookup"><span data-stu-id="64627-147">Default warehouse</span></span></li>
<li><span data-ttu-id="64627-148">Wszystkie magazyny, w których istnieją dostępne zapasy</span><span class="sxs-lookup"><span data-stu-id="64627-148">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="64627-149">Wszystkie magazyny, które mają zamówienia podażowe</span><span class="sxs-lookup"><span data-stu-id="64627-149">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="64627-150">Wszystkie magazyny, które mają aktywne wersje list składowych (BOM)</span><span class="sxs-lookup"><span data-stu-id="64627-150">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="64627-151">Wyświetlanie informacji o alternatywnych opcjach dostawy</span><span class="sxs-lookup"><span data-stu-id="64627-151">View information about delivery alternatives</span></span>

<span data-ttu-id="64627-152">W tej sekcji opisano informacje o alternatywnych opcjach dostawy, które są dostępne na skróconej karcie na stronie **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="64627-152">This section describes the information about delivery alternatives that is available on each FastTab of the **Delivery alternatives** page.</span></span>

### <a name="the-product-fasttab"></a><span data-ttu-id="64627-153">Skrócona karta produktów</span><span class="sxs-lookup"><span data-stu-id="64627-153">The Product FastTab</span></span>

<span data-ttu-id="64627-154">Ta skrócona karta zawiera podsumowanie produktu i szczegółów bieżącego wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-154">This FastTab shows a summary of the product and details of the current sales line.</span></span>

### <a name="the-delivery-alternatives-fasttab"></a><span data-ttu-id="64627-155">Skrócona karta Dostawy alternatywne</span><span class="sxs-lookup"><span data-stu-id="64627-155">The Delivery alternatives FastTab</span></span>

<span data-ttu-id="64627-156">Ta skrócona karta zawiera listę alternatywnych opcji dostawy posortowanych według dat przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="64627-156">This FastTab shows a list of delivery alternatives that is sorted by receipt date.</span></span> <span data-ttu-id="64627-157">Nad listą można wybrać opcje, na których mają się opierać sugestie.</span><span class="sxs-lookup"><span data-stu-id="64627-157">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="64627-158">Można również wybrać metodę dostawy, co decyduje o liczbie dni transportu.</span><span class="sxs-lookup"><span data-stu-id="64627-158">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="64627-159">Dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="64627-159">The following options are available:</span></span>

- <span data-ttu-id="64627-160">**Uwzględnij inne warianty produktu** — Ta opcja jest dostępna dla produktów mających warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="64627-160">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="64627-161">Spowoduje uwzględnienie alternatywnych opcji dostawy dla innych wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="64627-161">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="64627-162">Ta opcja jest niedostępna dla metody CTP.</span><span class="sxs-lookup"><span data-stu-id="64627-162">This option isn't available for CTP.</span></span>
- <span data-ttu-id="64627-163">**Uwzględnij ilość częściową** — Domyślnie są uwzględniane tylko propozycje zaspokajające pełną ilość wiersza sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-163">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="64627-164">Wybierz tę opcję, aby uwzględniać sugestie, które tylko częściowo zaspokajają wiersz zamówienia.</span><span class="sxs-lookup"><span data-stu-id="64627-164">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="64627-165">Ta opcja jest przydatna, gdy odbiorca prosi o wcześniejszą datę dostawy i akceptuje dostawę częściową.</span><span class="sxs-lookup"><span data-stu-id="64627-165">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
- <span data-ttu-id="64627-166">**Uwzględnij późniejsze daty** — Domyślnie są wyświetlane tylko sugestie lepsze (wcześniejsze) niż bieżące daty w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-166">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="64627-167">Wybierz tę opcję, aby uwzględniać późniejsze daty.</span><span class="sxs-lookup"><span data-stu-id="64627-167">Select this option to include later dates.</span></span> <span data-ttu-id="64627-168">Ta opcja może być przydatna w sytuacjach, gdy pierwszeństwo mają parametry inne niż data.</span><span class="sxs-lookup"><span data-stu-id="64627-168">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="64627-169">Na przykład może być preferowany określony dostawca lub magazyn.</span><span class="sxs-lookup"><span data-stu-id="64627-169">For example, a specific vendor or warehouse might be preferred.</span></span>
- <span data-ttu-id="64627-170">**Metoda dostawy** — Umożliwia wybranie preferowanej metody dostawy w celu optymalizacji czasu i kosztów transportu.</span><span class="sxs-lookup"><span data-stu-id="64627-170">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="64627-171">Natychmiast zobaczysz wpływ na sugerowane alternatywne opcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-171">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="64627-172">Dzięki temu można łatwo porównywać alternatywne rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="64627-172">Therefore, it's easy to compare the alternatives.</span></span>
- <span data-ttu-id="64627-173">**Uwzględnij zaopatrzenie** — Po wybraniu kryterium zaopatrzenia sugerowane alternatywne opcje dostawy obejmują opcje pozyskiwania od dostawców zewnętrznych i od innych firm w przedsiębiorstwie (dostawy międzyfirmowe).</span><span class="sxs-lookup"><span data-stu-id="64627-173">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="64627-174">Opcja **Uwzględnij zaopatrzenie** opcja jest obsługiwana dla metod kontroli dat dostawy Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu.</span><span class="sxs-lookup"><span data-stu-id="64627-174">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="64627-175">Propozycje uwzględniają opcje zaopatrzenia od domyślnego i wszystkich zatwierdzonych dostawców wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="64627-175">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
- <span data-ttu-id="64627-176">W przypadku dostawców zewnętrznych obliczenie bazuje na czasie realizacji zakupu.</span><span class="sxs-lookup"><span data-stu-id="64627-176">For external vendors, the calculation is based on the purchase lead time.</span></span>
- <span data-ttu-id="64627-177">W zaopatrzeniu międzyfirmowym aparat obliczania bierze pod uwagę ilości dostępne w firmie zaopatrującej, używając funkcji kontrolę daty dostawy w firmie zaopatrującej.</span><span class="sxs-lookup"><span data-stu-id="64627-177">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
- <span data-ttu-id="64627-178">**Typ dostawy** (odpowiedni dla zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="64627-178">**Delivery type** (Relevant for procurement)</span></span>
  - <span data-ttu-id="64627-179">**Zapasy** — Produkty są wysyłane z magazynu zaopatrującego do oddziału/magazynu określonego w wierszu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-179">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="64627-180">Następnie są wysyłane z tego magazynu do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="64627-180">They are then shipped from that warehouse to the customer.</span></span>
  - <span data-ttu-id="64627-181">**Dostawa bezpośrednia** — Produkty są wysyłane bezpośrednio z magazynu zaopatrującego do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="64627-181">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="the-availability-information-fasttab"></a><span data-ttu-id="64627-182">Skrócona karta Informacje o dostępności</span><span class="sxs-lookup"><span data-stu-id="64627-182">The Availability information FastTab</span></span>

<span data-ttu-id="64627-183">Informacje na tej skróconej karcie dotyczą wybranego wiersza alternatywnych opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-183">Information on this FastTab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="64627-184">Wyświetlane są następujące informacje, w zależności od ustawienia kontroli daty dostawy w wierszu sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="64627-184">The following information is shown, depending on the delivery date control for the sales line:</span></span>

- <span data-ttu-id="64627-185">**Czas realizacji sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="64627-185">**Sales lead time**</span></span>
  - <span data-ttu-id="64627-186">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="64627-186">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="64627-187">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-187">**Parameters** - Show the inventory unit and sales lead time.</span></span>

- <span data-ttu-id="64627-188">**Dostępność zapasów i Dostępność zapasów + Zapas czasu dla rozchodu**</span><span class="sxs-lookup"><span data-stu-id="64627-188">**ATP and ATP + Issue margin**</span></span>
  - <span data-ttu-id="64627-189">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="64627-189">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="64627-190">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-190">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="64627-191">**Dostępność w przyszłości** — Pokazuje w sposób graficzny bieżącą i przyszłą dostępność w oddziale i magazynie wybranych w obszarze **Dostawy alternatywne**.</span><span class="sxs-lookup"><span data-stu-id="64627-191">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="64627-192">Możesz wybierać kolumny wykresu, aby zobaczyć więcej szczegółowych informacji o przyszłej dostępności produktu.</span><span class="sxs-lookup"><span data-stu-id="64627-192">You can select the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="64627-193">Suwak umożliwia wyświetlenie listy odnośnych zamówień popytowych i podażowych w granicach horyzontu czasowego dostępności zapasów.</span><span class="sxs-lookup"><span data-stu-id="64627-193">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

- <span data-ttu-id="64627-194">**Możliwe do zrealizowania**</span><span class="sxs-lookup"><span data-stu-id="64627-194">**CTP**</span></span>
  - <span data-ttu-id="64627-195">**Dostępne dzisiaj** — Pokazuje obecny stan zapasów fizycznie dostępnych na stanie, zarezerwowanych fizycznie i dostępnych fizycznie.</span><span class="sxs-lookup"><span data-stu-id="64627-195">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="64627-196">**Parametry** — Pokazuje jednostkę magazynową i czas realizacji sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="64627-196">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="64627-197">**Rozłożenie** — Pokazuje rozłożenie podaży w wybranej alternatywnej opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-197">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="64627-198">Można użyć przycisku **Ustawienia**, aby zmienić pola i wymiary magazynowe wyświetlane w rozłożeniu.</span><span class="sxs-lookup"><span data-stu-id="64627-198">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="the-impact-of-selected-alternative-fasttab"></a><span data-ttu-id="64627-199">Skrócona karta Wpływ wybranej alternatywy</span><span class="sxs-lookup"><span data-stu-id="64627-199">The Impact of selected alternative FastTab</span></span>

<span data-ttu-id="64627-200">Na tej skróconej karcie są eksponowane skutki wybranej alternatywnej opcji dostawy.</span><span class="sxs-lookup"><span data-stu-id="64627-200">This FastTab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="64627-201">Wybranie przycisku **OK** spowoduje aktualizację wiersza sprzedaży o wyeksponowane wartości w kolumnach WYBRANE.</span><span class="sxs-lookup"><span data-stu-id="64627-201">If you select **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="64627-202">Należy zwrócić uwagę, że jeśli ilość w wybranej alternatywnej opcji dostawy jest mniejsza niż ilość w wierszu sprzedaży, jest utworzony harmonogram dostaw, a wiersz zamówienia jest dzielony na dwa wiersze: jeden wiersz dla wybranej ilości i jeden wiersz na pozostałej ilości.</span><span class="sxs-lookup"><span data-stu-id="64627-202">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="64627-203">Można także zaktualizować wiersz handlowy, aby pasował do wierszy harmonogramu i miał wpływ na ceny.</span><span class="sxs-lookup"><span data-stu-id="64627-203">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64627-204">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="64627-204">Additional resources</span></span>

[<span data-ttu-id="64627-205">Zobowiązanie do zamówienia</span><span class="sxs-lookup"><span data-stu-id="64627-205">Order promising</span></span>](delivery-dates-available-promise-calculations.md)
