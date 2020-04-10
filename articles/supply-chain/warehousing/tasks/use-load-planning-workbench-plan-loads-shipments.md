---
title: Planowanie ładunków i wysyłek za pomocą pulpitu planowania wysyłki ładunku
description: W tym temacie pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a51031647e270662f37138848b0db9ed08d544e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145898"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="e7b3c-103">Planowanie ładunków i wysyłek za pomocą pulpitu planowania wysyłki ładunku</span><span class="sxs-lookup"><span data-stu-id="e7b3c-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7b3c-104">W tym temacie pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="e7b3c-105">Warunkiem wstępnym jest utworzenie zamówienia sprzedaży, co zrobimy najpierw.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="e7b3c-106">Ta procedura jest częścią codziennej pracy koordynatora transportu.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="e7b3c-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="e7b3c-108">Utwórz zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e7b3c-108">Create a sales order</span></span>
1. <span data-ttu-id="e7b3c-109">Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="e7b3c-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-110">Select **New**.</span></span>
3. <span data-ttu-id="e7b3c-111">W polu **Konto konta** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e7b3c-112">Wybierz konto **US-004**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="e7b3c-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-113">Select **OK**.</span></span>
6. <span data-ttu-id="e7b3c-114">W polu **Numer produktu** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e7b3c-115">Wybierz towar **A0001**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-115">Select item **A0001**.</span></span> <span data-ttu-id="e7b3c-116">Towar **A0001** jest włączony dla zarządzania transportem.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="e7b3c-117">W polu **Oddział** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie, a następnie wybierz towar.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="e7b3c-118">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="e7b3c-119">W polu **Magazyn** wpisz „24” na potrzeby tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="e7b3c-120">Ten magazyn jest włączony dla zarządzania transportem i zaawansowanego zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="e7b3c-121">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-121">Select **Save**.</span></span>
12. <span data-ttu-id="e7b3c-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="e7b3c-123">Tworzenie nowego ładunku</span><span class="sxs-lookup"><span data-stu-id="e7b3c-123">Create a new load</span></span>
1. <span data-ttu-id="e7b3c-124">Otwórz **Okienko nawigacji > Moduły > Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="e7b3c-125">Wybierz kartę **Wiersze sprzedaży**. Teraz utworzysz ładunek dla utworzonego właśnie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="e7b3c-126">Ładunki można tworzyć na podstawie podaży i popytu z zamówień zakupu, zamówień przeniesienia i zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="e7b3c-127">W okienku akcji wybierz opcję **Popyt i podaż**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="e7b3c-128">Wybierz opcję **Do nowego ładunku**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-128">Select **To new load**.</span></span>
5. <span data-ttu-id="e7b3c-129">W polu **Identyfikator szablonu ładunku** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="e7b3c-130">Szablon Ładunek określa maksymalne parametry wagi i objętości całego ładunku.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="e7b3c-131">Na przykład szablon ładunku może reprezentować rozmiar kontenera lub ciężarówki.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="e7b3c-132">Wybierz towar.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-132">Select an item.</span></span>
6. <span data-ttu-id="e7b3c-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="e7b3c-134">Ustawiania stawek i wyznaczania trasy dla ładunku</span><span class="sxs-lookup"><span data-stu-id="e7b3c-134">Rate and route the load</span></span>
1. <span data-ttu-id="e7b3c-135">Wybierz opcję **Ustawianie stawek i wybór trasy**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="e7b3c-136">Wybierz opcję **Pulpit ustalania stawek i wyznaczania tras**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="e7b3c-137">Wybierz opcję **Szukanie najlepszej stawki**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="e7b3c-138">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e7b3c-139">Wybierz opcję **Przypisz**.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-139">Select **Assign**.</span></span>
6. <span data-ttu-id="e7b3c-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e7b3c-140">Close the page.</span></span>

