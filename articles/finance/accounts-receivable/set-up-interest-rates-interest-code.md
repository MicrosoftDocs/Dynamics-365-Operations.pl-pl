---
title: Konfigurowanie stopy procentowej dla kodu odsetek
description: Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d9ff856e34eb894c5d0ab5fe17c8e95f62fff57
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555372"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="010b1-103">Konfigurowanie stopy procentowej dla kodu odsetek</span><span class="sxs-lookup"><span data-stu-id="010b1-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="010b1-104">Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych.</span><span class="sxs-lookup"><span data-stu-id="010b1-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="010b1-105">Można utworzyć jeden kod odsetek i zastosować do wielu profili księgowania odbiorców lub w określonych w wierszach faktury.</span><span class="sxs-lookup"><span data-stu-id="010b1-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="010b1-106">Gdy szczegóły kodu odsetek zmieniają się, wszystkie funkcje używane do kodu powodują automatyczne wprowadzenie zmian w nowych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="010b1-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="010b1-107">Dla każdego kodu odsetek należy zdefiniować dwa rodzaje stawek:</span><span class="sxs-lookup"><span data-stu-id="010b1-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="010b1-108">Stawki zysku z odsetek — reprezentują one przychód obciążany odsetkami w przypadku faktur i not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="010b1-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="010b1-109">Stawki dla płatności odsetek — reprezentują one koszt, który ma być stosowany do naliczania odsetek na fakturach korygujących.</span><span class="sxs-lookup"><span data-stu-id="010b1-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="010b1-110">Oba te typy stawek mogą istnieć w tym samym czasie i w tym samym kodzie odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="010b1-111">Stopy procentowe mogą być oparte na trzech typach obliczeń:</span><span class="sxs-lookup"><span data-stu-id="010b1-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="010b1-112">Procent odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-112">Interest by percentage.</span></span>
-   <span data-ttu-id="010b1-113">Kwota odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-113">Interest by amount.</span></span>
-   <span data-ttu-id="010b1-114">Odsetki według zakresu, które wynikają z oprocentowania lub kwoty.</span><span class="sxs-lookup"><span data-stu-id="010b1-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="010b1-115">Przy naliczaniu odsetek przy użyciu kodu odsetek jest tworzona oddzielna nota odsetkowa dla każdej stopy odsetkowej obowiązującej w okresie, w którym miała miejsce płatność dokonana już po terminie transakcji.</span><span class="sxs-lookup"><span data-stu-id="010b1-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="010b1-116">Na karcie **Zarobki** na stronie **Kod odsetek** można skonfigurować stawki odsetek dla odsetek uzyskanych poprzez naliczanie odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="010b1-117">Na karcie **Płatności** można skonfigurować stopy odsetkowe dla odsetek, które będziesz płacić.</span><span class="sxs-lookup"><span data-stu-id="010b1-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="010b1-118">Stopy odsetkowe oparte na procencie</span><span class="sxs-lookup"><span data-stu-id="010b1-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="010b1-119">Istnieje możliwość konfigurowania stóp odsetek, które są obliczane według określonych odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="010b1-120">Kwota odsetek ma zastosowanie do wszystkich walut.</span><span class="sxs-lookup"><span data-stu-id="010b1-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="010b1-121">Można wprowadzić opcjonalne limity kwot odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="010b1-122">Opcja **Procent** jest wybrana w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.</span><span class="sxs-lookup"><span data-stu-id="010b1-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="010b1-123">Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 5 co dwa miesiące, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 2 w polu **Obliczaj odsetki co** i wybierz opcję **Miesiąc**.</span><span class="sxs-lookup"><span data-stu-id="010b1-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="010b1-124">Nowy algorytm obliczania noty odsetkowej został dodany za pomocą funkcji zarządzania.</span><span class="sxs-lookup"><span data-stu-id="010b1-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="010b1-125">Aby użyć tego algorytmu, włącz funkcję **(GBL) Zezwalaj na obliczanie odsetek na dzień jako procent roku podzielony przez 365**.</span><span class="sxs-lookup"><span data-stu-id="010b1-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="010b1-126">Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="010b1-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="010b1-127">Wzór obliczania kwoty noty odsetkowej jest:</span><span class="sxs-lookup"><span data-stu-id="010b1-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="010b1-128">Kwota noty odsetkowej = Kwota należnego \* Odsetki rocznie % / 365 \* Liczba dni opóźnienia</span><span class="sxs-lookup"><span data-stu-id="010b1-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="010b1-129">Ta funkcja jest włączana w wersji 10.0.18 i nowsze.</span><span class="sxs-lookup"><span data-stu-id="010b1-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="010b1-130">Stopy odsetek oparte na kwotach</span><span class="sxs-lookup"><span data-stu-id="010b1-130">Interest rates based on amounts</span></span>
<span data-ttu-id="010b1-131">Można skonfigurować stopy procentowe, które obliczają określoną kwotę w walucie.</span><span class="sxs-lookup"><span data-stu-id="010b1-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="010b1-132">Kwotę odsetek określa się dla każdej waluty w kodzie odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="010b1-133">Można wprowadzić opcjonalne limity kwot odsetek.</span><span class="sxs-lookup"><span data-stu-id="010b1-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="010b1-134">Opcja **Kwota** jest wybrana w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.</span><span class="sxs-lookup"><span data-stu-id="010b1-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="010b1-135">Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 25,00 co 20 dni, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 20 w polu **Obliczaj odsetki co** oraz wybierz opcję **Dzień**.</span><span class="sxs-lookup"><span data-stu-id="010b1-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="010b1-136">Stopy odsetek oparte na zakresach</span><span class="sxs-lookup"><span data-stu-id="010b1-136">Interest rates based on ranges</span></span>
<span data-ttu-id="010b1-137">Istnieje możliwość konfigurowania stóp odsetek w zależności od kwoty zaległości, od liczby dni, o ile płatność jest opóźniona lub liczby miesięcy, o które płatność jest spóźniona.</span><span class="sxs-lookup"><span data-stu-id="010b1-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="010b1-138">Na karcie **Dochody wg waluty**, aby zdefiniować określone ustawienia odsetek dla każdej waluty.</span><span class="sxs-lookup"><span data-stu-id="010b1-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="010b1-139">Tu także definiuje się zakres.</span><span class="sxs-lookup"><span data-stu-id="010b1-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="010b1-140">Za pomocą przycisku **Zakresy** dodaje się wiersze będące zakresami, które mają zostać skonfigurowane..</span><span class="sxs-lookup"><span data-stu-id="010b1-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="010b1-141">Wartość **Z** odpowiada początkowi zakresu, a liczba **Wartość odsetek** określa procent lub kwotę, w zależności od wyboru dokonanego w polu **Podstawa naliczania odsetek** na stronie **Konfigurowanie kodów odsetek**.</span><span class="sxs-lookup"><span data-stu-id="010b1-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="010b1-142">Przykład 1: Odsetki według zakupu = ilość</span><span class="sxs-lookup"><span data-stu-id="010b1-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="010b1-143">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co trzy miesiące, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="010b1-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="010b1-144">Ma być podstawą obliczeń wartość procentową odsetek według interwałów stopniowanych kwot.</span><span class="sxs-lookup"><span data-stu-id="010b1-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="010b1-145">Wartość odsetek jest równa 1 procent faktury dla kwoty maksymalnej 1.000,00, 2 procentu dla kwoty od 1.001,00 do 5.000,00 i 3 procentu dla dużych kwot powyżej niż 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="010b1-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="010b1-146">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="010b1-147">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-147">**Field name**</span></span>                  | <span data-ttu-id="010b1-148">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="010b1-149">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-149">**Interest code**</span></span>               | <span data-ttu-id="010b1-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="010b1-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="010b1-151">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="010b1-151">**Calculate interest every**</span></span>    | <span data-ttu-id="010b1-152">3/miesiąc</span><span class="sxs-lookup"><span data-stu-id="010b1-152">3/Month</span></span>         |
| <span data-ttu-id="010b1-153">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="010b1-153">**Interest by range**</span></span>           | <span data-ttu-id="010b1-154">Kwota</span><span class="sxs-lookup"><span data-stu-id="010b1-154">Amount</span></span>          |
| <span data-ttu-id="010b1-155">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-155">**Calculate interest based on**</span></span> | <span data-ttu-id="010b1-156">Wartość procentowa</span><span class="sxs-lookup"><span data-stu-id="010b1-156">Percentage</span></span>      |

<span data-ttu-id="010b1-157">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="010b1-158">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="010b1-158">**From value**</span></span> | <span data-ttu-id="010b1-159">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="010b1-160">0</span><span class="sxs-lookup"><span data-stu-id="010b1-160">0</span></span>              | <span data-ttu-id="010b1-161">1</span><span class="sxs-lookup"><span data-stu-id="010b1-161">1</span></span>                  |
| <span data-ttu-id="010b1-162">1,001</span><span class="sxs-lookup"><span data-stu-id="010b1-162">1,001</span></span>          | <span data-ttu-id="010b1-163">2</span><span class="sxs-lookup"><span data-stu-id="010b1-163">2</span></span>                  |
| <span data-ttu-id="010b1-164">5,001</span><span class="sxs-lookup"><span data-stu-id="010b1-164">5,001</span></span>          | <span data-ttu-id="010b1-165">3</span><span class="sxs-lookup"><span data-stu-id="010b1-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="010b1-166">Przykład 2: Odsetki według zakupu = dni</span><span class="sxs-lookup"><span data-stu-id="010b1-166">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="010b1-167">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co 15 dni, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="010b1-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="010b1-168">Podstawą obliczeń wartości procentowej odsetek mają być interwały dni.</span><span class="sxs-lookup"><span data-stu-id="010b1-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="010b1-169">Wartość odsetek jest równa 10,00 przez 15 dni w okresie pierwszych 60 dni, 15,00 przez 15 dni w okresie 61 do 90 dni i 20,00 przez 15 dni od 91 dnia i później.</span><span class="sxs-lookup"><span data-stu-id="010b1-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="010b1-170">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="010b1-171">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-171">**Field name**</span></span>                  | <span data-ttu-id="010b1-172">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="010b1-173">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-173">**Interest code**</span></span>               | <span data-ttu-id="010b1-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="010b1-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="010b1-175">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="010b1-175">**Calculate interest every**</span></span>    | <span data-ttu-id="010b1-176">15/dzień</span><span class="sxs-lookup"><span data-stu-id="010b1-176">15/Day</span></span>          |
| <span data-ttu-id="010b1-177">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="010b1-177">**Interest by range**</span></span>           | <span data-ttu-id="010b1-178">Dni</span><span class="sxs-lookup"><span data-stu-id="010b1-178">Days</span></span>            |
| <span data-ttu-id="010b1-179">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-179">**Calculate interest based on**</span></span> | <span data-ttu-id="010b1-180">Kwota</span><span class="sxs-lookup"><span data-stu-id="010b1-180">Amount</span></span>          |

<span data-ttu-id="010b1-181">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="010b1-182">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="010b1-182">**From value**</span></span> | <span data-ttu-id="010b1-183">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="010b1-184">0</span><span class="sxs-lookup"><span data-stu-id="010b1-184">0</span></span>              | <span data-ttu-id="010b1-185">10</span><span class="sxs-lookup"><span data-stu-id="010b1-185">10</span></span>                 |
| <span data-ttu-id="010b1-186">61</span><span class="sxs-lookup"><span data-stu-id="010b1-186">61</span></span>             | <span data-ttu-id="010b1-187">15</span><span class="sxs-lookup"><span data-stu-id="010b1-187">15</span></span>                 |
| <span data-ttu-id="010b1-188">91</span><span class="sxs-lookup"><span data-stu-id="010b1-188">91</span></span>             | <span data-ttu-id="010b1-189">20</span><span class="sxs-lookup"><span data-stu-id="010b1-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="010b1-190">Przykład 3: Odsetki według zakupu = miesiące</span><span class="sxs-lookup"><span data-stu-id="010b1-190">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="010b1-191">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co miesiąc, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="010b1-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="010b1-192">Ma być podstawą obliczeń wartości procentowej odsetek według interwałów miesięcznych.</span><span class="sxs-lookup"><span data-stu-id="010b1-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="010b1-193">Wartość odsetek jest równa 1,5 procent przez miesiąc dla pierwszych trzech zaległych miesięcy, 2,0 procent przez miesiąc dla kolejnych trzech miesięcy i 2,5 procent przez miesiąc dla każdego miesiąca powyżej okresu pierwszych sześciu miesięcy.</span><span class="sxs-lookup"><span data-stu-id="010b1-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="010b1-194">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="010b1-195">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-195">**Field name**</span></span>                  | <span data-ttu-id="010b1-196">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="010b1-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="010b1-197">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-197">**Interest code**</span></span>               | <span data-ttu-id="010b1-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="010b1-198">1M%ByMth</span></span>        |
| <span data-ttu-id="010b1-199">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="010b1-199">**Calculate interest every**</span></span>    | <span data-ttu-id="010b1-200">1/miesiąc</span><span class="sxs-lookup"><span data-stu-id="010b1-200">1/Month</span></span>         |
| <span data-ttu-id="010b1-201">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="010b1-201">**Interest by range**</span></span>           | <span data-ttu-id="010b1-202">Miesiące</span><span class="sxs-lookup"><span data-stu-id="010b1-202">Months</span></span>          |
| <span data-ttu-id="010b1-203">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-203">**Calculate interest based on**</span></span> | <span data-ttu-id="010b1-204">Wartość procentowa</span><span class="sxs-lookup"><span data-stu-id="010b1-204">Percentage</span></span>      |

<span data-ttu-id="010b1-205">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="010b1-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="010b1-206">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="010b1-206">**From value**</span></span> | <span data-ttu-id="010b1-207">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="010b1-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="010b1-208">0</span><span class="sxs-lookup"><span data-stu-id="010b1-208">0</span></span>              | <span data-ttu-id="010b1-209">1.5</span><span class="sxs-lookup"><span data-stu-id="010b1-209">1.5</span></span>                |
| <span data-ttu-id="010b1-210">4</span><span class="sxs-lookup"><span data-stu-id="010b1-210">4</span></span>              | <span data-ttu-id="010b1-211">2</span><span class="sxs-lookup"><span data-stu-id="010b1-211">2</span></span>                  |
| <span data-ttu-id="010b1-212">7</span><span class="sxs-lookup"><span data-stu-id="010b1-212">7</span></span>              | <span data-ttu-id="010b1-213">2,5</span><span class="sxs-lookup"><span data-stu-id="010b1-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="010b1-214">Nowe wersje</span><span class="sxs-lookup"><span data-stu-id="010b1-214">New versions</span></span>
<span data-ttu-id="010b1-215">Kody odsetek są datą obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="010b1-215">Interest codes are date effective.</span></span> <span data-ttu-id="010b1-216">Jeśli chcesz zmodyfikować stopę procentową, możesz utworzyć **nową wersję** obowiązującą od daty w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="010b1-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="010b1-217">Aby wyświetlić różne wersje, można wybrać datę graniczną w menu **Na dzień**.</span><span class="sxs-lookup"><span data-stu-id="010b1-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="010b1-218">Można też wybrać opcję **Wyświetlaj wszystkie rekordy**, aby wyświetlać wszystkie kody zainteresowania na stronie.</span><span class="sxs-lookup"><span data-stu-id="010b1-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
