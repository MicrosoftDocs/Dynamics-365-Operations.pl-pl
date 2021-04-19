---
title: Wyszukiwanie zapasów w punkcie sprzedaży (POS)
description: W tym temacie opisano dostępne opcje przeglądania informacji o zapasach w aplikacji punktu sprzedaży (POS).
author: ashishmsft
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: a5f0d28e323177e46f3f686a4dea3b168863a227
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795580"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a><span data-ttu-id="ec876-103">Wyszukiwanie zapasów w punkcie sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="ec876-103">Inventory lookup in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ec876-104">Funkcja wyszukiwania zapasów w punkcie sprzedaży (POS) pozwala sprzedawcom detalicznym osiągnąć doskonałość operacyjną i w czasie rzeczywistym wyciągać wnioski dzięki połączeniu sklepów, aplikacji punktu sprzedaży i systemów zaplecza.</span><span class="sxs-lookup"><span data-stu-id="ec876-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="ec876-105">Ta funkcja przedstawia dokładny, aktualny stan zapasów produktów w sklepach i centrach dystrybucyjnych.</span><span class="sxs-lookup"><span data-stu-id="ec876-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="ec876-106">Pomaga również sprzedawcom detalicznym jeszcze bardziej poprawić efektywność i obniżać koszty poprzez usprawnienie planowania zapasów w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="ec876-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="ec876-107">Dokładny, aktualny obraz zapasów w organizacji pomaga pracownikom sklepów lepiej służyć i pomagać klientom.</span><span class="sxs-lookup"><span data-stu-id="ec876-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="ec876-108">Moment, który liczy się najbardziej, to chwila, kiedy klient jest gotowy do podjęcia decyzji zakupowej.</span><span class="sxs-lookup"><span data-stu-id="ec876-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="ec876-109">Ważne jest, aby kasjerzy w sklepie mieli aktualne informacje o zapasach zawsze pod ręką, tak aby rzetelnie deklarować dostawy i odbiory produktów.</span><span class="sxs-lookup"><span data-stu-id="ec876-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="ec876-110">Stronę **Wyszukiwanie w magazynie** można otworzyć z obszaru roboczego **Retail Modern POS** lub obszaru roboczego **Retail Cloud POS**.</span><span class="sxs-lookup"><span data-stu-id="ec876-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Kafelek wyszukiwania zapasów na stronie głównej aplikacji punktu sprzedaży](media/POSHomepage.png)

<span data-ttu-id="ec876-112">Na stronie **Wyszukiwanie w magazynie** można za pomocą klawiatury numerycznej wprowadzić numer produktu.</span><span class="sxs-lookup"><span data-stu-id="ec876-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="ec876-113">Następnie można wyświetlić ilość dostępnych zapasów w wielu sklepach i magazynach.</span><span class="sxs-lookup"><span data-stu-id="ec876-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Standardowa strona wyszukiwania zapasów](media/InventoryLookUp.png)

<span data-ttu-id="ec876-115">Dla każdej lokalizacji są także wyświetlane ilości **Zarezerwowane** i **Zamówione**.</span><span class="sxs-lookup"><span data-stu-id="ec876-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="ec876-116">**Zarezerwowane** — ta ilość odnosi się do wartości **Rezerwacja fizyczna** z systemu zaplecza dla określonego numeru produktu w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ec876-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="ec876-117">**Zamówione** — ta ilość odnosi się do wartości **Zamówione w sumie** z systemu zaplecza dla określonego numeru produktu w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ec876-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="ec876-118">Lokalizacje, dla których są wyświetlane informacje o dostępności zapasów</span><span class="sxs-lookup"><span data-stu-id="ec876-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="ec876-119">Lista lokalizacji obejmuje dwa typy jednostek:</span><span class="sxs-lookup"><span data-stu-id="ec876-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="ec876-120">**Sklepy** — lista sklepów skonfigurowanych przy użyciu grupy lokalizatora sklepów dla bieżącego sklepu w aplikacji Headquarters.</span><span class="sxs-lookup"><span data-stu-id="ec876-120">**Stores** – The list shows stores that are configured by using the store locator group for the current store in the Headquarters.</span></span>
- <span data-ttu-id="ec876-121">**Centra dystrybucji** — w usłudze Commerce można skonfigurować różne rodzaje centrów dystrybucyjnych (np. magazyny).</span><span class="sxs-lookup"><span data-stu-id="ec876-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Commerce.</span></span> <span data-ttu-id="ec876-122">Jednak na liście są wyświetlane informacje o dostępności zapasów tylko dla centrów dystrybucyjnych o domyślnym typie **Standardowy**.</span><span class="sxs-lookup"><span data-stu-id="ec876-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec876-123">Informacje o dostępności zapasów nie są widoczne dla magazynów o typach **Tranzyt**, **Kwarantanna** i **Towary w marszrucie** używanych w aplikacji POS.</span><span class="sxs-lookup"><span data-stu-id="ec876-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="ec876-124">Na stronie **Wyszukiwanie w magazynie** można dla każdego sklepu wyświetlić nie tylko bieżące ilości dostępnych zapasów, ilości zarezerwowane i ilości zamówione, ale również ilości zapasów dostępnych do przyrzeczenia (ATP).</span><span class="sxs-lookup"><span data-stu-id="ec876-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="ec876-125">Wybierz sklep, o którym chcesz obejrzeć informacje ATP, a następnie wybierz opcję **Pokaż dostępność sklepu**.</span><span class="sxs-lookup"><span data-stu-id="ec876-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![Ilości ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="ec876-127">Otwieranie widoku Macierz oparta na wymiarach w celu obejrzenia wszystkich wariantów</span><span class="sxs-lookup"><span data-stu-id="ec876-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="ec876-128">Na stronie **Szczegóły produktu** dla produktu głównego lub na stornie **Wyszukiwanie w magazynie** wybierz opcję **Wyświetl wszystkie warianty** na pasku aplikacji u dołu strony.</span><span class="sxs-lookup"><span data-stu-id="ec876-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="ec876-129">Widok **Macierz oparta na wymiarach** uruchamiany początkowo z tych stron zawiera informacje o dostępności zapasów dla wszystkich wariantów produktu w bieżącym sklepie.</span><span class="sxs-lookup"><span data-stu-id="ec876-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="ec876-130">Przycisk **Wyświetl wszystkie warianty** jest dostępny tylko dla produktów głównych towarów mających warianty produktu.</span><span class="sxs-lookup"><span data-stu-id="ec876-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="ec876-131">Nie jest dostępny dla samodzielnych produktów ani zestawów.</span><span class="sxs-lookup"><span data-stu-id="ec876-131">It isn't available for standalone products or kits.</span></span>

![Przycisk Wyświetl wszystkie warianty na stronie Wyszukiwanie w magazynie](media/StandardToMatrix.png)

<span data-ttu-id="ec876-133">Wybierz opcję **Wyświetl wszystkie warianty** na stronie **Szczegóły produktu** dla produktu głównego lub na stronie **Wyszukiwanie w magazynie**, nie wybierając lokalizacji, aby przejść do widoku **Macierz oparta na wymiarach** w celu wyświetlenia informacji o dostępności zapasów dla wszystkich wariantów produktu dla bieżącego sklepu.</span><span class="sxs-lookup"><span data-stu-id="ec876-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Widok Macierz oparta na wymiarach dla strony Wyszukiwanie w magazynie](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="ec876-135">Na poprzedniej ilustracji kolejność wyświetlania wymiarów jest alfabetyczna, ponieważ nie została skonfigurowana dla wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="ec876-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="ec876-136">W widoku **Macierz oparta na wymiarach** komórki wariantów produktu zawierają wartość dostępności zapasów w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="ec876-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="ec876-137">W tabeli poniżej opisano znaczenie poszczególnych wartości.</span><span class="sxs-lookup"><span data-stu-id="ec876-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="ec876-138">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="ec876-138">On-hand value</span></span>                            | <span data-ttu-id="ec876-139">opis</span><span class="sxs-lookup"><span data-stu-id="ec876-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="ec876-140">Wartość liczbowa większa niż 0 (zero)</span><span class="sxs-lookup"><span data-stu-id="ec876-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="ec876-141">Wariant został pomyślnie zwolniony do wybranej lokalizacji i można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="ec876-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="ec876-142">(Te działania są opisane bardziej szczegółowo w dalszej części tego tematu).</span><span class="sxs-lookup"><span data-stu-id="ec876-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="ec876-143">**0** (zero)</span><span class="sxs-lookup"><span data-stu-id="ec876-143">**0** (zero)</span></span>                             | <span data-ttu-id="ec876-144">Wariant został pomyślnie zwolniony do wybranej lokalizacji, ale towar nie jest w niej dostępny.</span><span class="sxs-lookup"><span data-stu-id="ec876-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="ec876-145">Jednak można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="ec876-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="ec876-146">(Te działania są opisane bardziej szczegółowo w dalszej części tego tematu).</span><span class="sxs-lookup"><span data-stu-id="ec876-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="ec876-147">**n/d** lub komórka nieaktywna</span><span class="sxs-lookup"><span data-stu-id="ec876-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="ec876-148">Wariant nie został pomyślnie zwolniony do wybranej lokalizacji i nie można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="ec876-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="ec876-149">Można również zmienić dokument bazowy wymiarów, wybierając nowy wymiar, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="ec876-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span>

![Zmienianie dokumentu bazowego](media/ChangePivot.png)

![Dokument bazowy zmieniony](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="ec876-152">Na poprzedniej ilustracji kolejność wyświetlania wymiarów wybranego produktu jest niestandardowa (niealfabetyczna).</span><span class="sxs-lookup"><span data-stu-id="ec876-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="ec876-153">Opiera się na kolejności wyświetlania wymiarów ustawionej w systemach zaplecza.</span><span class="sxs-lookup"><span data-stu-id="ec876-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="ec876-154">Ponadto w widoku **Macierz oparta na wymiarach** można wykonać więcej działań, które poprawiają wydajność pracownika sklepu.</span><span class="sxs-lookup"><span data-stu-id="ec876-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="ec876-155">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="ec876-155">Here are some examples:</span></span>

- <span data-ttu-id="ec876-156">Zmiana lokalizacji sklepu w celu wyszukiwania dostępnych zapasów wszystkich wariantów produktu w innych lokalizacjach.</span><span class="sxs-lookup"><span data-stu-id="ec876-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="ec876-157">Te lokalizacje obejmują inne sklepy w grupie lokalizatora sklepów oraz centra dystrybucyjne o domyślnym typie **Standardowy**.</span><span class="sxs-lookup"><span data-stu-id="ec876-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="ec876-158">Sprzedawanie odbiorcy określonego wariantu produktu przy użyciu metody zapłaty przy kasie i wychodzenia z produktami ze sklepu (transportu własnego), odbioru w sklepie lub wysyłki na adres.</span><span class="sxs-lookup"><span data-stu-id="ec876-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="ec876-159">Podanie odbiorcy informacji ATP o określonym wariancie produktu w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ec876-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![Dodatkowe działania na kafelkach wariantów](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="ec876-161">Na poprzedniej ilustracji kolejność wyświetlania wymiarów jest alfabetyczna, ponieważ nie została skonfigurowana dla wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="ec876-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="ec876-162">Poniższa tabela zawiera więcej informacji o dodatkowych działaniach, które są dostępne.</span><span class="sxs-lookup"><span data-stu-id="ec876-162">The following table provides more information about the additional actions that are available.</span></span>

| <span data-ttu-id="ec876-163">Akcja</span><span class="sxs-lookup"><span data-stu-id="ec876-163">Action</span></span>               | <span data-ttu-id="ec876-164">opis</span><span class="sxs-lookup"><span data-stu-id="ec876-164">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="ec876-165">Sprzedaj teraz</span><span class="sxs-lookup"><span data-stu-id="ec876-165">Sell now</span></span>             | <span data-ttu-id="ec876-166">Dodawanie wybranego wariantu towaru do transakcji oraz przekierowywanie użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="ec876-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="ec876-167">(Ta akcja jest niedostępna, gdy wybraną lokalizacją jest centrum dystrybucji).</span><span class="sxs-lookup"><span data-stu-id="ec876-167">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="ec876-168">Odbiór w sklepie</span><span class="sxs-lookup"><span data-stu-id="ec876-168">Pick up in store</span></span>     | <span data-ttu-id="ec876-169">Tworzenie zamówienia odbiorcy na wariant produktu, który zostanie odebrany z wybranej lokalizacji, i przekierowywanie użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="ec876-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="ec876-170">(Ta akcja jest niedostępna, gdy wybraną lokalizacją jest centrum dystrybucji).</span><span class="sxs-lookup"><span data-stu-id="ec876-170">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="ec876-171">Wyślij produkt</span><span class="sxs-lookup"><span data-stu-id="ec876-171">Ship product</span></span>         | <span data-ttu-id="ec876-172">Tworzenie zamówienia odbiorcy na wariant produktu, który zostanie wysłany z wybranej lokalizacji, i przekierowywanie użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="ec876-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span> |
| <span data-ttu-id="ec876-173">Dostępność</span><span class="sxs-lookup"><span data-stu-id="ec876-173">Availability</span></span>         | <span data-ttu-id="ec876-174">Wyświetlanie informacji ATP o wybranej kombinacji wariantów dla wybranej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ec876-174">Show the ATP information for the selected variant combination for the selected location.</span></span> |
| <span data-ttu-id="ec876-175">Pokaż wszystkie lokalizacje</span><span class="sxs-lookup"><span data-stu-id="ec876-175">Show all locations</span></span>   | <span data-ttu-id="ec876-176">Przełączanie na standardowy widok wyszukiwania zapasów i wyróżnianie informacji o dostępności zapasów wariantu towaru we wszystkich sklepach w grupie lokalizatora sklepów oraz w centrach dystrybucyjnych o typie **Standardowy/Domyślnie**.</span><span class="sxs-lookup"><span data-stu-id="ec876-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the **Standard/Default** type.</span></span> |
| <span data-ttu-id="ec876-177">Wyświetlanie szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="ec876-177">View product details</span></span> | <span data-ttu-id="ec876-178">Przekierowywanie użytkownika do strony **Szczegóły produktu** skojarzonego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="ec876-178">Redirect the user to the **Product details** page of the associated product master.</span></span> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]