---
title: Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje dotyczące możliwości zamówień magazynowych, które są używane jako część obciążenia jednostek skalowania magazynów.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105724"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="c41fe-103">Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego</span><span class="sxs-lookup"><span data-stu-id="c41fe-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="c41fe-104">Nie wszystkie funkcje biznesowe są w pełni obsługiwane w wersji zapoznawczej, gdy są używane obciążenia jednostek skalowania.</span><span class="sxs-lookup"><span data-stu-id="c41fe-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="c41fe-105">Jeśli używasz jednostek skalowania, pamiętaj, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c41fe-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="c41fe-106">Co to są zamówienia magazynowe?</span><span class="sxs-lookup"><span data-stu-id="c41fe-106">What are warehouse orders?</span></span>

<span data-ttu-id="c41fe-107">*Zamówienia magazynowe* to rodzaj zamówienia utworzonego w celu obsługi wdrożeń magazynu centrum i jednostki skalowania.</span><span class="sxs-lookup"><span data-stu-id="c41fe-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="c41fe-108">Umożliwiają one odbieranie zapasów podczas uruchamiania obciążenia magazynu na jednostce skalowania.</span><span class="sxs-lookup"><span data-stu-id="c41fe-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="c41fe-109">Są one obecnie używane tylko z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="c41fe-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="c41fe-110">Zamówienia magazynowe są używane w ramach przetwarzania zarządzania magazynem, na przykład gdy aplikacja magazynu służy do rejestrowania fizycznych dostępnych zapasów podczas przetwarzania przychodzącego zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="c41fe-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="c41fe-111">Zamówienia magazynowe są tworzone w ramach procesu *Zwalnianie do magazynu* dostępnego dla zamówień zakupu, w których określono magazyn jednostek skalowania oraz towary, dla których można używać procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="c41fe-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c41fe-112">Zamówienia magazynowe są dostępne tylko we wdrożeniach, które korzystają z [obciążenia zarządzania magazynem dla jednostek skali chmury i urządzeń brzegowych](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="c41fe-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="c41fe-113">Tworzenie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="c41fe-113">Create a warehouse order</span></span>

<span data-ttu-id="c41fe-114">Aby utworzyć zamówienie magazynowe, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c41fe-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="c41fe-115">Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Supply Chain Management działającego w centrum.</span><span class="sxs-lookup"><span data-stu-id="c41fe-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="c41fe-116">(Należy zainicjować proces *zwalniania do magazynu* po zalogowaniu się do centrum).</span><span class="sxs-lookup"><span data-stu-id="c41fe-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="c41fe-117">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="c41fe-118">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="c41fe-119">Aby wyświetlić powiązane wiersze zamówienia magazynowego, otwórz odpowiednie zamówienie zakupu, wybierz wiersz w sekcji **Wiersze zamówienia zakupu**, a następnie na pasku narzędzi wybierz pozycję **Magazyn \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="c41fe-120">Aby wyświetlić wszystkie wiersze, przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="c41fe-121">Anulowanie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="c41fe-121">Cancel a warehouse order</span></span>

<span data-ttu-id="c41fe-122">W ramach procesu *zwalniania do magazynu* transakcje magazynowe zamówień zakupu są łączone z zamówieniami magazynowymi i nie są aktualizowane przez centrum.</span><span class="sxs-lookup"><span data-stu-id="c41fe-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="c41fe-123">Jeśli przeprowadzono zwalnianie do magazynu przez pomyłkę lub masz inny powód anulowania tworzenia wierszy zamówień magazynowych, można zażądać anulowania wierszy zamówień magazynowych.</span><span class="sxs-lookup"><span data-stu-id="c41fe-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="c41fe-124">Aby anulować wiersze zamówienia magazynowego, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c41fe-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="c41fe-125">Zaloguj się do wystąpienia rozwiązania Supply Chain Management działającego w centrum.</span><span class="sxs-lookup"><span data-stu-id="c41fe-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="c41fe-126">Przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="c41fe-127">Wybierz odpowiedni wiersz.</span><span class="sxs-lookup"><span data-stu-id="c41fe-127">Select the relevant line.</span></span>
1. <span data-ttu-id="c41fe-128">W okienku akcji wybierz pozycję **Anuluj wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="c41fe-129">Żądanie anulowania wierszy nie będzie realizowane w przypadku wierszy, które już oczekują na anulowanie lub które są aktywnie przetwarzane w magazynie, w których jest uruchomione obciążenie w jednostce skalowania.</span><span class="sxs-lookup"><span data-stu-id="c41fe-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="c41fe-130">Monitorowanie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="c41fe-130">Monitor a warehouse order</span></span>

<span data-ttu-id="c41fe-131">W widoku **wierszy zamówienia magazynowego** można monitorować postęp przyjmowania towarów przychodzącego, przeglądając wartości w kolumnie **Ilość pozostała do odebrania**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="c41fe-132">Aby wyświetlić szczegóły dotyczące pracy wykonanej za pomocą aplikacji magazynu, wykonaj jedną z poniższych czynności.</span><span class="sxs-lookup"><span data-stu-id="c41fe-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="c41fe-133">Przejdź do obszaru **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówień magazynowych** i użyj filtru, aby znaleźć szukane wiersze.</span><span class="sxs-lookup"><span data-stu-id="c41fe-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="c41fe-134">Przejdź do pozycji **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu** i otwórz odpowiednie zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="c41fe-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="c41fe-135">W sekcji **Wiersze zamówienia zakupu** zaznacz jeden lub więcej wierszy, a następnie na pasku narzędzi wybierz pozycje **Magazyn \> Wpisy przyjęcia do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="c41fe-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
