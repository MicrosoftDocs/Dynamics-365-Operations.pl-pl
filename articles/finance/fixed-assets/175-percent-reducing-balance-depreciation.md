---
title: Amortyzacja regresywna 175 procent
description: Ten temat zawiera omówienie metody amortyzacji 175% amortyzacja degresywna.
author: saraschi2
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0747c34a4b28340227209adadf367f672deb1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827153"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="dfe53-103">Amortyzacja regresywna 175 procent</span><span class="sxs-lookup"><span data-stu-id="dfe53-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfe53-104">Ten temat zawiera omówienie metody amortyzacji 175% amortyzacja degresywna.</span><span class="sxs-lookup"><span data-stu-id="dfe53-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="dfe53-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 175%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="dfe53-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="dfe53-106">Aby skonfigurować amortyzację degresywną 175%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="dfe53-107">Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="dfe53-108">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dfe53-108">Select a depreciation year</span></span>
<span data-ttu-id="dfe53-109">Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="dfe53-110">Domyślna wartość to **Kalendarzowy**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="dfe53-111">Wybór określa opcje dostępne w polu **Częstotliwość okresu**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="dfe53-112">W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="dfe53-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="dfe53-113">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="dfe53-113">Calendar</span></span>

<span data-ttu-id="dfe53-114">W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** .</span><span class="sxs-lookup"><span data-stu-id="dfe53-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="dfe53-115">Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="dfe53-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="dfe53-116">Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji.</span><span class="sxs-lookup"><span data-stu-id="dfe53-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="dfe53-117">W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="dfe53-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="dfe53-118">W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:</span><span class="sxs-lookup"><span data-stu-id="dfe53-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="dfe53-119">**Roczne** — księgowanie kwoty 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="dfe53-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="dfe53-120">**Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="dfe53-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="dfe53-121">**Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="dfe53-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="dfe53-122">**Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="dfe53-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="dfe53-123">**Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="dfe53-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="dfe53-124">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="dfe53-124">Fiscal</span></span>

<span data-ttu-id="dfe53-125">W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 175% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="dfe53-126">Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="dfe53-127">Aby uzyskać więcej informacji, zobacz [Kalendarze, lata i okresy obrachunkowe](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="dfe53-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="dfe53-128">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="dfe53-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="dfe53-129">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="dfe53-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="dfe53-130">Amortyzacja jest automatycznie korygowana dla każdego okresu obrachunkowego, a długość kolejnego roku obrachunkowego jest określona przez okresy obrachunkowe zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="dfe53-131">W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="dfe53-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="dfe53-132">**Rocznie** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="dfe53-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="dfe53-133">**Okres obrachunkowy** oblicza łączną kwotę amortyzacji w roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="dfe53-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="dfe53-134">Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="dfe53-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="dfe53-135">Przykład amortyzacji degresywnej 175%</span><span class="sxs-lookup"><span data-stu-id="dfe53-135">Example of 175% reducing balance depreciation</span></span>

| <span data-ttu-id="dfe53-136">Pole</span><span class="sxs-lookup"><span data-stu-id="dfe53-136">Field</span></span>                          | <span data-ttu-id="dfe53-137">Wartość</span><span class="sxs-lookup"><span data-stu-id="dfe53-137">Value</span></span>  |
|--------------------------------|--------|
| <span data-ttu-id="dfe53-138">Koszt nabycia</span><span class="sxs-lookup"><span data-stu-id="dfe53-138">Acquisition cost</span></span>               | <span data-ttu-id="dfe53-139">11,000</span><span class="sxs-lookup"><span data-stu-id="dfe53-139">11,000</span></span> |
| <span data-ttu-id="dfe53-140">Wartość odzyskana</span><span class="sxs-lookup"><span data-stu-id="dfe53-140">Salvage value</span></span>                  | <span data-ttu-id="dfe53-141">1 000</span><span class="sxs-lookup"><span data-stu-id="dfe53-141">1,000</span></span>  |
| <span data-ttu-id="dfe53-142">Podstawa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dfe53-142">Depreciation base</span></span>              | <span data-ttu-id="dfe53-143">10000</span><span class="sxs-lookup"><span data-stu-id="dfe53-143">10,000</span></span> |
| <span data-ttu-id="dfe53-144">Okres użytkowania (lata)</span><span class="sxs-lookup"><span data-stu-id="dfe53-144">Service life years</span></span>             | <span data-ttu-id="dfe53-145">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="dfe53-145">5</span></span>      |
| <span data-ttu-id="dfe53-146">Roczna wartość procentowa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dfe53-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="dfe53-147">35%</span><span class="sxs-lookup"><span data-stu-id="dfe53-147">35%</span></span>    |

<span data-ttu-id="dfe53-148">Metoda amortyzacji degresywnej 175% dzieli wartość 175% między lata okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="dfe53-148">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="dfe53-149">Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.</span><span class="sxs-lookup"><span data-stu-id="dfe53-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="dfe53-150">Okres</span><span class="sxs-lookup"><span data-stu-id="dfe53-150">Period</span></span> | <span data-ttu-id="dfe53-151">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="dfe53-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="dfe53-152">Wartość księgowa</span><span class="sxs-lookup"><span data-stu-id="dfe53-152">Book value</span></span>                  | <span data-ttu-id="dfe53-153">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="dfe53-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="dfe53-154">Rok 1</span><span class="sxs-lookup"><span data-stu-id="dfe53-154">Year 1</span></span> | <span data-ttu-id="dfe53-155">(11000 – 1000) × 35% = 3500</span><span class="sxs-lookup"><span data-stu-id="dfe53-155">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="dfe53-156">11 000 – 3500 = 7500</span><span class="sxs-lookup"><span data-stu-id="dfe53-156">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="dfe53-157">11000 – 1000 – 3500 = 6500</span><span class="sxs-lookup"><span data-stu-id="dfe53-157">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="dfe53-158">Rok 2</span><span class="sxs-lookup"><span data-stu-id="dfe53-158">Year 2</span></span> | <span data-ttu-id="dfe53-159">6500 × 35% = 2275</span><span class="sxs-lookup"><span data-stu-id="dfe53-159">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="dfe53-160">7500 – 2275 = 5225</span><span class="sxs-lookup"><span data-stu-id="dfe53-160">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="dfe53-161">6500 – 2275 = 4225</span><span class="sxs-lookup"><span data-stu-id="dfe53-161">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="dfe53-162">Rok 3</span><span class="sxs-lookup"><span data-stu-id="dfe53-162">Year 3</span></span> | <span data-ttu-id="dfe53-163">4225 × 35% = 1478,75</span><span class="sxs-lookup"><span data-stu-id="dfe53-163">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="dfe53-164">5225 – 1478,75 = 3746,25</span><span class="sxs-lookup"><span data-stu-id="dfe53-164">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="dfe53-165">4225 – 1478,75 = 2746,25</span><span class="sxs-lookup"><span data-stu-id="dfe53-165">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="dfe53-166">Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 175%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="dfe53-166">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]