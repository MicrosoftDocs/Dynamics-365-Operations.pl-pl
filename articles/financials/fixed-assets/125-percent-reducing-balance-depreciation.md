---
title: 125% amortyzacja degresywna
description: "Ten artykuł zawiera omówienie metody amortyzacji 125% amortyzacja degresywna."
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
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 680396bd251cda603dbcd244664fa3421d12e85a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="72a4a-103">125% amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="72a4a-103">125 percent reducing balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="72a4a-104">Ten artykuł zawiera omówienie metody amortyzacji 125% amortyzacja degresywna.</span><span class="sxs-lookup"><span data-stu-id="72a4a-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="72a4a-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 125%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="72a4a-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="72a4a-106">Wartość procentowa jest obliczana na podstawie okresu użytkowania środków.</span><span class="sxs-lookup"><span data-stu-id="72a4a-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="72a4a-107">Na przykład, jeżeli okres użytkowania środków wynosi pięć lat, wartość procentowa zostanie obliczona jako 25% (125%/5).</span><span class="sxs-lookup"><span data-stu-id="72a4a-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="72a4a-108">Aby skonfigurować amortyzację degresywną 125%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="72a4a-109">Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="72a4a-110">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="72a4a-110">Select a depreciation year</span></span>
<span data-ttu-id="72a4a-111">Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="72a4a-112">Domyślna wartość to **Kalendarzowy**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="72a4a-113">Wybór określa opcje dostępne w polu **Częstotliwość okresu**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="72a4a-114">W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="72a4a-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="72a4a-115">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="72a4a-115">Calendar</span></span>

<span data-ttu-id="72a4a-116">W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** .</span><span class="sxs-lookup"><span data-stu-id="72a4a-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="72a4a-117">Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="72a4a-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="72a4a-118">Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji.</span><span class="sxs-lookup"><span data-stu-id="72a4a-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="72a4a-119">W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="72a4a-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="72a4a-120">W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:</span><span class="sxs-lookup"><span data-stu-id="72a4a-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="72a4a-121">**Roczne** — księgowanie kwoty 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="72a4a-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="72a4a-122">**Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="72a4a-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="72a4a-123">**Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="72a4a-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="72a4a-124">**Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="72a4a-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="72a4a-125">**Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="72a4a-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="72a4a-126">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="72a4a-126">Fiscal</span></span>

<span data-ttu-id="72a4a-127">W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 125% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="72a4a-128">Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="72a4a-129">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="72a4a-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="72a4a-130">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="72a4a-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="72a4a-131">Amortyzacja jest automatycznie korygowana dla każdego okresu obrachunkowego, a długość kolejnego roku obrachunkowego jest określona przez okresy obrachunkowe zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="72a4a-132">W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="72a4a-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="72a4a-133">**Roczne** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="72a4a-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="72a4a-134">**Okres obrachunkowy** księguje łączną kwotę amortyzacji w roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="72a4a-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="72a4a-135">Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="72a4a-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="72a4a-136">Przykład 125% amortyzacji degresywnej</span><span class="sxs-lookup"><span data-stu-id="72a4a-136">Example of 125% reducing balance depreciation</span></span>
|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="72a4a-137">Koszt nabycia</span><span class="sxs-lookup"><span data-stu-id="72a4a-137">Acquisition cost</span></span>               | <span data-ttu-id="72a4a-138">11 000</span><span class="sxs-lookup"><span data-stu-id="72a4a-138">11,000</span></span> |
| <span data-ttu-id="72a4a-139">Wartość odzyskana</span><span class="sxs-lookup"><span data-stu-id="72a4a-139">Salvage value</span></span>                  | <span data-ttu-id="72a4a-140">1 000</span><span class="sxs-lookup"><span data-stu-id="72a4a-140">1,000</span></span>  |
| <span data-ttu-id="72a4a-141">Podstawa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="72a4a-141">Depreciation base</span></span>              | <span data-ttu-id="72a4a-142">10000</span><span class="sxs-lookup"><span data-stu-id="72a4a-142">10,000</span></span> |
| <span data-ttu-id="72a4a-143">Okres użytkowania (lata)</span><span class="sxs-lookup"><span data-stu-id="72a4a-143">Service life years</span></span>             | <span data-ttu-id="72a4a-144">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="72a4a-144">5</span></span>      |
| <span data-ttu-id="72a4a-145">Roczna wartość procentowa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="72a4a-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="72a4a-146">25%</span><span class="sxs-lookup"><span data-stu-id="72a4a-146">25%</span></span>    |

<span data-ttu-id="72a4a-147">Metoda amortyzacji degresywnej 125% dzieli wartość 125% między lata okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="72a4a-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="72a4a-148">Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.</span><span class="sxs-lookup"><span data-stu-id="72a4a-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="72a4a-149">Okres</span><span class="sxs-lookup"><span data-stu-id="72a4a-149">Period</span></span> | <span data-ttu-id="72a4a-150">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="72a4a-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="72a4a-151">Wartość księgowa</span><span class="sxs-lookup"><span data-stu-id="72a4a-151">Book value</span></span>                    | <span data-ttu-id="72a4a-152">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="72a4a-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="72a4a-153">Rok 1</span><span class="sxs-lookup"><span data-stu-id="72a4a-153">Year 1</span></span> | <span data-ttu-id="72a4a-154">(11 000 – 1000) × 25% = 2500</span><span class="sxs-lookup"><span data-stu-id="72a4a-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="72a4a-155">(11 000 – 2500) = 8500</span><span class="sxs-lookup"><span data-stu-id="72a4a-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="72a4a-156">(11 000 – 1000 – 2500) = 7500</span><span class="sxs-lookup"><span data-stu-id="72a4a-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="72a4a-157">Rok 2</span><span class="sxs-lookup"><span data-stu-id="72a4a-157">Year 2</span></span> | <span data-ttu-id="72a4a-158">7500 × 25% = 1875</span><span class="sxs-lookup"><span data-stu-id="72a4a-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="72a4a-159">(8500 – 1875) = 6625</span><span class="sxs-lookup"><span data-stu-id="72a4a-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="72a4a-160">(7500 – 1875) = 5625</span><span class="sxs-lookup"><span data-stu-id="72a4a-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="72a4a-161">Rok 3</span><span class="sxs-lookup"><span data-stu-id="72a4a-161">Year 3</span></span> | <span data-ttu-id="72a4a-162">5625 × 25% = 1406,25</span><span class="sxs-lookup"><span data-stu-id="72a4a-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="72a4a-163">(6625 – 1406,25) = 5218,75</span><span class="sxs-lookup"><span data-stu-id="72a4a-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="72a4a-164">(5625 – 1406,25) = 4218,75</span><span class="sxs-lookup"><span data-stu-id="72a4a-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="72a4a-165">Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 125%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="72a4a-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




