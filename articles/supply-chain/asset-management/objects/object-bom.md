---
title: Obiekty BOM składnika majątku
description: W tym temacie opisano BOM składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02686c97a19fa86c3ea93d7c400067f0855b5c4d
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571491"
---
# <a name="asset-boms"></a><span data-ttu-id="8d3de-103">Obiekty BOM składnika majątku</span><span class="sxs-lookup"><span data-stu-id="8d3de-103">Asset BOMs</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8d3de-104">W tym temacie opisano BOM składników majątku w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-104">This topic describes asset bills of materials (BOMs) in Asset Management.</span></span> <span data-ttu-id="8d3de-105">Strona **BOM składnika majątku** zawiera listę wszystkich elementów (części zamiennych i innych pozycji) używanych w składniku majątku w całym jego cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="8d3de-105">The **Asset BOM** page shows a list of all items (spare parts and other items) that are used on an asset during its whole lifetime.</span></span> <span data-ttu-id="8d3de-106">Podczas tworzenia nowego składnika majątku należy rozważyć skonfigurowanie BOM składnika majątku w ramach procedury instalacji.</span><span class="sxs-lookup"><span data-stu-id="8d3de-106">When you create a new asset, you should consider setting up an asset BOM as a part of the setup procedure.</span></span> <span data-ttu-id="8d3de-107">W ten sposób można śledzić historię elementów dla składnika majątku od daty utworzenia.</span><span class="sxs-lookup"><span data-stu-id="8d3de-107">In this way, you can track item history for the asset from the creation date.</span></span>

<span data-ttu-id="8d3de-108">Po zakończeniu zadania konserwacji i zarejestrowaniu zużycia pozycji w zleceniu pracy, można śledzić zużycie części zamiennych i innych elementów, które są używane w składniku majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-108">After you've completed a maintenance job, and item consumption has been registered on a work order, you can track consumption of spare parts and other items that are used on the asset.</span></span> <span data-ttu-id="8d3de-109">Ta funkcja pozwala zachować pełny rekord konsumpcji wszystkich składników majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-109">This functionality lets you keep a complete item consumption record for all your assets.</span></span> <span data-ttu-id="8d3de-110">Można na przykład użyć rekordu do monitorowania, czy dana część zamienna jest często zastępowana, czy też do śledzenia części zamiennych lub innych elementów, które są aktualnie używane na danym składnikiem majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-110">For example, you can use the record to monitor whether a specific spare part is often replaced, or to keep track of the spare parts or other items that are currently used on an asset.</span></span>

> [!NOTE]
> <span data-ttu-id="8d3de-111">W przypadku zlecenia roboczego zużycie pozycji może obejmować zarówno części zamienne, jak i inne, dodatkowe elementy, takie jak smary, sworznie i uszczelki.</span><span class="sxs-lookup"><span data-stu-id="8d3de-111">On a work order, item consumption might include both spare parts and other, additional items, such as lubricants, bolts, and gaskets.</span></span>

<span data-ttu-id="8d3de-112">BOM składnika majątku może być automatycznie aktualizowany na podstawie ustawień w module Zarządzanie składnikami majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-112">An asset BOM can be automatically updated based on the setup in Asset Management.</span></span> <span data-ttu-id="8d3de-113">Jeśli stan cyklu życia zlecenia pracy został utworzony w celu obsługi gotowych lub zakończonych zleceń pracy, a opcja **Aktualizuj BOM składnika majątku** dla tego stanu cyklu życia zlecenia pracy jest ustawiona na **Tak** na stronie **Stany cyklu życia zlecenia pracy**, wszystkie elementy, które są używane w zleceniu pracy zostaną automatycznie zaktualizowane na stronie **BOM składnika majątku** po zaktualizowaniu zlecenia pracy do tego stanu cyklu życia.</span><span class="sxs-lookup"><span data-stu-id="8d3de-113">If a work order lifecycle state has been created to handle finished or completed work orders, and if the **Update asset BOM** option for that work order lifecycle state is set to **Yes** on the **Work order lifecycle states** page, all items that are used on the work order will be automatically updated on the **Asset BOM** page when the work order is updated to that lifecycle state.</span></span> 


<span data-ttu-id="8d3de-114">Można również ręcznie zaktualizować BOM składnika majątku, tworząc nowe wiersze pozycji na stronie **BOM składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-114">You can also manually update an asset BOM by creating new item lines on the **Asset BOM** page.</span></span>

<span data-ttu-id="8d3de-115">Na stronie **BOM składnika majątku** można śledzić historię części zamiennych dla składników majątku po zarejestrowaniu zużycia pozycji w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="8d3de-115">On the **Asset BOM** page, you can track spare parts history for assets after item consumption is registered on a work order.</span></span> <span data-ttu-id="8d3de-116">Aby korzystać z tej funkcji, należy wybrać grupy elementów, które mają być używane do rejestracji części zamiennych na stronie **Grupy pozycji części zamiennych**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-116">To use this functionality, you must select the item groups that should be used for spare parts registration on the **Spare parts item groups** page.</span></span>

<span data-ttu-id="8d3de-117">Aby korzystać z funkcji BOM składnika majątku, należy najpierw skonfigurować wymagane grupy pozycji części zamiennych.</span><span class="sxs-lookup"><span data-stu-id="8d3de-117">To use asset BOM functionality, you must first set up the required spare parts items groups.</span></span> <span data-ttu-id="8d3de-118">Następnie jeśli BOM składnika majątku ma być automatycznie aktualizowany po zakończeniu zlecenia pracy, można skonfigurować stan cyklu życia zlecenia pracy do obsługi tej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="8d3de-118">Then, if you want the asset BOM to be automatically updated when a work order is completed, you can set up a work order lifecycle state to handle that update.</span></span> 


## <a name="set-up-spare-parts-item-groups"></a><span data-ttu-id="8d3de-119">Konfigurowanie grup pozycji części zamiennych</span><span class="sxs-lookup"><span data-stu-id="8d3de-119">Set up spare parts item groups</span></span>

<span data-ttu-id="8d3de-120">Konfiguracja historii części zamiennych jest oparta na grupach pozycji utworzonych w module **Zarządzanie składnikami majątku i magazynem**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-120">The setup of spare parts history is based on item groups that are created in the **Inventory and warehouse management** module.</span></span> <span data-ttu-id="8d3de-121">W module Zarządzanie składnikami majątku można skonfigurować grupy pozycji, aby można było śledzić historię części zamiennych dla pozycji w wybranych grupach pozycji.</span><span class="sxs-lookup"><span data-stu-id="8d3de-121">In Asset Management, you set up item groups so that you can track spare parts history for the items in the selected item groups.</span></span>

1. <span data-ttu-id="8d3de-122">Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składnik majątku** \> **Grupy pozycji części zamiennych**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-122">Select **Asset management** \> **Setup** \> **Asset** \> **Spare parts item groups**.</span></span>
2. <span data-ttu-id="8d3de-123">Wybierz opcję **Nowa**, aby skonfigurować grupę pozycji.</span><span class="sxs-lookup"><span data-stu-id="8d3de-123">Select **New** to set up an item group.</span></span>
3. <span data-ttu-id="8d3de-124">W polu **Grupa pozycji** wybierz grupę.</span><span class="sxs-lookup"><span data-stu-id="8d3de-124">In the **Item group** field, select the group.</span></span> <span data-ttu-id="8d3de-125">Nazwa grupy jest automatycznie wprowadzana w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-125">The name of the group is automatically entered in the **Name** field.</span></span>

## <a name="view-and-update-asset-boms"></a><span data-ttu-id="8d3de-126">Wyświetlanie i aktualizowanie obiektów BOM składnika majątku</span><span class="sxs-lookup"><span data-stu-id="8d3de-126">View and update asset BOMs</span></span>

<span data-ttu-id="8d3de-127">Po zaksięgować zużycia pozycji w zleceniu pracy, można wyświetlić zużycie zarejestrowanej pozycji na stronie **BOM składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-127">After you post item consumption on a work order, you can view the registered item consumption on the **Asset BOM** page.</span></span>

1. <span data-ttu-id="8d3de-128">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Aktywne składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-128">Select **Asset management** \> **Common** \> **Assets** \> **Active assets**.</span></span> <span data-ttu-id="8d3de-129">Wybierz składnik majątku na liście, a następnie wybierz pozycję **BOM składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-129">Select the asset in the list, and then select **Asset BOM**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d3de-130">Aby wyświetlić wszystkie rejestracje zużycia składnika majątku dla wszystkich składników majątku, wybierz **Zarządzanie składnikami majątku** \> **Informacje** \> **Składniki majątku** \> **BOM składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-130">To view all item consumption registrations on all assets, select **Asset management** \> **Inquiries** \> **Assets** \> **Asset BOM**.</span></span>

2. <span data-ttu-id="8d3de-131">Wybierz pozycję **Aktualizuj BOM składnika majątku**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-131">Select **Update asset BOM**.</span></span> <span data-ttu-id="8d3de-132">Można dodawać składniki majątku, typy składników majątku oraz składniki majątku do aktualizacji zgodnie z wymaganiem, wybierając opcję **Zaznacz**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-132">You can add assets, asset types, and resources to the update as you require by selecting **Select**.</span></span> <span data-ttu-id="8d3de-133">Wybierz przycisk **OK**, aby rozpocząć aktualizację.</span><span class="sxs-lookup"><span data-stu-id="8d3de-133">Select **OK** to start the update.</span></span> <span data-ttu-id="8d3de-134">Można również skonfigurować funkcję aktualizacji jako zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="8d3de-134">You can also set up the Update function as a batch job.</span></span>
3. <span data-ttu-id="8d3de-135">Jeśli chcesz zobaczyć więcej informacji związanych z pozycjami, możesz dodać wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="8d3de-135">If you want to see more information that is related to the items, you can add inventory dimensions.</span></span> <span data-ttu-id="8d3de-136">Wybierz **Zapasy** \> **Wyświetlanie wymiarów**, a następnie zaznacz pola wyboru odpowiadające wymiarom, które chcesz zobaczyć.</span><span class="sxs-lookup"><span data-stu-id="8d3de-136">Select **Inventory** \> **Dimensions display**, and then select the check boxes for the dimensions that you want to see.</span></span> <span data-ttu-id="8d3de-137">Aby zachować tę konfigurację dla wszystkich składników majątku na stronie **BOM składnika majątku**, ustaw opcję **Zapisz konfigurację** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-137">To keep this setup for all assets on the **Asset BOM** page, set the **Save setup** option to **Yes**.</span></span>
4. <span data-ttu-id="8d3de-138">Aby uzyskać informacje o tym, gdzie w module Zarządzaniu składnikami majątku jest używany element w wybranym wierszu, w odniesieniu do składników majątku domyślnych typów zadań, części zamiennych i zleceń pracy, wybierz opcję **Używająca pozycja**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-138">To get an overview of where in Asset Management the item on the selected line is used, in relation to assets, job type defaults, spare parts, and work orders, select **Item where used**.</span></span> 
5. <span data-ttu-id="8d3de-139">Jeśli chcesz zobaczyć tylko aktywne linie towaru, wybierz kolejno **Wyświetl** \> **Bieżące**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-139">If you want to see only active item lines, select **View** \> **Current**.</span></span> <span data-ttu-id="8d3de-140">Aby zobaczyć wszystkie wiersze pozycji, w tym wiersze, w których data wygaśnięcia jest wcześniejsza niż data bieżąca, zaznacz **Wyświetl** \> **Wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-140">To see all item lines, including lines where the expiration date is earlier than the current date, select **View** \> **All**.</span></span>

> [!NOTE]
> <span data-ttu-id="8d3de-141">Po zakończeniu zlecenia pracy, jeśli niektóre pozycje lub części zamienne związane z powiązanym składnikiem majątku wygasły lub zostały zastąpione innymi pozycjami lub częściami zamiennymi, zaleca się odpowiednie zaktualizowanie BOM składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-141">When you've completed a work order, if some items or spare parts that are related to the related asset have expired or have been replaced by other items or spare parts, we recommend that you update the asset BOM accordingly.</span></span>

## <a name="create-a-new-item-line-in-an-asset-bom"></a><span data-ttu-id="8d3de-142">Tworzenie nowego wiersza w obiekcie BOM składnika majątku</span><span class="sxs-lookup"><span data-stu-id="8d3de-142">Create a new item line in an asset BOM</span></span>

<span data-ttu-id="8d3de-143">Można ręcznie tworzyć wiersze pozycji dla składników majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-143">You can manually create item lines for assets.</span></span>

1. <span data-ttu-id="8d3de-144">Na stronie **BOM składnika majątku** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-144">On the **Asset BOM** page, select **New**.</span></span>
2. <span data-ttu-id="8d3de-145">W polu **Składnik majątku** wybierz składnik majątku, dla którego ma zostać dodany wiersz pozycji.</span><span class="sxs-lookup"><span data-stu-id="8d3de-145">In the **Asset** field, select the asset to add an item line for.</span></span>
3. <span data-ttu-id="8d3de-146">W polu **Numer wiersza** wprowadź numer kolejnego wiersza.</span><span class="sxs-lookup"><span data-stu-id="8d3de-146">In the **Line number** field, enter a sequential line number.</span></span>
4. <span data-ttu-id="8d3de-147">W polu **Data wejścia w życie** wprowadź datę początkową dla składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="8d3de-147">In the **Effective** field, enter a start date for the item.</span></span>
5. <span data-ttu-id="8d3de-148">Jeśli element wygaśnie, w polu **Wygaśnięcie** wprowadź datę końcową.</span><span class="sxs-lookup"><span data-stu-id="8d3de-148">If the item will expire, in the **Expiration** field, enter an end date.</span></span>
6. <span data-ttu-id="8d3de-149">W polu **Numer pozycji** wybierz pozycję.</span><span class="sxs-lookup"><span data-stu-id="8d3de-149">In the **Item number** field, select the item.</span></span> <span data-ttu-id="8d3de-150">Nazwa jest automatycznie wprowadzana w polu **Nazwa produktu**.</span><span class="sxs-lookup"><span data-stu-id="8d3de-150">The name is automatically entered in the **Product name** field.</span></span>
7. <span data-ttu-id="8d3de-151">W polu **Ilość** wprowadź używaną ilość.</span><span class="sxs-lookup"><span data-stu-id="8d3de-151">In the **Quantity** field, enter the quantity that is used.</span></span> <span data-ttu-id="8d3de-152">Pole **Jednostka** jest aktualizowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="8d3de-152">The **Unit** field is automatically updated.</span></span>
