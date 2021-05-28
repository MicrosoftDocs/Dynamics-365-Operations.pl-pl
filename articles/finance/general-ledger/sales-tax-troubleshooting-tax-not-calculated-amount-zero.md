---
title: Podatek nie został obliczony lub kwota podatku wynosi zero
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w sytuacji, gdy kwota podatku wynosi 0 (zero) lub podatek nie został obliczony.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c398579a0a408e7f5625a3e801a967955c4b1e5b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020122"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="c8cb4-103">Podatek nie został obliczony lub kwota podatku wynosi zero</span><span class="sxs-lookup"><span data-stu-id="c8cb4-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8cb4-104">Transakcja może zawierać kwotę wiersza różną od 0 (zero), ale nie obliczono podatku albo obliczona kwota podatku wynosi 0.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="c8cb4-105">W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="c8cb4-106">Sprawdzanie, czy kody podatku są poprawnie wybrane przez transakcję</span><span class="sxs-lookup"><span data-stu-id="c8cb4-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="c8cb4-107">Jeśli transakcja nie wybierze poprawnych kodów podatków lub nie wybierze żadnych kodów podatków, podatki od niej nie będą obliczane.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="c8cb4-108">Wykonaj następujące kroki, aby sprawdzić, czy kody podatku są poprawnie wybrane przez transakcję.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="c8cb4-109">W wierszu transakcji, na skróconej karcie **Szczegóły wiersza**, na karcie **Ustawienia**, w sekcji **Podatek** sprawdź, czy w polach **Grupa podatków dla towaru** i **Grupa podatków** zostały wybrane poprawne grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="c8cb4-110">Jeśli nie wybrano prawidłowych grup podatków, należy je wybrać.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="c8cb4-111">[![Pola Grupa podatków dla towaru i Grupa podatków](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="c8cb4-112">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="c8cb4-113">Wybierz odpowiednią grupę podatków, a następnie na skróconej karcie **Ustawienia** zanotuj kod podatku w polu **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="c8cb4-114">[![Strona Grupy podatków](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="c8cb4-115">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków dla towaru**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="c8cb4-116">Wybierz odpowiednią grupę podatków dla towaru, a następnie na skróconej karcie **Ustawienia** sprawdź, czy kod podatku w polu **Kod podatku** odpowiada kodowi podatku grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="c8cb4-117">[![Strona Grupy podatków dla towaru](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="c8cb4-118">Jeśli kody podatków są różne, zaktualizuj kod podatku jednej z grup.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="c8cb4-119">Sprawdź, czy wybrane kody podatków nie podlegają zwolnieniu z podatku i mają prawidłową wartość stawki podatku</span><span class="sxs-lookup"><span data-stu-id="c8cb4-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="c8cb4-120">Jeśli kody podatków są zwolnione lub stawka podatku wynosi 0 (zero), wynikiem obliczenia podatku będzie 0.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="c8cb4-121">Aby sprawdzić, czy wybrane kody podatków są zwolnione z podatku i czy jest do nich stosowana właściwa stawka podatku, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="c8cb4-122">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="c8cb4-123">Wybierz odpowiednią grupę podatków, a następnie na skróconej karcie **Ustawienia** sprawdź, czy pole wyboru **Zwolnienie** nie jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="c8cb4-124">Jeśli jest zaznaczone, usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="c8cb4-125">[![Pole wyboru Zwolnienie na stronie Grupy podatków](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="c8cb4-126">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="c8cb4-127">Wybierz odpowiedni kod podatku, a następnie sprawdź, czy wartość stawki podatku w polu **Wartość** nie jest równa 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c8cb4-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="c8cb4-128">Jeśli wynosi 0, należy zaktualizować to pole, tak aby było ustawione na poprawną stawkę podatku.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="c8cb4-129">[![Pole Wartość na stronie Wartości kodu podatku](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="c8cb4-130">Określanie, czy zero jest poprawną kwotą podatku</span><span class="sxs-lookup"><span data-stu-id="c8cb4-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="c8cb4-131">W niektórych scenariuszach kwota podatku 0 (zero) jest poprawna.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="c8cb4-132">Aby określić, czy wartość 0 jest właściwą kwotą podatku dla transakcji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="c8cb4-133">Przejdź do pozycji **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="c8cb4-134">Sprawdź, czy wybrano wartość **Suma** na karcie **Podatek** w polu **Metoda obliczania**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="c8cb4-135">[![Pole Metoda obliczania na stronie Parametry księgi głównej](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="c8cb4-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="c8cb4-136">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="c8cb4-137">Wybierz odpowiedni kod podatku, wybierz opcje **Obliczanie** \> **Podstawa limitu** i sprawdź, czy podstawa limitu jest ustawiona na wartość **Kwota netto faktury** lub **Kwota faktury z innymi podatkami**.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="c8cb4-138">Aby uzyskać więcej informacji, zobacz temat [Suma faktury z innymi podatkami](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="c8cb4-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="c8cb4-139">Jeśli w krokach 2 i 4 określone są poprawne wartości, należy określić, czy łączna kwota transakcji wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c8cb4-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="c8cb4-140">Jeśli łączna kwota wynosi 0, należy oczekiwać kwoty podatku w wysokości 0.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="c8cb4-141">Ponieważ obliczenie podatku jest oparte na łącznej kwocie salda faktury i ta kwota nie jest wiersz po wierszu, kwota podatku w wysokości 0 zostanie przydzielona do każdego wiersza po obliczeniu podatku.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="c8cb4-142">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="c8cb4-142">Determine whether customization exists</span></span>

<span data-ttu-id="c8cb4-143">Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="c8cb4-144">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="c8cb4-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
