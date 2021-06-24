---
title: 200% amortyzacja degresywna
description: Ten artykuł zawiera omówienie metody amortyzacji 200% amortyzacja degresywna.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91876ae28d088a52b12ac58db06cb0cd84b129ad
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193523"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="03bd6-103">200% amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="03bd6-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03bd6-104">Ten artykuł zawiera omówienie metody amortyzacji 200% amortyzacja degresywna.</span><span class="sxs-lookup"><span data-stu-id="03bd6-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="03bd6-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 200%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="03bd6-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="03bd6-106">Wartość procentowa jest obliczana na podstawie okresu użytkowania środków.</span><span class="sxs-lookup"><span data-stu-id="03bd6-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="03bd6-107">Na przykład, jeżeli okres użytkowania środków wynosi pięć lat, wartość procentowa zostanie obliczona jako 40% (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="03bd6-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="03bd6-108">Ta metoda jest określana jako amortyzacja przyspieszona podwójna.</span><span class="sxs-lookup"><span data-stu-id="03bd6-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="03bd6-109">Aby skonfigurować amortyzację degresywną 200%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="03bd6-110">Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="03bd6-111">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="03bd6-111">Select a depreciation year</span></span>
<span data-ttu-id="03bd6-112">Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="03bd6-113">Domyślna wartość to **Kalendarzowy**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="03bd6-114">Wybór określa opcje dostępne w polu **Częstotliwość okresu**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="03bd6-115">W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="03bd6-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="03bd6-116">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="03bd6-116">Calendar</span></span>

<span data-ttu-id="03bd6-117">W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** .</span><span class="sxs-lookup"><span data-stu-id="03bd6-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="03bd6-118">Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="03bd6-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="03bd6-119">Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji.</span><span class="sxs-lookup"><span data-stu-id="03bd6-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="03bd6-120">W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="03bd6-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="03bd6-121">W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:</span><span class="sxs-lookup"><span data-stu-id="03bd6-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="03bd6-122">**Roczne** — księgowanie kwoty 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="03bd6-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="03bd6-123">**Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="03bd6-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="03bd6-124">**Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="03bd6-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="03bd6-125">**Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="03bd6-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="03bd6-126">**Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="03bd6-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="03bd6-127">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="03bd6-127">Fiscal</span></span>

<span data-ttu-id="03bd6-128">W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 200% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="03bd6-129">Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="03bd6-130">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="03bd6-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="03bd6-131">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="03bd6-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="03bd6-132">Amortyzacja jest korygowana dla każdego okresu.</span><span class="sxs-lookup"><span data-stu-id="03bd6-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="03bd6-133">Długość kolejnego roku obrachunkowego jest określana na podstawie konfiguracji okresów na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="03bd6-134">W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="03bd6-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="03bd6-135">**Roczne** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="03bd6-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="03bd6-136">**Okres obrachunkowy** księguje łączną kwotę amortyzacji w roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="03bd6-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="03bd6-137">Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="03bd6-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="03bd6-138">Przykład amortyzacji degresywnej 200%</span><span class="sxs-lookup"><span data-stu-id="03bd6-138">Example of 200% reducing balance depreciation</span></span>

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| <span data-ttu-id="03bd6-139">Koszt nabycia</span><span class="sxs-lookup"><span data-stu-id="03bd6-139">Acquisition cost</span></span>               | <span data-ttu-id="03bd6-140">11 000</span><span class="sxs-lookup"><span data-stu-id="03bd6-140">11,000</span></span> |
| <span data-ttu-id="03bd6-141">Wartość odzyskana</span><span class="sxs-lookup"><span data-stu-id="03bd6-141">Salvage value</span></span>                  | <span data-ttu-id="03bd6-142">1000</span><span class="sxs-lookup"><span data-stu-id="03bd6-142">1, 000</span></span> |
| <span data-ttu-id="03bd6-143">Podstawa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="03bd6-143">Depreciation base</span></span>              | <span data-ttu-id="03bd6-144">10000</span><span class="sxs-lookup"><span data-stu-id="03bd6-144">10,000</span></span> |
| <span data-ttu-id="03bd6-145">Okres użytkowania (lata)</span><span class="sxs-lookup"><span data-stu-id="03bd6-145">Service life years</span></span>             | <span data-ttu-id="03bd6-146">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="03bd6-146">5</span></span>      |
| <span data-ttu-id="03bd6-147">Roczna wartość procentowa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="03bd6-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="03bd6-148">40%</span><span class="sxs-lookup"><span data-stu-id="03bd6-148">40%</span></span>    |

<span data-ttu-id="03bd6-149">Metoda amortyzacji degresywnej 200% dzieli wartość 200% między lata okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="03bd6-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="03bd6-150">Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.</span><span class="sxs-lookup"><span data-stu-id="03bd6-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="03bd6-151">Okres</span><span class="sxs-lookup"><span data-stu-id="03bd6-151">Period</span></span> | <span data-ttu-id="03bd6-152">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="03bd6-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="03bd6-153">Wartość księgowa</span><span class="sxs-lookup"><span data-stu-id="03bd6-153">Book value</span></span>             | <span data-ttu-id="03bd6-154">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="03bd6-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="03bd6-155">Rok 1</span><span class="sxs-lookup"><span data-stu-id="03bd6-155">Year 1</span></span> | <span data-ttu-id="03bd6-156">(11000 – 1000) × 40% = 4000</span><span class="sxs-lookup"><span data-stu-id="03bd6-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="03bd6-157">11000 – 4000 = 7000</span><span class="sxs-lookup"><span data-stu-id="03bd6-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="03bd6-158">11000 – 1000 – 4000 = 6000</span><span class="sxs-lookup"><span data-stu-id="03bd6-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="03bd6-159">Rok 2</span><span class="sxs-lookup"><span data-stu-id="03bd6-159">Year 2</span></span> | <span data-ttu-id="03bd6-160">6000 × 40% = 2400</span><span class="sxs-lookup"><span data-stu-id="03bd6-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="03bd6-161">7000 – 2400 = 4600</span><span class="sxs-lookup"><span data-stu-id="03bd6-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="03bd6-162">6000 – 2400 = 3600</span><span class="sxs-lookup"><span data-stu-id="03bd6-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="03bd6-163">Rok 3</span><span class="sxs-lookup"><span data-stu-id="03bd6-163">Year 3</span></span> | <span data-ttu-id="03bd6-164">3600 × 40% = 1440</span><span class="sxs-lookup"><span data-stu-id="03bd6-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="03bd6-165">4600 – 1440 = 3160</span><span class="sxs-lookup"><span data-stu-id="03bd6-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="03bd6-166">3600 – 1440 = 2160</span><span class="sxs-lookup"><span data-stu-id="03bd6-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="03bd6-167">Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 200%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="03bd6-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]