---
title: Rozwiązywanie problemów dotyczących kompilowania i przesyłania ładunku
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z tworzeniem ładunków i wysyłkami w Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 2933bcfd2cc526e39a4e1343cd472334a5b95607
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645339"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="c8943-103">Rozwiązywanie problemów dotyczących kompilowania i przesyłania ładunku</span><span class="sxs-lookup"><span data-stu-id="c8943-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8943-104">W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z tworzeniem ładunków i wysyłkami w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8943-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="c8943-105">Otrzymuję następujący komunikat o błędzie: „Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe...”</span><span class="sxs-lookup"><span data-stu-id="c8943-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8943-106">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8943-106">Issue description</span></span>

<span data-ttu-id="c8943-107">Podczas próby zwolnienia zwrotu zamówienia sprzedaży do magazynu jest wyświetlany następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="c8943-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="c8943-108">Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="c8943-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="c8943-109">Nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru lokalizacji w hierarchii rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="c8943-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="c8943-110">Usuń nieprawidłowe wymiary z wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c8943-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8943-111">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8943-111">Issue resolution</span></span>

<span data-ttu-id="c8943-112">Niestety, produkt nie obsługuje przetwarzania ładunku dla procesu zwrotu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c8943-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="c8943-113">Nie można więc zwolnić zwrotu zamówienia sprzedaży do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c8943-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="c8943-114">W transakcjach zamówienia sprzedaży nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru **Lokalizacji** w hierarchii rezerwacji.</span><span class="sxs-lookup"><span data-stu-id="c8943-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="c8943-115">Rozwiązanie polega na usunięciu nieprawidłowych wymiarów z wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="c8943-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="c8943-116">Pojawia się następujący komunikat o błędzie: „Jeden z wierszy jest już w ładunku.</span><span class="sxs-lookup"><span data-stu-id="c8943-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="c8943-117">Zwolnienie do magazynu jest niemożliwe".</span><span class="sxs-lookup"><span data-stu-id="c8943-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8943-118">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8943-118">Issue description</span></span>

<span data-ttu-id="c8943-119">W przypadku ręcznego tworzenia ładunków lub konfigurowania procesu w taki sposób, aby ładunki były już tworzone przed wprowadzeniem wiersza zamówienia sprzedaży, założeniem jest, że kolejna wersja zostanie wykonana ręcznie i zostanie użyta trasa i ocena z ładunku.</span><span class="sxs-lookup"><span data-stu-id="c8943-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="c8943-120">W innym możliwym scenariuszu podejmowana jest próba automatycznego wydania do magazynu, ale nie udało się utworzyć pracy w procesie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c8943-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="c8943-121">W związku z tym zostanie utworzona otwarta wysyłka lub ładunek.</span><span class="sxs-lookup"><span data-stu-id="c8943-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="c8943-122">Ta otwarta przesyłka lub ładunek blokuje następnie kolejne próby automatycznego zwolnienia zamówienia do czasu usunięcia otwartej przesyłki lub załadowania albo ręcznego ponownego przetworzenia grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c8943-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8943-123">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8943-123">Issue resolution</span></span>

<span data-ttu-id="c8943-124">Można zwolnić ze strony zamówienia sprzedaży lub automatyczne zwolnienie można wykonać ze strony zwolnienia zamówienia sprzedaży tylko wtedy, gdy przed wydaniem do magazynu nie ma żadnego ładunku.</span><span class="sxs-lookup"><span data-stu-id="c8943-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="c8943-125">Ładunek zostanie automatycznie utworzony po przetworzeniu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c8943-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="c8943-126">Pojawia się następujący komunikat o błędzie: „Nie można przetworzyć korekty dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="c8943-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="c8943-127">Dokument dostawy zawiera tylko pozycje, które podlegają procesom zarządzania magazynem, ponieważ nie są one obsługiwane przez korektę dokumentu dostawy".</span><span class="sxs-lookup"><span data-stu-id="c8943-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8943-128">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8943-128">Issue description</span></span>

<span data-ttu-id="c8943-129">Po zaksięgowaniu dokumentu dostawy nie można go anulować, ponieważ przycisk **Anuluj** jest niedostępny.</span><span class="sxs-lookup"><span data-stu-id="c8943-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="c8943-130">Nie można również poprawić dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="c8943-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="c8943-131">W przypadku próby pojawi się ten komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="c8943-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8943-132">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8943-132">Issue resolution</span></span>

<span data-ttu-id="c8943-133">Aby skorygować zaksięgowane dokumenty dostawy dla towarów, dla których włączono funkcję zaawansowanego zarządzania magazynem (WMS), należy wykonać księgowanie z ładunku, a nie bezpośrednio w zamówieniu.</span><span class="sxs-lookup"><span data-stu-id="c8943-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="c8943-134">Jak można utworzyć pracę z ładunków wychodzących zamiast grup czynności?</span><span class="sxs-lookup"><span data-stu-id="c8943-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8943-135">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8943-135">Issue description</span></span>

<span data-ttu-id="c8943-136">Oto jeden ze sposobów odtworzenia tego problemu.</span><span class="sxs-lookup"><span data-stu-id="c8943-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="c8943-137">Utwórz ładunek wychodzący, używając zamówienia sprzedaży lub zlecenia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="c8943-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="c8943-138">Zwalnianie ładunku do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c8943-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="c8943-139">Zauważ, że żadne prace pobrania nie zostały jeszcze wygenerowane.</span><span class="sxs-lookup"><span data-stu-id="c8943-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8943-140">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8943-140">Issue resolution</span></span>

<span data-ttu-id="c8943-141">Jeśli praca musi zostać wygenerowana natychmiast po zwolnieniu ładunku, należy odpowiednio skonfigurować szablon grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="c8943-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="c8943-142">W szablonie grupy czynności ustaw następujące opcje na *Tak*:</span><span class="sxs-lookup"><span data-stu-id="c8943-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="c8943-143">Automatyczne tworzenie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="c8943-143">Automate wave creation</span></span>
- <span data-ttu-id="c8943-144">Przetwarza grupę czynności w czasie uwalniania jej do magazynu</span><span class="sxs-lookup"><span data-stu-id="c8943-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="c8943-145">Automatyczne uwolnienie grupy czynności</span><span class="sxs-lookup"><span data-stu-id="c8943-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="c8943-146">Nie mogę ponownie zwolnić częściowo wysłanego ładunku.</span><span class="sxs-lookup"><span data-stu-id="c8943-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c8943-147">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="c8943-147">Issue description</span></span>

<span data-ttu-id="c8943-148">Nie można zwolnić częściowo wysłanego ładunku do magazynu.</span><span class="sxs-lookup"><span data-stu-id="c8943-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="c8943-149">Po wydaniu do magazynu pojawia się komunikat „Operacja zakończona”, ale nic się nie dzieje i nie jest tworzona praca dla pozostałej ilości.</span><span class="sxs-lookup"><span data-stu-id="c8943-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="c8943-150">Ten problem występuje, gdy używasz funkcji transportu ładunku i istnieje niekompletna rezerwacja.</span><span class="sxs-lookup"><span data-stu-id="c8943-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c8943-151">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="c8943-151">Issue resolution</span></span>

<span data-ttu-id="c8943-152">[KB problem 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („Częściowo wysłane ładunki można ponownie pogrupować w grupy czynności i ponownie przetworzyć”) został naprawiony w [wydaniu 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="c8943-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>
