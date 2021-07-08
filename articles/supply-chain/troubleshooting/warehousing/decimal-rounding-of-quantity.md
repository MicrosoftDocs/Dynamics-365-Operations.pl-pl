---
title: Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie jest niepoprawne
description: Podczas generowania dokumentu dostawy ładunek wychodzący zawiera ilość, która nie odpowiada precyzji dziesiętnej zdefiniowanej w jednostce.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248799"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="e4690-103">Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie jest niepoprawne</span><span class="sxs-lookup"><span data-stu-id="e4690-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="e4690-104">Kod błędu: SYS19589</span><span class="sxs-lookup"><span data-stu-id="e4690-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="e4690-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="e4690-105">Symptoms</span></span>

<span data-ttu-id="e4690-106">Podczas generowania dokumentu dostawy ładunek wychodzący zawiera ilość, która nie odpowiada precyzji dziesiętnej zdefiniowanej w jednostce.</span><span class="sxs-lookup"><span data-stu-id="e4690-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="e4690-107">Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="e4690-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="e4690-108">Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie w jednostce %1 jest niepoprawne.</span><span class="sxs-lookup"><span data-stu-id="e4690-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="e4690-109">Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.</span><span class="sxs-lookup"><span data-stu-id="e4690-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e4690-110">Powód</span><span class="sxs-lookup"><span data-stu-id="e4690-110">Cause</span></span>

<span data-ttu-id="e4690-111">System ocenia, czy zaokrąglenie dziesiętne ilości wysyłkowej odpowiada precyzji dziesiętnej, która została zdefiniowana dla jednostki wysyłkowej.</span><span class="sxs-lookup"><span data-stu-id="e4690-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="e4690-112">Gdy system zaokrągla ilość wysyłkową do określonej liczby miejsc po przecinku, jeśli stwierdzi, że zaokrąglona ilość wysyłkowa nie odpowiada rzeczywistej ilości wysyłkowej, nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e4690-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="e4690-113">Na przykład ten problem może wystąpić, jeśli ilość sprzedaży wynosi 1,75 kilograma (kg), ale dokładność dziesiętna jest ustawiona na *1*.</span><span class="sxs-lookup"><span data-stu-id="e4690-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4690-114">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="e4690-114">Resolution</span></span>

<span data-ttu-id="e4690-115">Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="e4690-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="e4690-116">Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="e4690-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e4690-117">Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.</span><span class="sxs-lookup"><span data-stu-id="e4690-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="e4690-118">Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki.</span><span class="sxs-lookup"><span data-stu-id="e4690-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="e4690-119">Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem</span><span class="sxs-lookup"><span data-stu-id="e4690-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="e4690-120">Skorzystaj z poniższej procedury, aby przejrzeć linie ładunkowe i wprowadzić poprawki w celu zapewnienia, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.</span><span class="sxs-lookup"><span data-stu-id="e4690-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="e4690-121">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e4690-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e4690-122">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e4690-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e4690-123">Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.</span><span class="sxs-lookup"><span data-stu-id="e4690-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="e4690-124">Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.</span><span class="sxs-lookup"><span data-stu-id="e4690-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="e4690-125">Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.</span><span class="sxs-lookup"><span data-stu-id="e4690-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="e4690-126">Na karcie  **Szczegóły wiersza** wybierz **Zamówienie**.</span><span class="sxs-lookup"><span data-stu-id="e4690-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="e4690-127">Ustaw pole **Ilość** na ilość pobraną (czyli wartość pola **Ilość utworzona**), aby można było rozpocząć generowanie kartonu.</span><span class="sxs-lookup"><span data-stu-id="e4690-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="e4690-128">Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki</span><span class="sxs-lookup"><span data-stu-id="e4690-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="e4690-129">Korzystając z poniższej procedury, należy przejrzeć linie ładunkowe i dokonać korekty, aby upewnić się, że jednostka i ilość są wyrównane z dokładnością dziesiętną jednostki.</span><span class="sxs-lookup"><span data-stu-id="e4690-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="e4690-130">Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e4690-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e4690-131">Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e4690-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e4690-132">Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.</span><span class="sxs-lookup"><span data-stu-id="e4690-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="e4690-133">Zanotuj wartość pola **Ilość** i **Jednostka**.</span><span class="sxs-lookup"><span data-stu-id="e4690-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="e4690-134">Wybierz kolejno opcje **Administrowanie organizacją \> Jednostki \> Jednostki**.</span><span class="sxs-lookup"><span data-stu-id="e4690-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="e4690-135">Wybierz jednostkę, dla których nie można wygenerować dokumentu dostawy.</span><span class="sxs-lookup"><span data-stu-id="e4690-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e4690-136">W razie potrzeby dostosuj wartość pola **Dokładność dziesiętna**.</span><span class="sxs-lookup"><span data-stu-id="e4690-136">Adjust the value of the **Decimal precision** field as required.</span></span>
