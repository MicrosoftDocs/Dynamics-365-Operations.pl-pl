---
title: Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6151797001b1ccdb7e371c70b90c304a5ab422d8
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645127"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="e3aa2-103">Rozwiązywanie problemów z rezerwacjami w module zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="e3aa2-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3aa2-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z rezerwacjami w magazynie w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="e3aa2-105">Otrzymuje następujący komunikat o błędzie: „Nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aa2-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="e3aa2-106">Issue description</span></span>

<span data-ttu-id="e3aa2-107">Nie można usunąć rezerwacji zapasów w wierszu sprzedaży, ponieważ w wierszu istnieje otwarta praca.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aa2-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="e3aa2-108">Issue resolution</span></span>

<span data-ttu-id="e3aa2-109">Sprawdź, czy istnieje otwarta grupa załadunkowa, aby przenieść pozycję z stacji pakowania do innej lokalizacji (np. *Brama dokowa*).</span><span class="sxs-lookup"><span data-stu-id="e3aa2-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="e3aa2-110">Przejrzyj rekordy w **Dzienniku historii tworzenia pracy** i **Szczegóły pracy**, aby określić, co fizycznie rezerwuje zapasy, a następnie ukończyć lub usunąć pracę, aby zwolnić rezerwację.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="e3aa2-111">Zgłaszany jest następujący komunikat o błędzie: „Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2”...</span><span class="sxs-lookup"><span data-stu-id="e3aa2-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aa2-112">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="e3aa2-112">Issue description</span></span>

<span data-ttu-id="e3aa2-113">Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="e3aa2-114">Oto pełen tekst całego komunikatu o błędzie:</span><span class="sxs-lookup"><span data-stu-id="e3aa2-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="e3aa2-115">Ilość zapasów -%1 nie zostać zaktualizowane z powodu niewystarczających transakcji magazynowych dla pozycji %2 o wymiarze Wymiar=%3, Kolor=%4, Dodatki=%5, Oddział=%6, Magazyn=%7, Lokalizacja=%8, Stan zapasów=dostępny, Numer identyfikacyjny=%9, Numer partii=%10 dla identyfikatora odwołania %11 w identyfikatorze partii %12.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aa2-116">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="e3aa2-116">Issue resolution</span></span>

<span data-ttu-id="e3aa2-117">Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="e3aa2-118">Na przykład te transakcje mogą otwierać zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="e3aa2-119">Zgłaszany jest następujący komunikat o błędzie: „Fizycznie dostępne zapasy... nie mogą być zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00”.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aa2-120">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="e3aa2-120">Issue description</span></span>

<span data-ttu-id="e3aa2-121">Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="e3aa2-122">Oto pełen tekst całego komunikatu o błędzie:</span><span class="sxs-lookup"><span data-stu-id="e3aa2-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="e3aa2-123">Fizycznie dostępne w oddziale=%1, Magazyn=%2, Stan zapasów=dostępne, Numer partii=%3, Właściciel=%4: %5 nie może zostać zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aa2-124">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="e3aa2-124">Issue resolution</span></span>

<span data-ttu-id="e3aa2-125">Ten problem jest prawdopodobnie spowodowany otwarta pracą.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="e3aa2-126">Ukończ pracę lub odbierz bez tworzenia pracy.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="e3aa2-127">Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="e3aa2-128">Na przykład tymi transakcjami mogą być otwarte zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="e3aa2-129">Pojawia się następujący komunikat o błędzie: „Aby przypisać do grupy czynności, wiersze ładunku muszą określać wymiary powyżej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="e3aa2-130">Aby przypisać te wymiary, zarezerwuj i ponownie utwórz wiersz ładunku”.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e3aa2-131">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="e3aa2-131">Issue description</span></span>

<span data-ttu-id="e3aa2-132">W przypadku użycia towaru, który ma „partię powyżej” hierarchii rezerwacji (z wymiarem **numer partii** umieszczonym *nad* **wymiarem lokalizacji**), polecenie **Zwolnij do magazynu** na stronie **Pulpitu planowania ładunku** dla ilości częściowej nie działa.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="e3aa2-133">Pojawia się ten komunikat o błędzie i nie utworzono żadnej pracy dla ilości częściowej.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="e3aa2-134">Jednakże w przypadku użycia towaru, który ma „partię poniżej” hierarchii rezerwacji (z wymiarem **numer partii** umieszczonym *pod* wymiarem **lokalizacji**) można zwolnić ładunek ze strony **Warsztat planowania wysyłki ładunku** dla ilości częściowej.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e3aa2-135">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="e3aa2-135">Issue resolution</span></span>

<span data-ttu-id="e3aa2-136">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-136">This behavior is by design.</span></span> <span data-ttu-id="e3aa2-137">Jeśli wymiar zostanie umieszczony powyżej wymiaru **Lokalizacji** w hierarchii rezerwacji, musi zostać on określony przed zwolnieniem do magazynu.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="e3aa2-138">Microsoft ocenił ten błąd i ustalił, że jest on ograniczeniem funkcji w trakcie zwalniania do magazynu z warsztatu planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="e3aa2-139">Ilości częściowe nie mogą zostać zwolnione, jeśli nie określono co najmniej jednego wymiaru powyżej **Lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="e3aa2-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="e3aa2-140">Aby uzyskać więcej informacji, zobacz [Elastyczne zasady rezerwacji wymiarów na poziomie magazynu](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="e3aa2-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>
