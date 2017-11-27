---
title: "Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania"
description: "W tym temacie wyjaśniono, jak wartości w polach Podstawa limitu i Metoda obliczania ustalają stawki podatków w transakcji sprzedaży i zakupu."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bf0f8f2e3f553ea181e8cc9ab5b712fce64a89d4
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="7c004-103">Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania</span><span class="sxs-lookup"><span data-stu-id="7c004-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7c004-104">W tym temacie wyjaśniono, jak wartości w polach Podstawa limitu i Metoda obliczania ustalają stawki podatków w transakcji sprzedaży i zakupu.</span><span class="sxs-lookup"><span data-stu-id="7c004-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="7c004-105">Podstawa limitu na karcie skróconej Obliczenia na stronie Podatek określają, która kwota służy do pobierania odpowiedniej stawki podatkowej z kursów na stronie Wartości kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="7c004-106">Typ kwoty w polu Podstawa limitu w połączeniu z metodą w polu Metoda obliczania określa logikę znajdowania odpowiednich stawek podatku dla transakcji.</span><span class="sxs-lookup"><span data-stu-id="7c004-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="7c004-107">Rozmaite kombinacje wartości w tych polach generują całkowicie odmienne obliczenia podatku, jak pokazano na poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="7c004-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="7c004-108">W przykładach użyto tych samych wartości interwału podatku, które konfiguruje się na stronie Wartość kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="7c004-109">Aby otworzyć tę stronę, kliknij kolejno opcje Kod podatku &gt; Wartości na stronie Wartości kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="7c004-110">Jeśli podstawa limitu w co najmniej jednym kodzie podatku jest oparta na kwotach lub jednostkach wiersza, pole Metoda obliczania na stronie Parametry księgi głównej musi mieć wartość Wiersz.</span><span class="sxs-lookup"><span data-stu-id="7c004-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="7c004-111"> Kwota netto na wiersz</span><span class="sxs-lookup"><span data-stu-id="7c004-111">Net amount per line</span></span>
<span data-ttu-id="7c004-112">Wybierz tę opcję, aby określić stawki podatku na podstawie kwot netto dla wierszy faktury, z wykluczeniem wszelkich innych podatków.</span><span class="sxs-lookup"><span data-stu-id="7c004-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="7c004-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-113">Example</span></span>

<span data-ttu-id="7c004-114">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-115">Interwał kwoty</span><span class="sxs-lookup"><span data-stu-id="7c004-115">Amount interval</span></span>    | <span data-ttu-id="7c004-116">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="7c004-117">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-117">0 - 50</span></span>             | <span data-ttu-id="7c004-118">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-118">30%</span></span>      |
| <span data-ttu-id="7c004-119">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-119">50 - 100</span></span>           | <span data-ttu-id="7c004-120">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-120">20%</span></span>      |
| <span data-ttu-id="7c004-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-122">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="7c004-123">Górny limit zero (0) w ostatnim interwale oznacza, że wszystkie kwoty powyżej 100 są uwzględniane w tym interwale.</span><span class="sxs-lookup"><span data-stu-id="7c004-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="7c004-124">Podstawa limitu: **Kwota netto na wiersz**</span><span class="sxs-lookup"><span data-stu-id="7c004-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="7c004-125">Metoda obliczania: **Zakres**</span><span class="sxs-lookup"><span data-stu-id="7c004-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="7c004-126">Kupujesz 8 lamp po 25,00 każda.</span><span class="sxs-lookup"><span data-stu-id="7c004-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="7c004-127">Kwota netto dla wiersza faktury wynosi 200,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="7c004-128">Podatek jest obliczany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7c004-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="7c004-129">Łączny podatek = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00</span><span class="sxs-lookup"><span data-stu-id="7c004-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="7c004-130">Łączna kwota faktury = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="7c004-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="7c004-131">**Inny wariant**</span><span class="sxs-lookup"><span data-stu-id="7c004-131">**Variation**</span></span> 

<span data-ttu-id="7c004-132">Jeśli faktura ma dwa wiersze po cztery towary w każdym z nich, kwota netto w każdym wierszu wynosi 100,00, a podatek jest obliczany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7c004-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="7c004-133">Wiersz podatku 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="7c004-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="7c004-134">Wiersz podatku 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="7c004-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="7c004-135">Suma podatku = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="7c004-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="7c004-136">Łączna kwota faktury = 200,00 + 50,00 = 250,00</span><span class="sxs-lookup"><span data-stu-id="7c004-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="7c004-137"> Kwota netto na jednostkę</span><span class="sxs-lookup"><span data-stu-id="7c004-137">Net amount per unit</span></span>
<span data-ttu-id="7c004-138">Wybierz tę opcję, aby określić stawki podatku na podstawie wartości poszczególnych jednostek, z wykluczeniem wszelkich innych podatków.</span><span class="sxs-lookup"><span data-stu-id="7c004-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="7c004-139">Jeśli wybrana jest Podstawa limitu oparta na jednostce, wówczas dla Kodu podatku wystarczy określić tylko Jednostkę.</span><span class="sxs-lookup"><span data-stu-id="7c004-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="7c004-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-140">Example</span></span>

<span data-ttu-id="7c004-141">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-142">Ilość</span><span class="sxs-lookup"><span data-stu-id="7c004-142">Amount</span></span>             | <span data-ttu-id="7c004-143">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="7c004-144">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-144">0 - 50</span></span>             | <span data-ttu-id="7c004-145">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-145">30%</span></span>      |
| <span data-ttu-id="7c004-146">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-146">50 - 100</span></span>           | <span data-ttu-id="7c004-147">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-147">20%</span></span>      |
| <span data-ttu-id="7c004-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-149">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-149">10%</span></span>      |

<span data-ttu-id="7c004-150">Podstawa limitu: **Kwota netto na jednostkę**</span><span class="sxs-lookup"><span data-stu-id="7c004-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="7c004-151">Metoda obliczania: **Cała kwota**</span><span class="sxs-lookup"><span data-stu-id="7c004-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="7c004-152">Kupujesz 8 lamp po 25,00 każda.</span><span class="sxs-lookup"><span data-stu-id="7c004-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="7c004-153">Kwota netto dla wiersza faktury wynosi 200,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="7c004-154">Podatek jest obliczany w następujący sposób: Podatek na jednostkę = 25,00 x 30% = 7,50 Suma podatku = 7,50 x 8 jednostek = 60,00 Łączna kwota faktury = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="7c004-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="7c004-155"> Kwota netto faktury</span><span class="sxs-lookup"><span data-stu-id="7c004-155">Net amount of invoice balance</span></span>

<span data-ttu-id="7c004-156">Wybierz tę opcję, aby określić stawki podatku na podstawie łącznej wartości dla faktury, z wykluczeniem wszelkich innych podatków.</span><span class="sxs-lookup"><span data-stu-id="7c004-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="7c004-157">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-157">Example</span></span>

<span data-ttu-id="7c004-158">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-159">Ilość</span><span class="sxs-lookup"><span data-stu-id="7c004-159">Amount</span></span>            | <span data-ttu-id="7c004-160">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="7c004-161">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-161">0 - 50</span></span>            | <span data-ttu-id="7c004-162">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-162">30%</span></span>      |
| <span data-ttu-id="7c004-163">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-163">50 - 100</span></span>          | <span data-ttu-id="7c004-164">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-164">20%</span></span>      |
| <span data-ttu-id="7c004-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-166">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-166">10%</span></span>      |

<span data-ttu-id="7c004-167">Podstawa limitu: **Kwota netto faktury**</span><span class="sxs-lookup"><span data-stu-id="7c004-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="7c004-168">Metoda obliczeń: **Zakres** Faktura sprzedaży ma 2 wiersze z 4 lampami w każdym wierszu, każdy o wartości 25,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="7c004-169">Kwota netto salda faktury wynosi 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="7c004-170">Podatek jest obliczany w następujący sposób: Suma podatku = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Łączna kwota faktury = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="7c004-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="7c004-171"> Kwota brutto na wiersz</span><span class="sxs-lookup"><span data-stu-id="7c004-171">Gross amount per line</span></span>

<span data-ttu-id="7c004-172">Wybierz tę opcję, aby określić stawki podatku na podstawie wartości wiersza z uwzględnieniem wszystkich podatków dla tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="7c004-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="7c004-173">Grupa podatków może zawierać tylko jeden kod podatku z tą wartością wybraną w polu Podstawa limitu.</span><span class="sxs-lookup"><span data-stu-id="7c004-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="7c004-174">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-174">Example</span></span>

<span data-ttu-id="7c004-175">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-176">Ilość</span><span class="sxs-lookup"><span data-stu-id="7c004-176">Amount</span></span>             | <span data-ttu-id="7c004-177">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="7c004-178">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-178">0 - 50</span></span>             | <span data-ttu-id="7c004-179">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-179">30%</span></span>      |
| <span data-ttu-id="7c004-180">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-180">50 - 100</span></span>           | <span data-ttu-id="7c004-181">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-181">20%</span></span>      |
| <span data-ttu-id="7c004-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-183">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-183">10%</span></span>      |

<span data-ttu-id="7c004-184">Podstawa limitu: **Kwota brutto na wiersz** Metoda obliczania: **Zakres** Dodatkowo obliczany jest inny kod podatku dla specjalnego cła w wysokości 5,00 za każdą lampę.</span><span class="sxs-lookup"><span data-stu-id="7c004-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="7c004-185">Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="7c004-186">Kupujesz 8 lamp po 25,00 każda.</span><span class="sxs-lookup"><span data-stu-id="7c004-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="7c004-187">Kwota netto dla wiersza faktury wynosi 200,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="7c004-188">Kwota brutto dla wiersza faktury wynosi 8 x 25,00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="7c004-189">Podatek jest obliczany w następujący sposób: Łączny podatek = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="7c004-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="7c004-190">**Inny wariant**</span><span class="sxs-lookup"><span data-stu-id="7c004-190">**Variation**</span></span> 

<span data-ttu-id="7c004-191">Jeśli faktura jest złożona z 2 wierszy po 4 towary w każdym z nich, kwota netto na wiersz faktury wynosi 100,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="7c004-192">Kwota brutto (z uwzględnieniem cła 4 x 5,00) na wiersz faktury wynosi 120,00, a podatek jest obliczany w następujący sposób: Wiersz 1 podatku na fakturze = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Wiersz 2 podatku na fakturze = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Suma podatku = 27,00 + 27,00 = 54,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 54,00 + 40,00 = 294,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="7c004-193"> Kwota brutto na jednostkę</span><span class="sxs-lookup"><span data-stu-id="7c004-193">Gross amount per unit</span></span>

<span data-ttu-id="7c004-194">Wybierz tę opcję, aby określić stawki podatku na podstawie wartości poszczególnych jednostek, z uwzględnieniem wszelkich innych podatków.</span><span class="sxs-lookup"><span data-stu-id="7c004-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="7c004-195">Grupa podatków może zawierać tylko jeden kod podatku z tą wartością wybraną w polu Podstawa limitu.</span><span class="sxs-lookup"><span data-stu-id="7c004-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="7c004-196">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-196">Example</span></span>

<span data-ttu-id="7c004-197">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-198">Ilość</span><span class="sxs-lookup"><span data-stu-id="7c004-198">Amount</span></span>             | <span data-ttu-id="7c004-199">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="7c004-200">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-200">0 - 50</span></span>             | <span data-ttu-id="7c004-201">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-201">30%</span></span>      |
| <span data-ttu-id="7c004-202">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-202">50 - 100</span></span>           | <span data-ttu-id="7c004-203">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-203">20%</span></span>      |
| <span data-ttu-id="7c004-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-205">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-205">10%</span></span>      |

<span data-ttu-id="7c004-206">Podstawa limitu: **Kwota brutto na jednostkę** jest specjalnym cłem, które wynosi 5,00 za każdą lampę.</span><span class="sxs-lookup"><span data-stu-id="7c004-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="7c004-207">Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="7c004-208">Kupujesz 8 lamp po 25,00 każda.</span><span class="sxs-lookup"><span data-stu-id="7c004-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="7c004-209">Kwota brutto na jednostkę wynosi 30,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="7c004-210">Podatek jest obliczany w następujący sposób: Podatek na jednostkę = 30 x 30% = 9,00 Łączny podatek = 9,00 x 8 = 72,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="7c004-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="7c004-211"> Kwota faktury z innymi podatkami</span><span class="sxs-lookup"><span data-stu-id="7c004-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="7c004-212">Wybierz tę opcję, aby określić stawki podatku na podstawie łącznej wartości dla faktury, z uwzględnieniem wszelkich innych podatków.</span><span class="sxs-lookup"><span data-stu-id="7c004-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="7c004-213">Grupa podatków może zawierać tylko jeden kod podatku z tą wartością wybraną w polu Podstawa limitu.</span><span class="sxs-lookup"><span data-stu-id="7c004-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="7c004-214">Przykład</span><span class="sxs-lookup"><span data-stu-id="7c004-214">Example</span></span>

<span data-ttu-id="7c004-215">Stawki podatku są skonfigurowane przy użyciu następujących interwałów.</span><span class="sxs-lookup"><span data-stu-id="7c004-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="7c004-216">Ilość</span><span class="sxs-lookup"><span data-stu-id="7c004-216">Amount</span></span>             | <span data-ttu-id="7c004-217">Stawka podatkowa</span><span class="sxs-lookup"><span data-stu-id="7c004-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="7c004-218">0–50</span><span class="sxs-lookup"><span data-stu-id="7c004-218">0 - 50</span></span>             | <span data-ttu-id="7c004-219">30%</span><span class="sxs-lookup"><span data-stu-id="7c004-219">30%</span></span>      |
| <span data-ttu-id="7c004-220">50–100</span><span class="sxs-lookup"><span data-stu-id="7c004-220">50 - 100</span></span>           | <span data-ttu-id="7c004-221">20%</span><span class="sxs-lookup"><span data-stu-id="7c004-221">20%</span></span>      |
| <span data-ttu-id="7c004-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="7c004-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="7c004-223">10%</span><span class="sxs-lookup"><span data-stu-id="7c004-223">10%</span></span>      |

<span data-ttu-id="7c004-224">Podstawa limitu: **Kwota faktury z innymi podatkami** Metoda obliczania: **Zakres** </span><span class="sxs-lookup"><span data-stu-id="7c004-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="7c004-225">Każda lampa jest obłożona specjalnym cłem równym 5,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="7c004-226">Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku.</span><span class="sxs-lookup"><span data-stu-id="7c004-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="7c004-227">Kupujesz 8 lamp po 25,00 każda.</span><span class="sxs-lookup"><span data-stu-id="7c004-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="7c004-228">Kwota netto dla faktury wynosi 200,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="7c004-229">Kwota brutto dla faktury wynosi 200,00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="7c004-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="7c004-230">Podatek jest obliczany w następujący sposób: Łączny podatek = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="7c004-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="7c004-231">Aby uzyskać więcej informacji, zobacz [Opcje obliczania Cała kwota i Zakres dla kodów podatku](whole-amount-interval-options-sales-tax-codes.md) i [Wybieranie metody obliczeń podatków w polu podstawy](sales-tax-calculation-methods-origin-field.md)</span><span class="sxs-lookup"><span data-stu-id="7c004-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>




