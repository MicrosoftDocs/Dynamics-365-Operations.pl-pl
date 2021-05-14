---
title: Grupy jakości pozycji
description: W tym temacie opisano sposób używania i tworzenia grup kontroli jakości towarów w celu logicznego grupowania produktów w celu przypisania ich do skojarzeń jakości w celu automatycznego generowania zleceń kontroli jakości.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3074a6a8cc054be045bf593b509e76a1043af0b7
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956785"
---
# <a name="item-quality-groups"></a><span data-ttu-id="a4b84-103">Grupy jakości pozycji</span><span class="sxs-lookup"><span data-stu-id="a4b84-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4b84-104">Grupa jakości reprezentuje wspólne wymagania dotyczące testowania towarów.</span><span class="sxs-lookup"><span data-stu-id="a4b84-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="a4b84-105">W tym temacie opisano sposób używania i tworzenia grup kontroli jakości towarów w celu logicznego grupowania produktów w celu przypisania ich do skojarzeń jakości w celu automatycznego generowania zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="a4b84-106">W celu konfigurowanie, edytowania i wyświetlania towarów przypisanych do grupy kontroli jakości lub grup kontroli jakości przypisanych do towaru, należy przejść do **Zarządzanie zapasami \> Ustawienia \> Grupy kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="a4b84-107">Po zdefiniowaniu wymogów testu na stronie **Grupy testowe** można zdefiniować reguły automatycznego generowania zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="a4b84-108">Aby uprościć proces, nie definiuje się reguł dla poszczególnych towarów.</span><span class="sxs-lookup"><span data-stu-id="a4b84-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="a4b84-109">Zamiast tego można zdefiniować się reguły dla grupy kontroli jakości na stronie **Skojarzenia jakości**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="a4b84-110">Przykład grupy kontroli jakości towarów</span><span class="sxs-lookup"><span data-stu-id="a4b84-110">Example of an item quality group</span></span>

<span data-ttu-id="a4b84-111">Firma produkcyjna nabywa kilka surowców mających te same wymagania dotyczące testowania przed zbliżającą się inspekcją.</span><span class="sxs-lookup"><span data-stu-id="a4b84-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="a4b84-112">Dlatego firma definiuje grupę kontroli jakości, a następnie przypisuje do tej grupy kody towarów, które są skojarzone z surowcami.</span><span class="sxs-lookup"><span data-stu-id="a4b84-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="a4b84-113">Później firma nabywa nowy typ surowca, który ma te same wymagania dotyczące testowania.</span><span class="sxs-lookup"><span data-stu-id="a4b84-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="a4b84-114">Zamiast konfigurować nowe wymagania dotyczące nowego materiału, firma dodaje kod towaru dla nowego materiału do istniejącej grupy jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="a4b84-115">Ta sama firma produkuje również towary mające te same wymagania dotyczące testowania produkcji i wysyła towary mające te same wymagania dotyczące przeprowadzania testów przed wysyłką.</span><span class="sxs-lookup"><span data-stu-id="a4b84-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="a4b84-116">Dlatego firma definiuje dwie dodatkowe grupy kontroli jakości i przypisuje do każdej z nich odpowiednie kody towarów.</span><span class="sxs-lookup"><span data-stu-id="a4b84-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="a4b84-117">Tworzenie grupy kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="a4b84-117">Create a quality group</span></span>

<span data-ttu-id="a4b84-118">Aby utworzyć grupę kontroli jakości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="a4b84-119">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="a4b84-120">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="a4b84-121">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="a4b84-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="a4b84-122">**Grupa kontroli jakości** – wpisz unikatowy identyfikator lub nazwę grupy kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="a4b84-123">**Opis** – wprowadź szczegółowy opis grupy kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="a4b84-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a4b84-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="a4b84-125">Ręczne dodawanie towarów do grupy kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="a4b84-125">Manually add items to a quality group</span></span>

<span data-ttu-id="a4b84-126">Aby ręcznie dodać towary do grupy kontroli jakości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="a4b84-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="a4b84-127">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="a4b84-128">Wybierz grupę kontroli jakości, do której chcesz dodać towary.</span><span class="sxs-lookup"><span data-stu-id="a4b84-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="a4b84-129">W okienku akcji kliknij pozycję **Towary**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="a4b84-130">Na stronie **Towary w grupie kontroli jakości** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="a4b84-131">Następnie dla nowego wiersza ustaw w polu **Numer towaru** numer towaru, który chcesz dodać.</span><span class="sxs-lookup"><span data-stu-id="a4b84-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="a4b84-132">Powtórz poprzedni krok dla każdego dodatkowego towaru, który musi zostać dodany.</span><span class="sxs-lookup"><span data-stu-id="a4b84-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="a4b84-133">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="a4b84-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="a4b84-134">Dodawanie wielu towarów do grupy kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="a4b84-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="a4b84-135">Aby dodać wiele towarów do grupy kontroli jakości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="a4b84-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="a4b84-136">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="a4b84-137">Utwórz lub wybierz grupę kontroli jakości, do której chcesz dodać towary.</span><span class="sxs-lookup"><span data-stu-id="a4b84-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="a4b84-138">W okienku akcji kliknij pozycję **Dodaj towary**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="a4b84-139">W oknie dialogowym **Zapytanie** wprowadź kryteria filtrowania towarów, które chcesz dodać.</span><span class="sxs-lookup"><span data-stu-id="a4b84-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="a4b84-140">Można na przykład filtrować wszystkie towary w określonej grupie towarów.</span><span class="sxs-lookup"><span data-stu-id="a4b84-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="a4b84-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-141">Select **OK**.</span></span>
1. <span data-ttu-id="a4b84-142">W oknie dialogowym **Dodawanie towarów** w siatce są wyświetlane wszystkie towary spełniające kryteria zapytania.</span><span class="sxs-lookup"><span data-stu-id="a4b84-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="a4b84-143">Przejrzyj wyniki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-143">Review the results.</span></span>

    <span data-ttu-id="a4b84-144">Jeśli są wymagane jakiekolwiek zmiany, wybierz opcję **Wybierz**, aby powrócić do okna dialogowego **Zapytanie** i skorygować zapytanie.</span><span class="sxs-lookup"><span data-stu-id="a4b84-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="a4b84-145">Jeśli wyniki obejmują wszystkie towary, które chcesz dodać, wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="a4b84-146">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a4b84-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="a4b84-147">Ręczne skojarzenie towaru z grupą kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="a4b84-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="a4b84-148">Aby ręcznie skojarzyć towar z grupą kontroli jakości, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="a4b84-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="a4b84-149">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Grupy kontroli jakości towaru**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="a4b84-150">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="a4b84-151">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="a4b84-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="a4b84-152">**Numer artykułu** — wybierz numer artykułu, aby go dodać.</span><span class="sxs-lookup"><span data-stu-id="a4b84-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="a4b84-153">**Grupa kontroli jakości** — umożliwia wybór grupy kontroli jakości, która ma zostać przypisana do towaru.</span><span class="sxs-lookup"><span data-stu-id="a4b84-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="a4b84-154">Powtórz poprzedni krok dla każdej dodatkowej kombinacji towaru i grupy kontroli jakości, która musi zostać dodana.</span><span class="sxs-lookup"><span data-stu-id="a4b84-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="a4b84-155">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="a4b84-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="a4b84-156">Ręczne dodawanie grupy kontroli jakości ze strony Zwolnione produkty</span><span class="sxs-lookup"><span data-stu-id="a4b84-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="a4b84-157">Aby ręcznie dodać grupę kontroli jakości ze strony **Zwolnione produkty**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="a4b84-158">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="a4b84-159">Wybierz produkt, do którego chcesz przypisać grupę kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="a4b84-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="a4b84-160">W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Jakość** wybierz **Grupy kontroli jakości towaru**.</span><span class="sxs-lookup"><span data-stu-id="a4b84-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="a4b84-161">Na stronie **Towary w grupie kontroli jakości** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="a4b84-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="a4b84-162">Następnie w przypadku nowego wiersza w polu **Grupa kontroli jakości** ustaw grupę kontroli jakości, którą chcesz przypisać do produktu.</span><span class="sxs-lookup"><span data-stu-id="a4b84-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="a4b84-163">Powtórz poprzedni krok z każdą dodatkową grupą kontroli jakości, którą chcesz przypisać do produktu.</span><span class="sxs-lookup"><span data-stu-id="a4b84-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="a4b84-164">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="a4b84-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4b84-165">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a4b84-165">Additional resources</span></span>

- [<span data-ttu-id="a4b84-166">Przyrządy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="a4b84-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="a4b84-167">Testy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="a4b84-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="a4b84-168">Grupy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="a4b84-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="a4b84-169">Zmienne testu zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="a4b84-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="a4b84-170">Powiązania jakości</span><span class="sxs-lookup"><span data-stu-id="a4b84-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
