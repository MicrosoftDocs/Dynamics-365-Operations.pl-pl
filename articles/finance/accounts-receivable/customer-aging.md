---
title: Raport wiekowania dla odbiorców
description: Raport wiekowania dla odbiorców zawiera salda należne od odbiorców, posortowane według interwałów dat lub okresów wiekowania.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236993"
---
# <a name="customer-aging-report"></a><span data-ttu-id="a2bcb-103">Raport wiekowania dla odbiorców</span><span class="sxs-lookup"><span data-stu-id="a2bcb-103">Customer aging report</span></span> 

<span data-ttu-id="a2bcb-104">Raport **Wiekowanie odbiorców** zawiera salda należne od odbiorców, posortowane według interwałów dat lub okresów wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="a2bcb-105">Podczas generowania tego raportu, wyświetlane są następujące parametry domyślne.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="a2bcb-106">Możesz używać tych parametrów filtrowania danych, które będą wyświetlane w raporcie.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="a2bcb-107">Aby uzyskać więcej informacji, zobacz [Konfigurowanie kolekcji](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a2bcb-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a2bcb-108">Pole</span><span class="sxs-lookup"><span data-stu-id="a2bcb-108">Field</span></span></p></th>
<th><p><span data-ttu-id="a2bcb-109">opis</span><span class="sxs-lookup"><span data-stu-id="a2bcb-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-110"><strong>Klasyfikacja faktur</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-111">Wybierz jedną lub kilka klasyfikacji faktur do uwzględnienia w raporcie.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="a2bcb-112">**Uwaga:** Ten formant jest dostępny tylko wtedy, gdy wybrano klucz konfiguracji <STRONG>Sektor publiczny</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-113"><strong>Uwzględnij transakcje bez klasyfikacji faktur</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-114">Jeśli to pole wyboru jest zaznaczone, w raporcie będą wyświetlane wszystkie transakcje, które nie mają przypisanej klasyfikacji faktur.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="a2bcb-115">**Uwaga:** Ten formant jest dostępny tylko wtedy, gdy wybrano klucz konfiguracji <STRONG>Sektor publiczny</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-116"><strong>Wiekowanie na dzień</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-117">Umożliwia wprowadzenie daty używanej w bieżącym zasobniku wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-118"><strong>Saldo na</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-119">Umożliwia wprowadzenie daty, według której będą wyświetlane salda odbiorców.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="a2bcb-120">Jest ona również określana jako data graniczna transakcji.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-121"><strong>Rozpoczęcie</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-122">Służy do wprowadzania daty należącej do pierwszego przedziału okresu lub okresu wiekowania do uwzględnienia w raporcie.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-123"><strong>Kryterium</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-124">Służy do wybrania typu daty, na której ma się opierać raport.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="a2bcb-125"><strong>Data transakcji</strong> – data księgowania wybranej transakcji.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="a2bcb-126">Na przykład może to być data faktury stanowiąca podstawę obliczania terminu płatności.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="a2bcb-127"><strong>Data ukończenia</strong> — termin transakcji na podstawie warunków płatności.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="a2bcb-128"><strong>Data dokumentu</strong> — data dokumentu zdefiniowanego przez użytkownika stanowiąca podstawę obliczeń terminu.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-129"><strong>Definicja okresu wiekowania</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-130">Wybierz definicję okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-130">Select an aging period definition.</span></span> <span data-ttu-id="a2bcb-131">Pole <strong>Interwał</strong> nie jest używane w przypadku wybrania definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="a2bcb-132">W wydrukowanym raporcie nie można używać definicji okresów wiekowania mających więcej niż sześć okresów wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="a2bcb-133">**Uwaga:** okresy wiekowania można skonfigurować na stronie <STRONG>Definicje okresów wiekowania</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-134"><strong>Drukuj opis okresu wiekowania</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-135">Wybierz opcję <strong>Tak</strong>, aby na górze każdej kolumny okresu wiekowania w raporcie uwzględnić opisy okresów wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="a2bcb-136">Wybierz opcję <strong>Nie</strong>, aby wydrukować raport bez nagłówków kolumn.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-137"><strong>Interwał</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-138">Służy do definiowania okresu do zastosowania za pomocą wprowadzenia liczby jednostek dni lub miesięcy w każdym okresie.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="a2bcb-139">Na przykład aby wyświetlić informacje wiekowania według tygodnia, wpisz 7 w tym polu i wybierz <strong>Dzień</strong> w polu <strong>Dzień/Mies</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="a2bcb-140">**Uwaga:** Informacje wprowadzone w tym polu są używane tylko, jeśli nie wybrano definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="a2bcb-141">W przeciwnym razie kierunek drukowania jest definiowany w definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-142"><strong>Dzień/Mies.</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-143">Służy do wybierania jednostki, <strong>Dzień</strong> lub <strong>Miesiąc</strong>, która jest stosowana do definiowania okresu w polu <strong>Interwał</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-144"><strong>Kierunek drukowania</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-145">Umożliwia określenie, czy mają być obliczane salda i drukowany raport wiekowania w przeszłych i przyszłych okresach.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="a2bcb-146">Daty są oceniane w odniesieniu do daty wybranej w polu <strong>Saldo na dzień</strong>.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="a2bcb-147">Należy wybrać opcję <strong>Wstecz</strong>, aby umieścić informacje dla minionych okresów.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="a2bcb-148">Należy wybrać opcję<strong>Dalej</strong>, aby umieścić informacje dla przyszłych okresów.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="a2bcb-149">
  
<STRONG>Uwaga:</STRONG> Informacje wprowadzone w tym polu są używane tylko, jeśli nie wybrano definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-150"><strong>Szczegóły</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-151">Wybierz, aby wyświetlić listę transakcji transakcji zawartych w saldach wyświetlonych w raporcie.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-152"><strong>Uwzględnij kwoty w walucie transakcji</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-153">Wybierz tę opcję, aby uwzględnić w walucie transakcji kwoty, oprócz kwot w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="a2bcb-154">Jeśli to pole wyboru nie jest zaznaczone, kwoty w raporcie są wyświetlane tylko w walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-155"><strong>Saldo ujemne</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-156">Wybierz tę opcję, aby uwzględnić konta odbiorców, które mają salda ujemne.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2bcb-157"><strong>Wyklucz zerowe konta bilansowe</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-158">Wybierz tę opcję, aby wykluczyć konta odbiorców, które mają salda zerowe.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2bcb-159"><strong>Pozycjonowanie płatności</strong></span><span class="sxs-lookup"><span data-stu-id="a2bcb-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="a2bcb-160">Wybranie tej opcji umożliwia wyświetlenie płatności, które nie zostały rozliczone.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="a2bcb-161">Są one wyświetlane w pierwszej kolumnie raportu.</span><span class="sxs-lookup"><span data-stu-id="a2bcb-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]