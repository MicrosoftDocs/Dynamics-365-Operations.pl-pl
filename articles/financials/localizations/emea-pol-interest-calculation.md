---
title: Odsetki podatkowe i rynkowe w Polsce
description: W tym temacie omówiono proces konfigurowania i obliczania odsetek od podatku dla Polski.
author: ShylaThompson
manager: AnnBe
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Poland
ms.author: shylaw
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 5ee6c7c7d556c64f54849e02958ef34536ae1687
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549042"
---
# <a name="tax-interest-and-free-hand-interest"></a><span data-ttu-id="a7950-103">Odsetki podatkowe i rynkowe</span><span class="sxs-lookup"><span data-stu-id="a7950-103">Tax interest and free-hand interest</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a7950-104">W Polsce używane są dwa rodzaje stawek odsetek:</span><span class="sxs-lookup"><span data-stu-id="a7950-104">In Poland, two types of interest rates are used:</span></span>

- <span data-ttu-id="a7950-105">**Stawki odsetek podatkowych** są określane przez Ministerstwo Finansów.</span><span class="sxs-lookup"><span data-stu-id="a7950-105">**Tax interest rates** are specified by the Ministry of Finance.</span></span> <span data-ttu-id="a7950-106">Te stopy procentowe są także określane jako *ustawowe stopy odsetek*.</span><span class="sxs-lookup"><span data-stu-id="a7950-106">These interest rates are also referred to as *statutory interest rates*.</span></span>
- <span data-ttu-id="a7950-107">**Rynkowe stawki odsetek** są wynikiem negocjacji między dostawcą a odbiorcą.</span><span class="sxs-lookup"><span data-stu-id="a7950-107">**Free-hand interest rates** are negotiated between the vendor and the customer.</span></span>

> [!NOTE]
> <span data-ttu-id="a7950-108">Odsetki rynkowe mogą nie być obliczane, zależnie od umowy między odbiorcą a dostawcą.</span><span class="sxs-lookup"><span data-stu-id="a7950-108">Free-hand interest might not be calculated, depending on the agreement between the customer and the vendor.</span></span> <span data-ttu-id="a7950-109">Należy jednak obliczyć odsetki od podatków.</span><span class="sxs-lookup"><span data-stu-id="a7950-109">However, tax interest must be calculated.</span></span>

<span data-ttu-id="a7950-110">Zazwyczaj dostawca ustawia okres rozliczenia nie dłuższy niż 30 dni.</span><span class="sxs-lookup"><span data-stu-id="a7950-110">Usually, the vendor sets a settlement period that is no longer than 30 days.</span></span> <span data-ttu-id="a7950-111">Jednak mogą występować następujące sytuacje:</span><span class="sxs-lookup"><span data-stu-id="a7950-111">However, the following situations can arise:</span></span>

- <span data-ttu-id="a7950-112">Dostawca i nabywca zgadzają się na okres rozliczenia, który jest dłuższy niż 30 dni lub okres rozliczenia nie został ustawiony.</span><span class="sxs-lookup"><span data-stu-id="a7950-112">The vendor and customer agree on a settlement period that is longer than 30 days, or the settlement period isn't set.</span></span> <span data-ttu-id="a7950-113">W takim przypadku odsetki rynkowe mogą być obliczane od trzydziestego pierwszego dnia do daty wymagalności.</span><span class="sxs-lookup"><span data-stu-id="a7950-113">In this case, free-hand interest can be calculated from the thirty-first day until the due date.</span></span> <span data-ttu-id="a7950-114">Ewentualnie odsetki od podatków można obliczyć, aż do daty płatności.</span><span class="sxs-lookup"><span data-stu-id="a7950-114">Alternatively, tax interest can be calculated until the date of payment.</span></span>
- <span data-ttu-id="a7950-115">Okres rozliczeniowy jest krótszy niż 30 dni.</span><span class="sxs-lookup"><span data-stu-id="a7950-115">The settlement period is shorter than 30 days.</span></span> <span data-ttu-id="a7950-116">W takim przypadku dostawca może obliczyć odsetki podatkowe od dnia wymagalności aż do dnia zapłaty.</span><span class="sxs-lookup"><span data-stu-id="a7950-116">In this case, the vendor can calculate tax interest from the due date until the date of payment.</span></span>

## <a name="setup"></a><span data-ttu-id="a7950-117">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="a7950-117">Setup</span></span>

<span data-ttu-id="a7950-118">Zanim będzie można obliczać odsetki od podatków i odsetki rynkowe, należy wykonać następujące zadania konfiguracyjne.</span><span class="sxs-lookup"><span data-stu-id="a7950-118">Before you can calculate tax interest and free-hand interest, you must complete the following setup tasks.</span></span>

### <a name="set-up-the-accounts-receivable-parameters-to-calculate-interest"></a><span data-ttu-id="a7950-119">Konfigurowanie parametrów rozrachunków z odbiorcami do obliczania odsetek</span><span class="sxs-lookup"><span data-stu-id="a7950-119">Set up the Accounts receivable parameters to calculate interest</span></span>

<span data-ttu-id="a7950-120">Użyj tej procedury do zdefiniowania parametrów dla obliczania odsetek w module rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="a7950-120">Use this procedure to define the parameters for interest calculation in Accounts receivable.</span></span> 

1. <span data-ttu-id="a7950-121">Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="a7950-121">Select **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="a7950-122">Na stronie **Parametry modułu rozrachunków z odbiorcami** na stronie **Windykacja** na skróconej karcie **Odsetki i opłaty** w polu **Obliczanie odsetek** wybierz transakcje, dla których powinny zostać obliczone odsetki.</span><span class="sxs-lookup"><span data-stu-id="a7950-122">On the **Accounts receivable parameters** page, on the **Collections** tab, on the **Interest and fees** FastTab, in the **Interest calculation** field, select the transactions that interest should be calculated for.</span></span>

### <a name="set-up-interest-codes"></a><span data-ttu-id="a7950-123">Skonfiguruj kody odsetek</span><span class="sxs-lookup"><span data-stu-id="a7950-123">Set up interest codes</span></span>

<span data-ttu-id="a7950-124">Procedura ta służy do ustawiania i obsługi kodów odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-124">Use this procedure to set up and maintain interest codes.</span></span> <span data-ttu-id="a7950-125">Kody odsetek zawierają ustawienia określające, kiedy odsetki są nakładane i jak są obliczane na kontach zaległych.</span><span class="sxs-lookup"><span data-stu-id="a7950-125">Interest codes contain settings that determine when interest is charged, and how it's calculated on overdue accounts.</span></span>

1. <span data-ttu-id="a7950-126">Wybierz kolejno opcje **Kredyty i windykacja** &gt; **Odsetki** &gt; **Skonfiguruj kody odsetek**.</span><span class="sxs-lookup"><span data-stu-id="a7950-126">Select **Credit and collections** &gt; **Interest** &gt; **Set up interest codes**.</span></span>
2. <span data-ttu-id="a7950-127">Na stronie **Odsetki** w polu **Kod odsetek** wprowadź unikatowy kod, który ma być używany do obliczania odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-127">On the **Interest** page, in the **Interest code** field, enter a unique code that should be used to calculate interest.</span></span>
3. <span data-ttu-id="a7950-128">Umożliwia wprowadzenie opisu kodu odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-128">Enter a description of the interest code.</span></span>
4. <span data-ttu-id="a7950-129">W polu **Okres prolongaty** wprowadź liczbę dni, po upływie których zostaną obliczone odsetki.</span><span class="sxs-lookup"><span data-stu-id="a7950-129">In the **Grace period** field, enter the number of days before interest is calculated.</span></span>
5. <span data-ttu-id="a7950-130">Na skróconej karcie **Zarobki** w polu **Konto księgowania w księdze** wybierz numer konta księgowego dla zysków z odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-130">On the **Earnings** FastTab, in the **Ledger posting account** field, select the ledger account number for interest earnings.</span></span>
6. <span data-ttu-id="a7950-131">Na karcie skróconej karcie **Płatności** w polu **Konto księgowania w księdze** wybierz numer konta księgowego dla płatności z tytułu odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-131">On the **Payments** FastTab, in the **Ledger posting account** field, select the ledger account number for interest payments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7950-132">Odsetki są obliczane od daty płatności.</span><span class="sxs-lookup"><span data-stu-id="a7950-132">The interest is calculated from the payment date.</span></span>

7. <span data-ttu-id="a7950-133">Na skróconej karcie **Zarobki** w polu **Podstawa naliczania odsetek** wybierz opcję **Procent** lub **Kwota**.</span><span class="sxs-lookup"><span data-stu-id="a7950-133">On the **Earnings** FastTab, in the **Calculate interest based on** field, select either **Percentage** or **Amount**.</span></span> <span data-ttu-id="a7950-134">W przypadku wybrania opcji **Procent** wprowadź stawkę odsetek podatkowych w polu **Miesięczne odsetki w %**.</span><span class="sxs-lookup"><span data-stu-id="a7950-134">If you select **Percentage**, enter the tax interest rate in the **Monthly interest %** field.</span></span>
8. <span data-ttu-id="a7950-135">Powtórz krok 7 na skróconej karcie **Płatności**.</span><span class="sxs-lookup"><span data-stu-id="a7950-135">Repeat step 7 on the **Payments** FastTab.</span></span>

### <a name="set-up-a-number-sequence-code-for-the-interest-note-and-voucher"></a><span data-ttu-id="a7950-136">Konfigurowanie kodu numeracji dla noty odsetkowej i załącznika</span><span class="sxs-lookup"><span data-stu-id="a7950-136">Set up a number sequence code for the interest note and voucher</span></span>

<span data-ttu-id="a7950-137">Użyj tej procedury, aby ustawić sekwencję liczbową, która jest używana dla not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="a7950-137">Use this procedure to set up the number sequence that is used for interest notes.</span></span> <span data-ttu-id="a7950-138">Podczas tworzenia noty odsetkowej identyfikator dokumentu zostanie automatycznie przypisany w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="a7950-138">When you create an interest note, the document number is automatically assigned in a sequence.</span></span>

1. <span data-ttu-id="a7950-139">Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="a7950-139">Select **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="a7950-140">Na stronie **Parametry modułu rozrachunków z odbiorcami** na karcie **Sekwencje numerów** zaznacz kod numeracji dla odwołania **Nota odsetkowa**.</span><span class="sxs-lookup"><span data-stu-id="a7950-140">On the **Accounts receivable parameters** page, on the **Number sequences** tab, select a number sequence code for the **Interest note** reference.</span></span>
3. <span data-ttu-id="a7950-141">Wybierz kod numeracji dla odwołania **Załącznik noty odsetkowej**.</span><span class="sxs-lookup"><span data-stu-id="a7950-141">Select a number sequence code for the **Interest note voucher** reference.</span></span>

### <a name="set-up-customer-posting-profiles"></a><span data-ttu-id="a7950-142">Konfigurowanie profili księgowania odbiorców</span><span class="sxs-lookup"><span data-stu-id="a7950-142">Set up customer posting profiles</span></span>

<span data-ttu-id="a7950-143">Aby uzyskać więcej informacji, zobacz [Profile księgowania odbiorców](../accounts-receivable/customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a7950-143">For more information, see [Customer posting profiles](../accounts-receivable/customer-posting-profiles.md).</span></span>

## <a name="calculate-tax-interest-and-free-hand-interest"></a><span data-ttu-id="a7950-144">Obliczanie odsetek od podatku i odsetek rynkowych</span><span class="sxs-lookup"><span data-stu-id="a7950-144">Calculate tax interest and free-hand interest</span></span>

<span data-ttu-id="a7950-145">W Polsce stawki odsetek od podatku określa Minister Finansów.</span><span class="sxs-lookup"><span data-stu-id="a7950-145">In Poland, the tax interest rates are determined by the Ministry of Finance.</span></span> <span data-ttu-id="a7950-146">Dostawca oblicza odsetki, jeśli nastąpi rozliczenie płatności po terminie płatności.</span><span class="sxs-lookup"><span data-stu-id="a7950-146">The vendor calculates the interest if the payment settlement is made after the due date.</span></span> <span data-ttu-id="a7950-147">Jeśli okres płatności jest krótszy niż 30 dni, dostawca może obliczać odsetki od podatku począwszy od daty należności, aż do daty płatności.</span><span class="sxs-lookup"><span data-stu-id="a7950-147">If the payment period is shorter than 30 days, the vendor can calculate the tax interest from the due date through the payment date.</span></span> <span data-ttu-id="a7950-148">Stawki odsetek rynkowych są stosowane, gdy płatności są rozliczane między trzydziestym pierwszym dniem po księgowaniu a datą płatności.</span><span class="sxs-lookup"><span data-stu-id="a7950-148">Free-hand interest rates apply when payments are settled between the thirty-first day after the posting and the due date.</span></span>

1. <span data-ttu-id="a7950-149">Wybierz kolejno opcje **Kredyty i windykacja** &gt; **Odsetki** &gt; **Utwórz noty odsetkowe**.</span><span class="sxs-lookup"><span data-stu-id="a7950-149">Select **Credit and collections** &gt; **Interest** &gt; **Create interest notes**.</span></span>
2. <span data-ttu-id="a7950-150">W oknie dialogowym **Obliczanie odsetek** w ustawieniu **Faktura** zaznacz wartość **Tak**, aby obliczać odsetki na fakturach.</span><span class="sxs-lookup"><span data-stu-id="a7950-150">In the **Interest calculation** dialog box, set the **Invoice** option to **Yes** to calculate interest on invoices.</span></span>
3. <span data-ttu-id="a7950-151">W ustawieniu **Faktura korygująca** zaznacz opcję **Tak** , aby odliczać faktury korygujące odbiorcy przed obliczeniem odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-151">Set the **Credit note** option to **Yes** to deduct customer credit notes before the interest calculation.</span></span>
4. <span data-ttu-id="a7950-152">W ustawieniu **Płatność** zaznacz opcję **Tak**, aby przed obliczeniem odsetek odliczyć płatności od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a7950-152">Set the **Payment** option to **Yes** to deduct customer payments before the interest calculation.</span></span>
5. <span data-ttu-id="a7950-153">W ustawieniu **Odsetki** zaznacz opcję **Tak**, aby obliczać odsetki składane od poprzednich not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="a7950-153">Set the **Interest** option to **Yes** to calculate compound interest on previous interest notes.</span></span>
6. <span data-ttu-id="a7950-154">W polu **Od dnia** wybierz datę początkową obliczania odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-154">In the **From date** field, select the start date for the interest calculation.</span></span> <span data-ttu-id="a7950-155">Obliczanie uwzględnia transakcje, których termin mija w tym dniu lub później.</span><span class="sxs-lookup"><span data-stu-id="a7950-155">The calculation will include transactions that are due on or after this date.</span></span>
7. <span data-ttu-id="a7950-156">W polu **Do dnia** wybierz datę końcową obliczania odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-156">In the **To date** field, select the end date for the interest calculation.</span></span>
8. <span data-ttu-id="a7950-157">W polu **Zaokrąglenie** określ jednostki zaokrąglania kwoty odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-157">In the **Round-off** field, specify the units to round off the interest amount to.</span></span>
9. <span data-ttu-id="a7950-158">W polu **Użyj profilu księgowania z** wybierz profil księgowania, który ma być używany:</span><span class="sxs-lookup"><span data-stu-id="a7950-158">In the **Use posting profile from** field, select the posting profile that should be used:</span></span>

    - <span data-ttu-id="a7950-159">**Konto** — używanie profilu księgowania z odpowiedniego konta odbiorcy dla każdej noty odsetkowej.</span><span class="sxs-lookup"><span data-stu-id="a7950-159">**Account** – Use the posting profile from the relevant customer account for each interest note.</span></span>
    - <span data-ttu-id="a7950-160">**Wybierz** — Używanie profilu księgowania określonego w polu **Profil księgowania**.</span><span class="sxs-lookup"><span data-stu-id="a7950-160">**Select** – Use the posting profile that is specified in the **Posting profile** field.</span></span>
    
10. <span data-ttu-id="a7950-161">Jeśli w polu **Użyj profilu księgowania z** wybrano opcję **Wybierz**, to w polu **Profil księgowania** należy wybrać profil księgowania dla obliczenia.</span><span class="sxs-lookup"><span data-stu-id="a7950-161">If you selected **Select** in the **Use posting profile from** field, in the **Posting profile** field, select the posting profile for the calculation.</span></span>
11. <span data-ttu-id="a7950-162">W ustawieniu **Odsetki od podatków** zaznacz opcję **Tak**, aby obliczać odsetki rynkowe oraz odsetki od podatków.</span><span class="sxs-lookup"><span data-stu-id="a7950-162">Set the **Tax interest** option to **Yes** to calculate the free-hand interest and tax interest.</span></span>
12. <span data-ttu-id="a7950-163">Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtr**, aby znaleźć i wybrać rekordy dla obliczania odsetek.</span><span class="sxs-lookup"><span data-stu-id="a7950-163">On the **Records to include** FastTab, select **Filter** to find and select records for the interest calculation.</span></span>
13. <span data-ttu-id="a7950-164">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7950-164">Select **OK**.</span></span>
