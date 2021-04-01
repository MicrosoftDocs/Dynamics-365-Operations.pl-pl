---
title: Integrowanie zarządzania składnikami majątku ze środkami trwałymi
description: W tym temacie opisano sposób integrowania modułów zarządzanie składnikami majątku i Środki trwałe, dzięki czemu można łączyć środki trwałe z konserwowanymi składnikami majątku.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: adc14019c243b1992cdaa22ef7aa32cb44bfffd9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253597"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="e8a27-103">Integrowanie zarządzania składnikami majątku ze środkami trwałymi</span><span class="sxs-lookup"><span data-stu-id="e8a27-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8a27-104">Integrując moduły **Zarządzanie składnikami majątku** i **Środki trwałe**, dzięki czemu można łączyć środki trwałe z konserwowanymi składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="e8a27-105">Użytkownicy środków trwałych mogą następnie utworzyć konserwowany składnik majątku z nowego lub istniejącego środka trwałego, a użytkownicy zarządzania zasobami mogą skojarzyć konserwowany składnik majątku z istniejącym środkiem trwałym.</span><span class="sxs-lookup"><span data-stu-id="e8a27-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="e8a27-106">Ta funkcja ułatwia także użytkownikom środków trwałych wyświetlanie kosztów zaksięgowanych z zleceń roboczych dla powiązanych konserwowanych składników majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="e8a27-107">W tym temacie *konserwowany składników majątku* odnoszą się do środków trwałych z modułu **Zarządzanie zasobami** , a *środki trwałe* odnoszą się do środków trwałych z modułu **Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="e8a27-108">Umożliwia ustawienie domyślnej lokalizacji dla nowych konserwowanych składników majątku, które są tworzone ze środków trwałych (opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="e8a27-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="e8a27-109">Ta opcjonalna konfiguracja umożliwia ustawienie domyślnej lokalizacji czynności konserwacyjnych dla nowych konserwowanych składników majątku, które są tworzone ze środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="e8a27-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="e8a27-110">Ta konfiguracja jest zazwyczaj przeprowadzana jednorazowo, jeśli w ogóle została ukończona.</span><span class="sxs-lookup"><span data-stu-id="e8a27-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="e8a27-111">Aby przeprowadzić tę konfigurację, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="e8a27-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-112">Wybierz kolejno opcje **Zarządzanie składnikami majątku \> Ustawienia \> Parametry zarządzania składnikami majątku**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="e8a27-113">Na karcie **Środki trwałe** w polu **Lokaliacja czynności konserwacyjnych** wybierz domyślną lokalizację dla towarów gotowych.</span><span class="sxs-lookup"><span data-stu-id="e8a27-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="e8a27-114">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="e8a27-115">Praca ze zintegrowanymi konserwowanymi składnikami majątku i środkami trwałymi</span><span class="sxs-lookup"><span data-stu-id="e8a27-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="e8a27-116">W tej sekcji znajduje się kolekcja procedur pokazujących różne sposoby pracy z funkcjami zintegrowanego zarządzania składnikami majątku i środkami trwałymi.</span><span class="sxs-lookup"><span data-stu-id="e8a27-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="e8a27-117">Kojarzenie istniejącego konserwowanego składnika majątku z środkiem trwałym</span><span class="sxs-lookup"><span data-stu-id="e8a27-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="e8a27-118">Aby skojarzyć istniejący konserwowany składnik majątku z środkiem trwałym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-119">Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).</span><span class="sxs-lookup"><span data-stu-id="e8a27-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="e8a27-120">Wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-120">Select an asset.</span></span>
1. <span data-ttu-id="e8a27-121">Na skróconej karcie **Środka trwałego** w polu **Numer środka trwałego** wybierz istniejący środek trwały.</span><span class="sxs-lookup"><span data-stu-id="e8a27-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="e8a27-122">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="e8a27-123">Umożliwia wyświetlenie środka trwałego skojarzonego z wybranym konserwowanm składnikiem majątku</span><span class="sxs-lookup"><span data-stu-id="e8a27-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="e8a27-124">Aby wyświetlić środek trwały skojarzonego z wybranym konserwowanm składnikiem majątku, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-125">Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).</span><span class="sxs-lookup"><span data-stu-id="e8a27-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="e8a27-126">Wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-126">Select an asset.</span></span>
1. <span data-ttu-id="e8a27-127">Na skróconej karcie **Środka trwałego** w polu **Numer środka trwałego** wybierz łącze..</span><span class="sxs-lookup"><span data-stu-id="e8a27-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="e8a27-128">Zostanie otwarta strona **Środki trwałe** dla wybranego środka trwałego.</span><span class="sxs-lookup"><span data-stu-id="e8a27-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="e8a27-129">(Zazwyczaj tę stronę można znaleźć pod **Środki trwałe \> Środki trwałe \> Środki trwałe**.)</span><span class="sxs-lookup"><span data-stu-id="e8a27-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="e8a27-130">Umożliwia wyświetlenie konserwowanego składnika majątku skojarzonego z wybranym środkiem trwałym</span><span class="sxs-lookup"><span data-stu-id="e8a27-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="e8a27-131">Aby wyświetlić konserwowany składnik majątku skojarzony z wybranym środkiem trwałym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-132">Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="e8a27-133">Wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-133">Select an asset.</span></span>
1. <span data-ttu-id="e8a27-134">W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Wyświetl** wybierz **Konserwowany składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="e8a27-135">Strona **Konserwowany składnik majątku** dla składnika majątku powiązana z wybranym środkiem trwałym jest otwarta.</span><span class="sxs-lookup"><span data-stu-id="e8a27-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="e8a27-136">(Zazwyczaj ta strona znajduje się w **Zarządzanie składnikami majątku \> Składniki majątku \> Wszystkie składniki majątku**.)</span><span class="sxs-lookup"><span data-stu-id="e8a27-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="e8a27-137">Wyświetlanie kosztów konserwacji skojarzonych ze środkiem trwałym</span><span class="sxs-lookup"><span data-stu-id="e8a27-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="e8a27-138">Zarządzanie środkami trwałymi może być księgowane na potrzeby środków konserwacyjnych, a każde z tych zleceń jest zazwyczaj kosztami.</span><span class="sxs-lookup"><span data-stu-id="e8a27-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="e8a27-139">Gdy środek trwały jest skojarzony z zasobem obsługi, można przejść bezpośrednio ze środka trwałego w celu wyświetlenia odpowiednich kosztów.</span><span class="sxs-lookup"><span data-stu-id="e8a27-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="e8a27-140">Aby wyświetlić koszt konserwacji majątku skojarzony ze środkiem trwałym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-141">Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="e8a27-142">Wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-142">Select an asset.</span></span>
1. <span data-ttu-id="e8a27-143">W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Wyświetl** wybierz **Koszt konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="e8a27-144">Zostanie otwarta strona **Koszt konserwacji** i zostaną wyświetlone powiązane z tym koszty.</span><span class="sxs-lookup"><span data-stu-id="e8a27-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="e8a27-145">Tworzenie nowego konserwowanego składnika majątku dla istniejącego środka trwałego</span><span class="sxs-lookup"><span data-stu-id="e8a27-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="e8a27-146">Aby utworzyć nowy konserwowany składnik majątku dla istniejącego środka trwałego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-147">Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="e8a27-148">Wybierz składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="e8a27-148">Select an asset.</span></span>
1. <span data-ttu-id="e8a27-149">W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Nowe** wybierz **Stwórz konserwowany składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="e8a27-150">(Jeśli ta opcja jest niedostępna, konserwowany składnik majątku może być już skojarzony z wybranym środkiem trwałym.)</span><span class="sxs-lookup"><span data-stu-id="e8a27-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="e8a27-151">Zakończ tworzenie składnika majątku w sposób opisany w temacie [Tworzenie składnika majątku](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="e8a27-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="e8a27-152">Tworzenie nowego środka trwałego i dodawanie nowego konserwowanego składnika majątku</span><span class="sxs-lookup"><span data-stu-id="e8a27-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="e8a27-153">Aby utworzyć nowy środek trwały i dodać nowy konserwowany składnik majątku dla niego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-154">Wybierz kolejno opcje **Środki trwałe \> Środki trwałe \> Środki trwałe**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="e8a27-155">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e8a27-156">Zakończ tworzenie środka trwałego w sposób opisany w temacie [Tworzenie środka trwałego](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="e8a27-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="e8a27-157">W okienku akcji, na karcie **Zarządzanie składnikami majątku** w grupie **Nowe** wybierz **Stwórz konserwowany składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="e8a27-158">Zakończ tworzenie składnika majątku w sposób opisany w temacie [Tworzenie składnika majątku](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="e8a27-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="e8a27-159">Usuń powiązanie między dwoma środkami trwałymi</span><span class="sxs-lookup"><span data-stu-id="e8a27-159">Remove the association between two assets</span></span>

<span data-ttu-id="e8a27-160">W niektórych przypadkach może być konieczne usunięcie skojarzenia konserwowanego składnika majątku ze środkiem trwałym.</span><span class="sxs-lookup"><span data-stu-id="e8a27-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="e8a27-161">Jeśli na przykład chcesz [utworzyć nowy konserwowany składnik majątku](#new-maintenance-from-fixed) ze środka trwałego, musisz najpierw usunąć istniejące skojarzenie.</span><span class="sxs-lookup"><span data-stu-id="e8a27-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="e8a27-162">Aby usunąć istniejące powązanie między konserwowanym składnikiem majątku i środka trwałego, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e8a27-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="e8a27-163">Wybierz **Zarządzanie składnikami majątku  \> Składniki majątku \> Wszystkie składniki majątku** (lub Aktywne **składniki majątku**).</span><span class="sxs-lookup"><span data-stu-id="e8a27-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="e8a27-164">Znajdź i otwórz środek trwały.</span><span class="sxs-lookup"><span data-stu-id="e8a27-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="e8a27-165">Na skróconej karcie **Środka trwałego** wyczyść wartość w polu **Lokalizacja czynności konserwacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="e8a27-166">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8a27-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]