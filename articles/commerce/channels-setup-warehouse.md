---
title: Ustawianie magazynu
description: W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6da72ae612f0520965a2b11a21123d4642303ac3
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113766"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="de4b4-103">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="de4b4-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="de4b4-104">W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="de4b4-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="de4b4-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="de4b4-105">Overview</span></span>

<span data-ttu-id="de4b4-106">Każdy kanał Commerce wymaga, aby skonfigurowany magazyn był skojarzony z nim.</span><span class="sxs-lookup"><span data-stu-id="de4b4-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="de4b4-107">Poniższe procedury zapewniają minimalną konfigurację wymaganą do skonfigurowania magazynu dla kanału Commerce.</span><span class="sxs-lookup"><span data-stu-id="de4b4-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="de4b4-108">Aby uzyskać więcej informacji dotyczących konfiguracji magazynu, zobacz [Omówienie zarządzania magazynem](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="de4b4-108">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="de4b4-109">Konfiguracja oddział magazynu</span><span class="sxs-lookup"><span data-stu-id="de4b4-109">Configure a warehouse site</span></span>

<span data-ttu-id="de4b4-110">Przed skonfigurowaniem magazynu należy skonfigurować oddział magazynu.</span><span class="sxs-lookup"><span data-stu-id="de4b4-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="de4b4-111">Aby skonfigurować oddział magazynu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="de4b4-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="de4b4-112">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Oddziały**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="de4b4-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="de4b4-114">Wprowadź wartość w polu **Oddział**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="de4b4-115">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="de4b4-116">W sekcji **Ogólne** określ odpowiednią **Strefę czasową**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="de4b4-117">W polu **Adresy** wprowadź adres.</span><span class="sxs-lookup"><span data-stu-id="de4b4-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="de4b4-118">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="de4b4-119">Poniższy obraz przedstawia przykład oddział magazynu.</span><span class="sxs-lookup"><span data-stu-id="de4b4-119">The following image shows an example warehouse site.</span></span>

![Przykład oddziału magazynu](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="de4b4-121">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="de4b4-121">Set up a warehouse</span></span>

<span data-ttu-id="de4b4-122">Aby skonfigurować magazyn, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="de4b4-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="de4b4-123">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="de4b4-124">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="de4b4-125">Wprowadź lub wybierz wartość w polu **Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="de4b4-126">Jeśli jest to mapowanie 1:1 do sklepu, należy rozważyć użycie nazwy sklepu lub nazwy regionalnego centrum dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="de4b4-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="de4b4-127">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="de4b4-128">Z listy rozwijanej **oddziału** Wybierz utworzoną wcześniej witrynę magazynową.</span><span class="sxs-lookup"><span data-stu-id="de4b4-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="de4b4-129">W polu **Typ** zaznacz opcję **Domyślny**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="de4b4-130">Aby utworzyć **Magazyn kwarantanny**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Kwarantanna**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="de4b4-131">Aby utworzyć **Magazyn tranzytowy**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Tranzyt**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="de4b4-132">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="de4b4-133">Ustawianie korytarzy w magazynie</span><span class="sxs-lookup"><span data-stu-id="de4b4-133">Set up inventory aisles</span></span>

<span data-ttu-id="de4b4-134">Aby skonfigurować korytarzy magazynowych, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="de4b4-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="de4b4-135">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Ustawienia lokalizacji \> Korytarze w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="de4b4-136">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="de4b4-137">Z listy rozwijanej **Magazyn** Wybierz utworzoną wcześniej witrynę magazynową.</span><span class="sxs-lookup"><span data-stu-id="de4b4-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="de4b4-138">W polu **Korytarz** wprowadź nazwę (na przykład „Def”).</span><span class="sxs-lookup"><span data-stu-id="de4b4-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="de4b4-139">W polu **Nazwa** wprowadź nazwę (na przykład „Domyślny korytarz”).</span><span class="sxs-lookup"><span data-stu-id="de4b4-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="de4b4-140">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="de4b4-141">Ustaw lokalizacje zapasów</span><span class="sxs-lookup"><span data-stu-id="de4b4-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="de4b4-142">Aby skonfigurować lokalizacje magazynów magazynowych dla standardowych, uszkodzonych i zwróconych zapasów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="de4b4-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="de4b4-143">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="de4b4-144">Zaznacz utworzony wcześniej magazyn.</span><span class="sxs-lookup"><span data-stu-id="de4b4-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="de4b4-145">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="de4b4-146">W okienku akcji wybierz opcję **Magazyn**, a następnie wybierz opcję **Lokalizacja zapasów**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="de4b4-147">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-147">On the action pane, select **New**.</span></span> <span data-ttu-id="de4b4-148">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="de4b4-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="de4b4-149">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="de4b4-150">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="de4b4-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="de4b4-151">W polu **Lokalizacja** wprowadź nazwę magazynu.</span><span class="sxs-lookup"><span data-stu-id="de4b4-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="de4b4-152">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="de4b4-153">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="de4b4-154">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="de4b4-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="de4b4-155">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="de4b4-156">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="de4b4-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="de4b4-157">W polu **Lokalizacja** wprowadź „uszkodzony”.</span><span class="sxs-lookup"><span data-stu-id="de4b4-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="de4b4-158">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="de4b4-159">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="de4b4-160">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="de4b4-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="de4b4-161">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="de4b4-162">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="de4b4-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="de4b4-163">W polu **Lokalizacja** wprowadź „Zwrócony”.</span><span class="sxs-lookup"><span data-stu-id="de4b4-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="de4b4-164">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="de4b4-165">Na poniższym rysunku przedstawiono konfigurację lokalizacji magazynu w San Francisco.</span><span class="sxs-lookup"><span data-stu-id="de4b4-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Przykładowe ustawienia lokalizacji zapasów](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="de4b4-167">Zakończ konfigurację magazynu</span><span class="sxs-lookup"><span data-stu-id="de4b4-167">Complete warehouse setup</span></span>

<span data-ttu-id="de4b4-168">Aby zakończyć tę konfigurację magazynu, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="de4b4-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="de4b4-169">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="de4b4-170">Zaznacz utworzony wcześniej magazyn.</span><span class="sxs-lookup"><span data-stu-id="de4b4-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="de4b4-171">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="de4b4-172">W **Zarządzanie zapasami i magazynem**:</span><span class="sxs-lookup"><span data-stu-id="de4b4-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="de4b4-173">Ustaw **Domyślna lokalizacja przychodu** jako lokalizację domyślną utworzoną powyżej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="de4b4-174">Wybierz **Domyślna lokalizacja rozchodu** jako lokalizację domyślną utworzoną powyżej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="de4b4-175">W sekcji **Adresy** wprowadź adres magazynu.</span><span class="sxs-lookup"><span data-stu-id="de4b4-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="de4b4-176">W sekcji **Retail**:</span><span class="sxs-lookup"><span data-stu-id="de4b4-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="de4b4-177">W polu **Domyślna lokalizacja zwrotu** wprowadź pozostałą lokalizację zwrotu utworzoną wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="de4b4-178">Określ wartość **Sklep** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="de4b4-179">W polu **Waga** ustaw wartość **1.00**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="de4b4-180">W polu **Wymiary magazynowania** wprowadź dkomyślną lokalizację utworzoną wcześniej.</span><span class="sxs-lookup"><span data-stu-id="de4b4-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="de4b4-181">W sekcji **Magazyn** ustaw **Ujemne wartości magazynu fizycznego** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="de4b4-182">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="de4b4-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="de4b4-183">Poniższy obraz przedstawia szczegóły dotyczące skonfigurowanego magazynu.</span><span class="sxs-lookup"><span data-stu-id="de4b4-183">The following image shows details for a configured warehouse.</span></span>

![Przykładowy magazyn skonfigurowany](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="de4b4-185">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="de4b4-185">Additional resources</span></span>

[<span data-ttu-id="de4b4-186">Omówienie zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="de4b4-186">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="de4b4-187">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="de4b4-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="de4b4-188">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="de4b4-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="de4b4-189">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="de4b4-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="de4b4-190">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="de4b4-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="de4b4-191">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="de4b4-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





