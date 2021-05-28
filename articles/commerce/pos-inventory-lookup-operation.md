---
title: Operacja wyszukiwania zapasów w POS
description: W tym temacie opisano, jak używać operacji wyszukiwania zapasów w punkcie sprzedaży (POS) Dynamics 365 Commerce do przeglądania dostępnych zapasów produktów w sklepach i magazynach.
author: boycezhu
ms.date: 05/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 873c6413c14d2ee8315c149ee9c495bb59dbd930
ms.sourcegitcommit: 11ca5863175150b6c39f47a9322caa2186727a26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6025455"
---
# <a name="inventory-lookup-operation-in-pos"></a><span data-ttu-id="fbcbc-103">Operacja wyszukiwania zapasów w POS</span><span class="sxs-lookup"><span data-stu-id="fbcbc-103">Inventory lookup operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fbcbc-104">W tym temacie opisano, jak używać operacji wyszukiwania zapasów w punkcie sprzedaży (POS) Dynamics 365 Commerce do przeglądania dostępnych zapasów produktów w sklepach i magazynach.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-104">This topic describes how to use the inventory lookup operation in Dynamics 365 Commerce point of sale (POS) to view the on-hand inventory availability of products across stores and warehouses.</span></span>

<span data-ttu-id="fbcbc-105">Dokładny widok zapasów w całej organizacji pomaga pracownikom sklepu zapewnić terminową i efektywną obsługę klienta.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-105">An accurate view of inventory across an organization helps store associates provide timely, effective customer service.</span></span> <span data-ttu-id="fbcbc-106">Moment, który liczy się najbardziej, to chwila, kiedy klient jest gotowy do podjęcia decyzji zakupowej.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-106">The moment that matters most is the moment when a customer is ready to make a purchase decision.</span></span> <span data-ttu-id="fbcbc-107">Ważne jest, aby kasjerzy w sklepie detalicznym mieli dostęp do informacji o stanie magazynowym w czasie rzeczywistym lub prawie w czasie rzeczywistym, aby mogli dokładnie obiecać dostawę i odbiór produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-107">It's important that cashiers in a retail store have real-time or near real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="fbcbc-108">Operacja wyszukiwania zapasów w programie Commerce POS pomaga sprzedawcom detalicznym realizować transakcje operacyjne i zyskać wgląd w dane poprzez łączenie sklepów z centralą commerce.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-108">The inventory lookup operation in Commerce POS helps retailers achieve operational excellence and gain insights by connecting stores with Commerce headquarters.</span></span> <span data-ttu-id="fbcbc-109">Ta funkcja udostępnia widok dostępności zapasów produktów we wszystkich sklepach i magazynach.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-109">This functionality provides an inventory availability view of products across stores and warehouses.</span></span> <span data-ttu-id="fbcbc-110">Pomaga również sprzedawcom detalicznym jeszcze bardziej poprawić efektywność i obniżać koszty poprzez usprawnienie planowania zapasów w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-110">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="fbcbc-111">Gdy operacja wyszukiwania zapasów jest uruchamiana z aplikacji punktu sprzedaży, kasjer punktu sprzedaży używa klawiatury numerycznej do wprowadzenia numeru produktu w celu wysłania zapytania o informacje o zapasach.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-111">When the inventory lookup operation is started from the POS application, the POS cashier uses the numeric keyboard to enter a product number to query its inventory information.</span></span> <span data-ttu-id="fbcbc-112">Jeśli wprowadzony produkt ma warianty, kasjer może opcjonalnie wybrać wymiary lub inne wartości, aby sprawdzić informacje magazynowe określonego wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-112">If the product entered has variants, the cashier can optionally select dimensions or other values to check inventory information of a specific product variant.</span></span>

## <a name="inventory-lookup-list-view-for-individual-products"></a><span data-ttu-id="fbcbc-113">Widok listy wyszukiwania zapasów dla poszczególnych produktów</span><span class="sxs-lookup"><span data-stu-id="fbcbc-113">Inventory lookup list view for individual products</span></span>

<span data-ttu-id="fbcbc-114">W przypadku pojedynczego produktu operacja wyszukiwania zapasów udostępnia widok listy wyszukiwania zapasów, w którym są wyświetlane następujące informacje o produktach z listy lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="fbcbc-114">For an individual product, the inventory lookup operation provides an inventory lookup list view showing the following product information for a list of locations:</span></span>

- <span data-ttu-id="fbcbc-115">**Zapasy** — odnosi się do „fizycznie dostępnej” ilości produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-115">**Inventory** - Refers to the "available physical" quantity of a product.</span></span>
- <span data-ttu-id="fbcbc-116">**Zarezerwowane** — dotyczy ilości fizycznie zarezerwowanej pobranej z centrali.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-116">**Reserved** - Refers to the "physical reserved" quantity retrieved from headquarters.</span></span>
- <span data-ttu-id="fbcbc-117">**Zamówiona** — Odnosi się do ilości „zamówionych ogółem” pobranej z centrali.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-117">**Ordered** - Refers to the "ordered in total" quantity retrieved from headquarters.</span></span>
- <span data-ttu-id="fbcbc-118">**Jednostka** — odnosi się do towaru jednostka miary skonfigurowanego w centrali.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-118">**Unit** - Refers to the inventory unit of measure configured in headquarters.</span></span>

<span data-ttu-id="fbcbc-119">Widok listy lokalizacji zawiera wszystkie sklepy i magazyny skonfigurowane w grupach realizacji, z którym jest połączony bieżący sklep, jak pokazano na poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-119">The list view of locations includes all stores and warehouses that are configured in the fulfillment groups that the current store is linked to, as shown in the following example image.</span></span>

![Widok listy operacji wyszukiwania zapasów](media/inventory-lookup-list-view.png)

<span data-ttu-id="fbcbc-121">Na pasku aplikacji POS są dostępne następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="fbcbc-121">The following actions are available on the POS app bar:</span></span>

- <span data-ttu-id="fbcbc-122">**Sortuj** — ta akcja umożliwia użytkownikowi punktu końcowego posortowanie danych w widoku listy na podstawie różnych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-122">**Sort** - This action lets the POS user sort the data in the list view based on various criteria.</span></span> <span data-ttu-id="fbcbc-123">Sortowanie oparte na lokalizacjach jest domyślną opcją sortowania.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-123">Location-based sorting is the default sort option.</span></span> 
  - <span data-ttu-id="fbcbc-124">**Lokalizacja geograficzna** (od najbliższej do najmniejszej lokalizacji w porównaniu z bieżącym sklepem)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-124">**Geo location** (from the closest location to the farthest location, compared with the current store)</span></span>
  - <span data-ttu-id="fbcbc-125">**Nazwa** (w kolejności rosnącej lub malejącej)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-125">**Name** (in ascending or descending order)</span></span>
  - <span data-ttu-id="fbcbc-126">**Numer sklepu** (w kolejności rosnącej lub malejącej)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-126">**Store number** (in ascending or descending order)</span></span>
  - <span data-ttu-id="fbcbc-127">**Zapasy** (w porządku malejącym)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-127">**Inventory** (in descending order)</span></span>
  - <span data-ttu-id="fbcbc-128">**Zarezerwowany** (w porządku malejącym)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-128">**Reserved** (in descending order)</span></span>
  - <span data-ttu-id="fbcbc-129">**Zamówiona** (w porządku malejącym)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-129">**Ordered** (in descending order)</span></span>
- <span data-ttu-id="fbcbc-130">**Filtr** — ta akcja umożliwia użytkownikowi punktu końcowego wyświetlenie przefiltrowanych danych dla określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-130">**Filter** - This action lets the POS user view filtered data for a specific location.</span></span>
- <span data-ttu-id="fbcbc-131">**Pokaż dostępność sklepu** — ta akcja umożliwia użytkownikowi punktu sprzedaży wyświetlenie ilości dostępnych do dostępności (ATP) dla produktu w wybranym sklepie.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-131">**Show store availability** - This action lets the POS user view the available-to-promise (ATP) quantities for a product in the selected store.</span></span>
- <span data-ttu-id="fbcbc-132">**Pokaż lokalizację sklepu** — ta akcja powoduje otwarcie osobnej strony w celu wyświetlenia widoku mapy, adresu i godzin sklepu dla wybranego sklepu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-132">**Show store location** - This action opens a separate page to show the map view, address, and store hours for the selected store.</span></span>
- <span data-ttu-id="fbcbc-133">**Odbierz w sklepie** - Ta akcja tworzy zamówienie klienta na produkt, który zostanie odebrany z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-133">**Pick up in store** - This action creates a customer order for the product that will be picked up from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="fbcbc-134">**Wyślij produkt** - Ta akcja tworzy zamówienie klienta na produkt, który zostanie wysłany z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-134">**Ship product** - This action creates a customer order for the product that will be shipped from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="fbcbc-135">**Wyświetlanie wszystkich wariantów** — w przypadku produktu z wariantami ta akcja przełącza się z widoku listy na widok macierzy, w którym są wyświetlane informacje o zapasach dla wszystkich wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-135">**View all variants** - For a product with variants, this action switches from a list view to a matrix view that displays inventory information for all variants of the product.</span></span>
- <span data-ttu-id="fbcbc-136">**Dodaj do transakcji** — ta akcja powoduje dodanie produktu do koszyka i przekierowywanie użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-136">**Add to transaction** - This action adds the product to the cart and redirects the user to the transaction screen.</span></span>

> [!NOTE]
> <span data-ttu-id="fbcbc-137">W przypadku sortowania opartego na lokalizacjach odległość między lokalizacją a bieżącym sklepem jest określana na podstawie współrzędnych (szerokości geograficznej i długości) zdefiniowanych w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-137">For a location-based sort, the distance between a location and current store is determined by the coordinates (latitude and longitude) defined in Commerce headquarters.</span></span> <span data-ttu-id="fbcbc-138">W przypadku sklepu informacje o lokalizacji są definiowane w podstawowym adresie jednostki operacyjnej skojarzonej ze sklepem.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-138">For a store, the location information is defined in the primary address of the operating unit associated with the store.</span></span> <span data-ttu-id="fbcbc-139">W przypadku magazynu, który nie jest magazynem sklepowym, informacje o lokalizacji są zdefiniowane w adresie magazynu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-139">For a non-store warehouse, the location information is defined in the warehouse address.</span></span> <span data-ttu-id="fbcbc-140">Jeśli dla bieżącego sklepu nie są poprawnie zdefiniowane współrzędne, opcja sortowania według lokalizacji spowoduje wyświetlenie bieżącego sklepu na początku listy, a następnie posortowanie innych lokalizacji według nazwy.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-140">If the current store doesn't have coordinates properly defined, the location-based sort option will display the current store at the top of the list and then sort other locations by name.</span></span>

> [!NOTE]
> <span data-ttu-id="fbcbc-141">Akcje **Pokaż dostępność sklepu**, **Pokaż lokalizację sklepu**, **Odbiór w sklepie** i **Wyślij produkt** są niedostępne w lokalizacjach poza sklepem.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-141">The **Show store availability**, **Show store location**, **Pick up in store**, and **Ship product** actions are not available for non-store locations.</span></span>

## <a name="inventory-lookup-matrix-view-for-variants"></a><span data-ttu-id="fbcbc-142">Widok macierzy wyszukiwania zapasów dla wariantów</span><span class="sxs-lookup"><span data-stu-id="fbcbc-142">Inventory lookup matrix view for variants</span></span>

<span data-ttu-id="fbcbc-143">W przypadku produktu głównego z wariantami operacja wyszukiwania zapasów udostępnia także widok macierzy oparty na wymiarach, który wyświetla informacje o dostępności zapasów dla wszystkich wariantów produktu głównego w wybranej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-143">For a master product with variants, the inventory lookup operation also provides a dimension-based matrix view that displays inventory availability information for all variants of the master product at a selected location.</span></span> <span data-ttu-id="fbcbc-144">Domyślnie widok macierzy pokazuje dane dla bieżącego sklepu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-144">By default, the matrix view shows data for the current store.</span></span> <span data-ttu-id="fbcbc-145">Akcji **Sklep** na pasku aplikacji można użyć w celu wyszukiwania informacji o zapasach w innych sklepach skonfigurowanych w grupach realizacji, z które jest połączony bieżący sklep.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-145">You can use the **Store** action on the app bar to look up inventory information at other stores configured in the fulfillment groups that the current store is linked to.</span></span>

<span data-ttu-id="fbcbc-146">Poniższy przykładowy obraz przedstawia widok macierzy wyszukiwania zapasów w programie POS.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-146">The following example image shows the inventory lookup matrix view in POS.</span></span>

![Widok macierzy operacji wyszukiwania zapasów](media/inventory-lookup-matrix-view.png)

<span data-ttu-id="fbcbc-148">W widoku macierzy każda komórka reprezentuje indywidualny wariant i wyświetla stan zapasów (dostępna fizyczna) w prawym dolnym rogu, a także wartości **zarezerwowane** (zarezerwowane fizycznie) i **zamówione** (łącznie) w górnym -lewy róg.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-148">In the matrix view, each cell represents an individual variant, and displays an on-hand inventory (available physical) value in the lower-right corner, as well as **reserved** (physical reserved) and **ordered** (ordered in total) values in the upper-left corner.</span></span> <span data-ttu-id="fbcbc-149">Poniższa tabela wyjaśnia znaczenie różnych dostępnych wartości.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-149">The following table explains the meaning of the various on-hand values.</span></span>

| <span data-ttu-id="fbcbc-150">Dostępna wartość</span><span class="sxs-lookup"><span data-stu-id="fbcbc-150">On-hand value</span></span>                            | <span data-ttu-id="fbcbc-151">opis</span><span class="sxs-lookup"><span data-stu-id="fbcbc-151">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="fbcbc-152">Wartość liczbowa większa niż 0 (zero)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-152">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="fbcbc-153">Wariant został pomyślnie zwolniony do wybranej lokalizacji i można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-153">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> |
| <span data-ttu-id="fbcbc-154">**0** (zero)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-154">**0** (zero)</span></span>                             | <span data-ttu-id="fbcbc-155">Wariant został pomyślnie zwolniony do wybranej lokalizacji, ale towar nie jest w niej dostępny.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-155">A variant has been released to the selected location, but the item isn't available at the selected location.</span></span> <span data-ttu-id="fbcbc-156">Można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-156">You can perform additional actions in the cell.</span></span> |
| <span data-ttu-id="fbcbc-157">**n/d** lub komórka nieaktywna</span><span class="sxs-lookup"><span data-stu-id="fbcbc-157">**n/a**, or an inactive cell</span></span>              | <span data-ttu-id="fbcbc-158">Wariant nie został pomyślnie zwolniony do wybranej lokalizacji i nie można wykonywać dodatkowe czynności w komórce.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-158">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="fbcbc-159">Kolejność wyświetlania wartości wymiarów w widoku macierzy jest oparta na konfiguracji kolejności wyświetlania wymiarów w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-159">The display order of the dimension values in the matrix view is based on the dimension display order configuration in Commerce headquarters.</span></span> <span data-ttu-id="fbcbc-160">Można zmienić konfigurację kolejności wyświetlania wymiarów, wybierając nowy wymiar do użycia.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-160">You can change the dimension display order configuration by selecting a new dimension to use.</span></span> 

<span data-ttu-id="fbcbc-161">W komórce widoku macierzy dostępne są następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="fbcbc-161">The following actions are available in the matrix view cell:</span></span>

- <span data-ttu-id="fbcbc-162">**Sprzedaj teraz** — Ta akcja dodaje wybrany wariant do koszyka i przekierowuje użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-162">**Sell now** - This action adds the selected variant to the cart, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="fbcbc-163">**Odbierz w sklepie** - Ta akcja tworzy zamówienie klienta na wybrany wariant, które zostanie odebrane z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-163">**Pick up in store** - This action creates a customer order for the selected variant that will be picked up from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="fbcbc-164">**Wyślij produkt** -Ta akcja tworzy zamówienie klienta dla wybranego wariantu, które zostanie wysłane z wybranego sklepu i przekierowuje użytkownika do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-164">**Ship product** - This action creates a customer order for the selected variant that will be shipped from the selected store, and redirects the user to the transaction screen.</span></span>
- <span data-ttu-id="fbcbc-165">**Dostępność** — ta akcja przenosi użytkownika na osobną stronę pokazującą ilości ATP dla wybranego wariantu w wybranym sklepie.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-165">**Availability** - This action takes the user to a separate page showing the ATP quantities for the selected variant in the selected store.</span></span>
- <span data-ttu-id="fbcbc-166">**Pokaż wszystkie lokalizacje** — ta akcja przełącza do widoku standardowej listy dostępności zapasów, wyświetlając informacje o zapasach dla wybranego wariantu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-166">**Show all locations** - This action switches to the standard inventory availability list view showing the inventory information for the selected variant.</span></span>
- <span data-ttu-id="fbcbc-167">**Wyświetl szczegóły produktu** — ta akcja przekieruje użytkownika do strony szczegółów produktu (PDP) wybranego wariantu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-167">**View product details** - This action redirects the user to the product details page (PDP) of the selected variant.</span></span>

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a><span data-ttu-id="fbcbc-168">Uzyskiwanie dostępu do wyszukiwania zapasów z innych stron w aplikacji POS</span><span class="sxs-lookup"><span data-stu-id="fbcbc-168">Access inventory lookup from other pages in POS</span></span>

<span data-ttu-id="fbcbc-169">Użytkownicy punktu dostępu mogą uzyskać dostęp do operacji wyszukiwania zapasów z innych stron w programie POS.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-169">POS users can access the inventory lookup operation from other pages in POS.</span></span>

<span data-ttu-id="fbcbc-170">Poniższy przykładowy obraz przedstawia wyniki wyszukiwania zapasów z PDP w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-170">The following example image shows inventory lookup results from a PDP in POS.</span></span>

![Wyszukiwania zapasów ze strony szczegółów produktu](media/inventory-lookup-from-product-details-page.png)

<span data-ttu-id="fbcbc-172">W pdp produktu głównego można użyć akcji **Wyświetlanie wszystkich wariantów** na pasku aplikacji w celu uruchomienia widoku macierzy wyszukiwania zapasów, w którym są wyświetlane informacje o dostępności zapasów dla bieżącego sklepu dla wszystkich wariantów produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-172">On the PDP of a master product, you can use the **View all variants** action on the app bar to launch the inventory lookup matrix view that displays inventory availability information for the current store for all variants of a product.</span></span> <span data-ttu-id="fbcbc-173">W przypadku pojedynczego produktu pdP wyświetla wartość dostępnych zapasów (fizycznie dostępnych) tego produktu dla bieżącego sklepu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-173">For an individual product, the PDP displays the on-hand inventory (available physical) value of that product for the current store.</span></span> <span data-ttu-id="fbcbc-174">Dodatkowo można zaznaczyć łącze **Inne zapasy sklepów**, aby uruchomić operację wyszukiwania zapasów, aby sprawdzić dostępność zapasów produktu w innych sklepach lub magazynach.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-174">Additionally, you can select the **Other stores inventory** link to launch the inventory lookup operation to check the inventory availability of a product across other stores or warehouses.</span></span>

> [!NOTE]
> <span data-ttu-id="fbcbc-175">Akcja **Wyświetl wszystkie warianty** na PDP jest dostępna tylko dla produktów głównych, które mają warianty.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-175">The **View all variants** action on the PDP is available only for master products that have variants.</span></span> <span data-ttu-id="fbcbc-176">Nie jest dostępna dla określonych produktów lub zestawów.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-176">It isn't available for specific products or kits.</span></span>

<span data-ttu-id="fbcbc-177">Można skonfigurować operację wyszukiwania zapasów, aby była wyświetlana jako łącze w siatce przycisków na ekranie transakcji POS.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-177">You can configure the inventory lookup operation to appear as a link in the button grid on the POS transaction screen.</span></span> <span data-ttu-id="fbcbc-178">Po konfiguracji, gdy użytkownik wybierze wiersz koszyka, a następnie wybierze przycisk **Wyszukiwania zapasów**, zostanie wyświetlony widok listy wyszukiwania zapasów dla wybranego produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-178">After configuration, when the user selects a cart line and then selects the **Inventory lookup** button, the inventory lookup list view for the selected product will be displayed.</span></span> <span data-ttu-id="fbcbc-179">Aby uzyskać więcej informacji dotyczących konfigurowania siatek przycisków za pomocą narzędzia konstruktora układu ekranu programu POS, zobacz [konfiguracje graficzne interfejsu użytkownika programu POS](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="fbcbc-179">For more information about how to configure button grids using POS screen layout designer tool, see [POS user interface visual configurations](pos-screen-layouts.md).</span></span>

## <a name="inventory-lookup-with-channel-side-calculation"></a><span data-ttu-id="fbcbc-180">Wyszukiwanie w magazynie z obliczaniem po stronie kanału</span><span class="sxs-lookup"><span data-stu-id="fbcbc-180">Inventory lookup with channel-side calculation</span></span>

<span data-ttu-id="fbcbc-181">W wersji Commerce 10.0.9 i wcześniejszych **dostępne fizycznie** wartość w operacji wyszukiwania zapasów jest pobierana z centrali Commerce za pośrednictwem połączenia serwisowego w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-181">In Commerce release 10.0.9 and earlier, the **available physical** value in the inventory lookup operation is retrieved from Commerce headquarters via a real-time service call.</span></span> <span data-ttu-id="fbcbc-182">W wersji Commerce 10.0.10 i nowszych można skonfigurować operację wyszukiwania zapasów POS, aby używać obliczeń po stronie kanału na serwerze Commerce w celu określenia dostępnej wartości fizycznej, co może zapewnić bardziej wiarygodne i dokładniejsze oszacowanie dostępnych zapasów poprzez uwzględnienie danych transakcyjnych, które nie zostały jeszcze zsynchronizowane z centralą.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-182">In Commerce release 10.0.10 and later, you can configure the POS inventory lookup operation to use channel-side calculation on the Commerce server to determine the available physical value, which can provide a more reliable and more accurate estimate of the on-hand inventory by factoring in the transactional data that is not yet synchronized to headquarters.</span></span> <span data-ttu-id="fbcbc-183">Aby uzyskać więcej informacji o obliczaniu zapasów po stronie kanału i związanej z nim konfiguracji programu POS w centrali, zobacz temat [Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="fbcbc-183">For more information about channel-side inventory calculation and related POS configuration in headquarters, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fbcbc-184">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fbcbc-184">Additional resources</span></span>

[<span data-ttu-id="fbcbc-185">Konfiguracje wizualne interfejsu użytkownika punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="fbcbc-185">POS user interface visual configurations</span></span>](pos-screen-layouts.md)

[<span data-ttu-id="fbcbc-186">Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="fbcbc-186">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]