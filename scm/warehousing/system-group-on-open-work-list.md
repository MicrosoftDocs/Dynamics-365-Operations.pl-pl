---
title: "Grupowanie systemowe na liście otwartych prac"
description: "W tym temacie opisano sposób filtrowania listy otwartych prac na urządzeniu przenośnym."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="13597-103">Grupowanie systemowe na liście otwartych prac</span><span class="sxs-lookup"><span data-stu-id="13597-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="13597-104">Za pomocą pola grup systemowych można wyfiltrować listę otwartych prac bez konieczności edytowania elementu menu w urządzeniu komórkowym.</span><span class="sxs-lookup"><span data-stu-id="13597-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="13597-105">Funkcja grupowania systemowego filtruje listę prac według jednego pola nagłówka pracy.</span><span class="sxs-lookup"><span data-stu-id="13597-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="13597-106">Nie można używać grupowania systemowego do filtrowania według pól na poziomie wierszy.</span><span class="sxs-lookup"><span data-stu-id="13597-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="13597-107">Konfigurowanie grupowania systemowego listy otwartych prac</span><span class="sxs-lookup"><span data-stu-id="13597-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="13597-108">Wykonaj poniższe kroki, aby skonfigurować grupowanie systemowego listy otwartych prac.</span><span class="sxs-lookup"><span data-stu-id="13597-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="13597-109">Na urządzeniu komórkowym z menu wybierz opcje **Tryb: Pośrednie** i **Kod działania: Wyświetl listę otwartych prac**.</span><span class="sxs-lookup"><span data-stu-id="13597-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="13597-110">Zostaną udostępnione opcje wymienione poniżej.</span><span class="sxs-lookup"><span data-stu-id="13597-110">The following options become available.</span></span> <span data-ttu-id="13597-111">Te opcje są wymagane przy grupowaniu systemowym listy otwartych prac.</span><span class="sxs-lookup"><span data-stu-id="13597-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="13597-112">Opcja</span><span class="sxs-lookup"><span data-stu-id="13597-112">Option</span></span>        | <span data-ttu-id="13597-113">opis</span><span class="sxs-lookup"><span data-stu-id="13597-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="13597-114">Zezwalaj na grupowanie systemowe</span><span class="sxs-lookup"><span data-stu-id="13597-114">Allow system grouping</span></span>   | <span data-ttu-id="13597-115">Umożliwia grupowanie systemowe dla wybranej pozycji listy prac.</span><span class="sxs-lookup"><span data-stu-id="13597-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="13597-116">Pole grup systemowych</span><span class="sxs-lookup"><span data-stu-id="13597-116">System grouping field</span></span>   | <span data-ttu-id="13597-117">Opcja dostępna tylko wtedy, gdy w polu **Zezwalaj na pracę systemową** zaznaczono wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="13597-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="13597-118">Wybierz pole określające, jak praca pobrania będzie grupowana dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="13597-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="13597-119">Na przykład, jeśli wybierzesz pole **ShipmentId**, pracownik będzie skanować identyfikator wysyłki w celu pogrupowania pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="13597-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="13597-120">Wszystkie prace dla wysyłki są następnie przypisywane do pracownika.</span><span class="sxs-lookup"><span data-stu-id="13597-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="13597-121">To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system.</span><span class="sxs-lookup"><span data-stu-id="13597-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="13597-122">Za pomocą pola **Etykieta grup systemowych** można poinformować pracownika, co ma być skanowane.</span><span class="sxs-lookup"><span data-stu-id="13597-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="13597-123">Etykieta grup systemowych</span><span class="sxs-lookup"><span data-stu-id="13597-123">System grouping label</span></span>   | <span data-ttu-id="13597-124">Opcja dostępna tylko wtedy, gdy w polu **Zezwalaj na pracę systemową** zaznaczono wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="13597-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="13597-125">Wprowadź informacje dla pracownika o tym, co należy zeskanować podczas grupowania pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="13597-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="13597-126">Na przykład jeśli używasz pola **ShipmentId** do grupowania pracy pobrania według wysyłki, możesz w polu wpisać Identyfikator wysyłki.</span><span class="sxs-lookup"><span data-stu-id="13597-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="13597-127">To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system.</span><span class="sxs-lookup"><span data-stu-id="13597-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="13597-128">Musisz także wybrać pole, według którego będzie przeprowadzane grupowanie w polu **Grupowanie systemowe**.</span><span class="sxs-lookup"><span data-stu-id="13597-128">You must also select the field to group by in the **System grouping** field.</span></span>|

