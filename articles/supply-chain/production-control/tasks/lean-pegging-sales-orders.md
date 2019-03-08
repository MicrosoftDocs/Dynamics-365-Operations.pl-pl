---
title: Oznaczenie transakcji produkcji oszczędnej z zamówień sprzedaży
description: Ta procedura skupia się na sprawdzeniu poprawności drzewa oznaczania transakcji z poziomu wiersza sprzedaży, gdzie towar jest produkowany za pomocą kart Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2e2448dfd83304d4f7e5dfc8ce0d02cdac998779
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "340368"
---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="fec43-103">Oznaczenie transakcji produkcji oszczędnej z zamówień sprzedaży</span><span class="sxs-lookup"><span data-stu-id="fec43-103">Lean pegging from sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fec43-104">Ta procedura skupia się na sprawdzeniu poprawności drzewa oznaczania transakcji z poziomu wiersza sprzedaży, gdzie towar jest produkowany za pomocą kart Kanban.</span><span class="sxs-lookup"><span data-stu-id="fec43-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="fec43-105">Po weryfikacji drzewa oznaczania transakcji wszystkie zadania w systemie Kanban są zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="fec43-106">Jest to przydatne w scenariuszach zamawiania, gdzie osoba przyjmująca zamówienie musi się upewnić, że produkcja może zostać od razu rozpoczęta.</span><span class="sxs-lookup"><span data-stu-id="fec43-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="fec43-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="fec43-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fec43-108">Ta procedura jest przeznaczona dla specjalistów ds. przyjmowania zamówień pracujących w firmie stosującej zasady produkcji oszczędnej.</span><span class="sxs-lookup"><span data-stu-id="fec43-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="fec43-109">Tworzenie zamówienia sprzedaży dla towaru kontrolowanego w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="fec43-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="fec43-110">Przejdź do okna Wszystkie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fec43-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="fec43-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fec43-111">Click New.</span></span>
3. <span data-ttu-id="fec43-112">W polu Konto odbiorcy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fec43-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="fec43-113">Użyj wartości USA-001.</span><span class="sxs-lookup"><span data-stu-id="fec43-113">Use US-001.</span></span>  
4. <span data-ttu-id="fec43-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="fec43-114">Click OK.</span></span>
5. <span data-ttu-id="fec43-115">W polu Numer pozycji wpisz „L0001”.</span><span class="sxs-lookup"><span data-stu-id="fec43-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="fec43-116">W polu Ilość wpisz wartość 30.</span><span class="sxs-lookup"><span data-stu-id="fec43-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="fec43-117">Jest ważne, aby ilość była większa niż 24, co zapewni wyzwalanie reguły Kanban zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="fec43-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="fec43-118">Otwieranie drzewa oznaczania transakcji</span><span class="sxs-lookup"><span data-stu-id="fec43-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="fec43-119">Kliknij opcję Produkt i dostawa.</span><span class="sxs-lookup"><span data-stu-id="fec43-119">Click Product and supply.</span></span>
2. <span data-ttu-id="fec43-120">Kliknij opcję Wyświetl drzewo oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="fec43-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="fec43-121">Należy zauważyć, że drzewo oznaczania transakcji pokazuje wszystkie poziomy oznaczania transakcji potrzebne dla wiersza zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fec43-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="fec43-122">W tym przypadku istnieją dwa poziomy kart Kanban i wszystkie wymagane składniki.</span><span class="sxs-lookup"><span data-stu-id="fec43-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="fec43-123">Planowanie drzewa oznaczania transakcji</span><span class="sxs-lookup"><span data-stu-id="fec43-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="fec43-124">W drzewie zaznacz element „Wiersz sprzedaży 000832\Kanban 000558”.</span><span class="sxs-lookup"><span data-stu-id="fec43-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="fec43-125">Rozwiń sekcję Zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="fec43-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="fec43-126">Należy zauważyć, że stan zadania w systemie Kanban to Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="fec43-127">Kliknij opcję Zaplanuj całe drzewo oznaczania transakcji.</span><span class="sxs-lookup"><span data-stu-id="fec43-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="fec43-128">Spowoduje to zaplanowanie wszystkich zadań w systemie Kanban w drzewie oznaczania transakcji oraz zmianę stanu zadania z Niezaplanowane na Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="fec43-129">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="fec43-129">Refresh the page.</span></span>
    * <span data-ttu-id="fec43-130">Należy zauważyć, że stan zadania w systemie Kanban zmienił się z Niezaplanowane na Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="fec43-131">W drzewie zaznacz element „Wiersz sprzedaży 000832\Kanban 000558\Wydanie towaru L0001\Kanban 000559”.</span><span class="sxs-lookup"><span data-stu-id="fec43-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="fec43-132">Zadanie na drugiej karcie Kanban jest również zaplanowane, ponieważ całe drzewo oznaczania transakcji jest zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="fec43-133">Należy zauważyć, że stan zadania w systemie Kanban zmienił się z Niezaplanowane na Zaplanowane.</span><span class="sxs-lookup"><span data-stu-id="fec43-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  

