---
title: Amortyzacja degresywna
description: Ten artykuł zawiera omówienie metody amortyzacji Degresywna.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e36a7e1a5d83a95de53b70b8e3c3b667aae9c6c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "321186"
---
# <a name="reduce-balance-depreciation"></a><span data-ttu-id="f26f5-103">Amortyzacja degresywna</span><span class="sxs-lookup"><span data-stu-id="f26f5-103">Reduce balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f26f5-104">Ten artykuł zawiera omówienie metody amortyzacji Degresywna.</span><span class="sxs-lookup"><span data-stu-id="f26f5-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="f26f5-105">Jeśli przy konfiguracji profilu amortyzacji środka stałego zostanie wybrana opcja Degresywna w polu Metoda na stronie Profile amortyzacji, wówczas środki trwałe, do których przypisany jest ten profil amortyzacji, będą amortyzowane o tę samą wartość procentową w każdym okresie amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="f26f5-106">Aby skonfigurować amortyzację degresywną, należy również zaznaczyć pola na skróconej karcie Ogólne na stronie Profile amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="f26f5-107">Najpierw wybierz rok w polu Amortyzacja roczna.</span><span class="sxs-lookup"><span data-stu-id="f26f5-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="f26f5-108">Opcje dostępne w polu Częstotliwość okresu są uzależnione od opcji wybranych w pierwszym polu, co zostało opisane w sekcjach poniżej.</span><span class="sxs-lookup"><span data-stu-id="f26f5-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="f26f5-109">Należy również wprowadzić wartość w polu Procent dla profilu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="f26f5-110">Jeśli zostanie wybrana opcja Pełna amortyzacja, pozostała podstawa amortyzacji zostanie pobrana w ostatnim okresie amortyzacji i może to być duża kwota.</span><span class="sxs-lookup"><span data-stu-id="f26f5-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="f26f5-111">W niektórych krajach/regionach nie używa się przełączania na metodę liniową.</span><span class="sxs-lookup"><span data-stu-id="f26f5-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="f26f5-112">Zamiana następuje wtedy, gdy kwota metody alternatywnej jest większa niż kwota podstawowego profilu amortyzacji lub jest jej równa, zostanie pobrana kwota amortyzacji z metody alternatywnej.</span><span class="sxs-lookup"><span data-stu-id="f26f5-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="f26f5-113">Ponieważ środek trwały nigdy nie zostanie w pełni zamortyzowany na podstawie obliczenia wartości procentowej, należy wybrać opcję Pełna amortyzacja, aby w pełni zamortyzować środek trwały.</span><span class="sxs-lookup"><span data-stu-id="f26f5-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="f26f5-114">Wybór roku amortyzacji</span><span class="sxs-lookup"><span data-stu-id="f26f5-114">Select a depreciation year</span></span>
<span data-ttu-id="f26f5-115">Można wybrać Kalendarzowy lub Obrachunkowy w polu Rok amortyzacji na stronie Profile amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="f26f5-116">Wybór określa opcje dostępne w polu Częstotliwość okresu.</span><span class="sxs-lookup"><span data-stu-id="f26f5-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="f26f5-117">Opcją domyślną jest Kalendarz.</span><span class="sxs-lookup"><span data-stu-id="f26f5-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="f26f5-118">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="f26f5-118">Calendar</span></span>

<span data-ttu-id="f26f5-119">Opcja Kalendarz aktualizuje podstawę amortyzacji (zwykle wartość księgowa netto pomniejszona o wartość likwidacji) 1. stycznia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="f26f5-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="f26f5-120">W przykładzie amortyzacji degresywnej, niżej w tym temacie, podstawą amortyzacji jest licznik pierwszego wyrażenia w obliczeniach kolumny Obliczenia.</span><span class="sxs-lookup"><span data-stu-id="f26f5-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="f26f5-121">Po wybraniu opcji Kalendarz dostępne są następujące opcje w polu Częstotliwość okresu, które określa daty księgowania naliczenia amortyzacji oraz kwoty w całym roku kalendarzowym:</span><span class="sxs-lookup"><span data-stu-id="f26f5-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="f26f5-122">Roczne — służy do księgowania 31 grudnia.</span><span class="sxs-lookup"><span data-stu-id="f26f5-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="f26f5-123">Miesięczne — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.</span><span class="sxs-lookup"><span data-stu-id="f26f5-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="f26f5-124">Kwartalne — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="f26f5-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="f26f5-125">Półroczne — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).</span><span class="sxs-lookup"><span data-stu-id="f26f5-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="f26f5-126">Dzienne — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.</span><span class="sxs-lookup"><span data-stu-id="f26f5-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="f26f5-127">Na przykład jeśli wybierzesz opcję Roczne, roczna amortyzacja jest księgowana tylko raz, 31 grudnia każdego roku.</span><span class="sxs-lookup"><span data-stu-id="f26f5-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="f26f5-128">Jeśli wybierzesz opcję Miesięczne, miesięczna amortyzacja jest księgowana każdego miesiąca jako 1/12 kwoty amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="f26f5-129">Fiskalny</span><span class="sxs-lookup"><span data-stu-id="f26f5-129">Fiscal</span></span>

<span data-ttu-id="f26f5-130">Jeśli zostanie wybrana opcja Obrachunkowy w polu Rok amortyzacji, będzie używana liniowa metoda amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="f26f5-131">Jest ona obliczana na podstawie roku obrachunkowego, który został ustawiony na stronie Kalendarze obrachunkowe dla kalendarza obrachunkowego wybranego na stronie Księga.</span><span class="sxs-lookup"><span data-stu-id="f26f5-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="f26f5-132">Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca.</span><span class="sxs-lookup"><span data-stu-id="f26f5-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="f26f5-133">Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy.</span><span class="sxs-lookup"><span data-stu-id="f26f5-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="f26f5-134">Amortyzacja jest korygowana dla każdego okresu obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="f26f5-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="f26f5-135">Długość następnego roku obrachunkowego opiera się na okresach obrachunkowych, które konfiguruje się podczas tworzenia nowego roku obrachunkowego na stronie Kalendarze obrachunkowe.</span><span class="sxs-lookup"><span data-stu-id="f26f5-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="f26f5-136">W przypadku wybrania opcji Fiskalny w polu Częstotliwość okresu dostępne są następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="f26f5-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="f26f5-137">Roczne — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="f26f5-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="f26f5-138">Okres obrachunkowy służy do księgowania łącznej kwoty amortyzacji obliczonej dla roku obrachunkowego, która jest naliczana w okresach obrachunkowych zdefiniowanych dla kalendarza obrachunkowego wybranego na stronie Księga lub dla kalendarza obrachunkowego wybranego dla księgi zawierającej środek trwały.</span><span class="sxs-lookup"><span data-stu-id="f26f5-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="f26f5-139">Przykład amortyzacji degresywnej</span><span class="sxs-lookup"><span data-stu-id="f26f5-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="f26f5-140">Załóżmy, że cena nabycia środka trwałego wynosi 11,000, wartość likwidacji -1,000, a procentowy współczynnik amortyzacji -30.</span><span class="sxs-lookup"><span data-stu-id="f26f5-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="f26f5-141">Jeśli używasz metody Degresywna, 30 procent podstawy amortyzacji (wartość księgowa netto minus wartość likwidacji) jest obliczane na koniec poprzedniego okresu amortyzacji.</span><span class="sxs-lookup"><span data-stu-id="f26f5-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="f26f5-142">Amortyzacja dla pierwszych trzech lat została przedstawiona w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="f26f5-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="f26f5-143">Okres</span><span class="sxs-lookup"><span data-stu-id="f26f5-143">Period</span></span> | <span data-ttu-id="f26f5-144">Obliczenie kwoty rocznej amortyzacji</span><span class="sxs-lookup"><span data-stu-id="f26f5-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="f26f5-145">Wartość księgowa netto pod koniec roku</span><span class="sxs-lookup"><span data-stu-id="f26f5-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="f26f5-146">Rok 1</span><span class="sxs-lookup"><span data-stu-id="f26f5-146">Year 1</span></span> | <span data-ttu-id="f26f5-147">(11 000 - 1000) \* 30% = 3000</span><span class="sxs-lookup"><span data-stu-id="f26f5-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="f26f5-148">(11 000 - 1000) - 3000 = 7000</span><span class="sxs-lookup"><span data-stu-id="f26f5-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="f26f5-149">Rok 2</span><span class="sxs-lookup"><span data-stu-id="f26f5-149">Year 2</span></span> | <span data-ttu-id="f26f5-150">(7000 - 1000) \* 30% = 1800</span><span class="sxs-lookup"><span data-stu-id="f26f5-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="f26f5-151">(7000 -1800) = 5200</span><span class="sxs-lookup"><span data-stu-id="f26f5-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="f26f5-152">Rok 3</span><span class="sxs-lookup"><span data-stu-id="f26f5-152">Year 3</span></span> | <span data-ttu-id="f26f5-153">(5200 - 1000) \* 30% = 1260</span><span class="sxs-lookup"><span data-stu-id="f26f5-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="f26f5-154">(5200 - 1260) = 3940</span><span class="sxs-lookup"><span data-stu-id="f26f5-154">(5,200 - 1,260) = 3,940</span></span>               |


-





