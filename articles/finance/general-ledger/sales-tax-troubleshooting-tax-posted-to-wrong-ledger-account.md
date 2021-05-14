---
title: Podatek jest księgowany na niewłaściwym koncie księgowym w załączniku
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc przy księgowanie podatku na niewłaściwym koncie księgowym w załączniku.
author: qire
manager: beya
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0404d71f0492e188ed5da62387bb90a336e69c5a
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947693"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a><span data-ttu-id="271b7-103">Podatek jest księgowany na niewłaściwym koncie księgowym w załączniku</span><span class="sxs-lookup"><span data-stu-id="271b7-103">Tax is posted to the wrong ledger account in the voucher</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="271b7-104">Podczas księgowania podatek może być księgowany na niewłaściwym koncie księgowym w załączniku.</span><span class="sxs-lookup"><span data-stu-id="271b7-104">During posting, tax might be posted to the wrong ledger account in the voucher.</span></span> <span data-ttu-id="271b7-105">W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="271b7-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span> <span data-ttu-id="271b7-106">W przykładach w tym temacie jako dokument biznesowy przyjmuje się zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="271b7-106">The examples in this topic use a sales order as the business document.</span></span>

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a><span data-ttu-id="271b7-107">Znajdowanie kodu podatku niepoprawnie zaksięgowanej transakcji podatkowej</span><span class="sxs-lookup"><span data-stu-id="271b7-107">Find the tax code of the incorrectly posted tax transaction</span></span>

1. <span data-ttu-id="271b7-108">Na stronie **Transakcje na załączniku** wybierz transakcję, którą chcesz się zajmować, a następnie wybierz pozycję **Zaksięgowany podatek**.</span><span class="sxs-lookup"><span data-stu-id="271b7-108">On the **Voucher transactions** page, select the transaction that you want to work with, and then select **Posted sales tax**.</span></span>

    <span data-ttu-id="271b7-109">[![Przycisk Zaksięgowany podatek na stronie Transakcje na załączniku](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-109">[![Posted sales tax button on the Voucher transactions page](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)</span></span>

2. <span data-ttu-id="271b7-110">Przejrzyj wartość w polu **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="271b7-110">Review the value in the **Sales tax code** field.</span></span> <span data-ttu-id="271b7-111">W tym przykładzie jest to **VAT 19**.</span><span class="sxs-lookup"><span data-stu-id="271b7-111">In this example, it's **VAT 19**.</span></span>

    <span data-ttu-id="271b7-112">[![Pole kodu podatku na stronie Zaksięgowany podatek](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-112">[![Sales tax code field on the Posted sales tax page](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)</span></span>

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a><span data-ttu-id="271b7-113">Weryfikacja grupy księgowania w księdze kodu podatku</span><span class="sxs-lookup"><span data-stu-id="271b7-113">Check the ledger posting group of the tax code</span></span>

1. <span data-ttu-id="271b7-114">Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.</span><span class="sxs-lookup"><span data-stu-id="271b7-114">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="271b7-115">Znajdź i wybierz kod podatku, a następnie przejrzyj wartość w polu **Grupa księgowania w księdze**.</span><span class="sxs-lookup"><span data-stu-id="271b7-115">Find and select the tax code, and then review the value in the **Ledger posting group** field.</span></span> <span data-ttu-id="271b7-116">W tym przykładzie jest to **VAT**.</span><span class="sxs-lookup"><span data-stu-id="271b7-116">In this example, it's **VAT**.</span></span>

    <span data-ttu-id="271b7-117">[![Pole Księgowanie podatku w księdze na stronie Kody podatku](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-117">[![Ledger posting group field on the Sales tax codes page](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)</span></span>

3. <span data-ttu-id="271b7-118">Wartość polu **Grupa księgowania w księdze** jest łączem.</span><span class="sxs-lookup"><span data-stu-id="271b7-118">The value in the **Ledger posting group** field is a link.</span></span> <span data-ttu-id="271b7-119">Aby wyświetlić szczegóły konfiguracji grupy, kliknij to łącze.</span><span class="sxs-lookup"><span data-stu-id="271b7-119">To view the details of the group's configuration, select the link.</span></span> <span data-ttu-id="271b7-120">Ewentualnie wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w polu, a następnie wybierz polecenie **Wyświetl szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="271b7-120">Alternatively, select and hold (or right-click) in the field, and then select **View details**.</span></span>

    <span data-ttu-id="271b7-121">[![Polecenie Wyświetl szczegóły](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-121">[![View details command](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)</span></span>

4. <span data-ttu-id="271b7-122">W polu **Podatek należny** sprawdź, czy numer konta jest poprawny zgodnie z typem transakcji.</span><span class="sxs-lookup"><span data-stu-id="271b7-122">In the **Sales tax payable** field, verify that the account number is correct, according to the transaction type.</span></span> <span data-ttu-id="271b7-123">Jeśli nie jest, wybierz poprawne konto, na którym transakcja ma być zaksięgowana.</span><span class="sxs-lookup"><span data-stu-id="271b7-123">If it isn't, select the correct account to post to.</span></span> <span data-ttu-id="271b7-124">W tym przykładzie podatek z zamówienia sprzedaży powinien być księgowany na koncie podatku należnego 222200.</span><span class="sxs-lookup"><span data-stu-id="271b7-124">In this example, the sales tax of the sales order should be posted to sales tax payable account 222200.</span></span>

    <span data-ttu-id="271b7-125">[![Pole Podatek należny na stronie Grupy księgowania](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-125">[![Sales tax payable field on the Ledger posting groups page](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)</span></span>

    <span data-ttu-id="271b7-126">W poniższej tabeli przedstawiono informacje o poszczególnych polach na stronie **Grupy księgowania w księdze**.</span><span class="sxs-lookup"><span data-stu-id="271b7-126">The following table provides information about each field on the **Ledger posting groups** page.</span></span>

    | <span data-ttu-id="271b7-127">Pole</span><span class="sxs-lookup"><span data-stu-id="271b7-127">Field</span></span>                  | <span data-ttu-id="271b7-128">opis</span><span class="sxs-lookup"><span data-stu-id="271b7-128">Description</span></span> |
    |------------------------|-------------|
    | <span data-ttu-id="271b7-129">Podatek należny</span><span class="sxs-lookup"><span data-stu-id="271b7-129">Sales tax payable</span></span>      | <span data-ttu-id="271b7-130">Konto główne wychodzących podatków, które są odprowadzane do urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="271b7-130">The main account for outgoing sales taxes that are payable to the tax authority.</span></span> |
    | <span data-ttu-id="271b7-131">Podatek naliczony</span><span class="sxs-lookup"><span data-stu-id="271b7-131">Sales tax receivable</span></span>   | <span data-ttu-id="271b7-132">Konto główne podatków przychodzących, które są otrzymywane od urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="271b7-132">The main account for incoming taxes that are received from the tax authority.</span></span> |
    | <span data-ttu-id="271b7-133">Wydatki podatku nienaliczonego</span><span class="sxs-lookup"><span data-stu-id="271b7-133">Use tax expense</span></span>        | <span data-ttu-id="271b7-134">Konto główne używane do księgowania ewentualnych podatków obrotowych podlegających odliczeniu, do których dostawcy nie zgłaszają roszczeń, lub raportowania ich do urzędu skarbowego w ramach mechanizmu odwrotnego obciążenia podatku od towarów i usług (GST) / ujednoliconego podatku (HST) Unii Europejskiej.</span><span class="sxs-lookup"><span data-stu-id="271b7-134">The main account that is used to post deductible use taxes that vendors don't claim or report to the tax authority as part of European Union (EU) reverse charge Goods and Services Tax (GST)/Harmonized Sales Tax (HST).</span></span> <span data-ttu-id="271b7-135">Opcja **Ewentualny podatek obrotowy** musi zostać wybrana dla kodu podatku w grupie podatków, która jest używana w transakcji.</span><span class="sxs-lookup"><span data-stu-id="271b7-135">**Use tax** must be selected for the sales tax code in the sales tax group that is used in the transaction.</span></span> <span data-ttu-id="271b7-136">To pole jest niedostępne, gdy na stronie **Parametry księgi głównej** zaznaczono opcję **Zastosuj zasady opodatkowania** dla podatku.</span><span class="sxs-lookup"><span data-stu-id="271b7-136">This field isn't available if **Apply sales tax taxation rules** is selected on the **General ledger parameters** page.</span></span> |
    | <span data-ttu-id="271b7-137">Podatek nienaliczony należny</span><span class="sxs-lookup"><span data-stu-id="271b7-137">Use tax payable</span></span>        | <span data-ttu-id="271b7-138">Konto główne używane do księgowania przychodzących ewentualnych podatków obrotowych, które są odprowadzane do urzędów skarbowych.</span><span class="sxs-lookup"><span data-stu-id="271b7-138">The main account that is used to post incoming use taxes that are payable to tax authorities.</span></span> |
    | <span data-ttu-id="271b7-139">Konto rozliczeniowe</span><span class="sxs-lookup"><span data-stu-id="271b7-139">Settlement account</span></span>     | <span data-ttu-id="271b7-140">Konto główne, które służy do księgowania salda netto kont księgowych określonych w polach **Należny ewentualny podatek obrotowy** i **Podatek naliczony**.</span><span class="sxs-lookup"><span data-stu-id="271b7-140">The main account that is used to post the net balance of the ledger accounts that are specified in the **Use tax payable** and **Sales tax receivable** fields.</span></span> |
    | <span data-ttu-id="271b7-141">Rabat gotówkowy dostawcy</span><span class="sxs-lookup"><span data-stu-id="271b7-141">Vendor cash discount</span></span>   | <span data-ttu-id="271b7-142">Konto główne, które służy do księgowania rabatów gotówkowych dla kodów podatku skojarzonych z tą grupą księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="271b7-142">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |
    | <span data-ttu-id="271b7-143">Rabat gotówkowy odbiorcy</span><span class="sxs-lookup"><span data-stu-id="271b7-143">Customer case discount</span></span> | <span data-ttu-id="271b7-144">Konto główne, które służy do księgowania rabatów gotówkowych dla kodów podatku skojarzonych z tą grupą księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="271b7-144">The main account that is used to post a cash discount for sales tax codes that are associated with this ledger posting group.</span></span> |

    <span data-ttu-id="271b7-145">Aby uzyskać więcej informacji, zobacz [Konfigurowanie grup księgowania dla podatku](tasks/set-up-ledger-posting-groups-sales-tax.md)</span><span class="sxs-lookup"><span data-stu-id="271b7-145">For more information, see, [Set up Ledger posting groups for sales tax](tasks/set-up-ledger-posting-groups-sales-tax.md)</span></span>

## <a name="debug-in-code-to-check-ledger-dimensions"></a><span data-ttu-id="271b7-146">Debugowanie w kodzie w celu sprawdzania wymiarów księgowych</span><span class="sxs-lookup"><span data-stu-id="271b7-146">Debug in code to check ledger dimensions</span></span>

<span data-ttu-id="271b7-147">W kodzie konto księgowania jest określone według wymiaru księgowego.</span><span class="sxs-lookup"><span data-stu-id="271b7-147">In the code, the posting account is determined by the ledger dimension.</span></span> <span data-ttu-id="271b7-148">Wymiar księgowy zapisuje identyfikator rekordu konta w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="271b7-148">The ledger dimension saves the record ID of an account in the database.</span></span>

1. <span data-ttu-id="271b7-149">W przypadku zamówienia sprzedaży dodaj punkt przerwania w metodach **Tax::saveAndPost()** i **Tax::post()**.</span><span class="sxs-lookup"><span data-stu-id="271b7-149">For a sales order, add a breakpoint at the **Tax::saveAndPost()** and **Tax::post()** methods.</span></span> <span data-ttu-id="271b7-150">Należy zwrócić uwagę na wartość **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="271b7-150">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="271b7-151">[![Przykładowy kod zamówienia sprzedaży z punktem przerwania](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-151">[![Sales order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)</span></span>

    <span data-ttu-id="271b7-152">W przypadku zamówienia zakupu dodaj punkt przerwania w metodach **TaxPost::saveAndPost()** i **TaxPost::postToTaxTrans()**.</span><span class="sxs-lookup"><span data-stu-id="271b7-152">For a purchase order, add a breakpoint at the **TaxPost::saveAndPost()** and **TaxPost::postToTaxTrans()** methods.</span></span> <span data-ttu-id="271b7-153">Należy zwrócić uwagę na wartość **\_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="271b7-153">Pay attention to the value of **\_ledgerDimension**.</span></span>

    <span data-ttu-id="271b7-154">[![Przykładowy kod zamówienia zakupu z punktem przerwania](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-154">[![Purchase order code sample that has a breakpoint](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)</span></span>

2. <span data-ttu-id="271b7-155">Uruchom następujące zapytanie SQL, aby znaleźć wartość wyświetlaną konta w bazie danych na podstawie identyfikatora rekordu zapisanego przez wymiar księgowy.</span><span class="sxs-lookup"><span data-stu-id="271b7-155">Run the following SQL query to find the display value of the account in the database, based on the record ID that is saved by the ledger dimension.</span></span>

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    <span data-ttu-id="271b7-156">[![Wartość wyświetlana identyfikatora rekordu](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span><span class="sxs-lookup"><span data-stu-id="271b7-156">[![Display value of the record ID](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)</span></span>

3. <span data-ttu-id="271b7-157">Znajdź w stosie wywoła miejsce, w którym jest przypisywana wartość wymiaru **_ledgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="271b7-157">Examine the callstack to find where the **_ledgerDimension** value is assigned.</span></span> <span data-ttu-id="271b7-158">Zazwyczaj ta wartość pochodzi z **TmpTaxWorkTrans**.</span><span class="sxs-lookup"><span data-stu-id="271b7-158">Usually, the value is from **TmpTaxWorkTrans**.</span></span> <span data-ttu-id="271b7-159">W takim przypadku należy dodać punkt przerwania w **TmpTaxWorkTrans::insert()** i **TmpTaxWorkTrans::update()**, aby znaleźć miejsce przypisania wartości.</span><span class="sxs-lookup"><span data-stu-id="271b7-159">In this case, you should add a breakpoint at **TmpTaxWorkTrans::insert()** and **TmpTaxWorkTrans::update()** to find where the value assigned.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="271b7-160">Określanie, czy dostosowanie istnieje</span><span class="sxs-lookup"><span data-stu-id="271b7-160">Determine whether customization exists</span></span>

<span data-ttu-id="271b7-161">Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje.</span><span class="sxs-lookup"><span data-stu-id="271b7-161">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="271b7-162">Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="271b7-162">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
