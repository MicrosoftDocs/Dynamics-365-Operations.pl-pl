---
title: Obsługa zamówień planowanych
description: Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68bccb632255eac975dc150cf322d4c579ff2f24
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813783"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="c8f91-104">Obsługa zamówień planowanych</span><span class="sxs-lookup"><span data-stu-id="c8f91-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8f91-105">Ten temat zawiera informacje o metodach zarządzania zamówienia planowanymi.</span><span class="sxs-lookup"><span data-stu-id="c8f91-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="c8f91-106">Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.</span><span class="sxs-lookup"><span data-stu-id="c8f91-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="c8f91-107">Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="c8f91-108">Stan zamówienia planowanego</span><span class="sxs-lookup"><span data-stu-id="c8f91-108">Planned order status</span></span>
<span data-ttu-id="c8f91-109">Pole **Stan** pomaga w śledzeniu postępu zamówień.</span><span class="sxs-lookup"><span data-stu-id="c8f91-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="c8f91-110">Używane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="c8f91-110">The following values are used:</span></span>

-   <span data-ttu-id="c8f91-111">Zamówienia planowane generowane podczas planowania głównego mają stan **Nieprzetworzone**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="c8f91-112">Jeżeli nie chcesz ustalać zamówienia planowanego, możesz nadać mu stan **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="c8f91-113">Aby ustalić zamówienie planowane, można zmienić stan na **zatwierdzone**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="c8f91-114">Zamówienia planowane ze stanem **zatwierdzonym** są przestrzegane w planowaniu głównym, więc nie można ich modyfikować ani usuwać podczas późniejszego przebiegu planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="c8f91-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> 

## <a name="firming-planned-orders"></a><span data-ttu-id="c8f91-115">Akceptacja planowanych zamówień</span><span class="sxs-lookup"><span data-stu-id="c8f91-115">Firming planned orders</span></span> 
<span data-ttu-id="c8f91-116">Podczas ustalania zamówień planowanych tworzone są rzeczywiste zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c8f91-116">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="c8f91-117">Są one również znane jako zamówienia *zwolnione* lub *otwarte*.</span><span class="sxs-lookup"><span data-stu-id="c8f91-117">These are also know as *released* or *open orders*.</span></span> <span data-ttu-id="c8f91-118">Po ustaleniu zamówienie planowane zostanie przesunięte do sekcji zamówień w odpowiednim module.</span><span class="sxs-lookup"><span data-stu-id="c8f91-118">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="c8f91-119">Na stronie **zamówienia planowane** można wybrać dwie opcje ustalania:</span><span class="sxs-lookup"><span data-stu-id="c8f91-119">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="c8f91-120">**Akceptowane** — umożliwia ustalenie jednego lub wielu wybranych zamówień planowanych.</span><span class="sxs-lookup"><span data-stu-id="c8f91-120">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="c8f91-121">**Zaakceptuj wszystko** — spowoduje to ustalenie wszystkich zamówień planowanych w filtrze.</span><span class="sxs-lookup"><span data-stu-id="c8f91-121">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="c8f91-122">Używanie **zaakceptuj wszystko** nie musisz wybierać planowanego zamówienia, wszystkie planowane zamówienia w ramach filtru zostaną ustalone.</span><span class="sxs-lookup"><span data-stu-id="c8f91-122">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="c8f91-123">Ta opcja może być przydatna w przypadku ustalania dużej liczby zamówień planowanych.</span><span class="sxs-lookup"><span data-stu-id="c8f91-123">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f91-124">Istnieje możliwość śledzenia planowanego zamówienia, które zostało ustalone z **Historia akceptacji** pod **Planowane formularze zamówień > Zobacz > Historia akceptacji**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-124">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="c8f91-125">Zrównoleglenie akceptacji</span><span class="sxs-lookup"><span data-stu-id="c8f91-125">Parallelize firming</span></span>
<span data-ttu-id="c8f91-126">Jeśli planujesz ustalać wiele zamówień w tym samym czasie, parallelizing przebieg może poprawić czas działania lub wydajność.</span><span class="sxs-lookup"><span data-stu-id="c8f91-126">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="c8f91-127">Ta opcja jest dostępna podczas ustalania wielu zamówień planowanych z **Zaakceptuj** lub **Zaakceptuj wszystko**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-127">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="c8f91-128">Dostępne są następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="c8f91-128">The following parameters are available:</span></span>

-   <span data-ttu-id="c8f91-129">**Równoległa akceptacja** — Jeśli **tak**, proces ustalania będzie równoległy do liczby wątków zdefiniowanych w **liczbie wątków.**</span><span class="sxs-lookup"><span data-stu-id="c8f91-129">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="c8f91-130">**Liczba wątków** — określa liczbę wątków używanych do parallelize procesu ustalania.</span><span class="sxs-lookup"><span data-stu-id="c8f91-130">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="c8f91-131">Parametr jest wyświetlany tylko wtedy, gdy ustawienie **Równoległa akceptacja** ma wartość **tak**.</span><span class="sxs-lookup"><span data-stu-id="c8f91-131">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="c8f91-132">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c8f91-132">Additional resources</span></span>
--------

[<span data-ttu-id="c8f91-133">Omówienie planów głównych</span><span class="sxs-lookup"><span data-stu-id="c8f91-133">Master plans overview</span></span>](master-plans.md)



