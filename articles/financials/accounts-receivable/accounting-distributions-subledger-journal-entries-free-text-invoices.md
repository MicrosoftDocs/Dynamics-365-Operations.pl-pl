---
title: Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur niezależnych
description: Zasady podziału księgowań służą do określania sposobu księgowania kwot, takich jak przychody, podatki lub opłaty, na fakturze niezależnej. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury niezależnej, będzie posiadać jedną lub więcej zasad podziału księgowań.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d1546e8537110daec5d6655f68d3328a58ca1cb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571195"
---
# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="d7678-104">Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur niezależnych</span><span class="sxs-lookup"><span data-stu-id="d7678-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7678-105">Zasady podziału księgowań służą do określania sposobu księgowania kwot, takich jak przychody, podatki lub opłaty, na fakturze niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="d7678-106">Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury niezależnej, będzie posiadać jedną lub więcej zasad podziału księgowań.</span><span class="sxs-lookup"><span data-stu-id="d7678-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="d7678-107">Zasady podziału księgowań</span><span class="sxs-lookup"><span data-stu-id="d7678-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="d7678-108">Za pomocą następujących przycisków na stronie Faktura niezależna, możesz wyświetlać i ewentualnie zmienić zasady podziału księgowań dla faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="d7678-109">**Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego wiersza i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty.</span><span class="sxs-lookup"><span data-stu-id="d7678-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="d7678-110">Można również wyświetlać i modyfikować zasady podziału księgowań dla wiersza podrzędnego bezpośrednio ze strony Transakcje podatkowe lub Transakcje opłat.</span><span class="sxs-lookup"><span data-stu-id="d7678-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="d7678-111">Zmienianie kwot nagłówka faktury niezależnej, takich jak opłaty lub kwoty zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="d7678-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="d7678-112">Zmienianie kwot wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="d7678-113">**Wyświetl dystrybucje** — Wyświetlanie zasad podziału księgowań dla wszystkich wierszy w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="d7678-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="d7678-114">Nie można zmienić zasad podziału księgowań w tym widoku.</span><span class="sxs-lookup"><span data-stu-id="d7678-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="d7678-115">Wyświetlenie kwot nagłówka i wiersza.</span><span class="sxs-lookup"><span data-stu-id="d7678-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="d7678-116">Przydzielanie kwot</span><span class="sxs-lookup"><span data-stu-id="d7678-116">Distributing amounts</span></span>
<span data-ttu-id="d7678-117">Podczas wprowadzania faktury niezależnej, każda kwota będzie podzielona w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="d7678-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7678-118">Typ kwoty pieniężnej</span><span class="sxs-lookup"><span data-stu-id="d7678-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="d7678-119">Skąd jest wyświetlane konto główne</span><span class="sxs-lookup"><span data-stu-id="d7678-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="d7678-120">Kolejność priorytetów, która określa, który domyślny wymiar finansowy jest wyświetlany</span><span class="sxs-lookup"><span data-stu-id="d7678-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d7678-121">Wiersz faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="d7678-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="d7678-122">Konto księgi dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d7678-123">Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</span><span class="sxs-lookup"><span data-stu-id="d7678-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d7678-124">Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-125">Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-126">Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="d7678-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d7678-127">Wiersz faktury niezależnej dla kombinacji środka trwałego i modelu ewidencji</span><span class="sxs-lookup"><span data-stu-id="d7678-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d7678-128"><strong>Uwaga </strong></span><span class="sxs-lookup"><span data-stu-id="d7678-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d7678-129">Konto główne w wierszu faktury niezależnej będzie kontem likwidacji środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="d7678-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="d7678-130">Konto księgi dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d7678-131">Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-132">Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="d7678-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d7678-133">Kwota rabatu faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="d7678-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="d7678-134">Pole Konto główne rabatów odbiorcy na stronie Rabaty gotówkowe.</span><span class="sxs-lookup"><span data-stu-id="d7678-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d7678-135">Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</span><span class="sxs-lookup"><span data-stu-id="d7678-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d7678-136">Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-137">Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-138">Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="d7678-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d7678-139">Kwota podatku na fakturze niezależnej</span><span class="sxs-lookup"><span data-stu-id="d7678-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="d7678-140">Pole Podatek należny na stronie Grupy księgowania.</span><span class="sxs-lookup"><span data-stu-id="d7678-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d7678-141">Należy użyć wymiarów finansowych, które zostały zdefiniowane w kwocie wiersza faktury niezależnej dystrybucjach dla kwoty wiersza opłaty.</span><span class="sxs-lookup"><span data-stu-id="d7678-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="d7678-142">Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-143">Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="d7678-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d7678-144">Kwota wiersza opłaty faktury niezależnej</span><span class="sxs-lookup"><span data-stu-id="d7678-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="d7678-145">Pole Konto kredytowe na stronie Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="d7678-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d7678-146">Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</span><span class="sxs-lookup"><span data-stu-id="d7678-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d7678-147">Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-148">Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d7678-149">Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="d7678-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="d7678-150">Dystrybuowanie podatków</span><span class="sxs-lookup"><span data-stu-id="d7678-150">Distributing taxes</span></span>
<span data-ttu-id="d7678-151">Zasady podziału księgowań dla podatków można utworzyć dopiero po obliczeniu podatków.</span><span class="sxs-lookup"><span data-stu-id="d7678-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="d7678-152">Aby obliczyć podatek, należy wykonać jedną z następujących czynności w formularzu Faktura od dostawcy:</span><span class="sxs-lookup"><span data-stu-id="d7678-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="d7678-153">Wyświetlanie podatku.</span><span class="sxs-lookup"><span data-stu-id="d7678-153">View the sales tax.</span></span>
-   <span data-ttu-id="d7678-154">Wyświetl sumę faktury.</span><span class="sxs-lookup"><span data-stu-id="d7678-154">View the invoice total.</span></span>
-   <span data-ttu-id="d7678-155">Wyświetl przepływy pieniężne.</span><span class="sxs-lookup"><span data-stu-id="d7678-155">View the cash flow.</span></span>
-   <span data-ttu-id="d7678-156">Wyświetlanie zasad podziału księgowań dla całej faktury niezależnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="d7678-157">Wyświetlanie arkusza księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="d7678-158"> Arkusze księgi podrzędnej dla faktur niezależnych</span><span class="sxs-lookup"><span data-stu-id="d7678-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="d7678-159">Przed zaksięgowaniem faktury niezależnej, można wyświetlić pełny wpis księgowy faktury, który obejmuje obciążenia i uznania, aby zweryfikować, że faktura została zaksięgowana na właściwych kontach.</span><span class="sxs-lookup"><span data-stu-id="d7678-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="d7678-160">Ten widok pełnego wpisu księgowania nazywa się arkuszem księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="d7678-161">Jeżeli zapis w arkuszu księgi podrzędnej jest nieprawidłowy w podglądzie przed zapisaniem faktury niezależnej w arkuszu, nie można modyfikować zapisu w arkuszu księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="d7678-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="d7678-162">Zamiast tego należy zmienić zasady podziału księgowań albo profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="d7678-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="d7678-163">Zasady podziału księgowań służą do definiowania jednej strony wpisu księgowania: debetu lub kredytu.</span><span class="sxs-lookup"><span data-stu-id="d7678-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="d7678-164">Zapis księgowania transakcji przeciwstawnych w arkuszu księgi podrzędnej jest tworzony z profilów księgowania, takich jak konto odbiorca lub podatek.</span><span class="sxs-lookup"><span data-stu-id="d7678-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>



