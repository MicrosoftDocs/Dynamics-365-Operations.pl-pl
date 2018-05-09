--- 
title: "Konfigurowanie dokumentów przesunięcia towarów wewnątrz firmy"
description: "Ta procedura pokazuje, jak utworzyć dokumenty przeniesienia w celu przesunięcia towarów wewnątrz firmy."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4f37846f5cc881a37f6e803bb6183f6495100683
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a><span data-ttu-id="bf15b-103">Konfigurowanie dokumentów przesunięcia towarów wewnątrz firmy</span><span class="sxs-lookup"><span data-stu-id="bf15b-103">Set up the transfer documents for goods movement inside a company</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf15b-104">Ta procedura pokazuje, jak utworzyć dokumenty przeniesienia w celu przesunięcia towarów wewnątrz firmy.</span><span class="sxs-lookup"><span data-stu-id="bf15b-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="bf15b-105">Procedura jest dostępna tylko dla firm z główną siedzibą na Litwie.</span><span class="sxs-lookup"><span data-stu-id="bf15b-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="bf15b-106">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się na Litwie.</span><span class="sxs-lookup"><span data-stu-id="bf15b-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="bf15b-107">Zanim będzie można wykonać tę procedurę, należy wykonać procedurę „Konfigurowanie dokumentów przesunięcia towarów wewnątrz firmy”.</span><span class="sxs-lookup"><span data-stu-id="bf15b-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="bf15b-108">Procedura jest przeznaczona dla pracowników księgujących zapasy.</span><span class="sxs-lookup"><span data-stu-id="bf15b-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="bf15b-109">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="bf15b-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="bf15b-110">Tworzenie zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="bf15b-110">Create a transfer order</span></span>
1. <span data-ttu-id="bf15b-111">Wybierz kolejno opcje Zarządzanie zapasami > Zamówienia przychodzące > Zamówienie przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="bf15b-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="bf15b-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="bf15b-112">Click New.</span></span>
3. <span data-ttu-id="bf15b-113">W polu Z magazynu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="bf15b-114">W polu Do magazynu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="bf15b-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="bf15b-115">Click Add.</span></span>
6. <span data-ttu-id="bf15b-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="bf15b-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="bf15b-117">W polu Numer towaru wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="bf15b-118">Wprowadzanie szczegółów transportu dla zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="bf15b-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="bf15b-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bf15b-119">Click Save.</span></span>
2. <span data-ttu-id="bf15b-120">W okienku akcji kliknij pozycję Wysyłka.</span><span class="sxs-lookup"><span data-stu-id="bf15b-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="bf15b-121">Kliknij opcję Szczegóły transportu.</span><span class="sxs-lookup"><span data-stu-id="bf15b-121">Click Transportation details.</span></span>
4. <span data-ttu-id="bf15b-122">W polu Drukuj szczegóły transportu zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="bf15b-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="bf15b-123">W polu Towary wydane przez wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="bf15b-124">W polu Opakowanie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="bf15b-125">W polu Poziom zagrożenia ładunku wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="bf15b-126">Wprowadź lub wybierz wartość w polu Przewoźnik.</span><span class="sxs-lookup"><span data-stu-id="bf15b-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="bf15b-127">Wprowadź lub wybierz wartość w polu Model.</span><span class="sxs-lookup"><span data-stu-id="bf15b-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="bf15b-128">W polu Numer rejestracji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="bf15b-129">W polu Numer rejestracyjny przyczepy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="bf15b-130">Wprowadź lub wybierz wartość w polu Kierowca.</span><span class="sxs-lookup"><span data-stu-id="bf15b-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="bf15b-131">W polu Nazwisko kierowcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="bf15b-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="bf15b-132">Click Save.</span></span>
15. <span data-ttu-id="bf15b-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bf15b-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="bf15b-134">Wyświetlanie dokumentu dostawy dla niezaksięgowanego zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="bf15b-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="bf15b-135">Kliknij opcję Dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="bf15b-135">Click Packing slip.</span></span>
2. <span data-ttu-id="bf15b-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bf15b-136">Click OK.</span></span>
3. <span data-ttu-id="bf15b-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bf15b-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="bf15b-138">Wyświetlanie dokumentu dostawy dla zaksięgowanego zamówienia przeniesienia</span><span class="sxs-lookup"><span data-stu-id="bf15b-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="bf15b-139">W okienku akcji kliknij pozycję Zamówienie przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="bf15b-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="bf15b-140">W okienku akcji kliknij pozycję Wysyłka.</span><span class="sxs-lookup"><span data-stu-id="bf15b-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="bf15b-141">Kliknij opcję Wyślij zamówienie przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="bf15b-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="bf15b-142">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="bf15b-142">Click the General tab.</span></span>
5. <span data-ttu-id="bf15b-143">W polu Aktualizuj wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="bf15b-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="bf15b-144">Kliknij kartę Przegląd.</span><span class="sxs-lookup"><span data-stu-id="bf15b-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="bf15b-145">W polu Dokument dostawy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bf15b-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="bf15b-146">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bf15b-146">Click OK.</span></span>
9. <span data-ttu-id="bf15b-147">W okienku akcji kliknij pozycję Wysyłka.</span><span class="sxs-lookup"><span data-stu-id="bf15b-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="bf15b-148">Kliknij opcję Dokument dostawy.</span><span class="sxs-lookup"><span data-stu-id="bf15b-148">Click Packing slip.</span></span>
11. <span data-ttu-id="bf15b-149">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bf15b-149">Click OK.</span></span>


