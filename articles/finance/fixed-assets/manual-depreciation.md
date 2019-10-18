---
title: Amortyzacja ręczna
description: Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja ręczna.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84cde511ab0b5cbe4b99e72832bf548336b6b28c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187229"
---
# <a name="manual-depreciation"></a><span data-ttu-id="68364-103">Amortyzacja ręczna</span><span class="sxs-lookup"><span data-stu-id="68364-103">Manual depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68364-104">Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja ręczna.</span><span class="sxs-lookup"><span data-stu-id="68364-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="68364-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu opcji **Ręczna** w polu **Metoda** na stronie **Profile amortyzacji**, amortyzacja środków trwałych przypisanych do tego profilu amortyzacji jest określana przez wartości procentowe wprowadzone dla poszczególnych interwałów w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="68364-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="68364-106">Interwały, dla których zostały ustawione wartości procentowe, są księgowane na podstawie wartości wybranej w polu **Częstotliwość okresu** na skróconej karcie **Ogólne** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="68364-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="68364-107">Można wybrać następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="68364-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="68364-108">Co rok</span><span class="sxs-lookup"><span data-stu-id="68364-108">Yearly</span></span>
-   <span data-ttu-id="68364-109">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="68364-109">Monthly</span></span>
-   <span data-ttu-id="68364-110">Kwartalna</span><span class="sxs-lookup"><span data-stu-id="68364-110">Quarterly</span></span>
-   <span data-ttu-id="68364-111">Półrocznie</span><span class="sxs-lookup"><span data-stu-id="68364-111">Half-Yearly</span></span>
-   <span data-ttu-id="68364-112">Dziennie</span><span class="sxs-lookup"><span data-stu-id="68364-112">Daily</span></span>

<span data-ttu-id="68364-113">Po wybraniu częstotliwości okresu kliknij opcję **Planowanie ręczne** i ustaw wartości procentowe dla poszczególnych interwałów księgowania.</span><span class="sxs-lookup"><span data-stu-id="68364-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="68364-114">Harmonogramy ręczne i interwały księgowania razem określają kwotę amortyzacji, co pokazano w poniższych przykładach w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="68364-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="68364-115">Amortyzacja ręczna jest zawsze obliczana jako wartość procentowa ceny nabycia.</span><span class="sxs-lookup"><span data-stu-id="68364-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="68364-116">W przypadku amortyzacji ręcznej suma wartości procentowych wprowadzonych w interwałach amortyzacji nie musi wynosić 100%.</span><span class="sxs-lookup"><span data-stu-id="68364-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="68364-117">Amortyzacja ręczna jest to elastyczna metoda amortyzacji, która jest zwykle używana do definiowania dodatkowego profilu amortyzacji na stronie **Księga**, jak np. amortyzacji nieokresowej dla celów specjalnych (np. podatkowych).</span><span class="sxs-lookup"><span data-stu-id="68364-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="68364-118">Przykłady</span><span class="sxs-lookup"><span data-stu-id="68364-118">Examples</span></span>
<span data-ttu-id="68364-119">Cena nabycia: 11,000.00 oczekiwana wartość likwidacji: 1,000.00. W poniższej tabeli przedstawiono interwały i wartości procentowe określane na stronie **Plany amortyzacji środków trwałych dla profilów**.</span><span class="sxs-lookup"><span data-stu-id="68364-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="68364-120">Numer zakresu</span><span class="sxs-lookup"><span data-stu-id="68364-120">Interval number</span></span> | <span data-ttu-id="68364-121">Wartość procentowa</span><span class="sxs-lookup"><span data-stu-id="68364-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="68364-122">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="68364-122">1</span></span>               | <span data-ttu-id="68364-123">10,00</span><span class="sxs-lookup"><span data-stu-id="68364-123">10.00</span></span>      |
| <span data-ttu-id="68364-124">2</span><span class="sxs-lookup"><span data-stu-id="68364-124">2</span></span>               | <span data-ttu-id="68364-125">50,00</span><span class="sxs-lookup"><span data-stu-id="68364-125">50.00</span></span>      |
| <span data-ttu-id="68364-126">3</span><span class="sxs-lookup"><span data-stu-id="68364-126">3</span></span>               | <span data-ttu-id="68364-127">8.00</span><span class="sxs-lookup"><span data-stu-id="68364-127">8.00</span></span>       |

<span data-ttu-id="68364-128">W poniższej tabeli pokazano sposób obliczania amortyzacji dla każdego interwału.</span><span class="sxs-lookup"><span data-stu-id="68364-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="68364-129">Numer zakresu</span><span class="sxs-lookup"><span data-stu-id="68364-129">Interval number</span></span> | <span data-ttu-id="68364-130">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="68364-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="68364-131">Wartość księgowa netto na koniec interwału</span><span class="sxs-lookup"><span data-stu-id="68364-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="68364-132">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="68364-132">1</span></span>                | <span data-ttu-id="68364-133">(11,000 – 1,000) × 10% = 1,000</span><span class="sxs-lookup"><span data-stu-id="68364-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="68364-134">10,000 (11,000 – 1,000)</span><span class="sxs-lookup"><span data-stu-id="68364-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="68364-135">2</span><span class="sxs-lookup"><span data-stu-id="68364-135">2</span></span>                | <span data-ttu-id="68364-136">(11,000 – 1,000) × 50% = 5,000</span><span class="sxs-lookup"><span data-stu-id="68364-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="68364-137">5,000 (10,000 – 5,000)</span><span class="sxs-lookup"><span data-stu-id="68364-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="68364-138">3</span><span class="sxs-lookup"><span data-stu-id="68364-138">3</span></span>                | <span data-ttu-id="68364-139">(11,000 – 1,000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="68364-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="68364-140">4,200 (5,000 – 800)</span><span class="sxs-lookup"><span data-stu-id="68364-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="68364-141">Jeśli w polu **Częstotliwość okresu** wybierzesz opcję **Miesięcznie**, ustawisz 12 interwałów harmonogramu ręcznego.</span><span class="sxs-lookup"><span data-stu-id="68364-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="68364-142">W poniższej tabeli przedstawiono kwoty amortyzacji dla pierwszych dwóch interwałów.</span><span class="sxs-lookup"><span data-stu-id="68364-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="68364-143">Interwał</span><span class="sxs-lookup"><span data-stu-id="68364-143">Interval</span></span> | <span data-ttu-id="68364-144">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="68364-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="68364-145">Styczeń</span><span class="sxs-lookup"><span data-stu-id="68364-145">January</span></span>  | <span data-ttu-id="68364-146">(11,000 – 1,000) × 10% = 1,000</span><span class="sxs-lookup"><span data-stu-id="68364-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="68364-147">Luty</span><span class="sxs-lookup"><span data-stu-id="68364-147">February</span></span> | <span data-ttu-id="68364-148">(11,000 – 1,000) × 50% = 5,000</span><span class="sxs-lookup"><span data-stu-id="68364-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="68364-149">Jeśli w polu *<strong><em>Częstotliwość okresu</em>*</strong> wybierzesz opcję <strong>Półrocznie</strong>, ustawisz 2 interwały harmonogramu ręcznego.</span><span class="sxs-lookup"><span data-stu-id="68364-149">If you select <strong>Half-Yearly</strong> in the *<strong><em>Period frequency</em>* field</strong>, you set up two manual schedule intervals.</span></span> <span data-ttu-id="68364-150">W poniższej tabeli przedstawiono kwoty amortyzacji dla tych dwóch interwałów.</span><span class="sxs-lookup"><span data-stu-id="68364-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="68364-151">Interwał</span><span class="sxs-lookup"><span data-stu-id="68364-151">Interval</span></span>    | <span data-ttu-id="68364-152">Kwota amortyzacji</span><span class="sxs-lookup"><span data-stu-id="68364-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="68364-153">30 czerwca</span><span class="sxs-lookup"><span data-stu-id="68364-153">June 30</span></span>     | <span data-ttu-id="68364-154">(11,000 – 1,000) × 10% = 1,000</span><span class="sxs-lookup"><span data-stu-id="68364-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="68364-155">31 grudnia</span><span class="sxs-lookup"><span data-stu-id="68364-155">December 31</span></span> | <span data-ttu-id="68364-156">(11,000 – 1,000) × 50% = 5,000</span><span class="sxs-lookup"><span data-stu-id="68364-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="68364-157">Suma wartości procentowych dla wszystkich interwałów nie musi być równa 100.</span><span class="sxs-lookup"><span data-stu-id="68364-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="68364-158">Jednakże wyświetlany jest komunikat, jeśli wartość w polu **Suma wartości procentowych** na stronie **Plany amortyzacji środków trwałych dla profilów** nie jest równa **100**.</span><span class="sxs-lookup"><span data-stu-id="68364-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>



