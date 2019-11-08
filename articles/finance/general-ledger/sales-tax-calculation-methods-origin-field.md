---
title: Wybieranie metody obliczeń podatków w polu podstawy
description: W tym artykule opisano opcje dostępne w polu Podstawy opodatkowania na stronie kodów podatków oraz sposób obliczania podatku na podstawie wybranej opcji kodu podatku.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37bb02dfc9cfcb3e2c1dcda446be3945563d6594
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570587"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="5cc13-103">Wybieranie metody obliczeń podatków w polu podstawy</span><span class="sxs-lookup"><span data-stu-id="5cc13-103">Sales tax calculation methods in the Origin field</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cc13-104">W tym artykule opisano opcje dostępne w polu Podstawy opodatkowania na stronie kodów podatków oraz sposób obliczania podatku na podstawie wybranej opcji kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="5cc13-105">Dla każdego kodu podatku utworzonego na stronie Kody podatku należy wybrać metodę obliczeń, która będzie stosowana w odniesieniu do kwoty podstawy podatku w polu Podstawa.</span><span class="sxs-lookup"><span data-stu-id="5cc13-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="5cc13-106">Procent od kwoty netto</span><span class="sxs-lookup"><span data-stu-id="5cc13-106">Percentage of net amount</span></span>
<span data-ttu-id="5cc13-107">Metoda obliczania wartości procentowej kwoty netto jest wartością domyślną w polu Podstawa.</span><span class="sxs-lookup"><span data-stu-id="5cc13-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="5cc13-108">Podatek jest obliczany jako procent kwoty zakupu lub kwoty sprzedaży niezawierających jakichkolwiek podatków.</span><span class="sxs-lookup"><span data-stu-id="5cc13-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="5cc13-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="5cc13-109">Example</span></span>

<span data-ttu-id="5cc13-110">Stawka podatku = 25%.</span><span class="sxs-lookup"><span data-stu-id="5cc13-110">The tax rate is 25%.</span></span> <span data-ttu-id="5cc13-111">Wiersz faktury zawiera 10 sztuk towaru po 1,00 USD, a odbiorca ma rabat wiersza w wysokości 10%.</span><span class="sxs-lookup"><span data-stu-id="5cc13-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="5cc13-112">Kwota netto: (10 x 1,00) -10% = 9,00 Podatek: 9,00 x 25% = 2,25 Łączna kwota: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="5cc13-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="5cc13-113"> Procent od kwoty brutto</span><span class="sxs-lookup"><span data-stu-id="5cc13-113">Percentage of gross amount</span></span>
<span data-ttu-id="5cc13-114">Jeśli wybierzesz metodę Procent od kwoty brutto, podatek jest obliczany jako procent kwoty sprzedaży brutto.</span><span class="sxs-lookup"><span data-stu-id="5cc13-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="5cc13-115">Kwota brutto to kwota netto wiersza plus wszystkie podatki i opłaty dla wiersza, z wyjątkiem podatku z podstawą = procent od kwoty brutto.</span><span class="sxs-lookup"><span data-stu-id="5cc13-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="5cc13-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="5cc13-116">Example</span></span>

<span data-ttu-id="5cc13-117">Urząd skarbowy nałożył na dany towar specjalne cła.</span><span class="sxs-lookup"><span data-stu-id="5cc13-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="5cc13-118">Kwoty ceł są dodawane do kwoty netto przed obliczeniem podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="5cc13-119">Kody podatków:</span><span class="sxs-lookup"><span data-stu-id="5cc13-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="5cc13-120">CŁO 1 = 10%, przy użyciu metody obliczeń Procent od kwoty netto</span><span class="sxs-lookup"><span data-stu-id="5cc13-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="5cc13-121">CŁO 2 = 20%, przy użyciu metody obliczeń Procent od kwoty netto</span><span class="sxs-lookup"><span data-stu-id="5cc13-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="5cc13-122">PODATEK = 25%, przy użyciu metody obliczeń Procent od kwoty brutto</span><span class="sxs-lookup"><span data-stu-id="5cc13-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="5cc13-123">Jeśli kwota netto = 10,00, wtedy cło 1 = 1,00 x 10.00%= 10 , a cło 2 = 2,00 x 10.00% = 20.</span><span class="sxs-lookup"><span data-stu-id="5cc13-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="5cc13-124">Kwoty będą następujące: Kwota brutto: kwota netto + CŁO 1 + CŁO 2 (10,00 + 1,00 + 2,00) = 13,00 PODATEK = 13,00 x 25% = 3,25 CŁA I PODATEK łącznie: 1,00 + 2,00 + 3,25 = 6,25 Suma: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="5cc13-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>

| <span data-ttu-id="5cc13-125">**Uwaga**</span><span class="sxs-lookup"><span data-stu-id="5cc13-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5cc13-126">Tylko jeden kod z Podstawą = Procent od kwoty brutto może być użyty w transakcji.</span><span class="sxs-lookup"><span data-stu-id="5cc13-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="5cc13-127">Jeśli więcej niż jeden taki kod podatku jest określony dla transakcji, zostanie wyświetlony błąd z informacją, że nie można obliczyć podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |


<a name="percentage-of-sales-tax"></a><span data-ttu-id="5cc13-128">Procent od podatku</span><span class="sxs-lookup"><span data-stu-id="5cc13-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="5cc13-129">Po wybraniu opcji Procent od sprzedaży w polu Podstawa, podatek jest obliczany jako procent podatku zaznaczonego w podatku w polu Podatek.</span><span class="sxs-lookup"><span data-stu-id="5cc13-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="5cc13-130">Najpierw jest obliczany podatek wybrany w opcji podatek w polu Podatek.</span><span class="sxs-lookup"><span data-stu-id="5cc13-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="5cc13-131">Na podstawie kwoty pierwszego podatku jest następnie obliczany drugi podatek.</span><span class="sxs-lookup"><span data-stu-id="5cc13-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="5cc13-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="5cc13-132">Example</span></span>

<span data-ttu-id="5cc13-133">Kody podatków:</span><span class="sxs-lookup"><span data-stu-id="5cc13-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="5cc13-134">CŁO 1 = 10%, przy użyciu metody Procent od kwoty netto</span><span class="sxs-lookup"><span data-stu-id="5cc13-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="5cc13-135">CŁO 2 = 20% przy użyciu metody Procent podatku, z cło 1 w opcji podatek w polu Podatek</span><span class="sxs-lookup"><span data-stu-id="5cc13-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="5cc13-136">PODATEK = 25%, przy użyciu metody obliczeń Procent od kwoty brutto</span><span class="sxs-lookup"><span data-stu-id="5cc13-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="5cc13-137">Kwota netto: 10,00 cło 1: 10,00 x 10% = 1,00 cło 2: 1,00 x 20% = 0,20 kwota brutto: 10,00 + 1,00 + 0,20 = 11,20 podatek: 11,20 x 25% = 2.80 Suma ceł i podatek: 1,00 + 0,20 + 2,80 = 4,00 łączna kwota: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="5cc13-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>

| <span data-ttu-id="5cc13-138">**Uwaga**</span><span class="sxs-lookup"><span data-stu-id="5cc13-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5cc13-139">Nie można używać wielu poziomów podatku w obliczeniach podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="5cc13-140">Podatek nie może być obliczany na podstawie podatku, który już jest obliczony na podstawie innego podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="5cc13-141">Można obliczyć wiele jednopoziomowych podatków dla kodu podatku w transakcji.</span><span class="sxs-lookup"><span data-stu-id="5cc13-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="5cc13-142"> Kwota na jednostkę</span><span class="sxs-lookup"><span data-stu-id="5cc13-142">Amount per unit</span></span>
<span data-ttu-id="5cc13-143">Po wybraniu opcji Kwota na jednostkę w polu Podstawa, podatek jest obliczany jako stała kwota na jednostkę pomnożona przez ilość wpisana w wierszu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5cc13-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="5cc13-144">Jednostka musi zostać określona polu Jednostka.</span><span class="sxs-lookup"><span data-stu-id="5cc13-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="5cc13-145">Kwota na jednostkę jest określana na stronie Wartości kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="5cc13-146">Przykład</span><span class="sxs-lookup"><span data-stu-id="5cc13-146">Example</span></span>

<span data-ttu-id="5cc13-147">Kod podatku jest skonfigurowany jako: 1,20 USD na jednostkę = pole W wierszu faktury sprzedaży 25 opakowań towaru jest sprzedanych Podatek jest obliczany jako 25 x 1,20 = 30,00.</span><span class="sxs-lookup"><span data-stu-id="5cc13-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>

| <span data-ttu-id="5cc13-148">**Uwaga**</span><span class="sxs-lookup"><span data-stu-id="5cc13-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5cc13-149">Jeśli transakcja zostanie wprowadzona w jednostce innej niż jednostka określona w kodzie podatku, jest ona automatycznie konwertowana w oparciu o konwersje jednostek ustawiane na stronie Konwersje jednostek.</span><span class="sxs-lookup"><span data-stu-id="5cc13-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="5cc13-150"> Kwota na jednostkę (opcja dodatkowa)</span><span class="sxs-lookup"><span data-stu-id="5cc13-150">Amount per unit, additional option</span></span>

<span data-ttu-id="5cc13-151">Na karcie Obliczanie, można wybrać, czy podatek obliczany na jednostkę jest obliczany przed innymi kodami podatków i dodawany do kwoty netto przed obliczeniem innych kodów podatków z Podstawą = Procent od kwoty netto.</span><span class="sxs-lookup"><span data-stu-id="5cc13-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="5cc13-152">Przykłady</span><span class="sxs-lookup"><span data-stu-id="5cc13-152">Examples</span></span>

<span data-ttu-id="5cc13-153">Załóżmy, że obliczamy 2 kody podatków dla transakcji:</span><span class="sxs-lookup"><span data-stu-id="5cc13-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="5cc13-154">CŁO: Podstawa = Kwota na jednostkę oraz podatek, wartość jest ustawiona na 5,00 na jednostkę = szt.</span><span class="sxs-lookup"><span data-stu-id="5cc13-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="5cc13-155">PODATEK: Źródło = jak pokazano w poniższych przykładach, wartość jest równa 25%</span><span class="sxs-lookup"><span data-stu-id="5cc13-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="5cc13-156">Sprzedajemy 1 sztukę towaru w cenie jednostkowej 10,00.</span><span class="sxs-lookup"><span data-stu-id="5cc13-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="5cc13-157">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="5cc13-157">Example 1</span></span>

<span data-ttu-id="5cc13-158">PODATEK: Źródło = metoda obliczeń Procent od kwoty brutto Opcja Oblicz przed naliczeniem podatku jest ignorowana, ponieważ PODATEK jest obliczany jako procent od kwoty brutto.</span><span class="sxs-lookup"><span data-stu-id="5cc13-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="5cc13-159">CŁO: 1 x 5,00 = 5,00 Kwota brutto: 10,00 + 5,00 = 15,00 PODATEK: 15,00 x 25% = 3,75 Całkowity podatek: 5,00 + 3,75 = 8,75 Łączna kwota: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="5cc13-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="5cc13-160">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="5cc13-160">Example 2</span></span>

<span data-ttu-id="5cc13-161">PODATEK: Źródło = Procent od kwoty netto Opcja Oblicz przed naliczeniem podatku nie jest zaznaczona dla obliczania CŁA.</span><span class="sxs-lookup"><span data-stu-id="5cc13-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="5cc13-162">Kwota netto: 10,00 CŁO: 1 x 5,00 = 5,00 PODATEK: 10,00 x 25% = 2,50 Całkowity podatek: 5,00 + 2,50 = 7,50 Łączna kwota: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="5cc13-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="5cc13-163">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="5cc13-163">Example 3</span></span>

<span data-ttu-id="5cc13-164">PODATEK: Źródło = Procent od kwoty netto Opcja Oblicz przed naliczeniem podatku jest zaznaczona dla obliczania CŁA.</span><span class="sxs-lookup"><span data-stu-id="5cc13-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="5cc13-165">Kwota netto: 10,00 CŁO: 1 x 5,00 = 5,00 PODATEK: (10,00 + 5,00) x 25% = 3,75 Całkowity podatek: 5,00 + 3,75 = 8,75 Łączna kwota: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="5cc13-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="5cc13-166">Przykład 4</span><span class="sxs-lookup"><span data-stu-id="5cc13-166">Example 4</span></span>

<span data-ttu-id="5cc13-167">Wyniki z przykładów 3 i 1 są takie same, ponieważ nałożono tylko jedno cło.</span><span class="sxs-lookup"><span data-stu-id="5cc13-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="5cc13-168">Załóżmy, że masz dwa CŁA, a tylko jedno z nich jest uwzględniane w kwocie netto do obliczania podatku: CŁO 1: 5,00, przy użyciu metody Kwota na jednostkę i opcja Oblicz przed naliczeniem podatku jest zaznaczona CŁO 2: 2,50, przy użyciu metody Kwota na jednostkę i opcja Oblicz przed naliczeniem podatku nie jest zaznaczona Podatek: 25%, przy użyciu metody Procent od kwoty netto Kwota netto: 10,00 CŁO 1: 1 x 5,00 CŁO 2: 1 x 2,50 = 2,50 Kwota netto do opodatkowani: 10,00 + 5,00 = 15,00 PODATEK: 15.00 x 25% = 3,75 Suma podatku uwzględniająca cła: 5.00 + 2,50 + 3,75 = 11,25 Łączna kwota: 10,00 + 11,25 = 21,25 25% PODATKU jest obliczane dla sumy kwoty netto (10,00) + CŁO 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="5cc13-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="5cc13-169">CŁO 2 jest dodawane do kwoty podatku po obliczeniu podatku.</span><span class="sxs-lookup"><span data-stu-id="5cc13-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="5cc13-170"> Obliczony procent kwoty netto</span><span class="sxs-lookup"><span data-stu-id="5cc13-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="5cc13-171">Obliczony procent kwoty netto obsługuje obliczanie podatku inaczej w zależności od ustawienia parametru Kwoty zawierają podatek dla dokumentu lub arkusza.</span><span class="sxs-lookup"><span data-stu-id="5cc13-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="5cc13-172">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="5cc13-172">Example 1</span></span>

<span data-ttu-id="5cc13-173">Dokument/arkusz jest ustawiony na Kwoty zawierają podatek = Tak Kwota wiersza transakcji: 10,00 Stawka podatku: 25% Podatek: Kwota wiersza transakcji x stawka podatku (10,00 x 25%) = 2,50 Kwota podstawy podatku (kwota źródła): Kwota wiersza transakcji - Podatek (10,00 - 2,50) = 7,50)</span><span class="sxs-lookup"><span data-stu-id="5cc13-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="5cc13-174">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="5cc13-174">Example 2</span></span>

<span data-ttu-id="5cc13-175">Dokument/arkusz jest ustawiony na Kwoty zawierają podatek = Nie Kwota wiersza transakcji: 10,00 Stawka podatku: 25% Podatek: (Kwota wiersza transakcji x stawka podatku) / (100 - stawka podatku) (10,00 x 25%) / (100% - 25%) = 3,33 Kwota podstawy podatku (kwota źródła): Kwota wiersza transakcji = 10,00</span><span class="sxs-lookup"><span data-stu-id="5cc13-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="additional-resources"></a><span data-ttu-id="5cc13-176">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5cc13-176">Additional resources</span></span>
--------

[<span data-ttu-id="5cc13-177">Ustalanie stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania</span><span class="sxs-lookup"><span data-stu-id="5cc13-177">Determining sale tax rates based on the Marginal base and Calculation method fields</span></span>](marginal-base-field.md)

[<span data-ttu-id="5cc13-178">Opcje Cała kwota i Obliczanie interwału dla kodów podatku</span><span class="sxs-lookup"><span data-stu-id="5cc13-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)



