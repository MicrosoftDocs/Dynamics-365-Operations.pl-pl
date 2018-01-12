---
title: Konfigurowanie stopy procentowej dla kodu odsetek
description: "Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 63bf043124797b328116fd7951913eaeda6ff97b
ms.openlocfilehash: c79b85f95ccb4164e33d6b559b23f740c555907f
ms.contentlocale: pl-pl
ms.lasthandoff: 01/12/2018

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="2d982-103">Konfigurowanie stopy procentowej dla kodu odsetek</span><span class="sxs-lookup"><span data-stu-id="2d982-103">Set up interest rates for an interest code</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2d982-104">Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych.</span><span class="sxs-lookup"><span data-stu-id="2d982-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="2d982-105">Można utworzyć jeden kod odsetek i zastosować do wielu profili księgowania odbiorców lub w określonych w wierszach faktury.</span><span class="sxs-lookup"><span data-stu-id="2d982-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="2d982-106">Gdy szczegóły kodu odsetek zmieniają się, wszystkie funkcje używane do kodu powodują automatyczne wprowadzenie zmian w nowych transakcjach.</span><span class="sxs-lookup"><span data-stu-id="2d982-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="2d982-107">Dla każdego kodu odsetek należy zdefiniować dwa rodzaje stawek:</span><span class="sxs-lookup"><span data-stu-id="2d982-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="2d982-108">Stawki zysku z odsetek — reprezentują one przychód obciążany odsetkami w przypadku faktur i not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="2d982-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="2d982-109">Stawki dla płatności odsetek — reprezentują one koszt, który ma być stosowany do naliczania odsetek na fakturach korygujących.</span><span class="sxs-lookup"><span data-stu-id="2d982-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="2d982-110">Oba te typy stawek mogą istnieć w tym samym czasie i w tym samym kodzie odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="2d982-111">Stopy procentowe mogą być oparte na trzech typach obliczeń:</span><span class="sxs-lookup"><span data-stu-id="2d982-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="2d982-112">Procent odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-112">Interest by percentage.</span></span>
-   <span data-ttu-id="2d982-113">Kwota odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-113">Interest by amount.</span></span>
-   <span data-ttu-id="2d982-114">Odsetki według zakresu, które wynikają z oprocentowania lub kwoty.</span><span class="sxs-lookup"><span data-stu-id="2d982-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="2d982-115">Przy naliczaniu odsetek przy użyciu kodu odsetek jest tworzona oddzielna nota odsetkowa dla każdej stopy odsetkowej obowiązującej w okresie, w którym miała miejsce płatność dokonana już po terminie transakcji.</span><span class="sxs-lookup"><span data-stu-id="2d982-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="2d982-116">Na karcie **Zarobki** na stronie **Kod odsetek** można skonfigurować stawki odsetek dla odsetek uzyskanych poprzez naliczanie odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="2d982-117">Na karcie **Płatności** można skonfigurować stopy odsetkowe dla odsetek, które będziesz płacić.</span><span class="sxs-lookup"><span data-stu-id="2d982-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="2d982-118">Stopy odsetkowe oparte na procencie</span><span class="sxs-lookup"><span data-stu-id="2d982-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="2d982-119">Istnieje możliwość konfigurowania stóp odsetek, które są obliczane według określonych odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-119">You can set up interest rates that calculate a specified percentage.</span></span>

-   <span data-ttu-id="2d982-120">Kwota odsetek ma zastosowanie do wszystkich walut.</span><span class="sxs-lookup"><span data-stu-id="2d982-120">Interest amount applies to all currencies.</span></span>
-   <span data-ttu-id="2d982-121">Można wprowadzić opcjonalne limity kwot odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-121">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="2d982-122">Opcja **Procent** jest wybrana** **w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.</span><span class="sxs-lookup"><span data-stu-id="2d982-122">**Percentage** is selected** **in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="2d982-123">Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 5 co dwa miesiące, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 2 w polu **Obliczaj odsetki co** i wybierz opcję **Miesiąc**.</span><span class="sxs-lookup"><span data-stu-id="2d982-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="2d982-124">Stopy odsetek oparte na kwotach</span><span class="sxs-lookup"><span data-stu-id="2d982-124">Interest rates based on amounts</span></span>
<span data-ttu-id="2d982-125">Można skonfigurować stopy procentowe, które obliczają określoną kwotę w walucie.</span><span class="sxs-lookup"><span data-stu-id="2d982-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
-   <span data-ttu-id="2d982-126">Kwotę odsetek określa się dla każdej waluty w kodzie odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-126">An interest amount is specified for each currency in the interest code.</span></span>
-   <span data-ttu-id="2d982-127">Można wprowadzić opcjonalne limity kwot odsetek.</span><span class="sxs-lookup"><span data-stu-id="2d982-127">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="2d982-128">Opcja **Kwota** jest wybrana w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.</span><span class="sxs-lookup"><span data-stu-id="2d982-128">**Amount **is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="2d982-129">Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 25,00 co 20 dni, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 20 w polu **Obliczaj odsetki co** oraz wybierz opcję **Dzień**.</span><span class="sxs-lookup"><span data-stu-id="2d982-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="2d982-130">Stopy odsetek oparte na zakresach</span><span class="sxs-lookup"><span data-stu-id="2d982-130">Interest rates based on ranges</span></span>
<span data-ttu-id="2d982-131">Istnieje możliwość konfigurowania stóp odsetek w zależności od kwoty zaległości, od liczby dni, o ile płatność jest opóźniona lub liczby miesięcy, o które płatność jest spóźniona.</span><span class="sxs-lookup"><span data-stu-id="2d982-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="2d982-132">Na karcie **Dochody wg waluty**, aby zdefiniować określone ustawienia odsetek dla każdej waluty.</span><span class="sxs-lookup"><span data-stu-id="2d982-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="2d982-133">Tu także definiuje się zakres.</span><span class="sxs-lookup"><span data-stu-id="2d982-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="2d982-134">Za pomocą przycisku **Zakresy** dodaje się wiersze będące zakresami, które mają zostać skonfigurowane..</span><span class="sxs-lookup"><span data-stu-id="2d982-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="2d982-135">Wartość **Z** odpowiada początkowi zakresu, a liczba **Wartość odsetek** określa procent lub kwotę, w zależności od wyboru dokonanego w polu **Podstawa naliczania odsetek** na stronie **Konfigurowanie kodów odsetek**.</span><span class="sxs-lookup"><span data-stu-id="2d982-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="2d982-136">Przykład 1: Odsetki według zakupu = ilość</span><span class="sxs-lookup"><span data-stu-id="2d982-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="2d982-137">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co trzy miesiące, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="2d982-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="2d982-138">Ma być podstawą obliczeń wartość procentową odsetek według interwałów stopniowanych kwot.</span><span class="sxs-lookup"><span data-stu-id="2d982-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="2d982-139">Wartość odsetek jest równa 1 procent faktury dla kwoty maksymalnej 1.000,00, 2 procentu dla kwoty od 1.001,00 do 5.000,00 i 3 procentu dla dużych kwot powyżej niż 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="2d982-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="2d982-140">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="2d982-141">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-141">**Field name**</span></span>                  | <span data-ttu-id="2d982-142">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="2d982-143">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-143">**Interest code**</span></span>               | <span data-ttu-id="2d982-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="2d982-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="2d982-145">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="2d982-145">**Calculate interest every**</span></span>    | <span data-ttu-id="2d982-146">3/miesiąc</span><span class="sxs-lookup"><span data-stu-id="2d982-146">3/Month</span></span>         |
| <span data-ttu-id="2d982-147">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="2d982-147">**Interest by range**</span></span>           | <span data-ttu-id="2d982-148">Kwota</span><span class="sxs-lookup"><span data-stu-id="2d982-148">Amount</span></span>          |
| <span data-ttu-id="2d982-149">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-149">**Calculate interest based on**</span></span> | <span data-ttu-id="2d982-150">Wartość procentowa</span><span class="sxs-lookup"><span data-stu-id="2d982-150">Percentage</span></span>      |

<span data-ttu-id="2d982-151">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="2d982-152">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="2d982-152">**From value**</span></span> | <span data-ttu-id="2d982-153">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="2d982-154">0</span><span class="sxs-lookup"><span data-stu-id="2d982-154">0</span></span>              | <span data-ttu-id="2d982-155">1</span><span class="sxs-lookup"><span data-stu-id="2d982-155">1</span></span>                  |
| <span data-ttu-id="2d982-156">1,001</span><span class="sxs-lookup"><span data-stu-id="2d982-156">1,001</span></span>          | <span data-ttu-id="2d982-157">2</span><span class="sxs-lookup"><span data-stu-id="2d982-157">2</span></span>                  |
| <span data-ttu-id="2d982-158">5,001</span><span class="sxs-lookup"><span data-stu-id="2d982-158">5,001</span></span>          | <span data-ttu-id="2d982-159">3</span><span class="sxs-lookup"><span data-stu-id="2d982-159">3</span></span>                  |

 
## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="2d982-160">Przykład 2: Odsetki według zakupu = dni</span><span class="sxs-lookup"><span data-stu-id="2d982-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="2d982-161">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co 15 dni, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="2d982-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="2d982-162">Podstawą obliczeń wartości procentowej odsetek mają być interwały dni.</span><span class="sxs-lookup"><span data-stu-id="2d982-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="2d982-163">Wartość odsetek jest równa 10,00 przez 15 dni w okresie pierwszych 60 dni, 15,00 przez 15 dni w okresie 61 do 90 dni i 20,00 przez 15 dni od 91 dnia i później.</span><span class="sxs-lookup"><span data-stu-id="2d982-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="2d982-164">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="2d982-165">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-165">**Field name**</span></span>                  | <span data-ttu-id="2d982-166">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="2d982-167">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-167">**Interest code**</span></span>               | <span data-ttu-id="2d982-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="2d982-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="2d982-169">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="2d982-169">**Calculate interest every**</span></span>    | <span data-ttu-id="2d982-170">15/dzień</span><span class="sxs-lookup"><span data-stu-id="2d982-170">15/Day</span></span>          |
| <span data-ttu-id="2d982-171">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="2d982-171">**Interest by range**</span></span>           | <span data-ttu-id="2d982-172">Dni</span><span class="sxs-lookup"><span data-stu-id="2d982-172">Days</span></span>            |
| <span data-ttu-id="2d982-173">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-173">**Calculate interest based on**</span></span> | <span data-ttu-id="2d982-174">Kwota</span><span class="sxs-lookup"><span data-stu-id="2d982-174">Amount</span></span>          |

<span data-ttu-id="2d982-175">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="2d982-176">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="2d982-176">**From value**</span></span> | <span data-ttu-id="2d982-177">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="2d982-178">0</span><span class="sxs-lookup"><span data-stu-id="2d982-178">0</span></span>              | <span data-ttu-id="2d982-179">10</span><span class="sxs-lookup"><span data-stu-id="2d982-179">10</span></span>                 |
| <span data-ttu-id="2d982-180">61</span><span class="sxs-lookup"><span data-stu-id="2d982-180">61</span></span>             | <span data-ttu-id="2d982-181">15</span><span class="sxs-lookup"><span data-stu-id="2d982-181">15</span></span>                 |
| <span data-ttu-id="2d982-182">91</span><span class="sxs-lookup"><span data-stu-id="2d982-182">91</span></span>             | <span data-ttu-id="2d982-183">20</span><span class="sxs-lookup"><span data-stu-id="2d982-183">20</span></span>                 |

 
## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="2d982-184">Przykład 3: Odsetki według zakupu = miesiące</span><span class="sxs-lookup"><span data-stu-id="2d982-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="2d982-185">Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co miesiąc, że płatności za fakturę transakcji przekraczają termin.</span><span class="sxs-lookup"><span data-stu-id="2d982-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="2d982-186">Ma być podstawą obliczeń wartości procentowej odsetek według interwałów miesięcznych.</span><span class="sxs-lookup"><span data-stu-id="2d982-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="2d982-187">Wartość odsetek jest równa 1,5 procent przez miesiąc dla pierwszych trzech zaległych miesięcy, 2,0 procent przez miesiąc dla kolejnych trzech miesięcy i 2,5 procent przez miesiąc dla każdego miesiąca powyżej okresu pierwszych sześciu miesięcy.</span><span class="sxs-lookup"><span data-stu-id="2d982-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="2d982-188">Utworzono kod odsetek wartości pól w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="2d982-189">**Nazwa pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-189">**Field name**</span></span>                  | <span data-ttu-id="2d982-190">**Wartość pola**</span><span class="sxs-lookup"><span data-stu-id="2d982-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="2d982-191">**Kod odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-191">**Interest code**</span></span>               | <span data-ttu-id="2d982-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="2d982-192">1M%ByMth</span></span>        |
| <span data-ttu-id="2d982-193">**Obliczaj odsetki co**</span><span class="sxs-lookup"><span data-stu-id="2d982-193">**Calculate interest every**</span></span>    | <span data-ttu-id="2d982-194">1/miesiąc</span><span class="sxs-lookup"><span data-stu-id="2d982-194">1/Month</span></span>         |
| <span data-ttu-id="2d982-195">**Odsetki według zakresu**</span><span class="sxs-lookup"><span data-stu-id="2d982-195">**Interest by range**</span></span>           | <span data-ttu-id="2d982-196">Miesiące</span><span class="sxs-lookup"><span data-stu-id="2d982-196">Months</span></span>          |
| <span data-ttu-id="2d982-197">**Podstawa naliczania odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-197">**Calculate interest based on**</span></span> | <span data-ttu-id="2d982-198">Wartość procentowa</span><span class="sxs-lookup"><span data-stu-id="2d982-198">Percentage</span></span>      |

<span data-ttu-id="2d982-199">Utworzono zakres informacji w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="2d982-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="2d982-200">**Od wartości**</span><span class="sxs-lookup"><span data-stu-id="2d982-200">**From value**</span></span> | <span data-ttu-id="2d982-201">**Wartości odsetek**</span><span class="sxs-lookup"><span data-stu-id="2d982-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="2d982-202">0</span><span class="sxs-lookup"><span data-stu-id="2d982-202">0</span></span>              | <span data-ttu-id="2d982-203">1.5</span><span class="sxs-lookup"><span data-stu-id="2d982-203">1.5</span></span>                |
| <span data-ttu-id="2d982-204">4</span><span class="sxs-lookup"><span data-stu-id="2d982-204">4</span></span>              | <span data-ttu-id="2d982-205">2</span><span class="sxs-lookup"><span data-stu-id="2d982-205">2</span></span>                  |
| <span data-ttu-id="2d982-206">7</span><span class="sxs-lookup"><span data-stu-id="2d982-206">7</span></span>              | <span data-ttu-id="2d982-207">2,5</span><span class="sxs-lookup"><span data-stu-id="2d982-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="2d982-208">Nowe wersje</span><span class="sxs-lookup"><span data-stu-id="2d982-208">New versions</span></span>
<span data-ttu-id="2d982-209">Kody odsetek są datą obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="2d982-209">Interest codes are date effective.</span></span> <span data-ttu-id="2d982-210">Jeśli chcesz zmodyfikować stopę procentową, możesz utworzyć **nową wersję** obowiązującą od daty w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2d982-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="2d982-211">Aby wyświetlić różne wersje, można wybrać datę graniczną w menu **Na dzień**.</span><span class="sxs-lookup"><span data-stu-id="2d982-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="2d982-212">Można też wybrać opcję **Wyświetlaj wszystkie rekordy**, aby wyświetlać wszystkie kody zainteresowania na stronie.</span><span class="sxs-lookup"><span data-stu-id="2d982-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




