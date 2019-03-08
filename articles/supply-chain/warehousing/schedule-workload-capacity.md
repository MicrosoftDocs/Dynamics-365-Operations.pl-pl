---
title: Planowanie możliwości obciążenia pracą
description: W tym temacie omówiono konfigurowanie i planowanie możliwości obciążenia pracą dla pracowników w magazynie lub dla całego magazynu.
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b1334dcba7d12f2da301f70e21a08fceb88e2b4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "317299"
---
# <a name="schedule-workload-capacity"></a><span data-ttu-id="b79b6-103">Planowanie możliwości obciążenia pracą</span><span class="sxs-lookup"><span data-stu-id="b79b6-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b79b6-104">Można zaplanować wielkość obciążenia pracą dla magazynów, a także prognozować bieżące i przyszłe obciążenia pracą dla pracowników w poszczególnych magazynach.</span><span class="sxs-lookup"><span data-stu-id="b79b6-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="b79b6-105">Istnieje możliwość zaprojektowania obciążenia pracą dla całego magazynu lub oddzielnie dla przychodzących i wychodzących obciążeń pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="b79b6-106">Aby sporządzić prognozę wyjściowego obciążenia pracą dla wybranych magazynów, muszą być dla nich dostępne dane planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="b79b6-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="b79b6-107">Aby uzyskać więcej informacji, zobacz [Plany główne](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b79b6-107">For more information, see [Master plans](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="b79b6-108">Planowanie i wyświetlanie obciążenia pracą dla magazynu</span><span class="sxs-lookup"><span data-stu-id="b79b6-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="b79b6-109">Aby zaplanować wielkości obciążenia pracą dla magazynu, utwórz ustawień obciążenia pracą dla jednego lub większej liczby magazynów, a następnie skojarzy ustawienia obciążenia pracą z planem głównym.</span><span class="sxs-lookup"><span data-stu-id="b79b6-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="b79b6-110">W konfiguracji obciążenia pracą można określić limity masy lub objętość dla transakcji przychodzących i wychodzących.</span><span class="sxs-lookup"><span data-stu-id="b79b6-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="b79b6-111">Można również utworzyć więcej niż jedną konfigurację dla każdego magazynu, a następnie skojarzyć konfigurację z indywidualnymi planami głównymi.</span><span class="sxs-lookup"><span data-stu-id="b79b6-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="b79b6-112">Na przykład można użyć tej metody, aby uwzględnić sezonowe zmiany obsady kadrowej.</span><span class="sxs-lookup"><span data-stu-id="b79b6-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="b79b6-113">Jeśli pracownicy magazynu pracują z transakcjami zarówno dla obciążeń przychodzących, jak i wychodzących, można utworzyć konfigurację możliwości obciążenia magazynu, tak aby obciążenie pracą było prognozowane w scalonym widoku.</span><span class="sxs-lookup"><span data-stu-id="b79b6-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="b79b6-114">Aby zaplanować i wyświetlić obciążenie pracą dla magazynów, wykonaj następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="b79b6-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="b79b6-115">Utwórz wielkość obciążenia pracą i zdefiniuj limity obciążeń pracą dla jednego lub większej liczby magazynów.</span><span class="sxs-lookup"><span data-stu-id="b79b6-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="b79b6-116">Skojarz ustawienia obciążenia pracą z planem głównym, aby utworzyć prognozy obciążenia pracą i określić, jak długo te prognozy mają obowiązywać.</span><span class="sxs-lookup"><span data-stu-id="b79b6-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="b79b6-117">Tworzenie ustawienia wielkości obciążenia pracą dla magazynu</span><span class="sxs-lookup"><span data-stu-id="b79b6-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="b79b6-118">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Monitorowanie magazynu** \> **Możliwości obciążenia pracą**.</span><span class="sxs-lookup"><span data-stu-id="b79b6-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="b79b6-119">W okienku akcji naciśnij przycisk **Nowy**, aby utworzyć konfigurację możliwości obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="b79b6-120">Na skróconej karcie **Magazyny** kliknij przycisk **Nowy**, a następnie wprowadź wartości w wierszu, aby skojarzyć magazyn z konfiguracją możliwości obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="b79b6-121">Zaznacz pole wyboru **Połączone przychodzące i wychodzące obciążenie pracą**, jeśli raport **Możliwości obciążenia pracą** powinien wykazywać łączne obciążenie pracą dla transakcji przychodzących i wychodzących w jednym widoku.</span><span class="sxs-lookup"><span data-stu-id="b79b6-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="b79b6-122">Na skróconej karcie **Typy transakcji** wybierz typy transakcji przychodzących i wychodzących, do których będą stosowane limity obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b79b6-123">Należy zaznaczyć co najmniej po jednym typie transakcji dla przychodzących i wychodzących obciążeń pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="b79b6-124">Definiowanie ograniczeń objętości lub masy</span><span class="sxs-lookup"><span data-stu-id="b79b6-124">Define limits for volume or weight</span></span>

<span data-ttu-id="b79b6-125">Można skonfigurować limity objętości lub masy, w zależności od tego, które ograniczenia są użyteczne dla pracowników magazynu.</span><span class="sxs-lookup"><span data-stu-id="b79b6-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="b79b6-126">Ograniczenia określone przez użytkownika są uwzględniane w prognozie obciążenia pracą, którą można obejrzeć w raporcie **Możliwości obciążenia pracą**.</span><span class="sxs-lookup"><span data-stu-id="b79b6-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="b79b6-127">Aby można było prognozować objętość i masę towarów, dla wszystkich produktów muszą być określone standardowe objętość i masa pozycji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="b79b6-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="b79b6-128">Pola wymagane są dostępne w następujących grupach pól na skróconej karcie **Zarządzanie zapasami** na stronie **Szczegóły zwolnionego produktu**:</span><span class="sxs-lookup"><span data-stu-id="b79b6-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="b79b6-129">Obsługa</span><span class="sxs-lookup"><span data-stu-id="b79b6-129">Handling</span></span>
- <span data-ttu-id="b79b6-130">Wymiary fizyczne</span><span class="sxs-lookup"><span data-stu-id="b79b6-130">Physical dimensions</span></span>
- <span data-ttu-id="b79b6-131">Miary ciężaru</span><span class="sxs-lookup"><span data-stu-id="b79b6-131">Weight measurements</span></span>

<span data-ttu-id="b79b6-132">Jeśli te informacje nie zostały określone poprawnie, zostanie wyświetlony komunikat o błędzie podczas generowania raportu **Możliwości obciążenia pracą**.</span><span class="sxs-lookup"><span data-stu-id="b79b6-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="b79b6-133">Z raportu można przejść do szczegółów, aby zidentyfikować brakujące informacje niezbędne do prognozowania przyszłego obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="b79b6-134">Skojarzenie ustawień obciążenia pracą z planem głównym</span><span class="sxs-lookup"><span data-stu-id="b79b6-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="b79b6-135">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Okresowe** \> **Planowanie obciążenia pracą**.</span><span class="sxs-lookup"><span data-stu-id="b79b6-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="b79b6-136">W polu **Plan główny** wybierz plan główny dla prognoz obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="b79b6-137">W polu **Liczba dni** określ liczbę dni, jaką obejmie prognoza obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="b79b6-138">W polu **Obciążenie pracą** wybierz konfigurację obciążenia pracą, która ma zostać skojarzona z planem głównym.</span><span class="sxs-lookup"><span data-stu-id="b79b6-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="b79b6-139">Wyświetlanie wielkości obciążenia pracą</span><span class="sxs-lookup"><span data-stu-id="b79b6-139">View workload capacity</span></span>

1. <span data-ttu-id="b79b6-140">Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Raporty zapasów fizycznych** \> **Możliwości obciążenia pracą**.</span><span class="sxs-lookup"><span data-stu-id="b79b6-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="b79b6-141">W polu **Liczba kolumn** określ liczbę kolumn, jaka ma być wyświetlana w raporcie.</span><span class="sxs-lookup"><span data-stu-id="b79b6-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="b79b6-142">W polu **Typ zamówienia** zaznacz opcję **Planowane i potwierdzone**, **Planowane** lub **Potwierdzone**, aby wskazać typ zamówień, których mają dotyczyć prognozy w raporcie.</span><span class="sxs-lookup"><span data-stu-id="b79b6-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="b79b6-143">W polu **Typ obciążenia pracą** wybierz typ obciążenia i w ten sposób wskazać, czy prognoza możliwości obciążenia ma dotyczyć objętości, czy masy.</span><span class="sxs-lookup"><span data-stu-id="b79b6-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="b79b6-144">W polu **Możliwości obciążenia pracą** wybierz konfigurację możliwości obciążenia pracą.</span><span class="sxs-lookup"><span data-stu-id="b79b6-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>
