---
title: Tworzenie i obsługa blokowania zapasów
description: W tej procedurze pokazano, jak za pomocą funkcji blokowania zapasów zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe dotyczące towarów wychodzących.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e76c3d1f46e31dcd2171682a629dabe5bf5db418
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204155"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="5301c-103">Tworzenie i obsługa blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5301c-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5301c-104">W tej procedurze pokazano, jak za pomocą funkcji blokowania zapasów zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe dotyczące towarów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="5301c-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="5301c-105">Tę procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="5301c-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="5301c-106">Przed rozpoczęciem tej procedury musisz mieć fizycznie dostępne zapasy towaru.</span><span class="sxs-lookup"><span data-stu-id="5301c-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="5301c-107">Tworzenie blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5301c-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="5301c-108">W **Okienku nawigacji** otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Blokowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="5301c-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="5301c-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5301c-109">Click **New**.</span></span>
3. <span data-ttu-id="5301c-110">W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5301c-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5301c-111">Na liście zaznacz towar, który chcesz wybrać.</span><span class="sxs-lookup"><span data-stu-id="5301c-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="5301c-112">Wybierz numer towaru fizycznie dostępnych zapasów, które chcesz zablokować.</span><span class="sxs-lookup"><span data-stu-id="5301c-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="5301c-113">Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar M9201.</span><span class="sxs-lookup"><span data-stu-id="5301c-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="5301c-114">W polu **Ilość** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5301c-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="5301c-115">Jeśli używasz towaru M9201, wybierz mniej niż 200.</span><span class="sxs-lookup"><span data-stu-id="5301c-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="5301c-116">Rozwiń skróconą kartę **Wymiary magazynowe**.</span><span class="sxs-lookup"><span data-stu-id="5301c-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="5301c-117">W polu **Magazyn** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5301c-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5301c-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5301c-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="5301c-119">Jeśli używasz towaru M9201, można wybrać magazyn 51.</span><span class="sxs-lookup"><span data-stu-id="5301c-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="5301c-120">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5301c-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="5301c-121">Aktualizowanie warunków blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5301c-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="5301c-122">W skróconej karcie **Ogólne** w polu **Ilość** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="5301c-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="5301c-123">Zaktualizuj pole ilości zapasów, aby uwzględniało ilość do zablokowania.</span><span class="sxs-lookup"><span data-stu-id="5301c-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="5301c-124">W polu **Oczekiwana data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="5301c-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="5301c-125">Warto określić, kiedy zablokowane zapasy powinny stać się dostępne do rezerwacji, przypisując im oczekiwaną datę.</span><span class="sxs-lookup"><span data-stu-id="5301c-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="5301c-126">Jeśli w ustawieniu blokowania zapasów zostanie zaznaczona opcja Przewidywane do przyjęcia, co ma miejsce domyślnie podczas ręcznego tworzenia blokowania, ta data będzie wyświetlana na oczekiwanej transakcji.</span><span class="sxs-lookup"><span data-stu-id="5301c-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="5301c-127">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5301c-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="5301c-128">Usuwanie blokowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5301c-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="5301c-129">W **Okienku akcji** kliknij pozycję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="5301c-129">On the **Action pane**, click **Delete**.</span></span>
2. <span data-ttu-id="5301c-130">Kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5301c-130">Click **Yes**.</span></span>
3. <span data-ttu-id="5301c-131">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="5301c-131">Close the page.</span></span>

