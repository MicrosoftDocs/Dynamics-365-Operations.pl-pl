---
title: Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje dotyczące możliwości zamówień magazynowych, które są używane jako część obciążenia jednostek skalowania magazynów.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ff1f13198a7acc35897252f3ca8f6c2b1f56852e
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938283"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="e906c-103">Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego</span><span class="sxs-lookup"><span data-stu-id="e906c-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="e906c-104">Nie wszystkie funkcje biznesowe są w pełni obsługiwane w wersji zapoznawczej, gdy są używane obciążenia jednostek skalowania.</span><span class="sxs-lookup"><span data-stu-id="e906c-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="e906c-105">Jeśli używasz jednostek skalowania, pamiętaj, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="e906c-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="e906c-106">Co to są zamówienia magazynowe?</span><span class="sxs-lookup"><span data-stu-id="e906c-106">What are warehouse orders?</span></span>

<span data-ttu-id="e906c-107">*Zamówienia magazynowe* to rodzaj zamówienia utworzonego w celu obsługi wdrożeń magazynu centrum i jednostki skalowania.</span><span class="sxs-lookup"><span data-stu-id="e906c-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="e906c-108">Umożliwiają one odbieranie zapasów podczas uruchamiania obciążenia magazynu na jednostce skalowania.</span><span class="sxs-lookup"><span data-stu-id="e906c-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="e906c-109">Są one obecnie używane tylko z zamówieniami zakupu.</span><span class="sxs-lookup"><span data-stu-id="e906c-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="e906c-110">Zamówienia magazynowe są używane w ramach przetwarzania zarządzania magazynem, na przykład gdy aplikacja Warehouse Management służy do rejestrowania fizycznych dostępnych zapasów podczas przetwarzania przychodzącego zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="e906c-110">Warehouse orders are used as part of warehouse management processing, such as when the Warehouse Management mobile app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="e906c-111">Zamówienia magazynowe są tworzone w ramach procesu *Zwalnianie do magazynu* dostępnego dla zamówień zakupu, w których określono magazyn jednostek skalowania oraz towary, dla których można używać procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="e906c-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e906c-112">Zamówienia magazynowe są dostępne tylko we wdrożeniach, które korzystają z [obciążenia zarządzania magazynem dla jednostek skali chmury i urządzeń brzegowych](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="e906c-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="e906c-113">Tworzenie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="e906c-113">Create a warehouse order</span></span>

<span data-ttu-id="e906c-114">Aby utworzyć zamówienie magazynowe, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="e906c-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="e906c-115">Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Supply Chain Management działającego w centrum.</span><span class="sxs-lookup"><span data-stu-id="e906c-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="e906c-116">(Należy zainicjować proces *zwalniania do magazynu* po zalogowaniu się do centrum).</span><span class="sxs-lookup"><span data-stu-id="e906c-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="e906c-117">Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="e906c-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="e906c-118">W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="e906c-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="e906c-119">Aby wyświetlić powiązane wiersze zamówienia magazynowego, otwórz odpowiednie zamówienie zakupu, wybierz wiersz w sekcji **Wiersze zamówienia zakupu**, a następnie na pasku narzędzi wybierz pozycję **Magazyn \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="e906c-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="e906c-120">Aby wyświetlić wszystkie wiersze, przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="e906c-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

<span data-ttu-id="e906c-121">Proces *Zwalniania do magazynu* można również wyzwolić z zadania wsadowego, przechodząc na pozycję **Zarządzanie magazynem > Zwolnij do magazynu > Automatyczne zwalnianie zamówień zakupu**.</span><span class="sxs-lookup"><span data-stu-id="e906c-121">You can also trigger the *Release to warehouse* process from a batch job by going to **Warehouse management > Release to warehouse > Automatic release of purchase orders**.</span></span> <span data-ttu-id="e906c-122">Podczas konfigurowania zadania wsadowego można wybrać określone wiersze zamówienia zakupu na podstawie zapytania.</span><span class="sxs-lookup"><span data-stu-id="e906c-122">When setting up the batch job, you can select specific purchase order lines based on a query.</span></span> <span data-ttu-id="e906c-123">Typowym scenariuszem byłoby skonfigurowanie powtarzającego się zadania wsadowego, które zwalnia wszystkie potwierdzone wiersze zamówienia zakupu, które mają nadejść następnego dnia.</span><span class="sxs-lookup"><span data-stu-id="e906c-123">A typical scenario would be to set up a recurrent batch job that releases all the confirmed purchase order lines expected to arrive the next day.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="e906c-124">Anulowanie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="e906c-124">Cancel a warehouse order</span></span>

<span data-ttu-id="e906c-125">W ramach procesu *zwalniania do magazynu* transakcje magazynowe zamówień zakupu są łączone z zamówieniami magazynowymi i nie są aktualizowane przez centrum.</span><span class="sxs-lookup"><span data-stu-id="e906c-125">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="e906c-126">Jeśli przeprowadzono zwalnianie do magazynu przez pomyłkę lub masz inny powód anulowania tworzenia wierszy zamówień magazynowych, można zażądać anulowania wierszy zamówień magazynowych.</span><span class="sxs-lookup"><span data-stu-id="e906c-126">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="e906c-127">Aby anulować wiersze zamówienia magazynowego, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="e906c-127">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="e906c-128">Zaloguj się do wystąpienia rozwiązania Supply Chain Management działającego w centrum.</span><span class="sxs-lookup"><span data-stu-id="e906c-128">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="e906c-129">Przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="e906c-129">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="e906c-130">Wybierz odpowiedni wiersz.</span><span class="sxs-lookup"><span data-stu-id="e906c-130">Select the relevant line.</span></span>
1. <span data-ttu-id="e906c-131">W okienku akcji wybierz pozycję **Anuluj wiersze zamówienia magazynowego**.</span><span class="sxs-lookup"><span data-stu-id="e906c-131">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="e906c-132">Żądanie anulowania wierszy nie będzie realizowane w przypadku wierszy, które już oczekują na anulowanie lub które są aktywnie przetwarzane w magazynie, w których jest uruchomione obciążenie w jednostce skalowania.</span><span class="sxs-lookup"><span data-stu-id="e906c-132">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="e906c-133">Monitorowanie zamówienia magazynowego</span><span class="sxs-lookup"><span data-stu-id="e906c-133">Monitor a warehouse order</span></span>

<span data-ttu-id="e906c-134">W widoku **wierszy zamówienia magazynowego** można monitorować postęp przyjmowania towarów przychodzącego, przeglądając wartości w kolumnie **Ilość pozostała do odebrania**.</span><span class="sxs-lookup"><span data-stu-id="e906c-134">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="e906c-135">Aby wyświetlić szczegóły dotyczące pracy wykonanej za pomocą aplikacji Warehouse Management, wykonaj jedną z poniższych czynności.</span><span class="sxs-lookup"><span data-stu-id="e906c-135">To view details that are related to work that is done by using the Warehouse Management mobile app, follow one of these steps.</span></span>

- <span data-ttu-id="e906c-136">Przejdź do obszaru **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówień magazynowych** i użyj filtru, aby znaleźć szukane wiersze.</span><span class="sxs-lookup"><span data-stu-id="e906c-136">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="e906c-137">Przejdź do pozycji **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu** i otwórz odpowiednie zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="e906c-137">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="e906c-138">W sekcji **Wiersze zamówienia zakupu** zaznacz jeden lub więcej wierszy, a następnie na pasku narzędzi wybierz pozycje **Magazyn \> Wpisy przyjęcia do magazynu**.</span><span class="sxs-lookup"><span data-stu-id="e906c-138">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
