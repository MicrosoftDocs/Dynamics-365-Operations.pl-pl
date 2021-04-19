---
title: Ustawianie magazynu
description: W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800502"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="4b0d9-103">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="4b0d9-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b0d9-104">W tym temacie opisano sposób konfigurowania magazynu, który ma być używany z nowym kanałem w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4b0d9-105">Każdy kanał Commerce wymaga, aby skonfigurowany magazyn był skojarzony z nim.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="4b0d9-106">Poniższe procedury zapewniają minimalną konfigurację wymaganą do skonfigurowania magazynu dla kanału Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="4b0d9-107">Aby uzyskać więcej informacji dotyczących konfiguracji magazynu, zobacz [Omówienie zarządzania magazynem](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="4b0d9-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="4b0d9-108">Konfiguracja oddział magazynu</span><span class="sxs-lookup"><span data-stu-id="4b0d9-108">Configure a warehouse site</span></span>

<span data-ttu-id="4b0d9-109">Przed skonfigurowaniem magazynu należy skonfigurować oddział magazynu.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="4b0d9-110">Aby skonfigurować oddział magazynu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="4b0d9-111">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Oddziały**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="4b0d9-112">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4b0d9-113">Wprowadź wartość w polu **Oddział**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="4b0d9-114">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="4b0d9-115">W sekcji **Ogólne** określ odpowiednią **Strefę czasową**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="4b0d9-116">W polu **Adresy** wprowadź adres.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="4b0d9-117">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="4b0d9-118">Poniższy obraz przedstawia przykład oddział magazynu.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-118">The following image shows an example warehouse site.</span></span>

![Przykład oddziału magazynu](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="4b0d9-120">Ustawianie magazynu</span><span class="sxs-lookup"><span data-stu-id="4b0d9-120">Set up a warehouse</span></span>

<span data-ttu-id="4b0d9-121">Aby skonfigurować magazyn, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-121">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="4b0d9-122">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-122">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="4b0d9-123">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-123">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4b0d9-124">Wprowadź lub wybierz wartość w polu **Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-124">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="4b0d9-125">Jeśli jest to mapowanie 1:1 do sklepu, należy rozważyć użycie nazwy sklepu lub nazwy regionalnego centrum dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-125">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="4b0d9-126">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-126">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="4b0d9-127">Z listy rozwijanej **oddziału** Wybierz utworzoną wcześniej witrynę magazynową.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-127">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="4b0d9-128">W polu **Typ** zaznacz opcję **Domyślny**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-128">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="4b0d9-129">Aby utworzyć **Magazyn kwarantanny**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Kwarantanna**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-129">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="4b0d9-130">Aby utworzyć **Magazyn tranzytowy**, najpierw trzeba wykonać poniższe kroki w celu utworzenia dodatkowego magazynu, w którym ustawiono **Typ** jako **Tranzyt**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-130">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="4b0d9-131">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-131">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="4b0d9-132">Ustawianie korytarzy w magazynie</span><span class="sxs-lookup"><span data-stu-id="4b0d9-132">Set up inventory aisles</span></span>

<span data-ttu-id="4b0d9-133">Aby skonfigurować korytarzy magazynowych, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-133">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="4b0d9-134">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Ustawienia lokalizacji \> Korytarze w magazynie**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-134">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="4b0d9-135">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-135">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="4b0d9-136">Z listy rozwijanej **Magazyn** Wybierz utworzoną wcześniej witrynę magazynową.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-136">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="4b0d9-137">W polu **Korytarz** wprowadź nazwę (na przykład „Def”).</span><span class="sxs-lookup"><span data-stu-id="4b0d9-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="4b0d9-138">W polu **Nazwa** wprowadź nazwę (na przykład „Domyślny korytarz”).</span><span class="sxs-lookup"><span data-stu-id="4b0d9-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="4b0d9-139">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="4b0d9-140">Ustaw lokalizacje zapasów</span><span class="sxs-lookup"><span data-stu-id="4b0d9-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="4b0d9-141">Aby skonfigurować lokalizacje magazynów magazynowych dla standardowych, uszkodzonych i zwróconych zapasów, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="4b0d9-142">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="4b0d9-143">Zaznacz utworzony wcześniej magazyn.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="4b0d9-144">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="4b0d9-145">W okienku akcji wybierz opcję **Magazyn**, a następnie wybierz opcję **Lokalizacja zapasów**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="4b0d9-146">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-146">On the action pane, select **New**.</span></span> <span data-ttu-id="4b0d9-147">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="4b0d9-148">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="4b0d9-149">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="4b0d9-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="4b0d9-150">W polu **Lokalizacja** wprowadź nazwę magazynu.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="4b0d9-151">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="4b0d9-152">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="4b0d9-153">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="4b0d9-154">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="4b0d9-155">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="4b0d9-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="4b0d9-156">W polu **Lokalizacja** wprowadź „uszkodzony”.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="4b0d9-157">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="4b0d9-158">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="4b0d9-159">Lista rozwijana **Magazyn** powinna domyślnie mieć wartość nowy magazyn.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="4b0d9-160">W polu **Korytarz** wprowadź nazwę korytarza, który został określony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="4b0d9-161">Ustawienie opcji **Ręczna aktualizacja** na wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="4b0d9-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="4b0d9-162">W polu **Lokalizacja** wprowadź „Zwrócony”.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="4b0d9-163">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="4b0d9-164">Na poniższym rysunku przedstawiono konfigurację lokalizacji magazynu w San Francisco.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Przykładowe ustawienia lokalizacji zapasów](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="4b0d9-166">Zakończ konfigurację magazynu</span><span class="sxs-lookup"><span data-stu-id="4b0d9-166">Complete warehouse setup</span></span>

<span data-ttu-id="4b0d9-167">Aby zakończyć tę konfigurację magazynu, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="4b0d9-168">W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="4b0d9-169">Zaznacz utworzony wcześniej magazyn.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="4b0d9-170">Na okienku akcji wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="4b0d9-171">W **Zarządzanie zapasami i magazynem**:</span><span class="sxs-lookup"><span data-stu-id="4b0d9-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="4b0d9-172">Ustaw **Domyślna lokalizacja przychodu** jako lokalizację domyślną utworzoną powyżej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="4b0d9-173">Wybierz **Domyślna lokalizacja rozchodu** jako lokalizację domyślną utworzoną powyżej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="4b0d9-174">W sekcji **Adresy** wprowadź adres magazynu.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="4b0d9-175">W sekcji **Retail**:</span><span class="sxs-lookup"><span data-stu-id="4b0d9-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="4b0d9-176">W polu **Domyślna lokalizacja zwrotu** wprowadź pozostałą lokalizację zwrotu utworzoną wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="4b0d9-177">Określ wartość **Sklep** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="4b0d9-178">W polu **Waga** ustaw wartość **1.00**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="4b0d9-179">W polu **Wymiary magazynowania** wprowadź dkomyślną lokalizację utworzoną wcześniej.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="4b0d9-180">W sekcji **Magazyn** ustaw **Ujemne wartości magazynu fizycznego** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="4b0d9-181">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="4b0d9-182">Poniższy obraz przedstawia szczegóły dotyczące skonfigurowanego magazynu.</span><span class="sxs-lookup"><span data-stu-id="4b0d9-182">The following image shows details for a configured warehouse.</span></span>

![Przykładowy magazyn skonfigurowany](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="4b0d9-184">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4b0d9-184">Additional resources</span></span>

[<span data-ttu-id="4b0d9-185">Omówienie zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="4b0d9-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="4b0d9-186">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="4b0d9-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="4b0d9-187">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="4b0d9-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="4b0d9-188">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4b0d9-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="4b0d9-189">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="4b0d9-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="4b0d9-190">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="4b0d9-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
