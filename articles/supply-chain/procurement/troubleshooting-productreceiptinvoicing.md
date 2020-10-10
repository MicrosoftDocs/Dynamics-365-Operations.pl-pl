---
title: Rozwiązywanie problemów z pokwitowaniem produktów i fakturowaniem
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z pokwitowaniami produktów i fakturowaniem.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d86fa3df1de13cc0e0fb94449207a326069da25b
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834412"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="41820-103">Rozwiązywanie problemów z pokwitowaniem produktów i fakturowaniem</span><span class="sxs-lookup"><span data-stu-id="41820-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="41820-104">W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z pokwitowaniami produktów i fakturowaniem.</span><span class="sxs-lookup"><span data-stu-id="41820-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="41820-105">Nie mogę zaksięgować więcej niż jednej faktury dla wiersza zamówienia zakupu zawierającego pozycje oparte na kategorii.</span><span class="sxs-lookup"><span data-stu-id="41820-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="41820-106">Ilość jest obowiązkowa, jeśli chcesz zaksięgować faktury.</span><span class="sxs-lookup"><span data-stu-id="41820-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="41820-107">Dlatego jeśli zafakturowano całą ilość w wierszu tylko dla części kwoty, nie będzie można zafakturować pozostałej kwoty na innej fakturze.</span><span class="sxs-lookup"><span data-stu-id="41820-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="41820-108">Otrzymuję komunikat o błędzie „Nie ustawiono odwołania do obiektu” podczas potwierdzania zamówienia zakupu lub podczas księgowania faktury od dostawcy zgłoszony został wyjątek „Obiekt docelowy wywołania” zgłosił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="41820-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="41820-109">Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="41820-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="41820-110">Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="41820-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="41820-111">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="41820-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="41820-112">Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="41820-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="41820-113">Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu, jeśli inne wiersze dokumentu przyjęcia produktów mają różne daty księgowania.</span><span class="sxs-lookup"><span data-stu-id="41820-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="41820-114">W starszych wersjach rozwiązania Microsoft Dynamics 365 Supply Chain Management konsolidacja była dopuszczalna w tej sytuacji.</span><span class="sxs-lookup"><span data-stu-id="41820-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="41820-115">Jednak praktyka ta jest podatna na błędy.</span><span class="sxs-lookup"><span data-stu-id="41820-115">However, the practice is prone to error.</span></span> <span data-ttu-id="41820-116">Data księgowania w tworzonych wierszach zamówienia zakupu nie powinna różnić się od daty księgowania w wierszach przyjęcia produktów, na podstawie których utworzono te wiersze zamówienia.</span><span class="sxs-lookup"><span data-stu-id="41820-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="41820-117">(Data księgowania w wierszach zamówienia jest zgodna z datą księgowania w nagłówku zamówienia). Dlatego konsolidacja wielu przyjęć produktów w pojedyncze zamówienia zakupu nie jest już dozwolona.</span><span class="sxs-lookup"><span data-stu-id="41820-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="41820-118">Data księgowania jest używana na przykład w odniesieniu do rezerwacji budżetu i przyszłych zobowiązań wiążących.</span><span class="sxs-lookup"><span data-stu-id="41820-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="41820-119">Dlatego należy go zachować podczas przejścia od przyjęcia produktu do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="41820-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="41820-120">W przypadku anulowania przyjęcia produktów transakcje mogą zostać zaksięgowane na zawieszonym koncie księgowym.</span><span class="sxs-lookup"><span data-stu-id="41820-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="41820-121">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="41820-121">Issue description</span></span>

<span data-ttu-id="41820-122">W przypadku anulowania przyjęcia produktów system umożliwia księgowanie transakcji na zawieszonych kontach księgowych, nawet jeśli konta główne są zawieszone.</span><span class="sxs-lookup"><span data-stu-id="41820-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="41820-123">Odtwórz ten błąd</span><span class="sxs-lookup"><span data-stu-id="41820-123">Reproduce the issue</span></span>

<span data-ttu-id="41820-124">Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.</span><span class="sxs-lookup"><span data-stu-id="41820-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="41820-125">Na stronie **Parametry rozrachunków z dostawcami** na karcie **Ogólne** upewnij się, że opcja **Księguj dokument przyjęcia produktów w księdze** jest ustawiona na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="41820-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="41820-126">Utwórz zamówienie zakupu i dodaj wiersz zamówienia z ilością *1 000* dla produktu.</span><span class="sxs-lookup"><span data-stu-id="41820-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="41820-127">Potwierdź zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="41820-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="41820-128">Zaksięguj dokument przyjęcia produktów i sprawdź załączniki.</span><span class="sxs-lookup"><span data-stu-id="41820-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="41820-129">Zawiesić odpowiednie konta główne, *200140* i *140200*.</span><span class="sxs-lookup"><span data-stu-id="41820-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="41820-130">Anuluj zaksięgowane przyjęcia produktu.</span><span class="sxs-lookup"><span data-stu-id="41820-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="41820-131">Zwróć uwagę, że transakcje mogą być księgowane na zawieszonych kontach księgowych.</span><span class="sxs-lookup"><span data-stu-id="41820-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41820-132">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="41820-132">Issue resolution</span></span>

<span data-ttu-id="41820-133">Transakcje mogą być księgowane na zawieszonych kontach księgowych po anulowaniu przyjęcia produktów, ponieważ takie zachowanie umożliwia prawidłowe księgowanie.</span><span class="sxs-lookup"><span data-stu-id="41820-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="41820-134">Numer kuponu przyjęcia produktu jest używany, nawet jeśli podczas przyjęcia produktu nie jest generowany żaden dowód finansowy.</span><span class="sxs-lookup"><span data-stu-id="41820-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="41820-135">Jeśli dla grupy modeli towaru dla opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** jest ustawiona wartość *Nie*, księgowanie nie będzie wykonywane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="41820-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="41820-136">Jednak zdarzenie fizyczne zostanie zarejestrowane do celów księgowania w księdze podrzędnej, a to zdarzenie wymaga numeru załącznika.</span><span class="sxs-lookup"><span data-stu-id="41820-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="41820-137">Ten numer załącznika jest numerem załącznika, do którego istnieje odwołanie w transakcjach magazynowych.</span><span class="sxs-lookup"><span data-stu-id="41820-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="41820-138">Zaleca się ustawienie opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** na wartość *Tak*, jak to opisano w następującym wpisie na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="41820-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="41820-139">Ustawienie Księgowanie obciążenia konta w księdze nie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="41820-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="41820-140">Opis problemu</span><span class="sxs-lookup"><span data-stu-id="41820-140">Issue description</span></span>

<span data-ttu-id="41820-141">Ten problem występuje w przypadku zafakturowania zamówienia zakupu, jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="41820-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="41820-142">Odtwórz ten błąd</span><span class="sxs-lookup"><span data-stu-id="41820-142">Reproduce the issue</span></span>

<span data-ttu-id="41820-143">Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.</span><span class="sxs-lookup"><span data-stu-id="41820-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="41820-144">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="41820-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="41820-145">Na karcie **Faktura** ustaw opcję **Księgowanie obciążenia konta w księdze** na wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="41820-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="41820-146">Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="41820-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="41820-147">Na karcie **Zamówienie zakupu** upewnij się, że usunięto wszystkie wiersze wydatków zakupu produktu.</span><span class="sxs-lookup"><span data-stu-id="41820-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="41820-148">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.</span><span class="sxs-lookup"><span data-stu-id="41820-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="41820-149">Umożliwia tworzenie zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="41820-149">Create a purchase order.</span></span> <span data-ttu-id="41820-150">W polu **Konto dostawcy** wybierz *1001 materiały biurowe Acme*.</span><span class="sxs-lookup"><span data-stu-id="41820-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="41820-151">Dodaj wiersz zamówienia zakupu z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="41820-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="41820-152">**Numer pozycji:** *D0011 projektor laserowy*</span><span class="sxs-lookup"><span data-stu-id="41820-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="41820-153">**Oddział:** *1*</span><span class="sxs-lookup"><span data-stu-id="41820-153">**Site:** *1*</span></span>
    - <span data-ttu-id="41820-154">**Magazyn:** *11*</span><span class="sxs-lookup"><span data-stu-id="41820-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="41820-155">**Ilość:** *4*</span><span class="sxs-lookup"><span data-stu-id="41820-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="41820-156">W okienku akcji na karcie **Zakup** w grupie **Akcja** wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="41820-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="41820-157">W okienku akcji na karcie **Odbierz** w grupie **Generowanie** wybierz pozycję **Przyjęcie produktu**.</span><span class="sxs-lookup"><span data-stu-id="41820-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="41820-158">W oknie dialogowym **Księgowanie dokumentu przyjęcia produktów** w polu **Dokument przyjęcia produktów** wprowadź dowolny numer, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="41820-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="41820-159">W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="41820-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="41820-160">W polu **Numer** wprowadź dowolną liczbę jako numer faktury.</span><span class="sxs-lookup"><span data-stu-id="41820-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="41820-161">Zaktualizuj stan uzgadniania i zaksięguj.</span><span class="sxs-lookup"><span data-stu-id="41820-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="41820-162">Zauważ, że teraz pojawia się następujący błąd podczas generowania faktury z zamówienia zakupu: „Numer konta dla typu transakcji Wydatki na zakup produktu nie istnieją”.</span><span class="sxs-lookup"><span data-stu-id="41820-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41820-163">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="41820-163">Issue resolution</span></span>

<span data-ttu-id="41820-164">Zależy to od ustawień parametrów dla faktur i grup faktur.</span><span class="sxs-lookup"><span data-stu-id="41820-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="41820-165">Aby uzyskać więcej informacji, zajrzyj do następującego wpisu na blogu: [Uwzględnianie opłaty za zakup i zmiany stanu zapasów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="41820-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>
