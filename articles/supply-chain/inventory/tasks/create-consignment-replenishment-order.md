---
title: Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
description: Ta procedura pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "315505"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="6900d-103">Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych</span><span class="sxs-lookup"><span data-stu-id="6900d-103">Create a consignment replenishment order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6900d-104">Ta procedura pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6900d-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="6900d-105">Prezentuje także sposób rejestrowania przyjęcia produktów, tak aby zapasy konsygnacyjne zostały zarejestrowane jako zapasy dostępne będące własnością dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6900d-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="6900d-106">Zazwyczaj procedurę wykonuje pracownik działu zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="6900d-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="6900d-107">Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6900d-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="6900d-108">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="6900d-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="6900d-109">Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych</span><span class="sxs-lookup"><span data-stu-id="6900d-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="6900d-110">Wybierz kolejno opcje Zaopatrzenie i sourcing > Konsygnacja > Zamówienia uzupełnienia zapasów konsygnacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6900d-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="6900d-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6900d-111">Click New.</span></span>
3. <span data-ttu-id="6900d-112">W polu Konto dostawcy wybierz dostawcę US-104.</span><span class="sxs-lookup"><span data-stu-id="6900d-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="6900d-113">Musisz wybrać dostawcę, który jest zarejestrowany jako właściciel na stronie Właściciele zapasów.</span><span class="sxs-lookup"><span data-stu-id="6900d-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="6900d-114">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6900d-114">Click OK.</span></span>
5. <span data-ttu-id="6900d-115">Kliknij przycisk Dodaj wiersz.</span><span class="sxs-lookup"><span data-stu-id="6900d-115">Click Add line.</span></span>
6. <span data-ttu-id="6900d-116">W polu Kod pozycji wpisz wartość M9211CI.</span><span class="sxs-lookup"><span data-stu-id="6900d-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="6900d-117">Należy wybrać towar, który jest skonfigurowany dla zapasów konsygnacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6900d-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="6900d-118">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="6900d-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="6900d-119">W polu Wymagana data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="6900d-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="6900d-120">Daty wymagalności i potwierdzona są używane przez aparat systemu MRP dla planowanego przybycia towarów.</span><span class="sxs-lookup"><span data-stu-id="6900d-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="6900d-121">W polu Potwierdzona data dostawy wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="6900d-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="6900d-122">Rozwiń sekcję Szczegóły wiersza.</span><span class="sxs-lookup"><span data-stu-id="6900d-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="6900d-123">Kliknij kartę Wymiary magazynowe.</span><span class="sxs-lookup"><span data-stu-id="6900d-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="6900d-124">Aby pokazać właściciela w polu Właściciel wymiarów magazynowych, odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="6900d-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="6900d-125">Dostawca US-104 jest teraz wymieniony jako właściciel.</span><span class="sxs-lookup"><span data-stu-id="6900d-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="6900d-126">Sprawdzanie stanu transakcji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6900d-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="6900d-127">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="6900d-127">Click Inventory.</span></span>
2. <span data-ttu-id="6900d-128">Kliknij opcję Transakcje.</span><span class="sxs-lookup"><span data-stu-id="6900d-128">Click Transactions.</span></span>
3. <span data-ttu-id="6900d-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6900d-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6900d-130">Należy zauważyć, że pole Przyjęcie jest ustawione na Zamówione.</span><span class="sxs-lookup"><span data-stu-id="6900d-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="6900d-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6900d-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="6900d-132">Odbierz pozycje</span><span class="sxs-lookup"><span data-stu-id="6900d-132">Receive items</span></span>
1. <span data-ttu-id="6900d-133">Kliknij opcję Dokument przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="6900d-133">Click Product receipt.</span></span>
2. <span data-ttu-id="6900d-134">W polu Zewnętrzny dokument przyjęcia produktów wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6900d-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="6900d-135">W polu Ilość wprowadź liczbę, która jest niższa niż liczba wyświetlana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="6900d-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span> 
4. <span data-ttu-id="6900d-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6900d-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="6900d-137">Sprawdzanie dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="6900d-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="6900d-138">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="6900d-138">Click Inventory.</span></span>
2. <span data-ttu-id="6900d-139">Kliknij opcję Zapasy.</span><span class="sxs-lookup"><span data-stu-id="6900d-139">Click On-hand.</span></span>
3. <span data-ttu-id="6900d-140">Kliknij przycisk Przegląd.</span><span class="sxs-lookup"><span data-stu-id="6900d-140">Click Overview.</span></span>
    * <span data-ttu-id="6900d-141">Towary, które zostały przyjęte jako zapasy konsygnacyjne będące własnością dostawcy, są dostępne.</span><span class="sxs-lookup"><span data-stu-id="6900d-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="6900d-142">Pozostała ilość w zamówieniu uzupełnienia zapasów konsygnacyjnych jest wyświetlana w polu Zamówione w sumie.</span><span class="sxs-lookup"><span data-stu-id="6900d-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="6900d-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6900d-143">Close the page.</span></span>
5. <span data-ttu-id="6900d-144">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="6900d-144">Click Close.</span></span>

