---
title: 175% amortyzacja degresywna
description: "Ten artykuł zawiera omówienie metody amortyzacji 175% amortyzacja degresywna."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 318e111f784157666c2853bcd6d5b3af2c9ffdc5
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="bb7cb-103">175% amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="bb7cb-103">175 percent reducing balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bb7cb-104">Ten artykuł zawiera omówienie metody amortyzacji 175% amortyzacja degresywna.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-104">This article gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="bb7cb-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 175%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="bb7cb-106">Aby skonfigurować amortyzację degresywną 175%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="bb7cb-107">Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="bb7cb-108">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bb7cb-108">Select a depreciation year</span></span>
<span data-ttu-id="bb7cb-109">Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="bb7cb-110">Domyślna wartość to **Kalendarzowy**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="bb7cb-111">Wybór określa opcje dostępne w polu **Częstotliwość okresu**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="bb7cb-112">W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="bb7cb-113">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="bb7cb-113">Calendar</span></span>

<span data-ttu-id="bb7cb-114">W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** .</span><span class="sxs-lookup"><span data-stu-id="bb7cb-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="bb7cb-115">Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="bb7cb-116">Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="bb7cb-117">W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="bb7cb-118">W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:</span><span class="sxs-lookup"><span data-stu-id="bb7cb-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="bb7cb-119">**Roczne** — księgowanie kwoty 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="bb7cb-120">**Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="bb7cb-121">**Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="bb7cb-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="bb7cb-122">**Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="bb7cb-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="bb7cb-123">**Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="bb7cb-124">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="bb7cb-124">Fiscal</span></span>

<span data-ttu-id="bb7cb-125">W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 175% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="bb7cb-126">Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="bb7cb-127">Aby uzyskać więcej informacji, zobacz [Kalendarze, lata i okresy obrachunkowe](..\budgeting\fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="bb7cb-127">For more information, see [Fiscal calendars, fiscal years, and periods.](..\budgeting\fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="bb7cb-128">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="bb7cb-129">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="bb7cb-130">Amortyzacja jest automatycznie korygowana dla każdego okresu obrachunkowego, a długość kolejnego roku obrachunkowego jest określona przez okresy obrachunkowe zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="bb7cb-131">W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="bb7cb-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="bb7cb-132">**Rocznie** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="bb7cb-133">**Okres obrachunkowy** oblicza łączną kwotę amortyzacji w roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="bb7cb-134">Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="bb7cb-135">Przykład amortyzacji degresywnej 175%</span><span class="sxs-lookup"><span data-stu-id="bb7cb-135">Example of 175% reducing balance depreciation</span></span>
|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="bb7cb-136">Koszt nabycia</span><span class="sxs-lookup"><span data-stu-id="bb7cb-136">Acquisition cost</span></span>               | <span data-ttu-id="bb7cb-137">11 000</span><span class="sxs-lookup"><span data-stu-id="bb7cb-137">11,000</span></span> |
| <span data-ttu-id="bb7cb-138">Wartość odzyskana</span><span class="sxs-lookup"><span data-stu-id="bb7cb-138">Salvage value</span></span>                  | <span data-ttu-id="bb7cb-139">1 000</span><span class="sxs-lookup"><span data-stu-id="bb7cb-139">1,000</span></span>  |
| <span data-ttu-id="bb7cb-140">Podstawa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bb7cb-140">Depreciation base</span></span>              | <span data-ttu-id="bb7cb-141">10000</span><span class="sxs-lookup"><span data-stu-id="bb7cb-141">10,000</span></span> |
| <span data-ttu-id="bb7cb-142">Okres użytkowania (lata)</span><span class="sxs-lookup"><span data-stu-id="bb7cb-142">Service life years</span></span>             | <span data-ttu-id="bb7cb-143">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="bb7cb-143">5</span></span>      |
| <span data-ttu-id="bb7cb-144">Roczna wartość procentowa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bb7cb-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="bb7cb-145">35%</span><span class="sxs-lookup"><span data-stu-id="bb7cb-145">35%</span></span>    |

<span data-ttu-id="bb7cb-146">Metoda amortyzacji degresywnej 175% dzieli wartość 175% między lata okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="bb7cb-147">Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="bb7cb-148">Okres</span><span class="sxs-lookup"><span data-stu-id="bb7cb-148">Period</span></span> | <span data-ttu-id="bb7cb-149">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="bb7cb-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="bb7cb-150">Wartość księgowa</span><span class="sxs-lookup"><span data-stu-id="bb7cb-150">Book value</span></span>                  | <span data-ttu-id="bb7cb-151">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="bb7cb-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="bb7cb-152">Rok 1</span><span class="sxs-lookup"><span data-stu-id="bb7cb-152">Year 1</span></span> | <span data-ttu-id="bb7cb-153">(11,000 – 1,000) × 35% = 3,500</span><span class="sxs-lookup"><span data-stu-id="bb7cb-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="bb7cb-154">11,000 – 3,500 = 7,500</span><span class="sxs-lookup"><span data-stu-id="bb7cb-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="bb7cb-155">11,000 – 1,000 – 3,500 = 6,500</span><span class="sxs-lookup"><span data-stu-id="bb7cb-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="bb7cb-156">Rok 2</span><span class="sxs-lookup"><span data-stu-id="bb7cb-156">Year 2</span></span> | <span data-ttu-id="bb7cb-157">6,500 × 35% = 2,275</span><span class="sxs-lookup"><span data-stu-id="bb7cb-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="bb7cb-158">7,500 – 2,275 = 5,225</span><span class="sxs-lookup"><span data-stu-id="bb7cb-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="bb7cb-159">6,500 – 2,275 = 4,225</span><span class="sxs-lookup"><span data-stu-id="bb7cb-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="bb7cb-160">Rok 3</span><span class="sxs-lookup"><span data-stu-id="bb7cb-160">Year 3</span></span> | <span data-ttu-id="bb7cb-161">4,225 × 35% = 1,478.75</span><span class="sxs-lookup"><span data-stu-id="bb7cb-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="bb7cb-162">5,225 – 1,478.75 = 3,746.25</span><span class="sxs-lookup"><span data-stu-id="bb7cb-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="bb7cb-163">4,225 – 1,478.75 = 2,746.25</span><span class="sxs-lookup"><span data-stu-id="bb7cb-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="bb7cb-164">Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 175%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="bb7cb-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




