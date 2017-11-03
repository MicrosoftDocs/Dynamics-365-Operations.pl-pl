---
title: "Raporty podatków dla Polski (konfigurowanie informacji podatkowych i innych funkcji)"
description: "Ten temat zawiera informacje o sprawozdawczości podatku VAT w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce."
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 274063
ms.search.region: Poland
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4f256733cc2afa6c81c88ccc3435b28e1c4570e1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-reports-for-poland-setting-up-tax-information-and-other-features"></a><span data-ttu-id="0d49e-103">Raporty podatków dla Polski (konfigurowanie informacji podatkowych i innych funkcji)</span><span class="sxs-lookup"><span data-stu-id="0d49e-103">Sales tax reports for Poland (setting up tax information and other features)</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="0d49e-104">Ten temat zawiera informacje o sprawozdawczości podatku VAT w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce.</span><span class="sxs-lookup"><span data-stu-id="0d49e-104">This topic provides information about Polish VAT reporting and the information that is legally required in VAT registers for Poland.</span></span> 

## <a name="poland---vat-report-date-codes"></a><span data-ttu-id="0d49e-105">Polska — Kody dat raportu VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-105">Poland - VAT report date codes</span></span>

<span data-ttu-id="0d49e-106">Zgodnie z polską ustawą o rachunkowości, która weszła w życie dnia 29 września 1994 r., podatek od towarów i usług (VAT) dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="0d49e-106">Per the Polish Accountancy Act, which took effect on September 29, 1994, value-added tax (VAT) for sales, purchases, and imported products must be processed separately.</span></span> <span data-ttu-id="0d49e-107">Dla każdej zaksięgowanej transakcji sprzedaży lub zakupu, która ma ustawione pole **Data rejestru VAT** lub **Kod daty rejestru VAT**, podatek będzie wykazywany w odpowiednich rejestrach podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-107">For every posted sales transaction or purchase transaction where the **Date of VAT register** or **VAT report date code** field is set, the tax will be accounted in relevant VAT registers.</span></span> <span data-ttu-id="0d49e-108">Pole **Kod daty rejestru VAT** znajduje się na kilku stronach transakcji.</span><span class="sxs-lookup"><span data-stu-id="0d49e-108">The **VAT report date code** field appears on several transaction pages.</span></span> <span data-ttu-id="0d49e-109">Podczas aktualizowania lub księgowania transakcji informacje o kodzie daty raportu VAT są księgowane w tabelach podatku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-109">When you update or post transactions, information about the VAT report date code is posted to the tax tables.</span></span> <span data-ttu-id="0d49e-110">Następnie będą drukowane w polskim rejestrze podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-110">It will then be printed on the Polish VAT register.</span></span> <span data-ttu-id="0d49e-111">Aby skonfigurować kody dat raportu VAT, otwórz stronę **Kody dat raportu VAT** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Kody dat raportu VAT**) i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="0d49e-111">To set up VAT report date codes, open the **VAT report date codes** page (**Tax** &gt; **Setup** &gt; **Sales tax** &gt; **VAT report date codes**), and set the following fields.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d49e-112">Pole</span><span class="sxs-lookup"><span data-stu-id="0d49e-112">Field</span></span></th>
<th><span data-ttu-id="0d49e-113">opis</span><span class="sxs-lookup"><span data-stu-id="0d49e-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0d49e-114">Kod daty rejestru VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-114">VAT report date code</span></span></td>
<td><span data-ttu-id="0d49e-115">Wprowadź kod daty raportu VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-115">Enter the VAT report date code.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-116">opis</span><span class="sxs-lookup"><span data-stu-id="0d49e-116">Description</span></span></td>
<td><span data-ttu-id="0d49e-117">Wprowadź opis kodu daty raportu VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-117">Enter a description of the VAT report date code.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-118">Uwzględnij w raporcie podatku VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-118">Include in VAT report</span></span></td>
<td><span data-ttu-id="0d49e-119">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="0d49e-119">Select one of the following options:</span></span>
<ul>
<li><span data-ttu-id="0d49e-120"><strong>Z datą raportu VAT</strong> - Raport pokazuje całą kwotę faktury, jeśli obliczona data w polu <strong>Data rejestru VAT</strong> na stronie <strong>Księgowanie faktury</strong> mieści się w przedziale dat objętym raportem.</span><span class="sxs-lookup"><span data-stu-id="0d49e-120"><strong>With VAT report date</strong> - The report shows the whole invoice amount if the calculated date in the <strong>Date of VAT register</strong> field on the <strong>Invoice posting</strong> page is in the date interval for the report.</span></span></li>
<li><span data-ttu-id="0d49e-121"><strong>Z datą raportu VAT nie później niż</strong>  Raport pokazuje całą kwotę faktury, jeśli data w polu <strong>Data rejestru VAT</strong> mieści się w przedziale dat objętym raportem.</span><span class="sxs-lookup"><span data-stu-id="0d49e-121"><strong>With VAT report date not later than</strong>  The report shows the whole invoice amount if the date in the <strong>Date of VAT register</strong> field is in the date interval for the report.</span></span> <span data-ttu-id="0d49e-122">Data jest obliczana na podstawie informacji w polach <strong>Liczone od</strong> i <strong>Liczba dni</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-122">The date is calculated based on the information in the <strong>Counted from</strong> and <strong>Number of days</strong> fields.</span></span></li>
<li><span data-ttu-id="0d49e-123"><strong>Z datą fizycznej płatności</strong> - W przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczoną część kwoty faktury, jeśli interwał raportowania obejmuje daty płatności.</span><span class="sxs-lookup"><span data-stu-id="0d49e-123"><strong>With date of physical payment</strong> - If you select the <strong>Partial settlements</strong> check box, the report shows the settled part of the invoice amount if the reporting interval includes the payment dates.</span></span> <span data-ttu-id="0d49e-124">Jeśli pole wyboru <strong>Rozliczenia częściowe</strong> jest wyczyszczone, raport nie pokazuje kwoty faktury, dopóki faktura nie zostanie całkowicie rozliczona.</span><span class="sxs-lookup"><span data-stu-id="0d49e-124">If the <strong>Partial settlements</strong> check box is cleared, the report doesn't show the invoice amount until the invoice is completely settled.</span></span></li>
<li><span data-ttu-id="0d49e-125"><strong>Z datą fizycznej płatności nie później niż</strong> - W przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczenia, dokonane w przedziale dat objętym raportem.</span><span class="sxs-lookup"><span data-stu-id="0d49e-125"><strong>With date of physical payment not later than</strong> - If you select the <strong>Partial settlements</strong> check box, the report shows settlements that occur in the date interval for the report.</span></span> <span data-ttu-id="0d49e-126">Jeśli obliczona wartość w polu <strong>Data rejestru VAT</strong> znajduje się w zakresie dat raportu, raport pokazuje łączną kwotę faktury, z wyjątkiem rozliczonych kwot poprzedniego okresu.</span><span class="sxs-lookup"><span data-stu-id="0d49e-126">If the calculated value in the <strong>Date of VAT register</strong> field is in the date interval for the report, the report shows the whole invoice amount, except the settled amounts for the previous period.</span></span> <span data-ttu-id="0d49e-127">Jeśli pole wyboru <strong>Rozliczenie częściowe</strong> jest wyczyszczone, wybierz opcję <strong>Data transakcji</strong> lub <strong>Data VAT</strong> w polu <strong>Liczone od</strong>, aby określić kryterium używane do obliczania daty rejestru VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-127">If the <strong>Partial settlements</strong> check box is cleared, select <strong>Transaction date</strong> or <strong>VAT date</strong> in the <strong>Counted from</strong> field to specify the criterion that is used to calculate the date of the VAT register.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-128">Liczba dni</span><span class="sxs-lookup"><span data-stu-id="0d49e-128">Number of days</span></span></td>
<td><span data-ttu-id="0d49e-129">Umożliwia wprowadzanie liczby dni po dacie zarejestrowania podatku VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-129">Enter the number of days after the VAT date register.</span></span> <span data-ttu-id="0d49e-130">To pole jest dostępne tylko wtedy, gdy pole <strong>Uwzględnij w raporcie podatku VAT</strong> jest ustawione na wartość <strong>Z datą raportu VAT nie później niż</strong> lub <strong>Z datą fizycznej płatności nie później niż</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-130">This field is available only when the <strong>Include in VAT report</strong> field is set to either <strong>With VAT report date not later than</strong> or <strong>With date of physical payment not later than</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-131">Liczone od</span><span class="sxs-lookup"><span data-stu-id="0d49e-131">Counted from</span></span></td>
<td><span data-ttu-id="0d49e-132">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="0d49e-132">Select one of the following options:</span></span>
<ul>
<li><span data-ttu-id="0d49e-133">Data transakcji</span><span class="sxs-lookup"><span data-stu-id="0d49e-133">Transaction date</span></span></li>
<li><span data-ttu-id="0d49e-134">Data VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-134">VAT date</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-135">Rozliczenia częściowe</span><span class="sxs-lookup"><span data-stu-id="0d49e-135">Partial settlements</span></span></td>
<td><span data-ttu-id="0d49e-136">Zaznacz to pole wyboru, aby rozliczać płatności częściowo.</span><span class="sxs-lookup"><span data-stu-id="0d49e-136">Select this check box to partially settle the payments.</span></span> <span data-ttu-id="0d49e-137">To pole wyboru jest dostępne tylko wtedy, gdy pole <strong>Uwzględnij w raporcie podatku VAT</strong> jest ustawione na wartość <strong>Z datą fizycznej płatności</strong> lub <strong>Z datą fizycznej płatności nie później niż</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-137">This check box is available only when the <strong>Include in VAT report</strong> field is set to either <strong>With date of physical payment</strong> or <strong>With date of physical payment not later than</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-138">Data podatku VAT jest datą płatności</span><span class="sxs-lookup"><span data-stu-id="0d49e-138">VAT date is the same as payment date</span></span></td>
<td><span data-ttu-id="0d49e-139">Zaznaczenie tego pola wyboru spowoduje wyświetlanie kodu daty raportu VAT tylko wtedy, gdy data płatności podatku VAT jest taka sama, jak data w rejestrze VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-139">Select this check box to show the VAT report date code only if the date of payment for VAT is the same as the date in the VAT register.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0d49e-140">Następujące strony zawierają kod daty raportu VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-140">The following pages include the VAT report date code.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d49e-141">Strona</span><span class="sxs-lookup"><span data-stu-id="0d49e-141">Page</span></span></th>
<th><span data-ttu-id="0d49e-142">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="0d49e-142">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0d49e-143">Parametry modułu rozrachunków z dostawcami</span><span class="sxs-lookup"><span data-stu-id="0d49e-143">Accounts payable parameters</span></span>
<ul>
<li><span data-ttu-id="0d49e-144">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Parametry</strong> <strong>modułu</strong> <strong>rozrachunków z dostawcami</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-144">Click <strong>Accounts payable</strong> &gt; <strong>Setup</strong> &gt; <strong>Accounts</strong> <strong>payable</strong> <strong>parameters</strong>.</span></span></li>
</ul></td>
<td><span data-ttu-id="0d49e-145">Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Dostawca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych dostawców.</span><span class="sxs-lookup"><span data-stu-id="0d49e-145">On the <strong>General</strong> tab, on the <strong>Vendor</strong> FastTab, enter the VAT report date code that should be used as the default code for new vendors.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-146">Parametry modułu rozrachunków z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="0d49e-146">Accounts receivable parameters</span></span>
<ul>
<li><span data-ttu-id="0d49e-147">Kliknij kolejno opcje <strong>Rozrachunki</strong> <strong>z dostawcami</strong> &gt; <strong>Konfiguracja</strong> &gt; <strong>Parametry</strong> <strong>modułu</strong> <strong>rozrachunków z odbiorcami</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-147">Click <strong>Accounts</strong> <strong>receivable</strong> &gt; <strong>Setup</strong> &gt; <strong>Accounts</strong> <strong>receivable</strong> <strong>parameters</strong>.</span></span></li>
</ul></td>
<td><span data-ttu-id="0d49e-148">Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Odbiorca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="0d49e-148">On the <strong>General</strong> tab, on the <strong>Customer</strong> FastTab, enter the VAT report date code that should be used as the default code for new purchase orders.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-149">Obsługa przedpłat</span><span class="sxs-lookup"><span data-stu-id="0d49e-149">Prepayment handling</span></span>
<ol>
<li><span data-ttu-id="0d49e-150">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Szczegóły</strong> <strong>dostawcy</strong> &gt; <strong>Transakcje</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-150">Click <strong>Accounts payable</strong> &gt; <strong>Vendor</strong> <strong>details</strong> &gt; <strong>Transactions</strong>.</span></span> <span data-ttu-id="0d49e-151">-lub- Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Szczegóły</strong> <strong>odbiorcy</strong> &gt; <strong>Transakcje</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-151">-or- Click <strong>Accounts receivable</strong> &gt; <strong>Customer</strong> <strong>details</strong> &gt; <strong>Transactions</strong>.</span></span></li>
<li><span data-ttu-id="0d49e-152">Zaznacz transakcję przedpłaty, a następnie kliknij przycisk <strong>Obsługa przedpłat</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-152">Select a prepayment transaction, and then click <strong>Prepayment handling</strong>.</span></span></li>
</ol></td>
<td><span data-ttu-id="0d49e-153">Pole <strong>Kod daty rejestru VAT</strong> jest widoczne, jeśli wybrano opcję <strong>Zaawansowane</strong> w polu <strong>Obsługa przedpłat</strong> na stronie <strong>Parametry modułu rozrachunków z dostawcami</strong> lub <strong>Parametry modułu rozrachunków z odbiorcami</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-153">The <strong>VAT report date code</strong> field is visible if you selected <strong>Advanced</strong> in the <strong>Prepayment handling</strong> field on the <strong>Accounts payable parameters</strong> page or the <strong>Accounts receivable parameters</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-154">Zatwierdzenie faktury od dostawcy</span><span class="sxs-lookup"><span data-stu-id="0d49e-154">Vendor invoice approval</span></span>
<ul>
<li><span data-ttu-id="0d49e-155">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz zatwierdzania faktur</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-155">Click <strong>Accounts payable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Invoice approval journal</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-156">Pula faktur</span><span class="sxs-lookup"><span data-stu-id="0d49e-156">Invoice pool</span></span>
<ul>
<li><span data-ttu-id="0d49e-157">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Pula faktur</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-157">Click <strong>Accounts payable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Invoice pool</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-158">Rejestr faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="0d49e-158">Vendor invoice register</span></span>
<ul>
<li><span data-ttu-id="0d49e-159">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Rejestr faktur</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-159">Click <strong>Accounts payable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Invoice register</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-160">Arkusz faktur od dostawców</span><span class="sxs-lookup"><span data-stu-id="0d49e-160">Vendor invoice journal</span></span>
<ul>
<li><span data-ttu-id="0d49e-161">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz faktur</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-161">Click <strong>Accounts payable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Invoice journal</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-162">Wszystkie zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="0d49e-162">All purchase orders</span></span>
<ul>
<li><span data-ttu-id="0d49e-163">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Zamówienia zakupu</strong> &gt; <strong>Wszystkie zamówienia zakupu</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-163">Click <strong>Accounts payable</strong> &gt; <strong>Purchase orders</strong> &gt; <strong>All purchase orders</strong>.</span></span></li>
</ul></td>
<td><span data-ttu-id="0d49e-164">Kod daty raportu VAT jest wyświetlany w nagłówku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-164">The VAT report date code is shown on the header.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-165">Specyfikacja</span><span class="sxs-lookup"><span data-stu-id="0d49e-165">Specification</span></span>
<ul>
<li><span data-ttu-id="0d49e-166">Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong> &gt; <strong>Wszyscy dostawcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-166">Click <strong>Accounts payable</strong> &gt; <strong>Vendors</strong> &gt; <strong>All vendors</strong>.</span></span> <span data-ttu-id="0d49e-167">Na karcie <strong>Faktura</strong> w grupie <strong>Rozlicz</strong> kliknij opcję <strong>Rozlicz transakcje</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-167">On the <strong>Invoice</strong> tab, in the <strong>Settle</strong> group, click <strong>Settle transactions</strong>.</span></span> <span data-ttu-id="0d49e-168">Kliknij kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>. Następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zakup</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-168">Click <strong>Inquiry</strong> &gt; <strong>Specifications</strong>, Then, on the <strong>Setup</strong> tab, in the <strong>View</strong> field, select <strong>Purchase</strong>.</span></span> <span data-ttu-id="0d49e-169">-lub- Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong> &gt; <strong>Wszyscy odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-169">-or- Click <strong>Accounts receivable</strong> &gt; <strong>Customers</strong> &gt; <strong>All customers</strong>.</span></span> <span data-ttu-id="0d49e-170">Na karcie <strong>Windykacja</strong> w grupie <strong>Rozlicz</strong> kliknij opcję <strong>Rozlicz transakcje</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-170">On the <strong>Collect</strong> tab, in the <strong>Settle</strong> group, click <strong>Settle transactions</strong>.</span></span> <span data-ttu-id="0d49e-171">Kliknij kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-171">Click <strong>Inquiry</strong> &gt; <strong>Specifications</strong>.</span></span> <span data-ttu-id="0d49e-172">Następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zamówienie sprzedaży</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-172">Then, on the <strong>Setup</strong> tab, in the <strong>View</strong> field, select <strong>Sales order</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-173">Załącznik arkusza</span><span class="sxs-lookup"><span data-stu-id="0d49e-173">Journal voucher</span></span>
<ul>
<li><span data-ttu-id="0d49e-174">Na stronie arkusza finansowego, arkusza okresowego, arkusza kasowego lub arkusza wydatków kliknij opcję <strong>Wiersze</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-174">On the general journal, periodic journal, slip journal, or expense journal page, click <strong>Lines</strong>.</span></span></li>
</ul></td>
<td><span data-ttu-id="0d49e-175">Zapoznaj się z kartą <strong>Faktura</strong> lub kartą <strong>Płatność</strong>. <strong>Uwaga:</strong> Dla arkusza wydatków pole <strong>Typ konta przeciwstawnego</strong> należy ustawić na <strong>Dostawca</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-175">Review the <strong>Invoice</strong> tab or the <strong>Payment</strong> tab. <strong>Note:</strong> For the expense journal, the <strong>Offset type account</strong> field should be set to <strong>Vendor</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-176">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0d49e-176">Sales order</span></span>
<ul>
<li><span data-ttu-id="0d49e-177">Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Zamówienia</strong> &gt; <strong>Wszystkie zamówienia sprzedaży</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-177">Click <strong>Accounts receivable</strong> &gt; <strong>Orders</strong> &gt; <strong>All sales orders</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0d49e-178">Faktura niezależna</span><span class="sxs-lookup"><span data-stu-id="0d49e-178">Free text invoice</span></span>
<ul>
<li><span data-ttu-id="0d49e-179">Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Faktury niezależne</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-179">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Free text invoices</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0d49e-180">Zaksięgowany podatek</span><span class="sxs-lookup"><span data-stu-id="0d49e-180">Posted sales tax</span></span>
<ul>
<li><span data-ttu-id="0d49e-181">Kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Zapytania i raporty</strong> &gt; <strong>Zapytania o podatki</strong> &gt; <strong>Zaksięgowany podatek</strong>.</span><span class="sxs-lookup"><span data-stu-id="0d49e-181">Click <strong>Tax</strong> &gt; <strong>Inquiries ad reports</strong> &gt; <strong>Sales tax inquiries</strong> &gt; <strong>Posted sales tax</strong>.</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="poland---name-of-services-for-vat-reporting"></a><span data-ttu-id="0d49e-182">Polska — Nazwy usług raportowania podatku VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-182">Poland - Name of services for VAT reporting</span></span>
<span data-ttu-id="0d49e-183">Numery taryf usługowych są wymagane podczas raportowania informacji o podatku VAT związanych z transakcją ze stroną, która nie znajduje się w Polsce.</span><span class="sxs-lookup"><span data-stu-id="0d49e-183">Service tariff numbers are required when you report information about VAT that involves a transaction with a party that isn't located in Poland.</span></span> <span data-ttu-id="0d49e-184">Numery taryf usługowych ustawia się na stronie **Numery taryf usługowych**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-184">You set up service tariff numbers on the **Service tariff numbers** page.</span></span> <span data-ttu-id="0d49e-185">Aby skonfigurować numery taryf usługowych, kliknij kolejno opcje **Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Numer taryfy usługowej** i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="0d49e-185">To set up service tariff numbers, click **Tax** &gt; **Setup** &gt; **Sales tax** &gt; **Service tariff number**, and set the following fields.</span></span>

| <span data-ttu-id="0d49e-186">Pole</span><span class="sxs-lookup"><span data-stu-id="0d49e-186">Field</span></span>                      | <span data-ttu-id="0d49e-187">opis</span><span class="sxs-lookup"><span data-stu-id="0d49e-187">Description</span></span>                                                                          |
|----------------------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="0d49e-188">Numer taryfy usługowej</span><span class="sxs-lookup"><span data-stu-id="0d49e-188">Service tariff number</span></span>      | <span data-ttu-id="0d49e-189">Wprowadź numer taryfy usługowej, który został przypisany do strony przez organ administracji państwowej.</span><span class="sxs-lookup"><span data-stu-id="0d49e-189">Enter the service tariff number that the government authority assigned to the party.</span></span> |
| <span data-ttu-id="0d49e-190">Opis taryfy usługowej</span><span class="sxs-lookup"><span data-stu-id="0d49e-190">Service tariff description</span></span> | <span data-ttu-id="0d49e-191">Umożliwia wprowadzanie opisu numeru taryfy usługowej.</span><span class="sxs-lookup"><span data-stu-id="0d49e-191">Enter a description of the service tariff number.</span></span>                                    |

<span data-ttu-id="0d49e-192">Można również ustawić parametr obowiązkowości numeru taryfy usługowej.</span><span class="sxs-lookup"><span data-stu-id="0d49e-192">You can also set a parameter to make the service tariff number mandatory.</span></span> <span data-ttu-id="0d49e-193">Kliknij kolejno opcje **Podatek** &gt; **Podatek** &gt; **Grupa podatków**, a następnie na skróconej karcie **Ogólne** ustaw pole **Obowiązkowy numer taryfy usługowej**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-193">Click **Tax** &gt; **Sales tax** &gt; **Sales tax group**, and then, on the **General** FastTab, set the **Mandatory service tariff number** field.</span></span> <span data-ttu-id="0d49e-194">Parametr **Obowiązkowy numer taryfy usługowej** parametr ma wpływ na następujące strony:</span><span class="sxs-lookup"><span data-stu-id="0d49e-194">The **Mandatory service tariff number** parameter affects the following pages:</span></span>

-   <span data-ttu-id="0d49e-195">**Wszystkie zamówienia sprzedaży** (kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Zamówienia** &gt; **Wszystkie zamówienia sprzedaży**) (nagłówek i wiersze)</span><span class="sxs-lookup"><span data-stu-id="0d49e-195">**All sales orders** (click **Accounts receivable** &gt; **Orders** &gt; **All sales orders**) (Header and lines)</span></span>
-   <span data-ttu-id="0d49e-196">**Wszystkie faktury niezależne** (kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Faktury**&gt; **Wszystkie faktury niezależne**) (nagłówek i wiersze)</span><span class="sxs-lookup"><span data-stu-id="0d49e-196">**All free text invoices** (click **Accounts receivable** &gt; **Invoices**&gt; **All free text invoices**) (Header and lines)</span></span>
-   <span data-ttu-id="0d49e-197">**Unieważnione zamówienia sprzedaży** (kliknij kolejno opcje **Sprzedaż i marketing** &gt; **Zapytania i raporty** &gt; **Historia** &gt; **Unieważnione zamówienia sprzedaży**, a następnie opcję **Pokaż**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-197">**Voided sales orders** (click **Sales and marketing** &gt; **Inquiries and reports** &gt; **History** &gt; **Voided sales orders**, and then click **Show**)</span></span>

<span data-ttu-id="0d49e-198">Następujące wspólne funkcje działają na wszystkich powyższych stronach:</span><span class="sxs-lookup"><span data-stu-id="0d49e-198">The following shared functionality works on all the preceding pages:</span></span>

-   <span data-ttu-id="0d49e-199">Podczas tworzenia nowego wiersza numer taryfy usługowej jest kopiowany z nagłówka do wiersza.</span><span class="sxs-lookup"><span data-stu-id="0d49e-199">When you create a new line, the service tariff number is copied from the header to the line.</span></span>
-   <span data-ttu-id="0d49e-200">Jeśli parametr **Obowiązkowy numer taryfy usługowej** jest włączony w grupie podatków, faktura zostanie zatrzymana i pojawi się komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="0d49e-200">If the **Mandatory service tariff number** parameter is enabled on the sales tax group, the invoice is stopped, and you receive an error message.</span></span>
-   <span data-ttu-id="0d49e-201">Podczas księgowania faktury transakcje podatku są dzielone według numerów taryf usługowych.</span><span class="sxs-lookup"><span data-stu-id="0d49e-201">When you post an invoice, sales tax transactions are split by service tariff number.</span></span> <span data-ttu-id="0d49e-202">Nawet grupa podatków i grupa podatków dla towaru są takie same.</span><span class="sxs-lookup"><span data-stu-id="0d49e-202">Even the sales tax group and item sales tax group are the same.</span></span>
-   <span data-ttu-id="0d49e-203">Podczas tworzenia faktury korygującej dla dowolnej zaksięgowanej faktury, której wiersze mają wartość w polu **Numer taryfy usługowej**, numer taryfy usługowej jest kopiowany do wierszy faktury korygującej z oryginalnego dokumentu, a nie z nagłówka faktury korygującej.</span><span class="sxs-lookup"><span data-stu-id="0d49e-203">When you create a credit note for any posted invoice where the lines have a value in the **Service tariff number** field, the service tariff number is copied to credit note lines from the original document, not from the credit note header.</span></span> <span data-ttu-id="0d49e-204">Numer taryfy usługowej może być edytowany dla wiersza korekty.</span><span class="sxs-lookup"><span data-stu-id="0d49e-204">The service tariff number can be edited on for the correction line.</span></span>

## <a name="poland---base-amount-for-vat"></a><span data-ttu-id="0d49e-205">Polska — Kwota podstawy podatku VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-205">Poland - Base amount for VAT</span></span>
<span data-ttu-id="0d49e-206">Pole **Kwota podstawy podatku VAT** jest włączone podczas wprowadzania transakcji podatku (pole **Kod podatku** ma wartość w wierszach arkusza) w następujących arkuszach:</span><span class="sxs-lookup"><span data-stu-id="0d49e-206">The **Base amount for VAT** field is enabled when you enter a tax transaction (the **Tax code** field has a value on journal lines) in the following journals:</span></span>

-   <span data-ttu-id="0d49e-207">Arkusz faktur (kliknij kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-207">Invoice journal (click **Accounts payable** &gt; **Journals** &gt; **Invoices** &gt; **Invoice journal**, click **Lines**, and then click the **General** tab)</span></span>
-   <span data-ttu-id="0d49e-208">Arkusz finansowy (kliknij kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-208">General journal (click **General ledger** &gt; **Journals** &gt; **General journal**, click **Lines**, and then click the **General** tab)</span></span>
-   <span data-ttu-id="0d49e-209">Arkusz kasowy (kliknij kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Transakcje kasowe** &gt; **Arkusz kasowy**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-209">Slip journal (click **Cash and bank management** &gt; **Cash transactions** &gt; **Slip journal**, click **Lines**, and then click the **General** tab)</span></span>

<span data-ttu-id="0d49e-210">W polu **Kwota podstawy podatku VAT** należy ręcznie wprowadzić kwotę podstawy podatku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-210">In the **Base amount for VAT** field, you manually enter the tax base amount.</span></span> <span data-ttu-id="0d49e-211">Po zaksięgowaniu arkusza wartość z pola **Kwota podstawy podatku VAT** jest przenoszona do pola **Podstawa opodatkowania** w transakcjach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="0d49e-211">After you post a journal, the value from the **Base amount for VAT** field transferred to **the Amount origin** field in tax transactions.</span></span>

## <a name="poland---sales-tax-vat-reporting"></a><span data-ttu-id="0d49e-212">Polska — Raportowanie podatku (VAT)</span><span class="sxs-lookup"><span data-stu-id="0d49e-212">Poland - Sales tax (VAT) reporting</span></span>
<span data-ttu-id="0d49e-213">Ta funkcja jest używana w arkuszach księgi, gdzie wiele wierszy ma ten sam załącznik.</span><span class="sxs-lookup"><span data-stu-id="0d49e-213">This feature is used in ledger journals where multiple lines have the same voucher.</span></span> <span data-ttu-id="0d49e-214">Gdy poniższe pola w jednym wierszu ulegają zmianie, pojawia się okno komunikatu umożliwiające zaktualizowanie pól w innych wierszach mających ten sam załącznik:</span><span class="sxs-lookup"><span data-stu-id="0d49e-214">When the following fields on one line are changed, a message box appears that lets you update the fields on other lines that have the same voucher:</span></span>

-   <span data-ttu-id="0d49e-215">Faktura VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-215">Invoice</span></span>
-   <span data-ttu-id="0d49e-216">Data dokumentu</span><span class="sxs-lookup"><span data-stu-id="0d49e-216">Document date</span></span>
-   <span data-ttu-id="0d49e-217">Adres</span><span class="sxs-lookup"><span data-stu-id="0d49e-217">Address</span></span>
-   <span data-ttu-id="0d49e-218">NIP</span><span class="sxs-lookup"><span data-stu-id="0d49e-218">Tax exempt number</span></span>
-   <span data-ttu-id="0d49e-219">Odbiorca/dostawca</span><span class="sxs-lookup"><span data-stu-id="0d49e-219">Customer/ Vendor</span></span>
-   <span data-ttu-id="0d49e-220">Data rejestru VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-220">Date of VAT register</span></span>
-   <span data-ttu-id="0d49e-221">Kod daty rejestru VAT</span><span class="sxs-lookup"><span data-stu-id="0d49e-221">VAT report date code</span></span>

> [!NOTE]
> <span data-ttu-id="0d49e-222">Okno komunikatu pojawia się tylko wtedy, gdy pola zostały zmodyfikowane dla wiersza, w którym skonfigurowano grupę podatków, grupę podatków dla towaru i kod podatku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-222">The message box appears only when the fields were changed for a line where a sales tax group, item sales tax group, and sales tax code are set up.</span></span> <span data-ttu-id="0d49e-223">Komunikat jest wywoływany na następujących stronach arkusza:</span><span class="sxs-lookup"><span data-stu-id="0d49e-223">The message is triggered on the following journal pages:</span></span>

-   <span data-ttu-id="0d49e-224">Arkusz finansowy (kliknij kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, a następnie kliknij opcję **Wiersze**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-224">General journal (click **General ledger** &gt; **Journals** &gt; **General journal**, and then click **Lines**)</span></span>
-   <span data-ttu-id="0d49e-225">Arkusz faktur (kliknij kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, a następnie kliknij opcję **Wiersze**)</span><span class="sxs-lookup"><span data-stu-id="0d49e-225">Invoice journal (click **Accounts payable** &gt; **Journals** &gt; **Invoices** &gt; **Invoice journal**, and then click **Lines**)</span></span>

## <a name="poland---tax-direction-for-the-line"></a><span data-ttu-id="0d49e-226">Polska — Kierunek podatku dla wiersza</span><span class="sxs-lookup"><span data-stu-id="0d49e-226">Poland - Tax direction for the line</span></span>
<span data-ttu-id="0d49e-227">Ta funkcja dotyczy księgowań za pośrednictwem arkusza finansowego, który obejmuje transakcje podatkowe.</span><span class="sxs-lookup"><span data-stu-id="0d49e-227">The feature is related to postings through the general journal that involves sales tax transactions.</span></span> <span data-ttu-id="0d49e-228">System automatycznie ustala kierunek podatku, który powinien być przypisywany do tworzonych transakcji podatkowych, w oparciu o typ konta użyty do księgowania.</span><span class="sxs-lookup"><span data-stu-id="0d49e-228">The system automatically determines the sales tax direction that should be assigned to tax transactions that are created, based on the account type that was used for the posting.</span></span> <span data-ttu-id="0d49e-229">Ta funkcja umożliwia poprawne ustalenie kont głównych i poprawne przypisanie kierunku podatku dla wierszy arkusza finansowego w tym samym załączniku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-229">This feature enables main accounts to be determined correctly and the sales tax direction to be assigned correctly for general journal lines within the same voucher.</span></span> <span data-ttu-id="0d49e-230">Wiersze muszą spełniać jeden z następujących warunków:</span><span class="sxs-lookup"><span data-stu-id="0d49e-230">Lines must meet one of the following conditions:</span></span>

-   <span data-ttu-id="0d49e-231">Konto jest typu **Odbiorca**, **Dostawca** lub **Gotówka podręczna**, a typem konta przeciwstawnego jest **Księga**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-231">The account type is **Customer**, **Vendor**, or **Petty cash**, and the offset account type is **Ledger**.</span></span> <span data-ttu-id="0d49e-232">Konto przeciwstawne musi być określone.</span><span class="sxs-lookup"><span data-stu-id="0d49e-232">The offset account must be specified.</span></span>
-   <span data-ttu-id="0d49e-233">Konto jest typu **Księga**, a typem konta przeciwstawnego jest **Odbiorca**, **Dostawca** lub **Gotówka podręczna**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-233">The account type is **Ledger**, and the offset account type is **Customer**, **Vendor**, or **Petty cash**.</span></span> <span data-ttu-id="0d49e-234">Konto przeciwstawne musi być określone.</span><span class="sxs-lookup"><span data-stu-id="0d49e-234">The offset account must be specified.</span></span>

<span data-ttu-id="0d49e-235">Dla wierszy arkusza finansowego spełniających powyższe warunki system przypisuje osobny kierunek podatku w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0d49e-235">For general journal lines that meet the preceding conditions, the system assigns a separate sales tax direction, as follows:</span></span>

-   <span data-ttu-id="0d49e-236">**Podatek należny** dla typ konta **Odbiorca**</span><span class="sxs-lookup"><span data-stu-id="0d49e-236">**Sales tax payable** for the **Customer** account type</span></span>
-   <span data-ttu-id="0d49e-237">**Podatek naliczony** dla typ konta **Dostawca**</span><span class="sxs-lookup"><span data-stu-id="0d49e-237">**Sales tax receivable** for the **Vendor** account type</span></span>
-   <span data-ttu-id="0d49e-238">**Podatek należny** dla typ konta **Gotówka podręczna**</span><span class="sxs-lookup"><span data-stu-id="0d49e-238">**Sales tax payable** for the **Petty cash** account type</span></span>

### <a name="example"></a><span data-ttu-id="0d49e-239">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d49e-239">Example</span></span>

<span data-ttu-id="0d49e-240">Tworzysz następujące wiersze arkusza finansowego:</span><span class="sxs-lookup"><span data-stu-id="0d49e-240">You create the following general journal lines.</span></span>

| <span data-ttu-id="0d49e-241">Typ konta</span><span class="sxs-lookup"><span data-stu-id="0d49e-241">Account type</span></span> | <span data-ttu-id="0d49e-242">Numer konta</span><span class="sxs-lookup"><span data-stu-id="0d49e-242">Account number</span></span> | <span data-ttu-id="0d49e-243">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="0d49e-243">Debit</span></span> | <span data-ttu-id="0d49e-244">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="0d49e-244">Credit</span></span> | <span data-ttu-id="0d49e-245">Typ konta przeciwstawnego</span><span class="sxs-lookup"><span data-stu-id="0d49e-245">Offset account type</span></span> | <span data-ttu-id="0d49e-246">Numer konta przeciwstawnego</span><span class="sxs-lookup"><span data-stu-id="0d49e-246">Offset account number</span></span> | <span data-ttu-id="0d49e-247">Grupa księgowania podatków</span><span class="sxs-lookup"><span data-stu-id="0d49e-247">Sales tax posting group</span></span> | <span data-ttu-id="0d49e-248">Grupa księgowania podatków dla towarów</span><span class="sxs-lookup"><span data-stu-id="0d49e-248">Item sales tax posting group</span></span> |
|--------------|----------------|-------|--------|---------------------|-----------------------|-------------------------|------------------------------|
| <span data-ttu-id="0d49e-249">Odbiorca</span><span class="sxs-lookup"><span data-stu-id="0d49e-249">Customer</span></span>     | <span data-ttu-id="0d49e-250">1101</span><span class="sxs-lookup"><span data-stu-id="0d49e-250">1101</span></span>           |       | <span data-ttu-id="0d49e-251">800</span><span class="sxs-lookup"><span data-stu-id="0d49e-251">800</span></span>    | <span data-ttu-id="0d49e-252">Księga</span><span class="sxs-lookup"><span data-stu-id="0d49e-252">Ledger</span></span>              | <span data-ttu-id="0d49e-253">0101</span><span class="sxs-lookup"><span data-stu-id="0d49e-253">0101</span></span>                  | <span data-ttu-id="0d49e-254">AR-DOM</span><span class="sxs-lookup"><span data-stu-id="0d49e-254">AR-DOM</span></span>                  | <span data-ttu-id="0d49e-255">PEŁNE</span><span class="sxs-lookup"><span data-stu-id="0d49e-255">FULL</span></span>                         |
| <span data-ttu-id="0d49e-256">Dostawca</span><span class="sxs-lookup"><span data-stu-id="0d49e-256">Vendor</span></span>       | <span data-ttu-id="0d49e-257">1001</span><span class="sxs-lookup"><span data-stu-id="0d49e-257">1001</span></span>           |       | <span data-ttu-id="0d49e-258">800</span><span class="sxs-lookup"><span data-stu-id="0d49e-258">800</span></span>    | <span data-ttu-id="0d49e-259">Księga</span><span class="sxs-lookup"><span data-stu-id="0d49e-259">Ledger</span></span>              | <span data-ttu-id="0d49e-260">0101</span><span class="sxs-lookup"><span data-stu-id="0d49e-260">0101</span></span>                  | <span data-ttu-id="0d49e-261">AR-DOM</span><span class="sxs-lookup"><span data-stu-id="0d49e-261">AR-DOM</span></span>                  | <span data-ttu-id="0d49e-262">PEŁNE</span><span class="sxs-lookup"><span data-stu-id="0d49e-262">FULL</span></span>                         |
| <span data-ttu-id="0d49e-263">Księga</span><span class="sxs-lookup"><span data-stu-id="0d49e-263">Ledger</span></span>       | <span data-ttu-id="0d49e-264">0102</span><span class="sxs-lookup"><span data-stu-id="0d49e-264">0102</span></span>           | <span data-ttu-id="0d49e-265">700</span><span class="sxs-lookup"><span data-stu-id="0d49e-265">700</span></span>   |        |                     |                       | <span data-ttu-id="0d49e-266">AR-DOM</span><span class="sxs-lookup"><span data-stu-id="0d49e-266">AR-DOM</span></span>                  | <span data-ttu-id="0d49e-267">PEŁNE</span><span class="sxs-lookup"><span data-stu-id="0d49e-267">FULL</span></span>                         |
| <span data-ttu-id="0d49e-268">Księga</span><span class="sxs-lookup"><span data-stu-id="0d49e-268">Ledger</span></span>       | <span data-ttu-id="0d49e-269">0103</span><span class="sxs-lookup"><span data-stu-id="0d49e-269">0103</span></span>           |       | <span data-ttu-id="0d49e-270">700</span><span class="sxs-lookup"><span data-stu-id="0d49e-270">700</span></span>    |                     |                       | <span data-ttu-id="0d49e-271">AR-DOM</span><span class="sxs-lookup"><span data-stu-id="0d49e-271">AR-DOM</span></span>                  | <span data-ttu-id="0d49e-272">PEŁNE</span><span class="sxs-lookup"><span data-stu-id="0d49e-272">FULL</span></span>                         |

<span data-ttu-id="0d49e-273">Poniżej przedstawiono wyniki księgowania:</span><span class="sxs-lookup"><span data-stu-id="0d49e-273">Here are the results of the posting:</span></span>

-   <span data-ttu-id="0d49e-274">Wiersz 1 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-274">Line 1 has a tax transaction that has a sales tax direction of **Sales tax payable**.</span></span>
-   <span data-ttu-id="0d49e-275">Wiersz 2 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-275">Line 2 has a tax transaction that has a sales tax direction of **Sales tax receivable**.</span></span>
-   <span data-ttu-id="0d49e-276">Wiersz 3 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-276">Line 3 has a tax transaction that has a sales tax direction of **Sales tax receivable**.</span></span>
-   <span data-ttu-id="0d49e-277">Wiersz 4 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.</span><span class="sxs-lookup"><span data-stu-id="0d49e-277">Line 4 has a tax transaction that has a sales tax direction of **Sales tax payable**.</span></span>

## <a name="poland---ssrs-vat-register-report"></a><span data-ttu-id="0d49e-278">Polska — Raport rejestru podatku VAT usług SSRS</span><span class="sxs-lookup"><span data-stu-id="0d49e-278">Poland - SSRS VAT register report</span></span>
<span data-ttu-id="0d49e-279">Raport **Rejestr VAT** jest traktowany jako główny dokument podsumowania podatku.</span><span class="sxs-lookup"><span data-stu-id="0d49e-279">The **VAT register** report is considered the main tax summary document.</span></span> <span data-ttu-id="0d49e-280">Na tym raporcie jest oparta deklaracja VAT.</span><span class="sxs-lookup"><span data-stu-id="0d49e-280">The VAT statement is prepared based on this report.</span></span> <span data-ttu-id="0d49e-281">Jest to główny dokument kontrolny w sprawozdawczości podatkowej w każdej polskiej firmie.</span><span class="sxs-lookup"><span data-stu-id="0d49e-281">It's the main tax reporting audit document in every Polish company.</span></span> <span data-ttu-id="0d49e-282">Podatek VAT dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="0d49e-282">The VAT for sales, purchases, and imported products must be processed separately.</span></span> <span data-ttu-id="0d49e-283">Ustawodawstwo określa także kilka oficjalnych sprawozdań podatku VAT oraz warunki transakcji, które muszą zostać uwzględnione w sprawozdaniach.</span><span class="sxs-lookup"><span data-stu-id="0d49e-283">The legislation also defines several official reports for VAT and conditions for transactions that must be included on the reports.</span></span> <span data-ttu-id="0d49e-284">Raport **Rejestr VAT** jest podstawowym dokumentem używanym w polskiej rachunkowości do raportowania podatków urzędowi skarbowemu.</span><span class="sxs-lookup"><span data-stu-id="0d49e-284">The **VAT register** report is a basic document that is used in Polish accounting as the basis for reporting taxes to the tax authorities.</span></span> <span data-ttu-id="0d49e-285">Rejestry VAT są drukowane regularnie według okresów sprawozdawczych.</span><span class="sxs-lookup"><span data-stu-id="0d49e-285">The VAT registers are printed regularly for reporting periods.</span></span> <span data-ttu-id="0d49e-286">(Zazwyczaj są drukowane co miesiąc). Raporty muszą być wydrukowane na papierze i podpisane przez jedną lub więcej uprawnionych osób, takich jak główny księgowy lub dyrektor finansowy.</span><span class="sxs-lookup"><span data-stu-id="0d49e-286">(They are usually printed every month.) The reports must be printed on paper, and they must be signed by one or more authorities, such as a chief accountant or a CFO.</span></span> <span data-ttu-id="0d49e-287">Raporty te są używane jako podstawa miesięcznej deklaracji podatkowej VAT-7.</span><span class="sxs-lookup"><span data-stu-id="0d49e-287">They are used as the basis for the monthly VAT 7 tax declaration.</span></span> <span data-ttu-id="0d49e-288">Dostęp do raportów **Rejestr VAT** można uzyskać z kilku miejsc:</span><span class="sxs-lookup"><span data-stu-id="0d49e-288">You can access **VAT register** reports from several places:</span></span>

-   <span data-ttu-id="0d49e-289">Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Sumaryczny rejestr podatku VAT (UE)</span><span class="sxs-lookup"><span data-stu-id="0d49e-289">Tax &gt; Inquiries and reports &gt; Sales tax reports &gt; EU summary VAT register</span></span>
-   <span data-ttu-id="0d49e-290">Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Rejestr VAT zakupów</span><span class="sxs-lookup"><span data-stu-id="0d49e-290">Tax &gt; Inquiries and reports &gt; Sales tax reports &gt; Purchase VAT register</span></span>
-   <span data-ttu-id="0d49e-291">Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Rejestr VAT sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0d49e-291">Tax &gt; Inquiries and reports &gt; Sales tax reports &gt; Sales VAT register</span></span>




