---
title: Uzgadnianie frachtu w module Zarządzanie transportem
description: W tym artykule opisano proces uzgadniania frachtu.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac07155e4dde77689b1994abfb8b30f45d5a5a30
ms.sourcegitcommit: b6686265314499056690538eaa95ca51cff7c720
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5014515"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="b9a91-103">Uzgadnianie frachtu w module Zarządzanie transportem</span><span class="sxs-lookup"><span data-stu-id="b9a91-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9a91-104">W tym artykule opisano proces uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="b9a91-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="b9a91-105">Uzgadnianie frachtu można wykonać ręcznie lub skonfigurować jego wykonywanie automatyczne.</span><span class="sxs-lookup"><span data-stu-id="b9a91-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="b9a91-106">Aby używać automatycznego uzgadnianie frachtu, należy skonfigurować główną inspekcję, gdzie można zdefiniować kryteria określające, które listy frachtowe mają być uzgadniane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="b9a91-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="b9a91-107">Proces uzgadniania frachtu</span><span class="sxs-lookup"><span data-stu-id="b9a91-107">The freight reconciliation process</span></span>

<span data-ttu-id="b9a91-108">Stawki frachtowe są obliczane przez aparat stawki skojarzony z odnośnym przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="b9a91-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="b9a91-109">Po potwierdzeniu ładunku jest generowany list frachtowy, a do niego są przenoszone stawki frachtowe.</span><span class="sxs-lookup"><span data-stu-id="b9a91-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="b9a91-110">Stawki frachtowe są przypisywane jako opłaty dodatkowe do odnośnego dokumentu źródłowego (zamówienia zakupu, zamówienia sprzedaży i/lub zamówienie przeniesienia), w zależności od konfiguracji używanej w standardowym procesie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="b9a91-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="b9a91-111">Proces uzgadniania frachtu (nazywany także procesem dopasowywania) może się rozpocząć natychmiast po otrzymaniu faktury za fracht od firmy przewozowej.</span><span class="sxs-lookup"><span data-stu-id="b9a91-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="b9a91-112">Fakturę można odebrać elektronicznie lub na papierze.</span><span class="sxs-lookup"><span data-stu-id="b9a91-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="b9a91-113">Jeśli faktura jest otrzymywana na papierze, można wygenerować fakturę elektroniczną, używając listu frachtowego jako szablonu.</span><span class="sxs-lookup"><span data-stu-id="b9a91-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span>

<span data-ttu-id="b9a91-114">[![Proces uzgadniania frachtu](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="b9a91-114">[![Freight reconciliation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="b9a91-115">Ręczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="b9a91-115">Manual reconciliation</span></span>

<span data-ttu-id="b9a91-116">Jeśli uzgadniasz fracht ręcznie, trzeba dopasować każdy wiersz faktury do wiersza lub wierszy listu frachtowego dla fakturowanego ładunku.</span><span class="sxs-lookup"><span data-stu-id="b9a91-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="b9a91-117">To dopasowanie odbywa się na stronie **Dopasowywanie opłat frachtowych i faktur**.</span><span class="sxs-lookup"><span data-stu-id="b9a91-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="b9a91-118">Jeśli kwota w wierszu faktury nie pasuje do kwoty w liście frachtowym, dla różnicy należy wybrać przyczynę uzgodnienia.</span><span class="sxs-lookup"><span data-stu-id="b9a91-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="b9a91-119">Jeśli istnieje wiele przyczyn uzgodnienia, można rozdzielić niezgodną kwotę między nie.</span><span class="sxs-lookup"><span data-stu-id="b9a91-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="b9a91-120">Przyczyna uzgodnienia określa, jak kwoty różnic są księgowane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="b9a91-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="b9a91-121">Po uzgodnieniu całej kwoty faktury faktura jest przedstawiana do zatwierdzenia, po czym następuje zaksięgowanie arkusza.</span><span class="sxs-lookup"><span data-stu-id="b9a91-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="b9a91-122">Poniższa ilustracja pokazuje sposób generowania faktury za fracht oraz uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="b9a91-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span>

<span data-ttu-id="b9a91-123">[![Zadania uzgadniania frachtu](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="b9a91-123">[![Freight reconciliation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>

## <a name="automatic-reconciliation"></a><span data-ttu-id="b9a91-124">Automatyczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="b9a91-124">Automatic reconciliation</span></span>

<span data-ttu-id="b9a91-125">Aby użyć automatycznego uzgadniania, należy określić harmonogram uzgadniania oraz faktury i przewoźników, których uzgadnianie ma dotyczyć.</span><span class="sxs-lookup"><span data-stu-id="b9a91-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="b9a91-126">Dopasowywanie wierszy faktur i listów frachtowych odbywa się zgodnie z konfiguracją głównej inspekcji i typem listu frachtowego.</span><span class="sxs-lookup"><span data-stu-id="b9a91-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="b9a91-127">Po uruchomieniu automatycznego uzgadniania należy zidentyfikować wszystkie faktury, których nie jest w stanie dopasować system.</span><span class="sxs-lookup"><span data-stu-id="b9a91-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="b9a91-128">Następnie należy wykonać ręczne przetwarzanie tych faktur, zanim będzie można zaksięgować wszystkie faktury do zapłaty.</span><span class="sxs-lookup"><span data-stu-id="b9a91-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a><span data-ttu-id="b9a91-129">Uzgadnianie rachunków frachtowych z fakturami za fracht przy użyciu uzgodnienia automatycznego lub ręcznego</span><span class="sxs-lookup"><span data-stu-id="b9a91-129">Match freight bills with freight invoices using automatic or manual reconciliation</span></span>

<span data-ttu-id="b9a91-130">*Uzgadnianie* to proces znajdowania rachunków frachtowych odpowiadających każdej fakturze za fracht.</span><span class="sxs-lookup"><span data-stu-id="b9a91-130">*Matching* is the process of finding the freight bills that correspond to each freight invoice.</span></span> <span data-ttu-id="b9a91-131">W tym celu należy kolejno uzgadniać wiersze faktury (uzgadnianie ręczne) lub uzgadniać wszystkie dostępne faktury na raz (automatyczne uzgadnianie).</span><span class="sxs-lookup"><span data-stu-id="b9a91-131">This can be done by matching the invoice lines one-by-one (manual matching), or by matching all available invoices at once (auto matching).</span></span>

### <a name="auto-matching"></a><span data-ttu-id="b9a91-132">Automatyczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="b9a91-132">Auto matching</span></span>

<span data-ttu-id="b9a91-133">W przypadku uzgadniania wielu faktur za fracht do tej samej opłaty frachtowej proces automatycznego uzgadniania działa następująco:</span><span class="sxs-lookup"><span data-stu-id="b9a91-133">When matching multiple freight invoices to the same freight bill, the process for auto matching works as follows:</span></span>

1. <span data-ttu-id="b9a91-134">Wszystkie niedopasowane faktury frachtowe są sortowane według kwoty, z największą kwotą jako pierwsza.</span><span class="sxs-lookup"><span data-stu-id="b9a91-134">All freight invoices not matched are sorted by amount, with largest amount first.</span></span>
1. <span data-ttu-id="b9a91-135">Faktury za fracht są dopasowywane kolejno, dopóki rachunek za fracht nie będzie mieć pozostałej kwoty dodatniej.</span><span class="sxs-lookup"><span data-stu-id="b9a91-135">The freight invoices are matched one-by-one, until the freight bill has no positive amount remaining.</span></span>
1. <span data-ttu-id="b9a91-136">W zależności od ustawień głównej inspekcji i pozostałej kwoty na fakturach za fracht jest ustawiana pozostała kwota.</span><span class="sxs-lookup"><span data-stu-id="b9a91-136">Depending on the setup of the audit master and the remaining amount on the freight invoices, the remaining amount is set.</span></span>

### <a name="manual-matching"></a><span data-ttu-id="b9a91-137">Uzgadnianie ręczne</span><span class="sxs-lookup"><span data-stu-id="b9a91-137">Manual matching</span></span>

<span data-ttu-id="b9a91-138">Wszystkie opłaty frachtowe z kwotami dodatnimi będą dostępne do dopasowania.</span><span class="sxs-lookup"><span data-stu-id="b9a91-138">All freight bills with positive amounts will be available for matching.</span></span> <span data-ttu-id="b9a91-139">Podobnie jak automatyczne uzgadnianie, użytkownik może dopasować tylko faktury za fracht z ujemnymi kwotami do w pełni dopasowanych rachunków frachtowych.</span><span class="sxs-lookup"><span data-stu-id="b9a91-139">Similar to auto matching, the user will only be able to match freight invoices with negative amounts to freight bills not fully matched.</span></span>

### <a name="example"></a><span data-ttu-id="b9a91-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="b9a91-140">Example</span></span>

<span data-ttu-id="b9a91-141">Załóżmy, że użytkownik ma rachunek frachtowy na kwotę 1500 i utworzono trzy faktury za fracht, po jednym wierszu faktury dla każdej faktury z następującymi ustawieniami:</span><span class="sxs-lookup"><span data-stu-id="b9a91-141">Suppose that you have a freight bill (FB) for an amount of 1500 and you have created three freight invoices for the freight bill with one invoice line for each invoice with following settings:</span></span>

- <span data-ttu-id="b9a91-142">Oryginalny rachunek frachtowy (FB): kwota 1500</span><span class="sxs-lookup"><span data-stu-id="b9a91-142">Original freight bill (FB): Amount 1500</span></span>
- <span data-ttu-id="b9a91-143">Faktura 1 (Inv1): kwota 1000</span><span class="sxs-lookup"><span data-stu-id="b9a91-143">Invoice 1 (Inv1): Amount 1000</span></span>
- <span data-ttu-id="b9a91-144">Faktura 2 (Inv2): kwota 600</span><span class="sxs-lookup"><span data-stu-id="b9a91-144">Invoice 2 (Inv2): Amount 600</span></span>
- <span data-ttu-id="b9a91-145">Faktura 3 (Inv3): kwota -100</span><span class="sxs-lookup"><span data-stu-id="b9a91-145">Invoice 3 (Inv3): Amount -100</span></span>

#### <a name="automatic-matching-result"></a><span data-ttu-id="b9a91-146">Wynik automatycznego uzgadniania</span><span class="sxs-lookup"><span data-stu-id="b9a91-146">Automatic matching result</span></span>

<span data-ttu-id="b9a91-147">Automatyczne uzgadnianie będzie wykonywane w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="b9a91-147">Auto matching will execute in following order:</span></span>

1. <span data-ttu-id="b9a91-148">Sortuj wszystkie faktury za fracht malejąco według kwoty: Inv1 -> Inv2 -> Inv3.</span><span class="sxs-lookup"><span data-stu-id="b9a91-148">Sort all freight invoices descending by amount: Inv1 -> Inv2 -> Inv3.</span></span>
1. <span data-ttu-id="b9a91-149">Dopasuj fakturę Inv1 do rachunku FB.</span><span class="sxs-lookup"><span data-stu-id="b9a91-149">Match Inv1 with FB.</span></span> <span data-ttu-id="b9a91-150">Inv1 ma dopasowane 1000, a FB ma pozostałą kwotę 500, więc stan jest ustawiony na *Częściowo dopasowane*.</span><span class="sxs-lookup"><span data-stu-id="b9a91-150">Inv1 has 1000 matched and FB has 500 amount remaining, so the status is set to *Partially matched*.</span></span>
1. <span data-ttu-id="b9a91-151">Dopasuj fakturę Inv2 do rachunku FB.</span><span class="sxs-lookup"><span data-stu-id="b9a91-151">Match Inv2 with FB.</span></span> <span data-ttu-id="b9a91-152">Inv2 ma dopasowane 500, a FB ma pozostałą kwotę 0, więc stan jest ustawiony na *W pełni dopasowane*.</span><span class="sxs-lookup"><span data-stu-id="b9a91-152">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="b9a91-153">Ponieważ konto FB jest teraz w pełni dopasowane, nie można przetworzyć faktury Inv3.</span><span class="sxs-lookup"><span data-stu-id="b9a91-153">Because FB is now fully matched, Inv3 won't be processed.</span></span>

#### <a name="manual-matching-result"></a><span data-ttu-id="b9a91-154">Wynik uzgadniania ręcznego</span><span class="sxs-lookup"><span data-stu-id="b9a91-154">Manual matching result</span></span>

<span data-ttu-id="b9a91-155">W przypadku uzgadniania ręcznego wyniki różnią się w zależności od kolejności uzgadniania, co przedstawiono w poniższych przykładowych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="b9a91-155">For manual matching, the results vary depending on the order of the matching, as illustrated in the following example cases.</span></span>

##### <a name="manual-matching-case-1"></a><span data-ttu-id="b9a91-156">Uzgadnianie ręczne — przypadek 1</span><span class="sxs-lookup"><span data-stu-id="b9a91-156">Manual matching case 1</span></span>

<span data-ttu-id="b9a91-157">W tym przykładzie można wykonać uzgadnianie ręczne w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="b9a91-157">One way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="b9a91-158">Dopasuj rachunek FB do faktury Inv1.</span><span class="sxs-lookup"><span data-stu-id="b9a91-158">Match FB with Inv1.</span></span> <span data-ttu-id="b9a91-159">FB ma dopasowaną kwotę 500, więc stan jest ustawiony na *Częściowo dopasowane*.</span><span class="sxs-lookup"><span data-stu-id="b9a91-159">FB has 500 amount remaining, so the status set to *Partially matched*.</span></span>
1. <span data-ttu-id="b9a91-160">Dopasuj fakturę Inv2 do rachunku FB.</span><span class="sxs-lookup"><span data-stu-id="b9a91-160">Match Inv2 with FB.</span></span> <span data-ttu-id="b9a91-161">Inv2 ma dopasowane 500, a FB ma pozostałą kwotę 0, więc stan jest ustawiony na *W pełni dopasowane*.</span><span class="sxs-lookup"><span data-stu-id="b9a91-161">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="b9a91-162">Podczas ręcznego uzgadniania faktury Inv3 nie będzie można znaleźć żadnych niedopasowanych rachunków frachtowych.</span><span class="sxs-lookup"><span data-stu-id="b9a91-162">When manually matching Inv3, you won't find any unmatched freight bills.</span></span>

<span data-ttu-id="b9a91-163">Te przypadek jest w zasadzie taki sam jak automatyczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="b9a91-163">This case is essentially the same as auto matching</span></span>

##### <a name="manual-matching-case-2"></a><span data-ttu-id="b9a91-164">Uzgadnianie ręczne — przypadek 2</span><span class="sxs-lookup"><span data-stu-id="b9a91-164">Manual matching case 2</span></span>

<span data-ttu-id="b9a91-165">W tym przykładzie można wykonać uzgadnianie ręczne w inny sposób:</span><span class="sxs-lookup"><span data-stu-id="b9a91-165">Another way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="b9a91-166">Dopasuj fakturę Inv3 do rachunku FB.</span><span class="sxs-lookup"><span data-stu-id="b9a91-166">Match Inv3 with FB.</span></span> <span data-ttu-id="b9a91-167">Teraz FB ma pozostałą kwotę 1600, która jest taka sama jak odjęcie ujemnej 100 od 1500.</span><span class="sxs-lookup"><span data-stu-id="b9a91-167">Now FB has amount remaining 1600, which is the same as subtracting negative 100 on top of 1500.</span></span> <span data-ttu-id="b9a91-168">Zarówno FB, jak i Inv3 mają dopasowaną ilość -100.</span><span class="sxs-lookup"><span data-stu-id="b9a91-168">Both FB and Inv3 have a matched quantity of -100.</span></span>
1. <span data-ttu-id="b9a91-169">Dopasuj kolejno faktury Inv1 i Inv 2 do FB.</span><span class="sxs-lookup"><span data-stu-id="b9a91-169">Match Inv1 and Inv 2 with FB one after another.</span></span> <span data-ttu-id="b9a91-170">Rachunek FB jest w pełni dopasowany.</span><span class="sxs-lookup"><span data-stu-id="b9a91-170">FB is fully matched.</span></span>

<span data-ttu-id="b9a91-171">Jak pokazano w tym przykładzie, uzgadnianie faktur za fracht z kwotami ujemnymi należy wykonać tylko ręcznie.</span><span class="sxs-lookup"><span data-stu-id="b9a91-171">As this example shows, matching freight invoices with negative amounts should only be done manually.</span></span> <span data-ttu-id="b9a91-172">Zapewnia to, że zawsze jest możliwe dopasowanie faktur za fracht z kwotami ujemnymi do w pełni dopasowanej opłaty frachtowej, ponieważ umożliwia to kontrolowanie kolejności uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="b9a91-172">This will ensure that it is always possible to match the freight invoices with negative amounts to a freight bill not fully matched because that enables you to control the matching sequence.</span></span>
