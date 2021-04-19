---
title: Mieszanie wymiarów produktów w lokalizacji
description: Ten temat zawiera informacje dotyczące mieszania rozmiarów produktów w lokalizacji. Ta funkcja profilu lokalizacji pomaga poprawić zarządzanie lokalizacjami, gdy używane są różne warianty produktu lub produkty mają różne wymiary – np. w branży modowej. Dzięki temu można określić, czy konfiguracje, kolory, style i rozmiary mogą być mieszane dla określonego profilu lokalizacji, czy dozwolony jest np. tylko jeden z tych wymiarów lub jakieś połączenie możliwości, które można umieścić w tej samej lokalizacji.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 28f59052a74b6d8b263c7a8a8b6061f2c4b34c89
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831297"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="1ef0c-105">Mieszanie wymiarów produktów w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1ef0c-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ef0c-106">Mieszanie wymiarów produktów w lokalizacji to funkcja profilu lokalizacji pomagająca poprawić zarządzanie przestrzenią, gdy używane są różne warianty produktu lub produkty mają różne wymiary – np. w branży modowej.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="1ef0c-107">Dzięki temu można określić, czy konfiguracje, kolory, style i rozmiary mogą być mieszane dla określonego profilu lokalizacji, czy dozwolony jest np. tylko jeden z tych wymiarów lub jakieś połączenie możliwości, które można umieścić w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="1ef0c-108">Włącz funkcję mieszania różnych wymiarów produktów w lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1ef0c-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="1ef0c-109">Aby móc używać funkcji mieszania wymiarów produktów w lokalizacji, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="1ef0c-110">Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="1ef0c-111">Ta funkcja jest wymieniona w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="1ef0c-112">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="1ef0c-113">**Nazwa funkcji:** *Mieszanie różnych wymiarów produktów w lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="1ef0c-114">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="1ef0c-114">Setup</span></span>

<span data-ttu-id="1ef0c-115">Z każdą lokalizacją w magazynie musi być skojarzony profil lokalizacji opisujący jej właściwości.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="1ef0c-116">Dlatego po skonfigurowaniu działania funkcji wszystkie lokalizacje korzystające z tego samego profilu lokalizacji będą mogły korzystać z możliwości mieszania wymiarów produktów w lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="1ef0c-117">Konfiguruj profile lokalizacji, aby umożliwić mieszanie wymiarów produktu</span><span class="sxs-lookup"><span data-stu-id="1ef0c-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="1ef0c-118">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="1ef0c-119">Z listy profilów lokalizacji wybierz opcję **BULK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="1ef0c-120">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1ef0c-121">Na skróconej karcie **Ogólne** ustaw opcję **Włącz mieszanie wymiarów produktów w lokalizacji** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ef0c-122">Tę opcję można ustawiać na *Tak* tylko wtedy, gdy wartość opcji **Zezwalaj na towary mieszane** jest ustawiona na *Nie*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="1ef0c-123">Na skróconej karcie **Zezwalaj na mieszanie wymiarów produktów** ustaw opcję **Rozmiar** na *Tak*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="1ef0c-124">W scenariuszu opisanym w tym temacie mieszanie może być wykonane tylko dla produktów mających różne **Rozmiary**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="1ef0c-125">Dostępne są także inne opcje.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-125">However, other options are also available.</span></span>
1. <span data-ttu-id="1ef0c-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="1ef0c-127">Stwórz nowy produkt główny i jego warianty</span><span class="sxs-lookup"><span data-stu-id="1ef0c-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="1ef0c-128">Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Produkty \> Produkty główne**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="1ef0c-129">W okienku akcji wybierz opcję **Nowa**, aby utworzyć nowy produkt główny.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="1ef0c-130">W wyświetlonym oknie dialogowym **Nowy produkt** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-131">**Typ produktu:** *Przedmiot*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="1ef0c-132">**Podtyp produktu:** *Produkt główny*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="1ef0c-133">**Numer produktu:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="1ef0c-134">**Nazwa produktu:** *B0001 Rozmiar*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="1ef0c-135">**Wymiar grupy produktu:** *Rozmiar*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="1ef0c-136">**Technologia konfiguracji:** *Wariant predefiniowany*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="1ef0c-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-137">Select **OK**.</span></span>
1. <span data-ttu-id="1ef0c-138">Na stronie **Szczegóły produktu** na skróconej karcie **Ogólne** należy określić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-139">**Automatyczne generowanie wariantów** *Tak*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="1ef0c-140">**Grupa rozmiarów:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="1ef0c-141">Aby wyświetlić wstępnie zdefiniowane warianty, w okienku akcji wybierz opcję **Warianty produktu**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="1ef0c-142">Zostanie wyświetlona strona **Warianty produktu**, a w polu zostanie wyświetlona lista wariantów z konfiguracji grupy rozmiarów.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="1ef0c-143">Zwalnianie produktów do firmy USMF</span><span class="sxs-lookup"><span data-stu-id="1ef0c-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="1ef0c-144">W okienku akcji wybierz pozycję **Zwalnianie produktów**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="1ef0c-145">Na stronie **Wybierz produkty do zwolnienia** potwierdź, że numer produktu *B0001* znajduje się na liście, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="1ef0c-146">Wybierz przycisk **Dalej**, aby potwierdzić warianty produktu do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="1ef0c-147">Na stronie **Wybierz firmy do których ma nastąpić zwolnienie** wybierz pozycję *USMF*, a następnie wybierz przycisk **Dalej**, aby potwierdzić wybór.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="1ef0c-148">Na stronie **Potwierdzenie wyboru** wybierz przycisk **Zakończ**, aby dokończyć zwalnianie.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="1ef0c-149">Zostanie wyświetlony komunikat „Operacja zakończona”.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="1ef0c-150">Aktualizowanie zwolnionego produktu w firmie USMF</span><span class="sxs-lookup"><span data-stu-id="1ef0c-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="1ef0c-151">Należy się upewnić, że użytkownik jest zalogowany do firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="1ef0c-152">Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Zwolnione produkty**, aby zakończyć tworzenie zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="1ef0c-153">Znajdź i wybierz numer pozycji *B0001*, aby otworzyć stronę **Szczegóły zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="1ef0c-154">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1ef0c-155">Na skróconej karcie **Ogólne** upewnij się, że w polu **Grupa modeli towaru** ustawiono wartość *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="1ef0c-156">W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Grupy wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="1ef0c-157">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-157">Set the following values:</span></span>

    - <span data-ttu-id="1ef0c-158">**Grupa wymiarów magazynowania:** *Towar*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="1ef0c-159">**Grupa wymiarów śledzenia:** *Brak*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="1ef0c-160">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-160">Select **OK**.</span></span>
1. <span data-ttu-id="1ef0c-161">W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Hierarchia rezerwacji**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="1ef0c-162">W polu **Hierarchia rezerwacji** wybierz wartość *Domyślne*, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="1ef0c-163">Na skróconej karcie **Ogólne** w sekcji **Administracja** zwróć uwagę, że wybory zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="1ef0c-164">Na skróconej karcie **Zakup** w polu **Cena** wprowadź wartość *10*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="1ef0c-165">Na skróconej karcie **Zarządzanie kosztami** w polu **Grupa pozycji** wprowadź *Audio*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="1ef0c-166">Na skróconej karcie **Zakup** w polu **Cena** wprowadź wartość *10*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="1ef0c-167">Na skróconej karcie **Magazyn** w polu **Identyfikator grupy sekwencji jednostek** wprowadź wartość *ea*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="1ef0c-168">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="1ef0c-169">Tworzenie dyrektywy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="1ef0c-169">Create a location directive</span></span>

1. <span data-ttu-id="1ef0c-170">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="1ef0c-171">W lewym panelu, w polu **Typ zlecenia pracy** zaznacz opcję *Zamówienia zakupu*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="1ef0c-172">Z listy wybierz dyrektywę lokalizacji o nazwie *24 PO Direct*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="1ef0c-173">Na skróconej karcie **Działania dyrektywy lokalizacji** wybierz **Nowe**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="1ef0c-174">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-175">**Numer sekwencyjny:** *1*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="1ef0c-176">Nowy wiersz powinien znajdować się przed poprzednio istniejącym wierszem.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="1ef0c-177">Aby wprowadzić zmianę, użyj przycisków **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi lub zmień wartość w polu **Numer sekwencyjny** istniejącego wiersza na *2*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="1ef0c-178">**Nazwa:** *Umieść w profilu lokalizacji zbiorczej BULK*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="1ef0c-179">**Stałe użycie lokalizacji:** *Stałe i niestałe lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="1ef0c-180">**Zezwalaj na ujemne zapasy:** *Wyczyść to pole wyboru (=Nie)*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="1ef0c-181">**Partia włączona:** *Wyczyść to pole wyboru (=Nie)*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="1ef0c-182">**Strategia:** *Brak*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="1ef0c-183">Gdy nowy wiersz jest wciąż zaznaczony, wybierz polecenie **Edytuj kwerendę** powyżej siatki.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="1ef0c-184">W polu dialogowym kwerendy, na karcie **Zakres** wybierz przycisk  **Dodaj**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="1ef0c-185">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-186">**Tabela:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="1ef0c-187">**Tabela pochodna:** *Lokalizacje*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="1ef0c-188">**Pole:** *Identyfikator profilu lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="1ef0c-189">**Kryteria:** *BULK*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="1ef0c-190">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-190">Select **OK**.</span></span>
1. <span data-ttu-id="1ef0c-191">Na stronie **Dyrektywy lokalizacji** w okienku akcji wybierz **Zapisz**, aby zapisać nową dyrektywę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1ef0c-192">Na skróconej karcie **Akcje dyrektywy lokalizacji** w polu **Strategia**, jeśli wykorzystywana jest strategia lokalizacji *Konsolidacja*, konfiguracja skróconej karty **Dozwolone mieszanie wymiarów produktów** znajdującej się w **Profilach lokalizacji** zostanie nadpisane, a przedmioty będą umieszczane w tej samej lokalizacji, nawet jeśli takie zachowanie nie jest dozwolone przez konfigurację.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="1ef0c-193">Tworzenie elementu menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="1ef0c-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="1ef0c-194">Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="1ef0c-195">W okienku akcji wybierz opcję **Nowy**, aby utworzyć element menu służący do sortowania.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="1ef0c-196">W nagłówku ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-197">**Nazwa elementu menu:** *Wiersz zamówienia zakupu – przyjęcie*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="1ef0c-198">**Nazwa:** *Wiersz zamówienia zakupu – przyjęcie*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="1ef0c-199">**Tryb:** *Praca*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="1ef0c-200">**Używanie istniejącej pracy:** *Nie*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="1ef0c-201">Na skróconej karcie **Ogólne** ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-202">**Proces tworzenia pracy:** *Przyjęcie i umieszczenie wierszy zamówienia zakupu*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="1ef0c-203">**Generuj numer identyfikacyjny:** *Tak*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="1ef0c-204">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="1ef0c-205">Konfigurowanie menu urządzenia przenośnego</span><span class="sxs-lookup"><span data-stu-id="1ef0c-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="1ef0c-206">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="1ef0c-207">Z listy menu wybierz opcję **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="1ef0c-208">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1ef0c-209">Na liście **Dostępne menu i elementy menu** znajdź i zaznacz **Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="1ef0c-210">Wybierz przycisk Strzałka w prawo, aby przenieść **Wiersz zamówienia zakupu – przyjęcie** do listy **Struktura menu**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="1ef0c-211">W ten sposób dodasz nowy element menu do wybranego menu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="1ef0c-212">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="1ef0c-213">Scenariusz</span><span class="sxs-lookup"><span data-stu-id="1ef0c-213">Scenario</span></span>

<span data-ttu-id="1ef0c-214">Ten scenariusz pokazowy prezentuje, jak dwa różne warianty produktów mogą być umieszczane w tej samej lokalizacji, gdy profil lokalizacji nie zezwala na towary mieszane, ale jest włączona funkcja *Mieszania wymiarów produktów w lokalizacji*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="1ef0c-215">W takim przypadku, używane kryterium to **Rozmiar**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="1ef0c-216">Przed rozpoczęciem należy się upewnić, że w magazynie *24* znajdują się puste lokalizacje, w których jest używany profil lokalizacji zbiorczej *BULK*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="1ef0c-217">Tworzenie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="1ef0c-217">Create a purchase order</span></span>

<span data-ttu-id="1ef0c-218">Użytkownik utworzy zamówienie zakupu z trzema wierszami: dwa wiersze dla tego samego numeru produktu, ale różne warianty **Rozmiaru** oraz trzeci wiersz dla innego produktu, który nie ma wariantów.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="1ef0c-219">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="1ef0c-220">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="1ef0c-221">W wyświetlonym oknie dialogowym **Utwórz zamówienie zakupu** można ustawić następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-222">**Konto dostawcy:** *1001*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="1ef0c-223">**Magazyn:** *24*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="1ef0c-224">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-224">Select **OK**.</span></span>
1. <span data-ttu-id="1ef0c-225">Utworzono zamówienie zakupu, a w wierszach skróconej karty **Wiersze zamówienia zakupu** jest dodawany nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="1ef0c-226">Zanotuj numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="1ef0c-227">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1ef0c-228">**Numer pozycji:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="1ef0c-229">**Rozmiar** *L*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-229">**Size** *L*</span></span>
    - <span data-ttu-id="1ef0c-230">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="1ef0c-231">Wybierz polecenie **Dodaj wiersz** ponad siatką, dodaj drugi wiersz zamówienia zakupu i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="1ef0c-232">**Numer pozycji:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="1ef0c-233">**Rozmiar** *XL*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-233">**Size** *XL*</span></span>
    - <span data-ttu-id="1ef0c-234">**Ilość:** *2*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="1ef0c-235">Wybierz polecenie **Dodaj wiersz**, dodaj trzeci wiersz zamówienia zakupu i określ następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="1ef0c-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="1ef0c-236">**Numer pozycji:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="1ef0c-237">**Ilość:** *1*</span><span class="sxs-lookup"><span data-stu-id="1ef0c-237">**Quantity:** *1*</span></span>

<span data-ttu-id="1ef0c-238">1. Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="1ef0c-239">Odbiór wierszy zamówienia zakupu w aplikacji Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="1ef0c-239">Receive purchase order lines in the Warehouse Management mobile app</span></span>

1. <span data-ttu-id="1ef0c-240">Zaloguj się do aplikacji Warehouse Management jako użytkownik, który jest uruchomiony dla magazynu *24*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-240">Sign in to the Warehouse Management mobile app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="1ef0c-241">Wybierz menu **Przychodzące**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="1ef0c-242">Wybierz **Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="1ef0c-243">Zaznacz pole **PONUM**, a następnie wprowadź numer zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="1ef0c-244">Potwierdź swój wpis, wybierając przycisk Potwierdź ( ✔ ) u dołu strony.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="1ef0c-245">Umożliwia wprowadzenie numeru wiersza z otrzymanego zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="1ef0c-246">Zaznacz pole **LINENUM**, a następnie za pomocą konsoli numerycznej wprowadź wartość *1*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="1ef0c-247">Potwierdź wpis.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-247">Confirm your entry.</span></span>
1. <span data-ttu-id="1ef0c-248">Umożliwia wprowadzenie ilości, która ma zostać odebrana.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-248">Enter the quantity to receive.</span></span> <span data-ttu-id="1ef0c-249">Kliknij przycisk **+** dwa razy, aby zwiększyć wartość w polu **Ilość** do wartości *2*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="1ef0c-250">Zarejestruj wpis, wybierając przycisk ( ✔ ) u dołu strony, a następnie potwierdź swój wpis, wybierając ponownie przycisk ( ✔ ).</span><span class="sxs-lookup"><span data-stu-id="1ef0c-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="1ef0c-251">Umożliwia wyświetlanie informacji na stronie **Zamówienia zakupu: Umieść**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="1ef0c-252">Na tej stronie jest wyświetlona praca, która została utworzona dla działania umieszczenia (praca 1).</span><span class="sxs-lookup"><span data-stu-id="1ef0c-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="1ef0c-253">Zostanie wyświetlona lokalizacja odebranego towaru, numer identyfikacyjny, towar, rozmiar oraz ilość zakończonego zadania **Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="1ef0c-254">Potwierdź pracę umieszczenia.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="1ef0c-255">Powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 2.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="1ef0c-256">Jednak w kroku 8 należy określić ilość równą *1*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="1ef0c-257">Nowa praca umieszczenia (Praca 2) jest tworzona dla tej samej lokalizacji co Praca 1.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="1ef0c-258">Znowu powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 2.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="1ef0c-259">Jednak w kroku 8 należy określić pozostałą ilość równą *1*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="1ef0c-260">Nowa praca umieszczenia (Praca 3) jest tworzona dla tej samej lokalizacji co Praca 1 i 2.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="1ef0c-261">To zachowanie występuje, ponieważ jest używana strategia dyrektywy lokalizacji *Konsolidacja*, a na skróconej karcie **Dozwolone mieszanie wymiarów** w konfiguracja **Profilu lokalizacji** *Bulk* pozwala na mieszanie wariantu **Rozmiar** w danej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="1ef0c-262">Powtórz kroki od 4 do 11 dla wiersza zamówienia zakupu 3.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="1ef0c-263">W kroku 8 określ ilość równą *1* dla towaru o numerze *A0001*.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="1ef0c-264">Nowa praca odłożenia (Praca 4) jest tworzona dla innej lokalizacji niż lokalizacja używana dla wierszy zamówienia zakupu 1 i 2.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="1ef0c-265">To zachowanie występuje, ponieważ profil lokalizacji nie zezwala na produkty mieszane, ale pozwala na tworzenie mieszanych wymiarów tego samego produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="1ef0c-266">Wybierz przycisk menu u góry strony (czasami nazywany przyciskiem Hamburger lub Hamburger), a następnie wybierz opcję **Anuluj**, aby zamknąć **Wiersz zamówienia zakupu – przyjęcie**.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="1ef0c-267">Ten scenariusz można powtórzyć, ale zmienić wartość **Rozmiar** - *Nie* na skróconej karcie **Zezwalaj na mieszanie wymiarów produktów** w profilu **Profile lokalizacji** zbiorczej *BULK*, tak aby żaden z wymiarów produktu nie mógł być mieszany.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="1ef0c-268">W takim przypadku po odebraniu zamówienia zakupu każdy wariant produktu zostanie umieszczony w nowym miejscu.</span><span class="sxs-lookup"><span data-stu-id="1ef0c-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]