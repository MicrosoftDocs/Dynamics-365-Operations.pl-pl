---
title: Planowanie z użyciem ujemnych ilości dostępnych zapasów
description: W tym temacie wyjaśniono sposób obsługi ujemnych wartości dostępnych zapasów podczas korzystania z optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 72367927a11879adffe68d7242d88f5cfab73e22
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323515"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="3b0a3-103">Planowanie z użyciem ujemnych ilości dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="3b0a3-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b0a3-104">Jeśli w systemie jest wyświetlana ujemna zagregowana ilość zapasów, aparat planowania traktuje ilość jako 0 (zero), aby uniknąć nadmiernej podaży.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="3b0a3-105">Oto, jak działa ta funkcja:</span><span class="sxs-lookup"><span data-stu-id="3b0a3-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="3b0a3-106">Funkcja optymalizacji planowania agreguje ilości dostępnych zapasów na najniższym poziomie wymiarów zapotrzebowania.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="3b0a3-107">(Jeśli na przykład *lokalizacja* nie jest wymiarem zapotrzebowania, funkcja optymalizacji planowania umożliwia agregowanie dostępnych ilości na poziomie *magazynu*.)</span><span class="sxs-lookup"><span data-stu-id="3b0a3-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="3b0a3-108">Jeśli zagregowana ilość dostępna na najniższym poziomie wymiarów zapotrzebowania jest ujemna, system zakłada, że ilość dostępnych zapasów wynosi w rzeczywistości 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3b0a3-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b0a3-109">System planowania może być tylko tak dokładny, jak dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="3b0a3-110">Jeśli dane wejściowe są niedokładne, ujemne rekordy dostępnych zapasów będą wskazywały, że informacje o zapasach w Microsoft Dynamics 365 Supply Chain Management nie są zsynchronizowane z rzeczywistym stanem.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="3b0a3-111">Z tego powodu wynik planowania będzie wadliwy.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="3b0a3-112">Aby uzyskać dokładny wynik planowania, należy zminimalizować liczbę rekordów pokazującą ujemną ilość dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="3b0a3-113">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="3b0a3-113">Example 1</span></span>

<span data-ttu-id="3b0a3-114">Magazyn 13 jest konfigurowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="3b0a3-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="3b0a3-115">**Kod objęcia świadczeniem:** Minimum/Maksimum.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="3b0a3-116">**Minimum:** 15 sztuk (szt.)</span><span class="sxs-lookup"><span data-stu-id="3b0a3-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="3b0a3-117">**Maksymalnie:** 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="3b0a3-118">Najniższy poziom wymiarów zapotrzebowania to *magazyn*, a następujące ilości dostępnych zapasów są rejestrowane na poziomie *lokalizacji*:</span><span class="sxs-lookup"><span data-stu-id="3b0a3-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="3b0a3-119">**Oddział 1, magazyn 13, Lokalizacja 1:** 20 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="3b0a3-120">**Oddział 1, magazyn 13, Lokalizacja 2:** &minus;8 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="3b0a3-121">Z tego względu zagregowana ilość dostępnych zapasów dla magazynu 13 wynosi 12 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="3b0a3-122">(= 20 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-122">(= 20 pcs.</span></span> <span data-ttu-id="3b0a3-123">&minus; 8 szt.).</span><span class="sxs-lookup"><span data-stu-id="3b0a3-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="3b0a3-124">W takim przypadku aparat planowania korzysta z zagregowanej ilości 12 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="3b0a3-125">dla magazynu 13.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-125">for warehouse 13.</span></span>

<span data-ttu-id="3b0a3-126">Wynik jest planowanym zamówieniem o ilości 13 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="3b0a3-127">(= 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-127">(= 25 pcs.</span></span> <span data-ttu-id="3b0a3-128">&minus; 12 szt.) w celu ponownego wypełnienia magazynu 13 od 12 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="3b0a3-129">do 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="3b0a3-130">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="3b0a3-130">Example 2</span></span>

<span data-ttu-id="3b0a3-131">Magazyn 13 jest konfigurowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="3b0a3-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="3b0a3-132">**Kod objęcia świadczeniem:** Minimum/Maksimum.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="3b0a3-133">**Minimum:** 15 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="3b0a3-134">**Maksymalnie:** 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="3b0a3-135">Najniższy poziom wymiarów zapotrzebowania to *magazyn*, a następujące ilości dostępnych zapasów są rejestrowane na poziomie *lokalizacji*:</span><span class="sxs-lookup"><span data-stu-id="3b0a3-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="3b0a3-136">**Oddział 1, magazyn 13, Lokalizacja 1:** 4 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="3b0a3-137">**Oddział 1, magazyn 13, Lokalizacja 2:** &minus;8 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="3b0a3-138">Z tego względu zagregowana ilość dostępnych zapasów dla magazynu 13 to &minus;4 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="3b0a3-139">(= 4 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-139">(= 4 pcs.</span></span> <span data-ttu-id="3b0a3-140">&minus; 8 szt.).</span><span class="sxs-lookup"><span data-stu-id="3b0a3-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="3b0a3-141">Innymi słowy, jest mniej niż 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3b0a3-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="3b0a3-142">W takim przypadku aparat planowania zakłada, że ilość dostępnych zapasów dla magazynu 13 wynosi 0 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="3b0a3-143">zamiast &minus;4 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="3b0a3-144">Wynik jest planowanym zamówieniem o ilości 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="3b0a3-145">(= 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-145">(= 25 pcs.</span></span> <span data-ttu-id="3b0a3-146">&minus; 0 szt.) w celu ponownego wypełnienia magazynu 13 od 0 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="3b0a3-147">do 25 szt.</span><span class="sxs-lookup"><span data-stu-id="3b0a3-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3b0a3-148">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="3b0a3-148">Related resources</span></span>

[<span data-ttu-id="3b0a3-149">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="3b0a3-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="3b0a3-150">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="3b0a3-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="3b0a3-151">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="3b0a3-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="3b0a3-152">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="3b0a3-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="3b0a3-153">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="3b0a3-153">Cancel a planning job</span></span>](cancel-planning-job.md)
