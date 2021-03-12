---
title: Rozwiązywanie problemów dotyczących pobierania i pakowania
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pobierania i pakowania w Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2cce1038ed393fc8a7bb489a37fc0921b0ac755e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993943"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="85bc8-103">Rozwiązywanie problemów dotyczących pobierania i pakowania</span><span class="sxs-lookup"><span data-stu-id="85bc8-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85bc8-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pobierania i pakowania w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="85bc8-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="85bc8-105">Otrzymuję następujący komunikat o błędzie: „Nie można pozostawić pustej lokalizacji wymiaru, jeśli ustawiono numer seryjny wymiaru”.</span><span class="sxs-lookup"><span data-stu-id="85bc8-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-106">Issue description</span></span>

<span data-ttu-id="85bc8-107">Ten komunikat o błędzie pojawia się, jeśli utworzysz zlecenie przeniesienia dla pozycji seryjnej przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę.</span><span class="sxs-lookup"><span data-stu-id="85bc8-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-108">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-108">Issue resolution</span></span>

<span data-ttu-id="85bc8-109">Pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”.</span><span class="sxs-lookup"><span data-stu-id="85bc8-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="85bc8-110">Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym.</span><span class="sxs-lookup"><span data-stu-id="85bc8-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="85bc8-111">Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="85bc8-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="85bc8-112">Zgłaszany jest następujący komunikat o błędzie: „Nieprawidłowy numer identyfikacyjny".</span><span class="sxs-lookup"><span data-stu-id="85bc8-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-113">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-113">Issue description</span></span>

<span data-ttu-id="85bc8-114">Ten komunikat o błędzie pojawia się w aplikacji magazynowania podczas skanowania identyfikatora numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="85bc8-114">You receive this error message in the warehouse app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-115">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-115">Issue resolution</span></span>

<span data-ttu-id="85bc8-116">Upewnij się, że identyfikator numeru identyfikacyjnego znajduje się w tabeli numerów identyfikacyjnych, a pozycje i ilości w numerze identyfikacyjnym są dostępne (innymi słowy, nie są zablokowane).</span><span class="sxs-lookup"><span data-stu-id="85bc8-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="85bc8-117">Otrzymuję następujący komunikat o błędzie: „Pole 'Waga ładunku' (=-%1) może zawierać tylko liczby dodatnie.</span><span class="sxs-lookup"><span data-stu-id="85bc8-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="85bc8-118">Aktualizacja została anulowana".</span><span class="sxs-lookup"><span data-stu-id="85bc8-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-119">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-119">Issue description</span></span>

<span data-ttu-id="85bc8-120">Ten komunikat o błędzie jest wyświetlany, jeśli podczas przetwarzania pracy z lokalizacji pakowania do lokalizacji przemieszczania lub z lokalizacji przemieszczania do lokalizacji dokowania jest otwarta praca.</span><span class="sxs-lookup"><span data-stu-id="85bc8-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-121">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-121">Issue resolution</span></span>

<span data-ttu-id="85bc8-122">Aby rozwiązać ten problem, przejdź do **Administrowanie systemem \> Zadania okresowe \> Baza danych \> Sprawdzanie spójności** i uruchom proces **Sprawdzenie spójności wagi ładunku magazynu**.</span><span class="sxs-lookup"><span data-stu-id="85bc8-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="85bc8-123">Otrzymuję następujący komunikat o błędzie: „Ilość jest nieprawidłowa dla jednostki %1”.</span><span class="sxs-lookup"><span data-stu-id="85bc8-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-124">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-124">Issue description</span></span>

<span data-ttu-id="85bc8-125">Ten komunikat o błędzie jest wyświetlany podczas próby przeprowadzenia *dzielenie pobierania* na wielu partiach.</span><span class="sxs-lookup"><span data-stu-id="85bc8-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-126">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-126">Issue resolution</span></span>

<span data-ttu-id="85bc8-127">Pracownik magazynu musi skorzystać z procesu *Pobieranie w niedomiarze* w aplikacji magazynu.</span><span class="sxs-lookup"><span data-stu-id="85bc8-127">The warehouse worker must use the *Short picking* process in the warehouse app.</span></span> <span data-ttu-id="85bc8-128">Jeśli próbujesz pobrać wiele partii z tej samej lokalizacji, możesz również skorzystać z opcji **Pełny** w aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="85bc8-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the warehouse app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="85bc8-129">Nie można przenieść zapasów do lokalizacji, kontrolowanej za pomocą numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="85bc8-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-130">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-130">Issue description</span></span>

<span data-ttu-id="85bc8-131">Nie można zredukować ilości pobranych w ładunku.</span><span class="sxs-lookup"><span data-stu-id="85bc8-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-132">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-132">Issue resolution</span></span>

<span data-ttu-id="85bc8-133">We wcześniejszych wersjach nie można zredukować ilości pobranych w ładunku.</span><span class="sxs-lookup"><span data-stu-id="85bc8-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="85bc8-134">Można jednak teraz cofnąć wybór lokalizacji kontrolowanej przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="85bc8-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="85bc8-135">Należy określić wartość **Lokalizacja** i wartość **Numer identyfikacyjny** dla wiersza ładunku na stronie **Zmniejsz ilość pobraną**.</span><span class="sxs-lookup"><span data-stu-id="85bc8-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="85bc8-136">Czy można wydrukować dokumentdostawy lub zawartość opakowania według magazynu?</span><span class="sxs-lookup"><span data-stu-id="85bc8-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-137">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-137">Issue description</span></span>

<span data-ttu-id="85bc8-138">Chcesz wydrukować dokument dostawy lub zawartość opakowania według magazynu lub oddziału na stronie **Aktualizacja wiersza szablonu audytu pracy**.</span><span class="sxs-lookup"><span data-stu-id="85bc8-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-139">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-139">Issue resolution</span></span>

<span data-ttu-id="85bc8-140">Podczas drukowania dokumentu przy użyciu ustawień zarządzania drukowaniem należy ograniczyć zakres (oddział/magazyn), korzystając z funkcji zarządzania drukowaniem, a nie wybierając opcję **Edytuj ustawienia drukowania** na stronie **Aktualizacja wiersza szablonu audytu pracy**.</span><span class="sxs-lookup"><span data-stu-id="85bc8-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="85bc8-141">Nie mogę anulować dokumentu dostawy po zaksięgowaniu go z zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="85bc8-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-142">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-142">Issue description</span></span>

<span data-ttu-id="85bc8-143">Po włączeniu procesu pobierania i wysyłania dla modułu WMS nie można anulować dokumentu dostawy po jego zaksięgowaniu z zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="85bc8-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-144">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-144">Issue resolution</span></span>

<span data-ttu-id="85bc8-145">Aby poprawić zaksięgowane dokumenty dostawy dla towarów, dla których włączono WMS, księgowanie musi nastąpić z ładunku, a nie z zamówienia.</span><span class="sxs-lookup"><span data-stu-id="85bc8-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="85bc8-146">Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji.</span><span class="sxs-lookup"><span data-stu-id="85bc8-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="85bc8-147">Ogólnie rzecz biorąc, zamówienie sprzedaży, które zostało pobrane i wysłane w ramach procesów zarządzania magazynem, może być dokumentem dostawy - aktualizowanym na podstawie ładunku lub wysyłki oraz samego dokumentu zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="85bc8-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="85bc8-148">Jednak w przypadku dokumentu dostawy zaktualizowanie zamówienia sprzedaży z dokumentu zamówienie sprzedaży, wycofanie dokumentu dostawy nadal nie może zostać wykonane z poziomu załadunku lub zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="85bc8-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="85bc8-149">Dlatego zalecamy użycie księgowania dokumentu dostawy z ładunku.</span><span class="sxs-lookup"><span data-stu-id="85bc8-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="85bc8-150">W takim przypadku wycofanie, które musi zostać wykonane z ładunku, będzie włączone.</span><span class="sxs-lookup"><span data-stu-id="85bc8-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="85bc8-151">Wyświetlany jest następujący komunikat o błędzie: „Dla grupy nie można znaleźć wystarczającej ilości pracy”.</span><span class="sxs-lookup"><span data-stu-id="85bc8-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85bc8-152">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="85bc8-152">Issue description</span></span>

<span data-ttu-id="85bc8-153">Używając procesu *Pobieranie dla grupy sterowane przez system*, jeśli skonfigurujesz profil grupy, w którym można odebrać na przykład 10 stanowisk, proces działa zgodnie według planu, kiedy jest wystarczająco pracy dla 10 stanowisk odbioru.</span><span class="sxs-lookup"><span data-stu-id="85bc8-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="85bc8-154">Jeśli jednak istnieje tylko osiem stanowisk do pobrania, ten komunikat o błędzie jest wyświetlany, ponieważ nie ma wystarczającej ilości pracy dla jednej grupy.</span><span class="sxs-lookup"><span data-stu-id="85bc8-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85bc8-155">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="85bc8-155">Issue resolution</span></span>

<span data-ttu-id="85bc8-156">Aby rozwiązać ten problem, edytuj profil grupy i w opcji **Aktywuj stanowiska** określ wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="85bc8-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>
