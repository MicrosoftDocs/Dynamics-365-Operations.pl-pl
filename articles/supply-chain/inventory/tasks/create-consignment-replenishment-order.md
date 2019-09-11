---
title: Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
description: Ten temat pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.
author: mkirknel
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f426dbf00eace23da2f26eb50dd9675fe22ed445
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914800"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="419aa-103">Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych</span><span class="sxs-lookup"><span data-stu-id="419aa-103">Create a consignment replenishment order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="419aa-104">Ten temat pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.</span><span class="sxs-lookup"><span data-stu-id="419aa-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="419aa-105">Prezentuje także sposób rejestrowania przyjęcia produktów, tak aby zapasy konsygnacyjne zostały zarejestrowane jako zapasy dostępne będące własnością dostawcy.</span><span class="sxs-lookup"><span data-stu-id="419aa-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="419aa-106">Zazwyczaj procedurę wykonuje pracownik działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="419aa-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="419aa-107">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="419aa-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="419aa-108">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="419aa-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="419aa-109">Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych</span><span class="sxs-lookup"><span data-stu-id="419aa-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="419aa-110">W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Konsygnacja > Zamówienia uzupełnienia zapasów konsygnacyjnych**.</span><span class="sxs-lookup"><span data-stu-id="419aa-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="419aa-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="419aa-111">Select **New**.</span></span>
3. <span data-ttu-id="419aa-112">W polu **Konto dostawcy** wybierz dostawca **US-104** (należy wybrać dostawcę, który jest zarejestrowany jako właściciel na stronie **właściciele zapasów**).</span><span class="sxs-lookup"><span data-stu-id="419aa-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="419aa-113">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="419aa-113">Select **OK**.</span></span>
5. <span data-ttu-id="419aa-114">Wybierz **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="419aa-114">Select **Add line**.</span></span>
6. <span data-ttu-id="419aa-115">W polu **Kod pozycji** wpisz typ `M9211CI` (należy wybrać towar skonfigurowany dla zapasów konsygnacyjnych).</span><span class="sxs-lookup"><span data-stu-id="419aa-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="419aa-116">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="419aa-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="419aa-117">W polu **Wymagana data dostawy** wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="419aa-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="419aa-118">Daty wymagalności i potwierdzona są używane przez aparat systemu MRP dla planowanego przybycia towarów.</span><span class="sxs-lookup"><span data-stu-id="419aa-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="419aa-119">W polu **Potwierdzona data dostawy** wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="419aa-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="419aa-120">Rozwiń sekcję **Szczegóły wiersza**.</span><span class="sxs-lookup"><span data-stu-id="419aa-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="419aa-121">Wybierz kartę **Wymiary magazynowe**.</span><span class="sxs-lookup"><span data-stu-id="419aa-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="419aa-122">Aby pokazać właściciela w polu **Właściciel wymiarów magazynowych**, odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="419aa-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="419aa-123">Dostawca US-104 jest teraz wymieniony jako właściciel.</span><span class="sxs-lookup"><span data-stu-id="419aa-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="419aa-124">Sprawdzanie stanu transakcji magazynowej</span><span class="sxs-lookup"><span data-stu-id="419aa-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="419aa-125">Wybierz **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="419aa-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="419aa-126">Wybierz **transakcje**.</span><span class="sxs-lookup"><span data-stu-id="419aa-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="419aa-127">W pożądanym wierszu, należy zauważyć, że pole **Przyjęcie** jest ustawione na **Zamówione**.</span><span class="sxs-lookup"><span data-stu-id="419aa-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="419aa-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="419aa-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="419aa-129">Odbierz pozycje</span><span class="sxs-lookup"><span data-stu-id="419aa-129">Receive items</span></span>
1. <span data-ttu-id="419aa-130">Wybierz pozycję **Przyjęcie produktu**.</span><span class="sxs-lookup"><span data-stu-id="419aa-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="419aa-131">W polu **Zewnętrzny dokument przyjęcia** produktów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="419aa-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="419aa-132">W polu **Ilość** wprowadź liczbę, która jest niższa niż liczba wyświetlana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="419aa-132">In the **Quantity** field, enter a number that’s lower than the number that’s shown there.</span></span> 
4. <span data-ttu-id="419aa-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="419aa-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="419aa-134">Sprawdzanie dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="419aa-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="419aa-135">Wybierz **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="419aa-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="419aa-136">Wybierz **Dostępne**.</span><span class="sxs-lookup"><span data-stu-id="419aa-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="419aa-137">Wybierz **Przegląd**.</span><span class="sxs-lookup"><span data-stu-id="419aa-137">Select **Overview**.</span></span> <span data-ttu-id="419aa-138">Towary, które zostały przyjęte jako zapasy konsygnacyjne będące własnością dostawcy, są dostępne.</span><span class="sxs-lookup"><span data-stu-id="419aa-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="419aa-139">Pozostała ilość w zamówieniu uzupełnienia zapasów konsygnacyjnych jest wyświetlana w polu **Zamówione w sumie**.</span><span class="sxs-lookup"><span data-stu-id="419aa-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="419aa-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="419aa-140">Close the page.</span></span>

