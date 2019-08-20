---
title: 150% amortyzacja degresywna
description: Ten artykuł zawiera omówienie metody amortyzacji 150% amortyzacja degresywna.
author: saraschi2
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
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a132a8d6e5eaf0dad54133fc9d0c12dcf5866c7c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840824"
---
# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="9edca-103">150% amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="9edca-103">150 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9edca-104">Ten artykuł zawiera omówienie metody amortyzacji 150% amortyzacja degresywna.</span><span class="sxs-lookup"><span data-stu-id="9edca-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="9edca-105">Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 150%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="9edca-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="9edca-106">Wartość procentowa jest obliczana na podstawie okresu użytkowania środków.</span><span class="sxs-lookup"><span data-stu-id="9edca-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="9edca-107">Na przykład, jeżeli okres użytkowania środków wynosi pięć lat, wartość procentowa zostanie obliczona jako 30% (150%/5).</span><span class="sxs-lookup"><span data-stu-id="9edca-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="9edca-108">Aby skonfigurować amortyzację degresywną 150%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="9edca-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9edca-109">Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="9edca-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="9edca-110">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="9edca-110">Selection of depreciation year</span></span>
<span data-ttu-id="9edca-111">Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**.</span><span class="sxs-lookup"><span data-stu-id="9edca-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="9edca-112">Domyślna wartość to **Kalendarzowy**.</span><span class="sxs-lookup"><span data-stu-id="9edca-112">The default value is **Calendar**.</span></span> <span data-ttu-id="9edca-113">Wybór określa opcje dostępne w polu **Częstotliwość okresu**.</span><span class="sxs-lookup"><span data-stu-id="9edca-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="9edca-114">W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.</span><span class="sxs-lookup"><span data-stu-id="9edca-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="9edca-115">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="9edca-115">Calendar</span></span>

<span data-ttu-id="9edca-116">W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** .</span><span class="sxs-lookup"><span data-stu-id="9edca-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="9edca-117">Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="9edca-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="9edca-118">Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji.</span><span class="sxs-lookup"><span data-stu-id="9edca-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="9edca-119">W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="9edca-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="9edca-120">W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:</span><span class="sxs-lookup"><span data-stu-id="9edca-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9edca-121">**Roczne** — księgowanie kwoty 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="9edca-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="9edca-122">**Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="9edca-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="9edca-123">**Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="9edca-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="9edca-124">**Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="9edca-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="9edca-125">**Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="9edca-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="9edca-126">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="9edca-126">Fiscal</span></span>

<span data-ttu-id="9edca-127">W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 150% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**.</span><span class="sxs-lookup"><span data-stu-id="9edca-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="9edca-128">Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="9edca-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="9edca-129">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="9edca-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="9edca-130">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="9edca-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="9edca-131">Amortyzacja jest korygowana dla każdego okresu.</span><span class="sxs-lookup"><span data-stu-id="9edca-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="9edca-132">Długość kolejnego roku obrachunkowego jest określana na podstawie konfiguracji okresów na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="9edca-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="9edca-133">W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="9edca-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9edca-134">**Rocznie** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="9edca-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="9edca-135">**Okres obrachunkowy** księguje łączną kwotę amortyzacji w roku obrachunkowym.</span><span class="sxs-lookup"><span data-stu-id="9edca-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="9edca-136">Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.</span><span class="sxs-lookup"><span data-stu-id="9edca-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="9edca-137">Przykład 150% amortyzacji degresywnej</span><span class="sxs-lookup"><span data-stu-id="9edca-137">Example of 150% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="9edca-138">Koszt nabycia</span><span class="sxs-lookup"><span data-stu-id="9edca-138">Acquisition cost</span></span>               | <span data-ttu-id="9edca-139">11 000</span><span class="sxs-lookup"><span data-stu-id="9edca-139">11,000</span></span> |
| <span data-ttu-id="9edca-140">Wartość odzyskana</span><span class="sxs-lookup"><span data-stu-id="9edca-140">Salvage value</span></span>                  | <span data-ttu-id="9edca-141">1 000</span><span class="sxs-lookup"><span data-stu-id="9edca-141">1,000</span></span>  |
| <span data-ttu-id="9edca-142">Podstawa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="9edca-142">Depreciation base</span></span>              | <span data-ttu-id="9edca-143">10000</span><span class="sxs-lookup"><span data-stu-id="9edca-143">10,000</span></span> |
| <span data-ttu-id="9edca-144">Okres użytkowania (lata)</span><span class="sxs-lookup"><span data-stu-id="9edca-144">Service life years</span></span>             | <span data-ttu-id="9edca-145">5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych</span><span class="sxs-lookup"><span data-stu-id="9edca-145">5</span></span>      |
| <span data-ttu-id="9edca-146">Roczna wartość procentowa amortyzacji</span><span class="sxs-lookup"><span data-stu-id="9edca-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="9edca-147">30%</span><span class="sxs-lookup"><span data-stu-id="9edca-147">30%</span></span>    |

<span data-ttu-id="9edca-148">Metoda amortyzacji degresywnej 150% dzieli wartość 150% między lata okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="9edca-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="9edca-149">Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.</span><span class="sxs-lookup"><span data-stu-id="9edca-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="9edca-150">Okres</span><span class="sxs-lookup"><span data-stu-id="9edca-150">Period</span></span> | <span data-ttu-id="9edca-151">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="9edca-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="9edca-152">Wartość księgowa</span><span class="sxs-lookup"><span data-stu-id="9edca-152">Book value</span></span>             | <span data-ttu-id="9edca-153">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="9edca-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="9edca-154">Rok 1</span><span class="sxs-lookup"><span data-stu-id="9edca-154">Year 1</span></span> | <span data-ttu-id="9edca-155">(11 000 – 1000) × 30% = 3000</span><span class="sxs-lookup"><span data-stu-id="9edca-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="9edca-156">11 000 – 3000 = 8000</span><span class="sxs-lookup"><span data-stu-id="9edca-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="9edca-157">11 000 – 1000 – 3000 = 7000</span><span class="sxs-lookup"><span data-stu-id="9edca-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="9edca-158">Rok 2</span><span class="sxs-lookup"><span data-stu-id="9edca-158">Year 2</span></span> | <span data-ttu-id="9edca-159">7000 × 30% = 2100</span><span class="sxs-lookup"><span data-stu-id="9edca-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="9edca-160">8000 – 2100 = 5900</span><span class="sxs-lookup"><span data-stu-id="9edca-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="9edca-161">7000 – 2100 = 4900</span><span class="sxs-lookup"><span data-stu-id="9edca-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="9edca-162">Rok 3</span><span class="sxs-lookup"><span data-stu-id="9edca-162">Year 3</span></span> | <span data-ttu-id="9edca-163">4900 × 30% = 1470</span><span class="sxs-lookup"><span data-stu-id="9edca-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="9edca-164">5900 – 1470 = 4430</span><span class="sxs-lookup"><span data-stu-id="9edca-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="9edca-165">4900 – 1470 = 3430</span><span class="sxs-lookup"><span data-stu-id="9edca-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="9edca-166">Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 150%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.</span><span class="sxs-lookup"><span data-stu-id="9edca-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



