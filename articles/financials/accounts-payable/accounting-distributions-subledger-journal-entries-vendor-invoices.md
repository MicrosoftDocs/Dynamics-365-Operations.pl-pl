---
title: "Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur od dostawcy"
description: "Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: bc774268bb9b431b033d47f59540db62df2d72a3
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a><span data-ttu-id="6dc94-104">Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur od dostawcy</span><span class="sxs-lookup"><span data-stu-id="6dc94-104">Accounting distributions and subledger journal entries for vendor invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6dc94-105">Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="6dc94-106">Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań.</span><span class="sxs-lookup"><span data-stu-id="6dc94-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="6dc94-107">Zasady podziału księgowań</span><span class="sxs-lookup"><span data-stu-id="6dc94-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="6dc94-108">Za pomocą następujących przycisków na stronie Faktura od dostawcy, możesz wyświetlać i ewentualnie zmodyfikować zasady podziału księgowań dla faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="6dc94-109">**Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego wiersza i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty.</span><span class="sxs-lookup"><span data-stu-id="6dc94-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="6dc94-110">Można również wyświetlać i modyfikować zasady podziału księgowań dla wiersza podrzędnego bezpośrednio ze strony Transakcje podatkowe lub Transakcje opłat.</span><span class="sxs-lookup"><span data-stu-id="6dc94-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="6dc94-111">Modyfikowanie kwot nagłówka faktury od dostawcy, takich jak opłaty lub kwoty zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="6dc94-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="6dc94-112">Modyfikowanie kwot wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="6dc94-113">**Wyświetl dystrybucje** — Wyświetlanie zasad podziału księgowań dla wszystkich wierszy w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="6dc94-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="6dc94-114">Nie można zmodyfikować zasad podziału księgowań w tym widoku.</span><span class="sxs-lookup"><span data-stu-id="6dc94-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="6dc94-115">Wyświetlenie kwot nagłówka i wiersza.</span><span class="sxs-lookup"><span data-stu-id="6dc94-115">View header and line amounts.</span></span>

<span data-ttu-id="6dc94-116">Jeśli faktura od dostawcy odwołuje się do zamówienia zakupu, można podzielić i zmodyfikować zasady podziału księgowań dla wierszy, które zawierają towar, który nie jest składowany.</span><span class="sxs-lookup"><span data-stu-id="6dc94-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="6dc94-117">Jeśli wiersz faktury od dostawcy nie odwołuje się do wiersza zamówienia zakupu, można usunąć zasady podziału księgowań.</span><span class="sxs-lookup"><span data-stu-id="6dc94-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="6dc94-118">Nie można rozdzielić lub usunąć wierszy dla opłat, podatków i rabatów wiersza.</span><span class="sxs-lookup"><span data-stu-id="6dc94-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="6dc94-119">Konto księgowe można zmodyfikować, ale nie można zmienić kwot lub wartości procentowych.</span><span class="sxs-lookup"><span data-stu-id="6dc94-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="6dc94-120">Jeśli wiersz nadrzędny zawiera towar, który nie jest składowany, a zasady podziału księgowań są podzielone, wiersz podrzędny zostanie podzielony automatycznie, aby dopasować wymiary finansowe wiersza nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="6dc94-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="6dc94-121">Zasady podziału księgowań dla wiersza podrzędnego nie mogą być dodatkowo podzielone ani usunięte, ale w zależności od konfiguracji wiersza podrzędnego, może być możliwe modyfikowanie konta księgowego dla zasad podziału księgowań podrzędnego wiersza.</span><span class="sxs-lookup"><span data-stu-id="6dc94-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="6dc94-122">Przydzielanie kwot</span><span class="sxs-lookup"><span data-stu-id="6dc94-122">Distributing amounts</span></span>
<span data-ttu-id="6dc94-123">Podczas wprowadzania faktury od dostawcy, każda kwota będzie podzielona w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="6dc94-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dc94-124">Typ wiersza dla faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="6dc94-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="6dc94-125">Kolejność priorytetów, która określa, skąd jest wyświetlane konto główne</span><span class="sxs-lookup"><span data-stu-id="6dc94-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="6dc94-126">Kolejność priorytetów, która określa, który domyślny wymiar finansowy jest wyświetlany</span><span class="sxs-lookup"><span data-stu-id="6dc94-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6dc94-127">Produkt magazynowany</span><span class="sxs-lookup"><span data-stu-id="6dc94-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-128">Zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-129">Pole Konto główne po wybraniu opcji Koszty zakupu produktów na stronie Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="6dc94-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-130">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-131">Użyj domyślnych wartości wymiaru finansowego dla faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-132">Kategoria zaopatrzenia lub towar, który nie jest składowany</span><span class="sxs-lookup"><span data-stu-id="6dc94-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-133">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury od dostawcy odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-134">Pole Konto główne po wybraniu opcji Koszty zakupu na stronie Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="6dc94-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-135">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-136">Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</span><span class="sxs-lookup"><span data-stu-id="6dc94-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="6dc94-137">Użyj domyślnych wartości wymiaru finansowego dla faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="6dc94-138">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-139">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6dc94-140">Środek trwały</span><span class="sxs-lookup"><span data-stu-id="6dc94-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-141">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury od dostawcy odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-142">Jeśli opcja Nabycie jest wybrana w polu Typ transakcji w formularzu Faktura od dostawcy, pole Konto główne po wybraniu opcji Nabycie na stronie Profile księgowania środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="6dc94-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="6dc94-143">Jeśli opcja Korekta wartości początkowej jest wybrana w polu Typ transakcji, pole Konto główne po wybraniu opcji Korekta wartości początkowej na stronie Profile księgowania środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="6dc94-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-144">Użyj zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-145">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-146">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-147">Projekt zdefiniowany w wierszu faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="6dc94-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-148">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-149">Po wybraniu opcji Saldo w Księgowaniu kosztów — pole towaru na stronie Grupy projektu, pole Konto główne, gdy wybrana jest opcja Koszt na stronie Konfiguracja księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="6dc94-150">Po wybraniu opcji Zyski i straty w Księgowaniu kosztów — pole towaru na stronie Grupy projektu, pole Konto główne, gdy wybrana jest opcja Koszt — towar na stronie Konfiguracja księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-151">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6dc94-152">Rabat wiersza</span><span class="sxs-lookup"><span data-stu-id="6dc94-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-153">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-154">Pole Konto główne, gdy opcja Rabat jest wybrana na stronie Księgowanie.</span><span class="sxs-lookup"><span data-stu-id="6dc94-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="6dc94-155">Jeśli nie zdefiniowano konta głównego dla rabatów w profilu księgowania, zasada podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-156">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-157">Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-158">Użyj wartości wymiaru finansowego dla wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-159">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-160">Opłata za zakup, która jest wprowadzona na karcie Cena i rabat wiersza zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="6dc94-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-161">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-162">Zasada podziału księgowań rozszerzonej ceny w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-163">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-164">Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6dc94-165">Opłata za wiersz</span><span class="sxs-lookup"><span data-stu-id="6dc94-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-166">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-167">Jeśli wybrano Konto księgowe w polu debetu Typ w formularzu Kod opłat, pole debetu Konto na stronie Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="6dc94-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="6dc94-168">Jeśli wybrano Towar w polu debetu Typ w formularzu Kod opłat, zasady podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-169">Jeśli wybrano Odbiorca/Dostawca w polu debetu Typ w formularzu Kod opłat, pole kredytu Konto na stronie Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="6dc94-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-170">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-171">Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-172">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-173">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-174">Podatek, pod następującym warunkiem:</span><span class="sxs-lookup"><span data-stu-id="6dc94-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="6dc94-175">Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych jest wybrana na stronie Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="6dc94-176">Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-177">Zasady podziału księgowań dla ceny rozszerzonej lub opłaty.</span><span class="sxs-lookup"><span data-stu-id="6dc94-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-178">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-179">Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-180">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6dc94-181">Podatek, pod następującymi warunkami:</span><span class="sxs-lookup"><span data-stu-id="6dc94-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6dc94-182">Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych nie jest wybrana na stronie Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="6dc94-183">Pole Użyj podatku dla grupy podatku nie jest zaznaczone na stronie Grupy podatku.</span><span class="sxs-lookup"><span data-stu-id="6dc94-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="6dc94-184">Jeśli kwota podatku jest objęta zwrotem, pole Podatek naliczony na stronie Grupy księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="6dc94-185">Jeśli kwota podatku nie jest objęta zwrotem, cena rozszerzona lub zasada podziału księgowań dla opłaty.</span><span class="sxs-lookup"><span data-stu-id="6dc94-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-186">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-187">Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-188">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-189">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-190">Podatek, pod następującymi warunkami:</span><span class="sxs-lookup"><span data-stu-id="6dc94-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="6dc94-191">Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych nie jest wybrana na stronie Parametry księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="6dc94-192">Pole Użyj podatku dla grupy podatku jest zaznaczone na stronie Grupy podatku.</span><span class="sxs-lookup"><span data-stu-id="6dc94-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="6dc94-193">Jeśli kwota podatku jest objęta zwrotem, pole Podatek naliczony na stronie Grupy księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="6dc94-194">Jeśli kwota podatku nie jest objęta zwrotem, pole Wydatki podatku nienaliczonego na stronie Grupy księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-195">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-196">Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-197">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-198">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6dc94-199">Opłata w nagłówku</span><span class="sxs-lookup"><span data-stu-id="6dc94-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-200">Jeśli wybrano Konto księgowe w polu debetu Typ w formularzu Kod opłat, pole debetu Konto na stronie Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="6dc94-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="6dc94-201">Jeśli wybrano Odbiorca/Dostawca w polu debetu Typ w formularzu Kod opłat, pole kredytu Konto na stronie Kod opłat.</span><span class="sxs-lookup"><span data-stu-id="6dc94-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-202">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-203">Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</span><span class="sxs-lookup"><span data-stu-id="6dc94-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="6dc94-204">Użyj domyślnych wartości szablonu wymiaru finansowego z nagłówka faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="6dc94-205">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-206">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6dc94-207">Rabat dla nagłówka</span><span class="sxs-lookup"><span data-stu-id="6dc94-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="6dc94-208">Pole Konto główne dla typu księgowania Rabat na fakturze dostawcy na stronie Konta dla transakcji automatycznych.</span><span class="sxs-lookup"><span data-stu-id="6dc94-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="6dc94-209">Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="6dc94-210">Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-211">Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="6dc94-212">Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</span><span class="sxs-lookup"><span data-stu-id="6dc94-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="6dc94-213">Dystrybuowanie podatków</span><span class="sxs-lookup"><span data-stu-id="6dc94-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="6dc94-214">Zasady podziału księgowań dla podatków można utworzyć dopiero po obliczeniu podatków.</span><span class="sxs-lookup"><span data-stu-id="6dc94-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="6dc94-215">Aby obliczyć podatek, należy wykonać jedną z następujących czynności na stronie Faktura od dostawcy:</span><span class="sxs-lookup"><span data-stu-id="6dc94-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="6dc94-216">Wyświetl sumę faktury.</span><span class="sxs-lookup"><span data-stu-id="6dc94-216">View the invoice total.</span></span>
-   <span data-ttu-id="6dc94-217">Wyświetlanie podatku.</span><span class="sxs-lookup"><span data-stu-id="6dc94-217">View the sales tax.</span></span>
-   <span data-ttu-id="6dc94-218">Wyświetlanie arkusza księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-218">View the subledger journal.</span></span>
-   <span data-ttu-id="6dc94-219">Wyświetlanie zasad podziału księgowań dla kompletnej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="6dc94-220">Wstrzymywanie faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="6dc94-221">Księgowanie faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6dc94-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="6dc94-222">Arkusze księgi podrzędnej dla faktur od dostawcy</span><span class="sxs-lookup"><span data-stu-id="6dc94-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="6dc94-223">Przed zaksięgowaniem faktury od dostawcy, można wyświetlić pełny wpis księgowy faktury, który obejmuje obciążenia i uznania, aby zweryfikować, że faktura została zaksięgowana na właściwych kontach.</span><span class="sxs-lookup"><span data-stu-id="6dc94-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="6dc94-224">Ten widok pełnego wpisu księgowania nazywa się arkuszem księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="6dc94-225">Jeżeli zapis w arkuszu księgi podrzędnej jest nieprawidłowy w podglądzie przed zapisaniem faktury od dostawcy w arkuszu, nie można modyfikować zapisu w arkuszu księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="6dc94-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="6dc94-226">Zamiast tego należy zmodyfikować zasady podziału księgowań albo profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="6dc94-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="6dc94-227">Zasady podziału księgowań służą do definiowania jednej strony wpisu księgowania: debetu lub kredytu.</span><span class="sxs-lookup"><span data-stu-id="6dc94-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="6dc94-228">Zapis księgowania transakcji przeciwstawnych w arkuszu księgi podrzędnej jest tworzony za pomocą profilów księgowania, takich jak konto dostawcy lub podatek.</span><span class="sxs-lookup"><span data-stu-id="6dc94-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>






