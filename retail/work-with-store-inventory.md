---
title: "Zarządzanie zapasami w sklepie"
description: "W tym artykule opisano typy dokumentów, których można używać do zarządzania zapasami."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1fd37bcd7155c61492f5f4990685203ea97bca36
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="manage-store-inventory"></a><span data-ttu-id="010f1-103">Zarządzanie zapasami w sklepie</span><span class="sxs-lookup"><span data-stu-id="010f1-103">Manage store inventory</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="010f1-104">W tym artykule opisano typy dokumentów, których można używać do zarządzania zapasami.</span><span class="sxs-lookup"><span data-stu-id="010f1-104">This article describes the types of documents that you can use to manage inventory.</span></span>

<span data-ttu-id="010f1-105">Następujące typy dokumentów służą do zarządzania zapasami w organizacji.</span><span class="sxs-lookup"><span data-stu-id="010f1-105">You can use the following types of documents to manage your organization's inventory.</span></span>

## <a name="purchase-orders"></a><span data-ttu-id="010f1-106">Zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="010f1-106">Purchase orders</span></span>
<span data-ttu-id="010f1-107">Zamówienia zakupu są tworzone w centrali.</span><span class="sxs-lookup"><span data-stu-id="010f1-107">Purchase orders are created at the head office.</span></span> <span data-ttu-id="010f1-108">Jeśli magazyn sprzedaży detalicznej znajduje się w nagłówku zamówienia zakupu, zamówienia można otrzymać w sklepie przy użyciu aplikacji Modern POS (MPOS) lub Cloud POS dostępnej w module Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="010f1-108">If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="010f1-109">Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować.</span><span class="sxs-lookup"><span data-stu-id="010f1-109">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="010f1-110">Można też zatwierdzić ilości i wysłać do centrali.</span><span class="sxs-lookup"><span data-stu-id="010f1-110">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="010f1-111">Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Dostarczone teraz** na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="010f1-111">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the purchase order.</span></span>

## <a name="transfer-orders"></a><span data-ttu-id="010f1-112">Zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="010f1-112">Transfer orders</span></span>
<span data-ttu-id="010f1-113">W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, z której można wysyłać towary.</span><span class="sxs-lookup"><span data-stu-id="010f1-113">A transfer order can specify that a particular store is a location that items can be shipped from.</span></span> <span data-ttu-id="010f1-114">W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie pobrania w aplikacji MPOS lub Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="010f1-114">In this case, the transfer order appears at the store as a picking request in MPOS or Cloud POS.</span></span> <span data-ttu-id="010f1-115">Po pobraniu żądanych ilości zostaną one zatwierdzone i przesłane do centrali.</span><span class="sxs-lookup"><span data-stu-id="010f1-115">After the quantities that are requested are picked, they are committed and sent to the head office.</span></span> <span data-ttu-id="010f1-116">Zlokalizowane w centrali ilości, które zostały pobrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Wyślij teraz** na zamówieniu przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="010f1-116">At the head office, the quantities that were picked at the store are displayed in Dynamics 365 for Retail, in the **Ship now** field on the transfer order.</span></span> <span data-ttu-id="010f1-117">W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, do której można wysyłać towary.</span><span class="sxs-lookup"><span data-stu-id="010f1-117">A transfer order may specify that a particular store is a location that items can be shipped to.</span></span> <span data-ttu-id="010f1-118">W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie przyjęcia w aplikacji MPOS lub Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="010f1-118">In this case, the transfer order appears at the store as a receiving request in MPOS or Cloud POS.</span></span> <span data-ttu-id="010f1-119">Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować.</span><span class="sxs-lookup"><span data-stu-id="010f1-119">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="010f1-120">Można też zatwierdzić ilości i wysłać do centrali.</span><span class="sxs-lookup"><span data-stu-id="010f1-120">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="010f1-121">Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Dostarczone teraz** na zamówieniu przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="010f1-121">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the transfer order.</span></span>

## <a name="stock-counts"></a><span data-ttu-id="010f1-122">Stany zapasów z inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="010f1-122">Stock counts</span></span>
<span data-ttu-id="010f1-123">Inwentaryzacje mogą być zaplanowane lub niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="010f1-123">Stock counts can be either scheduled or unscheduled.</span></span> <span data-ttu-id="010f1-124">Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="010f1-124">Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</span></span> <span data-ttu-id="010f1-125">Centrala tworzy dokument inwentaryzacji, który można otrzymać w sklepie. Rzeczywista ilość dostępnych zapasów jest wprowadzana w aplikacji MPOS lub Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="010f1-125">The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</span></span> <span data-ttu-id="010f1-126">Niezaplanowane inwentaryzacje są inicjowane w sklepie, a rzeczywista ilość dostępnych zapasów jest aktualizowana w aplikacji MPOS lub Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="010f1-126">Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</span></span> <span data-ttu-id="010f1-127">W odróżnieniu od zaplanowanej inwentaryzacji niezaplanowana nie ma wstępnie zdefiniowanej listy pozycji.</span><span class="sxs-lookup"><span data-stu-id="010f1-127">Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</span></span> <span data-ttu-id="010f1-128">Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali.</span><span class="sxs-lookup"><span data-stu-id="010f1-128">When a stock count of either type is completed, it is committed and sent to the head office.</span></span> <span data-ttu-id="010f1-129">W centrali dane podlegają sprawdzeniu i zaksięgowaniu.</span><span class="sxs-lookup"><span data-stu-id="010f1-129">At the head office, the count is validated and posted.</span></span>

## <a name="inventory-lookup"></a><span data-ttu-id="010f1-130">Wyszukiwanie w magazynie</span><span class="sxs-lookup"><span data-stu-id="010f1-130">Inventory lookup</span></span>
<span data-ttu-id="010f1-131">Bieżącą ilość produktów dostępnych w wielu sklepach i magazynach można obejrzeć na stronie Wyszukiwanie w magazynie.</span><span class="sxs-lookup"><span data-stu-id="010f1-131">The current product quantity on hand for multiple stores and warehouses can be viewed on the Inventory lookup page.</span></span> <span data-ttu-id="010f1-132">Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla poszczególnych sklepów.</span><span class="sxs-lookup"><span data-stu-id="010f1-132">In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</span></span> <span data-ttu-id="010f1-133">Aby to zrobić, zaznacz sklep, dla którego chcesz obejrzeć ATP, i kliknij przycisk **Pokaż dostępność sklepu**.</span><span class="sxs-lookup"><span data-stu-id="010f1-133">To do so, select the store that you want to view the ATP for and then click **Show store availability**.</span></span>





