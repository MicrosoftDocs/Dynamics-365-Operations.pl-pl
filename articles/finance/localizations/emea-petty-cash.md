---
title: Zarządzanie gotówką podręczną dla Europy Wschodniej i Rosji
description: Ten temat zawiera informacje o funkcji gotówki podręcznej, która pozwala użytkownikom w Estonii, na Litwie, w Czechach, na Węgrzech, na Łotwie, w Polsce i w Rosji uwzględniać operacje gotówkowe w systemie.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 268504
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a721d5602fa7b569b56e85e1bd66a8e543a39a41
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832703"
---
# <a name="petty-cash-for-eastern-europe-and-russia"></a><span data-ttu-id="9d48c-103">Zarządzanie gotówką podręczną dla Europy Wschodniej i Rosji</span><span class="sxs-lookup"><span data-stu-id="9d48c-103">Petty cash for Eastern Europe and Russia</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d48c-104">Ten temat zawiera informacje o funkcji gotówki podręcznej, która pozwala użytkownikom w Estonii, na Litwie, w Czechach, na Węgrzech, na Łotwie, w Polsce i w Rosji uwzględniać operacje gotówkowe w systemie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-104">This topic provides information about the petty cash functionality that lets users in Estonia, Lithuania, Czech Republic, Hungary, Latvia, Poland, and Russia reflect cash operations in the system.</span></span>

<span data-ttu-id="9d48c-105">Funkcja gotówki podręcznej umożliwia automatyzację operacji przychodów i rozchodów gotówkowych, tworzenie dokumentów podstawowych i drukowanie powiązanych raportów.</span><span class="sxs-lookup"><span data-stu-id="9d48c-105">You can use the petty cash functionality to automate operations for receipts and expenditures of cash, the creation of primary documents, and the printing of related reports.</span></span> <span data-ttu-id="9d48c-106">Funkcjonalność gotówki podręcznej umożliwia wykonywanie następujących operacji:</span><span class="sxs-lookup"><span data-stu-id="9d48c-106">The petty cash functionality lets you perform the following operations:</span></span>

-   <span data-ttu-id="9d48c-107">Rozliczanie przychodów i rozchodów dostępnych aktywów gotówkowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-107">Account the receipt and expenditure of available cash assets.</span></span>
-   <span data-ttu-id="9d48c-108">Generowanie typowych formularzy obrotu gotówkowego: dokumentów KP, dokumentów KW oraz arkusza rejestracji dokumentów kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-108">Generate typical cash forms: Cash reimbursement slips, Cash disbursement slips, and a Journal of registration for cash slips.</span></span>
-   <span data-ttu-id="9d48c-109">Kontrolowanie maksymalnej kwoty środków pieniężnych dozwolonej w operacjach z odbiorcami, dostawcami itd.</span><span class="sxs-lookup"><span data-stu-id="9d48c-109">Control the maximum cash amount that is allowed for operations with customers, vendors, and so on.</span></span>
-   <span data-ttu-id="9d48c-110">Uwzględnianie operacji gotówkowych w różnych walutach w systemie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-110">Reflect cash operations in various currencies in the system.</span></span>
-   <span data-ttu-id="9d48c-111">Konwertowanie kwot operacji gotówkowych w walutach obcych na walutę domyślną na potrzeby sprawozdawczości księgowej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-111">Convert the amounts of cash operations in foreign currency to the default currency to provide accounting reporting.</span></span>
-   <span data-ttu-id="9d48c-112">Generowanie raportu **Księga kasowa** i raportu kasjera.</span><span class="sxs-lookup"><span data-stu-id="9d48c-112">Generate a **Cash book** report and a cashier’s report.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d48c-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9d48c-113">Prerequisites</span></span>
<span data-ttu-id="9d48c-114">Aby można było używać funkcji gotówki podręcznej, należy wykonać następujące czynności wstępne:</span><span class="sxs-lookup"><span data-stu-id="9d48c-114">Before you can use the petty cash functionality, you must complete the following prerequisites:</span></span>

-   <span data-ttu-id="9d48c-115">Skonfigurowanie kont kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-115">Set up cash accounts.</span></span>
-   <span data-ttu-id="9d48c-116">Skonfigurowanie profili księgowania kasy.</span><span class="sxs-lookup"><span data-stu-id="9d48c-116">Set up cash posting profiles.</span></span>
-   <span data-ttu-id="9d48c-117">Skonfigurowanie numeracji dokumentów kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-117">Set up number sequences for cash document numbering.</span></span>
-   <span data-ttu-id="9d48c-118">Skonfigurowanie domyślnych wartości modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="9d48c-118">Set up default values for Cash and bank management parameters.</span></span>
-   <span data-ttu-id="9d48c-119">Skonfigurowanie nazw arkuszy kasowych w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-119">Set up cash journal names in General ledger.</span></span>

### <a name="set-up-cash-accounts"></a><span data-ttu-id="9d48c-120">Konfigurowanie kont kasowych</span><span class="sxs-lookup"><span data-stu-id="9d48c-120">Set up cash accounts</span></span>

<span data-ttu-id="9d48c-121">Aby skonfigurować konto kasowe, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe** &gt; **Konta kasowe** i wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9d48c-121">To set up a Cash, open **Cash and bank management** &gt; **Bank accounts** &gt; **Cash accounts**, and enter the following information.</span></span>

| <span data-ttu-id="9d48c-122">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-122">Field</span></span>                 | <span data-ttu-id="9d48c-123">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-123">Description</span></span>                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9d48c-124">Kasa</span><span class="sxs-lookup"><span data-stu-id="9d48c-124">Cash</span></span>                  | <span data-ttu-id="9d48c-125">Wprowadź kod identyfikujący konto kasowe (obrót gotówką).</span><span class="sxs-lookup"><span data-stu-id="9d48c-125">Enter a code to identify the cash account (cash).</span></span>                                                                    |
| <span data-ttu-id="9d48c-126">Nazwisko</span><span class="sxs-lookup"><span data-stu-id="9d48c-126">Name</span></span>                  | <span data-ttu-id="9d48c-127">Wprowadź opis konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-127">Enter a description of the cash account.</span></span>                                                                             |
| <span data-ttu-id="9d48c-128">Waluta</span><span class="sxs-lookup"><span data-stu-id="9d48c-128">Currency</span></span>              | <span data-ttu-id="9d48c-129">Wybierz domyślny kod waluty dla transakcji kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-129">Select the default currency code for cash transactions.</span></span>                                                              |
| <span data-ttu-id="9d48c-130">Grupa sekwencji numerów</span><span class="sxs-lookup"><span data-stu-id="9d48c-130">Number sequence group</span></span> | <span data-ttu-id="9d48c-131">Jeśli numeracja dokumentów kasowych musi się różnić od numeracji określonej w parametrach, wprowadź odpowiedni kod.</span><span class="sxs-lookup"><span data-stu-id="9d48c-131">If the numbering of cash documents must differ from the numbering that is specified in the parameters, enter a code.</span></span> |
| <span data-ttu-id="9d48c-132">Wiele walut</span><span class="sxs-lookup"><span data-stu-id="9d48c-132">More currencies</span></span>       | <span data-ttu-id="9d48c-133">Zaznacz to pole wyboru, aby umożliwić księgowanie walut różniących się od waluty rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-133">Select this check box to allow currencies that differ from the accounting currency to be posted.</span></span>                     |
| <span data-ttu-id="9d48c-134">Ujemne saldo kasowe</span><span class="sxs-lookup"><span data-stu-id="9d48c-134">Negative cash</span></span>         | <span data-ttu-id="9d48c-135">Zaznacz to pole wyboru, aby zezwolić na ujemne salda kasowe w dowolnej walucie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-135">Select this check box to allow negative cash balances in any currency.</span></span>                                               |

<span data-ttu-id="9d48c-136">Aby skonfigurować reguły kontroli salda kasowego dla konta kasowego, wybierz konto kasowe, a następnie w okienku akcji na karcie **Konto kasowe** w grupie **Limit salda** kliknij opcję **Limit salda**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-136">To set up cash balance control rules for a cash account, select the cash account, and then, on the Action Pane, on the **Cash account** tab, in the **Balance limit** group, click **Balance limit**.</span></span> <span data-ttu-id="9d48c-137">Wpisz następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-137">Enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-138">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-138">Field</span></span></th>
<th><span data-ttu-id="9d48c-139">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-140">Typ waluty</span><span class="sxs-lookup"><span data-stu-id="9d48c-140">Currency type</span></span></td>
<td><span data-ttu-id="9d48c-141">Wybierz typ waluty:</span><span class="sxs-lookup"><span data-stu-id="9d48c-141">Select the type of currency:</span></span>
<ul>
<li><span data-ttu-id="9d48c-142"><strong>Waluta rozliczeniowa</strong> — użyj kodu waluty podstawowej firmy.</span><span class="sxs-lookup"><span data-stu-id="9d48c-142"><strong>Accounting currency</strong> – Use the basic company currency code.</span></span></li>
<li><span data-ttu-id="9d48c-143"><strong>Wskazana waluta</strong> — użyj kod waluty różniącego się od kodu waluty podstawowej firmy.</span><span class="sxs-lookup"><span data-stu-id="9d48c-143"><strong>Indicated currency</strong> – Use a currency code that differs from the basic company currency code.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-144">Waluta</span><span class="sxs-lookup"><span data-stu-id="9d48c-144">Currency</span></span></td>
<td><span data-ttu-id="9d48c-145">Jeśli w polu <strong>Typ waluty</strong> zaznaczysz opcję <strong>Wskazana waluta</strong>, wybierz kod waluty.</span><span class="sxs-lookup"><span data-stu-id="9d48c-145">If you selected <strong>Indicated currency</strong> in the <strong>Currency type</strong> field, select a currency code.</span></span> <span data-ttu-id="9d48c-146">To pole nie jest dostępne, jeśli w polu <strong>Typ waluty</strong> wybrano opcję <strong>Waluta rozliczeniowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-146">This field is unavailable if you selected <strong>Accounting currency</strong> in the <strong>Currency type</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-147">Typ ograniczenia salda</span><span class="sxs-lookup"><span data-stu-id="9d48c-147">Balance limit type</span></span></td>
<td><span data-ttu-id="9d48c-148">Wybierz jedną z dostępnych wartości:</span><span class="sxs-lookup"><span data-stu-id="9d48c-148">Select one of the available values:</span></span>
<ul>
<li><span data-ttu-id="9d48c-149"><strong>Maksimum</strong> — saldo kasowe nie powinno być wyższe, niż kwota w polu <strong>Limit salda</strong> dla konta kasowego (górna granica).</span><span class="sxs-lookup"><span data-stu-id="9d48c-149"><strong>Maximum</strong> – The cash balance should not be allowed to exceed the <strong>Balance limit</strong> amount for the cash account (upper bound).</span></span></li>
<li><span data-ttu-id="9d48c-150"><strong>Minimum</strong> — saldo kasowe nie powinno być niższe, niż kwota w polu <strong>Limit salda</strong> dla konta kasowego (dolna granica).</span><span class="sxs-lookup"><span data-stu-id="9d48c-150"><strong>Minimum</strong> – The cash balance should not be allowed to go below the <strong>Balance limit</strong> amount for the cash account (bottom bound).</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-151">Sprawdź limit salda</span><span class="sxs-lookup"><span data-stu-id="9d48c-151">Check balance limit</span></span></td>
<td><span data-ttu-id="9d48c-152">Wybierz, co ma się dziać w procesie zatwierdzania dokumentów kasowych, jeśli kwota <strong>Limit salda</strong> dla konta kasowego zostanie przekroczona:</span><span class="sxs-lookup"><span data-stu-id="9d48c-152">Select what occurs during the approval process for cash documents if the <strong>Balance limit</strong> amount for the cash account is exceeded:</span></span>
<ul>
<li><span data-ttu-id="9d48c-153"><strong>Akceptuj</strong> — limit może zostać przekroczony.</span><span class="sxs-lookup"><span data-stu-id="9d48c-153"><strong>Accept</strong> – The limit can be exceeded.</span></span></li>
<li><span data-ttu-id="9d48c-154"><strong>Ostrzeżenie</strong> — limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="9d48c-154"><strong>Warning</strong> – The limit can be exceeded, but the user receives a warning message.</span></span> <span data-ttu-id="9d48c-155">Dokument kasowy jest potwierdzany lub zatwierdzany.</span><span class="sxs-lookup"><span data-stu-id="9d48c-155">The cash document is confirmed or approved.</span></span></li>
<li><span data-ttu-id="9d48c-156"><strong>Błąd</strong> — limit nie może zostać przekroczony.</span><span class="sxs-lookup"><span data-stu-id="9d48c-156"><strong>Error</strong> – The limit can&#39;t be exceeded.</span></span> <span data-ttu-id="9d48c-157">Użytkownik otrzymuje komunikat o błędzie, a dokument kasowy nie jest potwierdzany ani zatwierdzany.</span><span class="sxs-lookup"><span data-stu-id="9d48c-157">The user receives an error message, and the cash document isn&#39;t confirmed or approved.</span></span></li>
</ul>
<span data-ttu-id="9d48c-158">Aby uzyskać więcej informacji na temat procesu zatwierdzania dokumentów kasowych, zobacz sekcję &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot; w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="9d48c-158">For more information about the approval process for cash documents, see the &quot;Cash transaction approval and posting&quot; section, later in this topic.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-159">Limit salda</span><span class="sxs-lookup"><span data-stu-id="9d48c-159">Balance limit</span></span></td>
<td><span data-ttu-id="9d48c-160">Wprowadź dopuszczalny limit salda konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-160">Enter a limit for the cash account balance.</span></span> <span data-ttu-id="9d48c-161">Kwota powinna być w ustawionej przez Ciebie walucie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-161">The amount should be in the currency that you specified.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a><span data-ttu-id="9d48c-162">Konfigurowanie profili księgowania kasy</span><span class="sxs-lookup"><span data-stu-id="9d48c-162">Set up cash posting profiles</span></span>

<span data-ttu-id="9d48c-163">Profile księgowania kasy definiują sposób księgowania w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-163">Cash posting profiles define postings to the general ledger.</span></span> <span data-ttu-id="9d48c-164">Aby skonfigurować profil księgowania kasy, wybierz kolejno opcje **Zarządzanie** **gotówką i bankami** &gt; **Ustawienia** &gt; **Profile księgowania kasy** i wybierz lub utwórz profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="9d48c-164">To set up a cash posting profile, go to **Cash** **and bank management** &gt; **Setup** &gt; **Cash posting profiles**, and select or create a posting profile.</span></span> <span data-ttu-id="9d48c-165">Wpisz następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-165">Enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-166">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-166">Field</span></span></th>
<th><span data-ttu-id="9d48c-167">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-168">Ważny dla</span><span class="sxs-lookup"><span data-stu-id="9d48c-168">Valid for</span></span></td>
<td><span data-ttu-id="9d48c-169">Określ, czy profil księgowania dotyczy określonego konta kasowego czy wszystkich kont kasowych:</span><span class="sxs-lookup"><span data-stu-id="9d48c-169">Select whether the posting profile applies to a specific cash account or all cash accounts:</span></span>
<ul>
<li><span data-ttu-id="9d48c-170"><strong>Tabela</strong> — jeśli dla konta kasowego istnieje wiersz profilu księgowania, ten wiersz jest używany do księgowania transakcji kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-170"><strong>Table</strong> – If there is a posting profile line for the cash account, that line is used for cash transaction posting.</span></span></li>
<li><span data-ttu-id="9d48c-171"><strong>Wszystko</strong> — nie istnieje żaden wiersz profilu księgowania dla konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-171"><strong>All</strong> – There is no posting profile line for the cash account.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-172">Kasa</span><span class="sxs-lookup"><span data-stu-id="9d48c-172">Cash</span></span></td>
<td><span data-ttu-id="9d48c-173">Jeśli w polu <strong>Ważny dla</strong> wybrano opcję <strong>Tabela</strong>, określ konto kasowe.</span><span class="sxs-lookup"><span data-stu-id="9d48c-173">If you selected <strong>Table</strong> in the <strong>Valid for</strong> field, specify the cash account.</span></span> <span data-ttu-id="9d48c-174">To pole pozostaje puste, jeśli w polu <strong>Ważne dla</strong> wybrano opcję <strong>Wszystko</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-174">This field remains blank if you selected <strong>All</strong> in the <strong>Valid for</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-175">Konto księgowe</span><span class="sxs-lookup"><span data-stu-id="9d48c-175">Ledger account</span></span></td>
<td><span data-ttu-id="9d48c-176">Wprowadź numer konta księgowego, które ma być używane jako konto rozrachunkowe dla konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-176">Enter the number of the ledger account to use as the summary account for the cash account.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a><span data-ttu-id="9d48c-177">Konfigurowanie numeracji dla dokumentów kasowych</span><span class="sxs-lookup"><span data-stu-id="9d48c-177">Set up number sequences for cash documents</span></span>

<span data-ttu-id="9d48c-178">Aby skonfigurować numerację dokumentów kasowych, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-178">To set up number sequences for cash documents, go to **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters**.</span></span> <span data-ttu-id="9d48c-179">Na karcie **Sekwencja numerów** określ kody numeracji dla dokumentów **Dokumenty KP**, **Dokumenty KW**, **Załącznik korekty kasowej** i **Różnica kursowa** oraz dla parametru **Numer raportu kasowego**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-179">On the **Number sequence** tab, specify number sequence codes for the **Cash reimbursement slips**, **Cash disbursement slips**, **Cash correction voucher**, and **Exchange adjustment** documents, and for **Cash report number**.</span></span>

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a><span data-ttu-id="9d48c-180">Konfigurowanie domyślnych wartości modułu Zarządzanie gotówką i bankami</span><span class="sxs-lookup"><span data-stu-id="9d48c-180">Set up default values for Cash and bank management parameters</span></span>

<span data-ttu-id="9d48c-181">Aby skonfigurować domyślne wartości modułu Zarządzanie gotówką i bankami dla funkcji gotówki podręcznej, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-181">To set up default values for Cash and bank management parameters for the petty cash functionality, go to **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters**.</span></span> <span data-ttu-id="9d48c-182">Na karcie **Kasa** wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9d48c-182">On the **Cash** tab, enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-183">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-183">Field</span></span></th>
<th><span data-ttu-id="9d48c-184">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-185">Kasa</span><span class="sxs-lookup"><span data-stu-id="9d48c-185">Cash</span></span></td>
<td><span data-ttu-id="9d48c-186">Wybierz domyślne konto kasowe, które będzie używane w arkuszach.</span><span class="sxs-lookup"><span data-stu-id="9d48c-186">Select the default cash account in journals.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-187">Księgowanie kasy</span><span class="sxs-lookup"><span data-stu-id="9d48c-187">Cash posting</span></span></td>
<td><span data-ttu-id="9d48c-188">Wprowadź domyślny profil księgowania kasy, który będzie używany, jeśli nie został określony profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="9d48c-188">Enter the default cash posting profile that is used if no other posting profile is specified.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-189">Sprawdzanie użytego numeru załącznika</span><span class="sxs-lookup"><span data-stu-id="9d48c-189">Check for voucher used</span></span></td>
<td><span data-ttu-id="9d48c-190">Wybierz, co się dzieje w razie znalezienia zduplikowanych numerów podczas sprawdzania numer dokumentu kasowego:</span><span class="sxs-lookup"><span data-stu-id="9d48c-190">Select what occurs if duplicate numbers are found during the check of the cash document number:</span></span>
<ul>
<li><span data-ttu-id="9d48c-191">Odrzuć duplikaty</span><span class="sxs-lookup"><span data-stu-id="9d48c-191">Reject duplicate</span></span></li>
<li><span data-ttu-id="9d48c-192">Odrzuć kopie w roku obrachunkowym</span><span class="sxs-lookup"><span data-stu-id="9d48c-192">Reject copies within fiscal year</span></span></li>
<li><span data-ttu-id="9d48c-193">Dozwolone duplikaty</span><span class="sxs-lookup"><span data-stu-id="9d48c-193">Accept duplicates</span></span></li>
<li><span data-ttu-id="9d48c-194">Ostrzegaj w przypadku duplikatów</span><span class="sxs-lookup"><span data-stu-id="9d48c-194">Warn in case of duplicates</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-195">Sprawdź limit operacji</span><span class="sxs-lookup"><span data-stu-id="9d48c-195">Check operations limit</span></span></td>
<td><span data-ttu-id="9d48c-196">Określ, co się dzieje po przekroczeniu limitu operacji z kontrahentami:</span><span class="sxs-lookup"><span data-stu-id="9d48c-196">Specify what occurs if the limit for operations with counteragents is exceeded:</span></span>
<ul>
<li><span data-ttu-id="9d48c-197"><strong>Akceptuj</strong> — limit może zostać przekroczony.</span><span class="sxs-lookup"><span data-stu-id="9d48c-197"><strong>Accept</strong> – The limit can be exceeded.</span></span></li>
<li><span data-ttu-id="9d48c-198"><strong>Ostrzeżenie</strong> — limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="9d48c-198"><strong>Warning</strong> – The limit can be exceeded, but the user receives a warning message.</span></span> <span data-ttu-id="9d48c-199">Operacja jest księgowana.</span><span class="sxs-lookup"><span data-stu-id="9d48c-199">The operation is posted.</span></span></li>
<li><span data-ttu-id="9d48c-200"><strong>Błąd</strong> — limit nie może zostać przekroczony.</span><span class="sxs-lookup"><span data-stu-id="9d48c-200"><strong>Error</strong> – The limit can&#39;t be exceeded.</span></span> <span data-ttu-id="9d48c-201">Użytkownik otrzymuje komunikat o błędzie, a operacja nie jest księgowana.</span><span class="sxs-lookup"><span data-stu-id="9d48c-201">The user receives an error message, and the operation isn&#39;t posted.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-202">Metoda weryfikacji</span><span class="sxs-lookup"><span data-stu-id="9d48c-202">Validation method</span></span></td>
<td><span data-ttu-id="9d48c-203">Wybierz metodę sprawdzania poprawności służącą do kontrolowania przekroczenia kwot limitów dla operacji:</span><span class="sxs-lookup"><span data-stu-id="9d48c-203">Select the validation method that is used to control exceeded limit amounts for operations:</span></span>
<ul>
<li><span data-ttu-id="9d48c-204"><strong>Operacja</strong> — sprawdzanie poprawności jest wykonywane dla każdej transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-204"><strong>Operation</strong> – Validation is done per transaction</span></span></li>
<li><span data-ttu-id="9d48c-205"><strong>Umowa</strong> — sprawdzanie poprawności jest wykonywane dla każdej transakcji mającej przypisaną umowę z kontrahentem.</span><span class="sxs-lookup"><span data-stu-id="9d48c-205"><strong>Agreement</strong> – Validation is done per transaction that has a specified contract with a counteragent.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-206">Limit operacji</span><span class="sxs-lookup"><span data-stu-id="9d48c-206">Operations limit</span></span></td>
<td><span data-ttu-id="9d48c-207">Wprowadź maksymalną dozwoloną kwotę transakcji kasowych z kontrahentami.</span><span class="sxs-lookup"><span data-stu-id="9d48c-207">Enter the maximum amount that is allowed for operations with counteragents in cash.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-208">Księgowanie z wcześniejszą datą</span><span class="sxs-lookup"><span data-stu-id="9d48c-208">Posting on earlier date</span></span></td>
<td><span data-ttu-id="9d48c-209">Zaznacz to pole wyboru, aby umożliwić księgowanie transakcji kasowych z datą wcześniejszą niż data ostatniej transakcji kasowej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-209">Select this check box to enable cash transactions to be posted before the last date of the cash transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-210">Wymiary</span><span class="sxs-lookup"><span data-stu-id="9d48c-210">Dimensions</span></span></td>
<td><span data-ttu-id="9d48c-211">Wprowadź wymiary w polach <strong>Kod działu</strong>, <strong>Kod analityczny</strong> i <strong>Kod celu</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-211">Enter dimensions in the <strong>Department code</strong>, <strong>Analytical code</strong>, and <strong>Purpose code</strong> fields.</span></span> <span data-ttu-id="9d48c-212">Drukowana postać dokumentów kasowych będzie odzwierciedlała te informacje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-212">The printing form for cash documents will reflect this information.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-213">Użyj stanu potwierdzenia</span><span class="sxs-lookup"><span data-stu-id="9d48c-213">Use confirm status</span></span></td>
<td><span data-ttu-id="9d48c-214">Zaznacz to pole wyboru , aby korzystać z dodatkowego stanu <strong>Potwierdzone</strong> w procesie zatwierdzania dokumentów kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-214">Select this check box to use an additional status, <strong>Confirmed</strong>, during the approval process for cash documents.</span></span> <span data-ttu-id="9d48c-215">(Aby uzyskać więcej informacji, zobacz sekcję &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot;).</span><span class="sxs-lookup"><span data-stu-id="9d48c-215">(For more information, see the &quot;Cash transaction approval and posting&quot; section.)</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a><span data-ttu-id="9d48c-216">Konfigurowanie nazw arkuszy kasowych w księdze głównej</span><span class="sxs-lookup"><span data-stu-id="9d48c-216">Set up cash journal names in General ledger</span></span>

<span data-ttu-id="9d48c-217">Aby utworzyć arkusz do księgowania transakcji kasowych, **Księga główna** &gt; **Konfiguracja arkusza** &gt; **Nazwy arkuszy** i utwórz nowy rekord.</span><span class="sxs-lookup"><span data-stu-id="9d48c-217">To create a journal for cash transaction posting, go to **General ledger** &gt; **Journal setup** &gt; **Journal names**, and create a new record.</span></span> <span data-ttu-id="9d48c-218">W polu **Typ arkusza** wybierz opcję **Kasa**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-218">In the **Journal type** field, specify **Cash**.</span></span> <span data-ttu-id="9d48c-219">Zdefiniuj inne potrzebne domyślne parametry.</span><span class="sxs-lookup"><span data-stu-id="9d48c-219">Define other default journal parameters as you require.</span></span>

## <a name="daily-cash-operations-via-a-slip-journal"></a><span data-ttu-id="9d48c-220">Dokumentowanie codziennych operacje gotówkowych przy użyciu arkusza kasowego</span><span class="sxs-lookup"><span data-stu-id="9d48c-220">Daily cash operations via a Slip journal</span></span>
<span data-ttu-id="9d48c-221">Aby utworzyć dokument kasowy za pośrednictwem arkusza kasowego, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Transakcje kasowe** &gt; **Arkusz kasowy** i utwórz nowy arkusz.</span><span class="sxs-lookup"><span data-stu-id="9d48c-221">To create a cash document via a Slip journal, go to **Cash and bank management** &gt; **Cash transactions** &gt; **Slip journal**, and create a new journal.</span></span> <span data-ttu-id="9d48c-222">W okienku akcji kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-222">On the Action Pane, click **Lines**.</span></span> <span data-ttu-id="9d48c-223">Dodaj nowy wiersz i wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9d48c-223">Add a new line, and enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-224">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-224">Field</span></span></th>
<th><span data-ttu-id="9d48c-225">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-226">Data</span><span class="sxs-lookup"><span data-stu-id="9d48c-226">Date</span></span></td>
<td><span data-ttu-id="9d48c-227">Wprowadź datę transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-227">Enter the date of the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-228">Konto</span><span class="sxs-lookup"><span data-stu-id="9d48c-228">Account</span></span></td>
<td><span data-ttu-id="9d48c-229">Wybierz konto kasowe.</span><span class="sxs-lookup"><span data-stu-id="9d48c-229">Select the cash account.</span></span> <span data-ttu-id="9d48c-230">Domyślnie konto kasowe jest określone w oknie Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="9d48c-230">By default, a cash account is specified in the Cash and bank management parameters.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-231">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-231">Description</span></span></td>
<td><span data-ttu-id="9d48c-232">Wprowadź tekst wyjaśniający o transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-232">Enter explanatory text for the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-233">Debet Kredyt</span><span class="sxs-lookup"><span data-stu-id="9d48c-233">Debit Credit</span></span></td>
<td><span data-ttu-id="9d48c-234">Wprowadź kwotę z dokumentu kasowego w jednym z następujących pól:</span><span class="sxs-lookup"><span data-stu-id="9d48c-234">Enter cash document amount in one of these fields:</span></span>
<ul>
<li><span data-ttu-id="9d48c-235"><strong>Debet</strong> — to pole służy do rejestracji przychodów gotówkowych i dokumentu KP.</span><span class="sxs-lookup"><span data-stu-id="9d48c-235"><strong>Debit</strong> – Use this field to register cash receipts and a Cash reimbursement slip.</span></span></li>
<li><span data-ttu-id="9d48c-236"><strong>Kredyt</strong> — to pole służy do rejestracji rozchodów gotówkowych i dokumentu KW.</span><span class="sxs-lookup"><span data-stu-id="9d48c-236"><strong>Credit</strong> – Use this field to register cash expenditures and a Cash disbursement slip.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-237">Typ konta przeciwstawnego Konto przeciwstawne</span><span class="sxs-lookup"><span data-stu-id="9d48c-237">Offset account type Offset account</span></span></td>
<td><span data-ttu-id="9d48c-238">Wybierz typ i numer konta przeciwstawnego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-238">Select an offset account type and offset account number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-239">Waluta</span><span class="sxs-lookup"><span data-stu-id="9d48c-239">Currency</span></span></td>
<td><span data-ttu-id="9d48c-240">Wybierz kod waluty transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-240">Select the code for the transaction currency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-241">Załącznik</span><span class="sxs-lookup"><span data-stu-id="9d48c-241">Voucher</span></span></td>
<td><span data-ttu-id="9d48c-242">To pole jest wypełniane automatycznie na podstawie ustawień arkusza.</span><span class="sxs-lookup"><span data-stu-id="9d48c-242">This field is filled in automatically, based on the journal setup.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-243">Numer zamówienia</span><span class="sxs-lookup"><span data-stu-id="9d48c-243">Order number</span></span></td>
<td><span data-ttu-id="9d48c-244">Jeśli dla konta kasowego nie skonfigurowano innej numeracji, to pole jest wypełniane automatycznie na podstawie numeracji określonej w parametrach.</span><span class="sxs-lookup"><span data-stu-id="9d48c-244">If no other number sequence is set up for the cash account, this field is filled in automatically, based on the number sequence that is specified in the parameters.</span></span> <span data-ttu-id="9d48c-245">W razie potrzeby można ręcznie wprowadzić numer zamówienia w tym polu.</span><span class="sxs-lookup"><span data-stu-id="9d48c-245">You can manually enter an order number in this field as you require.</span></span> <span data-ttu-id="9d48c-246">Aby zapobiec niespójnościom w numeracji dokumentów kasowych, stosuje się następującą kontrolę: numer dokumentu kasowego z wcześniejszą datą operacji nie może być wyższy niż numer dokumentu kasowego z późniejszą datą operacji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-246">To prevent inconsistence in cash document numbering, the following control is applied: the number of a cash document that has an earlier date of operation can&#39;t be higher than number of a cash document that has a later date of operation.</span></span> <span data-ttu-id="9d48c-247">Jeśli nie potrzebujesz tej kontroli, zaznacz pole wyboru <strong>Księgowanie z wcześniejszą datą</strong> w oknie Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="9d48c-247">If you don&#39;t require this control, select the <strong>Posting on earlier date</strong> check box in the Cash and bank management parameters.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-248">Stan zatwierdzenia</span><span class="sxs-lookup"><span data-stu-id="9d48c-248">Approval status</span></span></td>
<td><span data-ttu-id="9d48c-249">Pierwszym stanem transakcji jest <strong>Brak</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-249">The first transaction status is <strong>None</strong>.</span></span> <span data-ttu-id="9d48c-250">Szczegółowe informacje o tym, jak ustawić stan transakcji, zawiera sekcja &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot;.</span><span class="sxs-lookup"><span data-stu-id="9d48c-250">For information about how to set the transaction status, See the &quot;Cash transaction approval and posting&quot; section.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-251">Typ dokumentu</span><span class="sxs-lookup"><span data-stu-id="9d48c-251">Document type</span></span></td>
<td><span data-ttu-id="9d48c-252">To pole na karcie <strong>Zamówienie gotówkowe</strong> jest wypełniane automatycznie na podstawie kwoty wprowadzonej w dokumencie kasowym:</span><span class="sxs-lookup"><span data-stu-id="9d48c-252">This field on the <strong>Cash order</strong> tab is filled in automatically, based on the amount that you entered for the cash document:</span></span>
<ul>
<li><span data-ttu-id="9d48c-253"><strong>Dokument KP</strong> — ta wartość jest używana, jeśli wprowadzono wartość w polu <strong>Debet</strong> dla konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-253"><strong>Cash reimbursement slip</strong> – This value is used if you entered an amount in the <strong>Debit</strong> field for the cash account.</span></span></li>
<li><span data-ttu-id="9d48c-254"><strong>Dokument KW</strong> — ta wartość jest używana, jeśli wprowadzono wartość w polu <strong>Kredyt</strong> dla konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-254"><strong>Cash disbursement slip</strong> – This value is used if you entered an amount in the <strong>Credit</strong> field for the cash account</span></span></li>
<li><span data-ttu-id="9d48c-255"><strong>Korekta</strong> — wprowadzono kwotę ujemną w polu <strong>Debet</strong> lub <strong>Kredyt</strong> dla konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-255"><strong>Correction</strong> – You entered a negative amount in either the <strong>Debit</strong> field or the <strong>Credit</strong> field for the cash account.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-256">Grupa podatków</span><span class="sxs-lookup"><span data-stu-id="9d48c-256">Sales tax group</span></span></td>
<td><span data-ttu-id="9d48c-257">Określ grupę podatków, która ma być używana do obliczania podatków od operacji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-257">Specify a sales tax group to calculate taxes on the operation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-258">Grupa podatków dla pozycji</span><span class="sxs-lookup"><span data-stu-id="9d48c-258">Item sales tax group</span></span></td>
<td><span data-ttu-id="9d48c-259">Określ grupę podatków od towarów, która ma być używana do obliczania podatków od operacji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-259">Specify an item sales tax group to calculate taxes on the operation.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-260">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="9d48c-260">Reason</span></span></td>
<td><span data-ttu-id="9d48c-261">Na karcie <strong>Zamówienie gotówkowe</strong> wprowadź tekst opisujący przedmiot transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-261">On the <strong>Cash order</strong> tab, enter text that describes the transaction subject.</span></span> <span data-ttu-id="9d48c-262">Ten tekst będzie drukowany w formularzu sprawozdawczym dokumentu kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-262">This text will be printed on the cash slip reporting form.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-263">Data dokumentu</span><span class="sxs-lookup"><span data-stu-id="9d48c-263">Document Date</span></span></td>
<td><span data-ttu-id="9d48c-264">Wprowadź opis, numer i datę dokumentu podstawowego będącego powodem transakcji (na przykład raport o zaliczkach, faktura lub zamówienie).</span><span class="sxs-lookup"><span data-stu-id="9d48c-264">Enter the description, number, and date of the primary document that is the reason for the transaction (for example, advance reports, invoice, or order).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-265">Typ przedstawiciela</span><span class="sxs-lookup"><span data-stu-id="9d48c-265">Representative type</span></span></td>
<td><span data-ttu-id="9d48c-266">To pole może przyjmować następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="9d48c-266">This field can have the following values:</span></span>
<ul>
<li><span data-ttu-id="9d48c-267"><strong>Pracownik</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę pracowników, jeśli pole <strong>Konto przeciwstawne</strong> zawiera wartość <strong>Księga</strong> lub <strong>Bank</strong>, albo listę osób kontaktowych u kontrahenta, jeśli pole <strong>Konto przeciwstawne</strong> zawiera wartość <strong>Odbiorca</strong> lub <strong>Dostawca</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-267"><strong>Worker</strong> – The <strong>Representative</strong> lookup contains a list of employees if the <strong>Offset account</strong> field is set to <strong>Ledger</strong> or <strong>Bank</strong>, or a list of the counteragent&#39;s contact persons if the <strong>Offset account</strong> field is set to <strong>Customer</strong> or <strong>Vendor</strong>.</span></span> <span data-ttu-id="9d48c-268">Aby skonfigurować przedstawicieli, wybierz kolejno opcje <strong>Podstawowe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Kontakty</strong> &gt; <strong>Osoba kontaktowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-268">To set up representatives, go to <strong>Basic</strong> &gt; <strong>Setup</strong> &gt; <strong>Contacts</strong> &gt; <strong>Contact person</strong>.</span></span></li>
<li><span data-ttu-id="9d48c-269"><strong>Inne</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę innych klientów.</span><span class="sxs-lookup"><span data-stu-id="9d48c-269"><strong>Other</strong> – The <strong>Representative</strong> lookup contains a list of other clients.</span></span> <span data-ttu-id="9d48c-270">Aby skonfigurować odbiorców, którzy nie figurują w tabeli <strong>Odbiorcy</strong> ani <strong>Dostawcy</strong>, wybierz kolejno opcje <strong>Księga główna</strong> &gt; <strong>Odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-270">To set up receivers who don&#39;t appear in the <strong>Customers</strong> or <strong>Vendors</strong> table, go to <strong>General ledger</strong> &gt; <strong>Receivers</strong>.</span></span> <span data-ttu-id="9d48c-271">Ten typ jest dostępny tylko w Hiszpanii.</span><span class="sxs-lookup"><span data-stu-id="9d48c-271">This type is available only for Latvia.</span></span> <span data-ttu-id="9d48c-272">(Musi być włączony klucz konfiguracji <strong>CSELatvia</strong>).</span><span class="sxs-lookup"><span data-stu-id="9d48c-272">(The <strong>CSELatvia</strong> configuration key should be enabled.)</span></span></li>
<li><span data-ttu-id="9d48c-273"><strong>Dostawca</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę dostawców.</span><span class="sxs-lookup"><span data-stu-id="9d48c-273"><strong>Vendor</strong> – The <strong>Representative</strong> lookup contains a list of vendors.</span></span> <span data-ttu-id="9d48c-274">Aby skonfigurować dostawców, wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-274">To set up vendors, go to <strong>Accounts payable</strong> &gt; <strong>Vendors</strong>.</span></span></li>
<li><span data-ttu-id="9d48c-275"><strong>Odbiorca</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9d48c-275"><strong>Customer</strong> – The <strong>Representative</strong> lookup contains a list of customers.</span></span> <span data-ttu-id="9d48c-276">Aby skonfigurować odbiorców, wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-276">To set up customers, go to <strong>Accounts receivable</strong> &gt; <strong>Customers</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-277">Przedstawiciel</span><span class="sxs-lookup"><span data-stu-id="9d48c-277">Representative</span></span></td>
<td><span data-ttu-id="9d48c-278">Wybierz przedstawiciela o typie określonym w polu <strong>Typ przedstawiciela</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-278">Select a representative of the type that you specified in the <strong>Representative type</strong> field.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-279">Nazwisko pracownika</span><span class="sxs-lookup"><span data-stu-id="9d48c-279">Name of person</span></span></td>
<td><span data-ttu-id="9d48c-280">To pole jest wypełniane automatycznie na podstawie zawartości pól <strong>Konto przeciwstawne</strong> i <strong>Przedstawiciel</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-280">This field is filled in automatically, based on the <strong>Offset account</strong> and <strong>Representative</strong> fields.</span></span> <span data-ttu-id="9d48c-281">Drukowana postać dokumentów kasowych będzie odzwierciedlała te informacje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-281">The printing form for cash slips will reflect this information.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-282">Dowód tożsamości</span><span class="sxs-lookup"><span data-stu-id="9d48c-282">Identity card</span></span></td>
<td><span data-ttu-id="9d48c-283">To pole jest wypełniane automatycznie na podstawie danych dowodu tożsamości osoby kontaktowej (przedstawiciela).</span><span class="sxs-lookup"><span data-stu-id="9d48c-283">This field is filled in automatically, based on the identity card data for the contact person (representative).</span></span> <span data-ttu-id="9d48c-284">Jeśli pole <strong>Typ konta przeciwstawnego</strong> jest ustawione na <strong>Posiadacz zaliczki</strong>, a pole <strong>Konto przeciwstawne</strong> na numer pracownika, można dokonywać przychodów i rozchodów gotówkowych do i od tego pracownika.</span><span class="sxs-lookup"><span data-stu-id="9d48c-284">If the <strong>Offset account type</strong> field is set to <strong>Advance holder</strong>, and the <strong>Offset account</strong> field is set to an employee number, cash receipts or expenditures can be done from or to the employee.</span></span> <span data-ttu-id="9d48c-285">W takim przypadku pole <strong>Dowód tożsamości</strong> jest wypełniane automatycznie przy użyciu danych dowodu tożsamości z tabeli <strong>Pracownik</strong> (<strong>Księgowanie personelu</strong> &gt; <strong>Tabela pracowników</strong>).</span><span class="sxs-lookup"><span data-stu-id="9d48c-285">In this case the <strong>Identity card</strong> field is filled in automatically by using data for the identity card from the <strong>Employee</strong> table (<strong>Staff accounting</strong> &gt; <strong>Employee table</strong>).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-286">Cel</span><span class="sxs-lookup"><span data-stu-id="9d48c-286">Purpose</span></span></td>
<td><span data-ttu-id="9d48c-287">W tabeli <strong>Cel</strong> zdefiniuj jeden lub więcej kodów przeznaczenia kwoty transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-287">In the <strong>Purpose</strong> table, define one or more destination codes for the transaction amount.</span></span> <span data-ttu-id="9d48c-288">Wybierz kod przeznaczenia w polu <strong>Cel</strong> i wpisz wyjaśnienie w polu <strong>Tekst transakcji</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-288">Select a destination code in the <strong>Purpose</strong> field, and enter an explanation in the <strong>Transaction text</strong> field.</span></span> <span data-ttu-id="9d48c-289">W polu <strong>Kwota</strong> wpisz kwotę w walucie transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-289">In the <strong>Amount</strong> field, enter an amount in the transaction currency.</span></span> <span data-ttu-id="9d48c-290">Pole <strong>Procent</strong> pokazuje (w procentach) stosunek kwoty docelowej do łącznej kwoty transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-290">The <strong>Percent</strong> field shows, as a percentage, the ratio of the destination amount to the total transaction amount.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-291">Upomnienie</span><span class="sxs-lookup"><span data-stu-id="9d48c-291">Remainder</span></span></td>
<td><span data-ttu-id="9d48c-292">Obliczana pozostała kwota.</span><span class="sxs-lookup"><span data-stu-id="9d48c-292">The remaining amount that is calculated.</span></span> <span data-ttu-id="9d48c-293">Należy zauważyć, że cała kwota transakcja musi być przypisana do kodów przeznaczenia.</span><span class="sxs-lookup"><span data-stu-id="9d48c-293">Note that the whole transaction amount must be assigned to destination codes.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-294">Dane urzędowe</span><span class="sxs-lookup"><span data-stu-id="9d48c-294">Officials</span></span></td>
<td><span data-ttu-id="9d48c-295">Na karcie <strong>Dane urzędowe</strong> podaj imiona, nazwiska i tytuły osób odpowiedzialnych: dyrektora, głównego księgowego i kasjera.</span><span class="sxs-lookup"><span data-stu-id="9d48c-295">On the <strong>Officials</strong> tab, specify the names and titles for responsible persons: Director, Chief accountant, and Cashier.</span></span> <span data-ttu-id="9d48c-296">Wartości pola <strong>Pozycja</strong> są określane przez konfigurację danych urzędowych na kartach <strong>Ogólne</strong> i <strong>Księga</strong> na stronie <strong>Dane urzędowe</strong> (<strong>Podstawowe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Kontakty</strong> &gt; <strong>Dane urzędowe</strong>).</span><span class="sxs-lookup"><span data-stu-id="9d48c-296">The <strong>Position</strong> values are determined by the setup of officials on the <strong>General</strong> and <strong>Ledger</strong> tabs of the <strong>Officials</strong> page (<strong>Basic</strong> &gt; <strong>Setup</strong> &gt; <strong>Contacts</strong> &gt; <strong>Officials</strong>).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-297">Zaliczka</span><span class="sxs-lookup"><span data-stu-id="9d48c-297">Prepayment</span></span></td>
<td><span data-ttu-id="9d48c-298">Należy zaznaczyć to pole wyboru, jeśli transakcja jest przedpłatą.</span><span class="sxs-lookup"><span data-stu-id="9d48c-298">Select this check box if the transaction is a prepayment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-299">Profil księgowania</span><span class="sxs-lookup"><span data-stu-id="9d48c-299">Posting profile</span></span></td>
<td><span data-ttu-id="9d48c-300">Wprowadź profil księgowania konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-300">Enter the posting profile for the cash account.</span></span> <span data-ttu-id="9d48c-301">Domyślnie jest używany profil księgowania określony w oknie Parametry modułu Zarządzanie gotówką i bankami.</span><span class="sxs-lookup"><span data-stu-id="9d48c-301">By default, the posting profile that is specified in the Cash and bank management parameters is used.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-302">Profil księgowania przeciwstawnego</span><span class="sxs-lookup"><span data-stu-id="9d48c-302">Offset posting profile</span></span></td>
<td><span data-ttu-id="9d48c-303">Wprowadź profil księgowania wybranego konta przeciwstawnego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-303">Enter the posting profile for the selected offset account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-304">Suma</span><span class="sxs-lookup"><span data-stu-id="9d48c-304">Total amount</span></span></td>
<td><span data-ttu-id="9d48c-305">W grupie pól <strong>Suma</strong> u dołu strony pole <strong>Zwroty</strong> zawiera sumę obliczaną dla wszystkich dokumentów KP wprowadzonych w bieżącym arkuszu, a pole <strong>Rozch</strong> zawiera sumę ze wszystkich dokumentów KW.</span><span class="sxs-lookup"><span data-stu-id="9d48c-305">In the <strong>Total amount</strong> field group at the bottom of the page, the <strong>Reimb</strong> field shows the total that is calculated for all Cash reimbursement slips that are entered in the current journal, and the <strong>Disb</strong> field shows the total for all Cash disbursement slips.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9d48c-306">Aby sprawdzić zapisy w arkuszu, w okienku akcji kliknij przycisk **Weryfikuj**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-306">To check journal entries, on the Action Pane, click **Validate**.</span></span>

## <a name="daily-cash-operations-via-a-general-journal"></a><span data-ttu-id="9d48c-307">Dokumentowanie codziennych operacje gotówkowych przy użyciu arkusza finansowego</span><span class="sxs-lookup"><span data-stu-id="9d48c-307">Daily cash operations via a General journal</span></span>
<span data-ttu-id="9d48c-308">Aby utworzyć transakcję kasową za pomocą arkusza finansowego, wybierz kolejno opcje **Księga główna** &gt; **Wpisy w arkuszu** &gt; **Arkusze finansowe** i utwórz nowy arkusz.</span><span class="sxs-lookup"><span data-stu-id="9d48c-308">To create a cash transaction via a General journal, go to **General ledger** &gt; **Journal entries** &gt; **General journals**, and create a new journal.</span></span> <span data-ttu-id="9d48c-309">W okienku akcji kliknij pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-309">On the Action Pane, click **Lines**.</span></span> <span data-ttu-id="9d48c-310">Dodaj nowy wiersz i wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9d48c-310">Add a new line, and enter the following information.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-311">Pole</span><span class="sxs-lookup"><span data-stu-id="9d48c-311">Field</span></span></th>
<th><span data-ttu-id="9d48c-312">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-312">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-313">Data</span><span class="sxs-lookup"><span data-stu-id="9d48c-313">Date</span></span></td>
<td><span data-ttu-id="9d48c-314">Wprowadź datę transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-314">Enter the date of the transaction.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-315">Typ konta</span><span class="sxs-lookup"><span data-stu-id="9d48c-315">Account type</span></span></td>
<td><span data-ttu-id="9d48c-316">Wybierz opcję <strong>Gotówka podręczna</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-316">Select <strong>Petty cash</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-317">Konto</span><span class="sxs-lookup"><span data-stu-id="9d48c-317">Account</span></span></td>
<td><span data-ttu-id="9d48c-318">Wybierz numer konta kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-318">Select the cash account number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-319">Tekst transakcji</span><span class="sxs-lookup"><span data-stu-id="9d48c-319">Transaction text</span></span></td>
<td><span data-ttu-id="9d48c-320">Wprowadź tekst wyjaśniający o transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-320">Enter explanatory text for the transaction.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-321">Debet Kredyt</span><span class="sxs-lookup"><span data-stu-id="9d48c-321">Debit Credit</span></span></td>
<td><span data-ttu-id="9d48c-322">Wprowadź kwotę z dokumentu kasowego w jednym z następujących pól:</span><span class="sxs-lookup"><span data-stu-id="9d48c-322">Enter cash document amount in one of these fields:</span></span>
<ul>
<li><span data-ttu-id="9d48c-323"><strong>Debet</strong> — to pole służy do rejestracji przychodów gotówkowych i dokumentu KP.</span><span class="sxs-lookup"><span data-stu-id="9d48c-323"><strong>Debit</strong> – Use this field to register cash receipts and a Cash reimbursement slip.</span></span></li>
<li><span data-ttu-id="9d48c-324"><strong>Kredyt</strong> — to pole służy do rejestracji rozchodów gotówkowych i dokumentu KW.</span><span class="sxs-lookup"><span data-stu-id="9d48c-324"><strong>Credit</strong> – Use this field to register cash expenditures and a Cash disbursement slip.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-325">Typ konta przeciwstawnego Konto przeciwstawne</span><span class="sxs-lookup"><span data-stu-id="9d48c-325">Offset account type Offset account</span></span></td>
<td><span data-ttu-id="9d48c-326">Wybierz typ i numer konta przeciwstawnego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-326">Select an offset account type and offset account number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-327">Waluta</span><span class="sxs-lookup"><span data-stu-id="9d48c-327">Currency</span></span></td>
<td><span data-ttu-id="9d48c-328">Wybierz kod waluty transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-328">Select the code for the transaction currency.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9d48c-329">Na karcie **Faktura** można określić profile księgowania dla wybranego konta i konta przeciwstawnego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-329">On the **Invoice** tab, you can specify posting profiles for the selected account and offset account.</span></span> <span data-ttu-id="9d48c-330">Jeżeli zarejestrowana transakcja to przedpłata, zaznacz pole wyboru **Przedpłata** na karcie **Płatność**. W grupie pola **Przedstawiciel** uzupełnij pola tak jak w wierszach arkusza kasowego w celu wydrukowania w raporcie **Kasa**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-330">If the registered transaction is a prepayment, select the **Prepayment** check box on the **Payment** tab. In the **Representative** field group, fill in the fields as you did for the Slip journal lines to print on the **Cash** report.</span></span> <span data-ttu-id="9d48c-331">Aby sprawdzić zapisy w arkuszu, w okienku akcji kliknij przycisk **Weryfikuj**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-331">To check journal entries, on the Action Pane, click **Validate**.</span></span>

## <a name="cash-transaction-approval-and-posting"></a><span data-ttu-id="9d48c-332">Zatwierdzanie i księgowanie transakcji kasowych</span><span class="sxs-lookup"><span data-stu-id="9d48c-332">Cash transaction approval and posting</span></span>
<span data-ttu-id="9d48c-333">Do transakcji kasowych mogą być stosowane następujące stany: **Brak**, **Potwierdzone**, **Zatwierdzone** i **Odrzucone**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-333">For cash transactions, the following statuses can be applied: **None**, **Confirmed**, **Approved**, and **Rejected**.</span></span> <span data-ttu-id="9d48c-334">Parametr **Użyj stanu potwierdzenia** na skróconej karcie **Zatwierdzenie** dostępnej na karcie **Kasa** w oknie **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami** pozwala włączyć dwa dodatkowe stany: **Potwierdzone** i **Odrzucone**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-334">A **Use confirm status** parameter on the **Approval** FastTab of the **Cash** tab at **Cash and bank management** &gt; **Setup** &gt; **Cash and bank management parameters** lets you activate two additional statuses: **Confirmed** and **Rejected**.</span></span> <span data-ttu-id="9d48c-335">Potwierdzenie należy zastosować, gdy są wydawane dokumenty kasowe, a przychody i rozchody gotówkowe są realizowanie wspólne przez dwóch pracowników: księgowego i kasjera.</span><span class="sxs-lookup"><span data-stu-id="9d48c-335">Confirmation is appropriate when cash documents are issued, and cash receipts or expenditures are shared between two employees: accountant and cashier.</span></span> <span data-ttu-id="9d48c-336">Funkcja **Resetuj stan** zmienia bieżący stan transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-336">The **Reset status** function changes the current transaction status.</span></span> <span data-ttu-id="9d48c-337">Stan **Zatwierdzone** staje się stanem **Potwierdzone**, a stan **Potwierdzone** zmienia się na **Brak**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-337">**Approved** becomes **Confirmed**, and **Confirmed** becomes **None**.</span></span> <span data-ttu-id="9d48c-338">Zapisy w arkuszu kasowym można edytować tylko wtedy, gdy stanem jest **Brak**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-338">Cash journal entries can be edited only when the status is **None**.</span></span> <span data-ttu-id="9d48c-339">Transakcje kasowe można odrzucać tylko wtedy, gdy stanem transakcji jest **Potwierdzone**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-339">Cash transactions can be rejected only if the transaction status is **Confirmed**.</span></span> <span data-ttu-id="9d48c-340">Odrzucone dokumenty kasowe znajdują się w raporcie **Arkusz rejestracji dokumentów kasowych**, ale nie są uwzględniane w raporcie **Księga kasowa**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-340">Rejected cash documents are included on the **Journal of registration of cash documents** report, but they aren't reflected on the **Cash book** report.</span></span> <span data-ttu-id="9d48c-341">Aby potwierdzić transakcję, wybierz odpowiedni wiersz arkusza kasowego, a następnie kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-341">To confirm a transaction, select the corresponding Slip journal line, and then click **Documents approval** &gt; **Confirm**.</span></span> <span data-ttu-id="9d48c-342">Zostanie wygenerowany numer zamówienia na podstawie ustawionej numeracji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-342">An order number is generated, based on the specified number sequence.</span></span> <span data-ttu-id="9d48c-343">Stan transakcji zmieni się na **Potwierdzone** i nie będzie można już edytować wiersza arkusza.</span><span class="sxs-lookup"><span data-stu-id="9d48c-343">The transaction status is changed to **Confirmed**, and you can no longer edit the journal line.</span></span> <span data-ttu-id="9d48c-344">Salda konta kasowego pozostaje bez zmian.</span><span class="sxs-lookup"><span data-stu-id="9d48c-344">The cash account balance remains unchanged.</span></span> <span data-ttu-id="9d48c-345">Aby odrzucić dokument kasowy, kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Odrzuć**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-345">To reject a cash document, click **Documents approval** &gt; **Reject**.</span></span> <span data-ttu-id="9d48c-346">Ta opcja jest dostępna tylko dla dokumentów o stanie **Potwierdzone**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-346">This option is available only for documents that have **Confirmed** status.</span></span> <span data-ttu-id="9d48c-347">Aby zatwierdzić transakcję, wybierz odpowiedni wiersz arkusza kasowego, a następnie kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Zatwierdź**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-347">To approve a transaction, select the corresponding Slip journal line, and then click **Documents approval** &gt; **Approve**.</span></span> <span data-ttu-id="9d48c-348">Stan **Zatwierdzone** wskazuje, że środki pieniężne zostały otrzymane lub wydatkowane.</span><span class="sxs-lookup"><span data-stu-id="9d48c-348">The **Approved** status indicates that cash funds are received or expended.</span></span> <span data-ttu-id="9d48c-349">Saldo kasowe się zmienia.</span><span class="sxs-lookup"><span data-stu-id="9d48c-349">The cash balance is changed.</span></span> <span data-ttu-id="9d48c-350">Transakcję kasową można zaksięgować.</span><span class="sxs-lookup"><span data-stu-id="9d48c-350">The cash transaction can be posted.</span></span> <span data-ttu-id="9d48c-351">Aby anulować stan **Zatwierdzone** i zresetować stan do wartości **Brak**, kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Resetuj stan**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-351">To cancel an **Approved** status and reset the status to **None**, click **Documents approval** &gt; **Reset status**.</span></span> <span data-ttu-id="9d48c-352">Można zaksięgować tylko zatwierdzone transakcje kasowe.</span><span class="sxs-lookup"><span data-stu-id="9d48c-352">Only approved cash transactions can be posted.</span></span> <span data-ttu-id="9d48c-353">Aby zaksięgować arkusz, kliknij kolejno opcje **Księguj** &gt; **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-353">To post a journal, click **Post** &gt; **Post**.</span></span>

## <a name="print-a-cash-order"></a><span data-ttu-id="9d48c-354">Drukowanie zamówienia gotówkowego</span><span class="sxs-lookup"><span data-stu-id="9d48c-354">Print a cash order</span></span>
<span data-ttu-id="9d48c-355">Aby wydrukować zamówienie gotówkowe, zaznacz wiersz arkusza kasowego, a następnie w okienku akcji kliknij kolejno opcje **Drukuj** &gt; **Raport zamówień gotówkowych**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-355">To print a cash order, select a Slip journal line, and then, on the Action Pane, click **Print** &gt; **Cash order report**.</span></span> <span data-ttu-id="9d48c-356">System wygeneruje drukowalną postać dokumentu KP lub KW, w zależności od tego, czy dla wybranego wiersza wprowadzono kwotę w polu **Debet**, czy **Kredyt**:</span><span class="sxs-lookup"><span data-stu-id="9d48c-356">The system generates a printing form for either a Cash reimbursement slip or a Cash disbursement slip, depending on whether an amount is entered in the **Debit** field the or **Credit** field for the selected line:</span></span>

-   <span data-ttu-id="9d48c-357">Jeśli istnieje kwota w pola **Debet**: dokument KP</span><span class="sxs-lookup"><span data-stu-id="9d48c-357">If there is an amount in the **Debit** field: Cash reimbursement slip</span></span>
-   <span data-ttu-id="9d48c-358">Jeśli istnieje kwota w pola **Kredyt**: dokument KW</span><span class="sxs-lookup"><span data-stu-id="9d48c-358">If there is an amount in the **Credit** field: Cash disbursement slip</span></span>

<span data-ttu-id="9d48c-359">Wiersze arkusza kasowego, które mają stan **Potwierdzone**, **Zatwierdzone** lub **Odrzucone**, mogą być drukowane.</span><span class="sxs-lookup"><span data-stu-id="9d48c-359">Slip journal lines that have **Confirmed**, **Approved**, or **Rejected** status can be printed.</span></span> <span data-ttu-id="9d48c-360">Dokumenty zamówień gotówkowych można również drukować z okna **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Zamówienie gotówkowe**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-360">You can also print cash order documents at **Cash and bank management** &gt; **Inquires and reports** &gt; **Cash order**.</span></span>

## <a name="periodic-tasks"></a><span data-ttu-id="9d48c-361">Zadania okresowe</span><span class="sxs-lookup"><span data-stu-id="9d48c-361">Periodic tasks</span></span>
<span data-ttu-id="9d48c-362">W oknie **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** można wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="9d48c-362">The following tasks can be performed at **Cash and bank management** &gt; **Periodic tasks**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d48c-363">Zadanie okresowe</span><span class="sxs-lookup"><span data-stu-id="9d48c-363">Periodic task</span></span></th>
<th><span data-ttu-id="9d48c-364">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-364">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9d48c-365">Sprawdź limit salda</span><span class="sxs-lookup"><span data-stu-id="9d48c-365">Check balance limit</span></span></td>
<td><span data-ttu-id="9d48c-366">Sprawdzanie salda wybranego konta kasowego na określony dzień oraz pokazywanie wyniku w komunikacie informacyjnym.</span><span class="sxs-lookup"><span data-stu-id="9d48c-366">Check the balance for the selected cash account on the specified date, and show the result in an information message.</span></span> <span data-ttu-id="9d48c-367">W obliczaniu salda mogą być uwzględniane tylko zatwierdzone transakcje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-367">Only approved transactions can be counted in the balance calculation.</span></span> <span data-ttu-id="9d48c-368">Transakcje oznaczone jako <strong>Dla listy płac</strong> nie są brane pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="9d48c-368">Transactions that are marked as <strong>For payroll</strong> aren&#39;t considered.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-369">Ponowne obliczanie salda kasowego</span><span class="sxs-lookup"><span data-stu-id="9d48c-369">Cash balance recalculation</span></span></td>
<td><span data-ttu-id="9d48c-370">To zadanie pozwala upewnić się, że salda księgi dla kont kasowych pasują do salda kasowego.</span><span class="sxs-lookup"><span data-stu-id="9d48c-370">Use this task to make sure that the ledger balances for cash accounts fit the cash balance.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-371">Tworzenie raportu kasowego (tylko Polska)</span><span class="sxs-lookup"><span data-stu-id="9d48c-371">Cash report creation (for Poland only)</span></span></td>
<td><span data-ttu-id="9d48c-372">Tworzenie raportu <strong>Kasa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-372">Create a <strong>Cash</strong> report.</span></span> <span data-ttu-id="9d48c-373">Numer raportu <strong>Kasa</strong> jest generowany na podstawie numeracji ustawionej w obszarze <strong>Numer raportu</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-373">The <strong>Cash</strong> report number is generated based on the number sequence that is set up for <strong>Report number</strong>.</span></span> <span data-ttu-id="9d48c-374">W oknie dialogowym zadania w polu <strong>Do dnia</strong> określ ostatni dzień, z którego transakcje kasowe powinny być uwzględniane w raporcie <strong>Kasa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-374">In the dialog box for the task, in the <strong>To date</strong>, specify the last date for which cash transactions should be counted for the <strong>Cash</strong> report.</span></span> <span data-ttu-id="9d48c-375">Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ dodatkowe kryteria ograniczające wybór transakcji kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-375">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify additional criteria to limit the selection of cash transactions.</span></span> <span data-ttu-id="9d48c-376">Kryteria te mogą obejmować numery kont kasowych i kody walut.</span><span class="sxs-lookup"><span data-stu-id="9d48c-376">These criteria can include cash account numbers and currency codes.</span></span> <span data-ttu-id="9d48c-377">W polu <strong>Autor</strong> wybierz użytkownika odpowiedzialnego za tworzenie raportów.</span><span class="sxs-lookup"><span data-stu-id="9d48c-377">In the <strong>Create by</strong> field, select the user who is responsible for report creation.</span></span> <span data-ttu-id="9d48c-378">Aby wyświetlić utworzony raport <strong>Kasa</strong>, użyj przycisku <strong>Raporty kasowe</strong> znajdującego się na stronie <strong>Konta kasowe</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-378">To view the <strong>Cash</strong> report that is created, use the <strong>Cash reports</strong> button on the <strong>Cash accounts</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9d48c-379">Kasa — korekta kursu wymiany (FIFO i LIFO) (tylko Polska)</span><span class="sxs-lookup"><span data-stu-id="9d48c-379">Cash - Exchange adjustment FIFO and LIFO (for Poland only)</span></span></td>
<td><span data-ttu-id="9d48c-380">Obliczanie różnic kursowych według polskich norm.</span><span class="sxs-lookup"><span data-stu-id="9d48c-380">Calculate the exchange adjustment per Polish standards.</span></span> <span data-ttu-id="9d48c-381">Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ konto kasowe, dla którego ma zostać wykonane zadanie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-381">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify the cash account to run the task for.</span></span> <span data-ttu-id="9d48c-382">Zaznacz pole wyboru <strong>Ponowne obliczanie</strong>, aby wykonać pełne ponowne obliczanie różnic kursowych dla wszystkich otwartych okresów.</span><span class="sxs-lookup"><span data-stu-id="9d48c-382">Select the <strong>Recalculation</strong> check box to do a full recalculation of the exchange adjustment difference for all open periods.</span></span> <span data-ttu-id="9d48c-383">Oto sposób obliczania różnic kursowych w przypadku używania metody FIFO (pierwsze na wejściu, pierwsze na wyjściu) i LIFO (ostatnie na wejściu, pierwsze na wyjściu):</span><span class="sxs-lookup"><span data-stu-id="9d48c-383">Here is how the exchange adjustment is calculated when the first in, first out (FIFO) and last in, first out (LIFO) methods are used:</span></span>
<ul>
<li><span data-ttu-id="9d48c-384"><strong>Metoda FIFO</strong> — System szuka transakcji wydatków mającej wcześniejszą datę transakcji (niższy numer zamówienia) i rozlicza ją względem transakcja przychodu mającej wcześniejszą datę transakcji (niższy numer zamówienia).</span><span class="sxs-lookup"><span data-stu-id="9d48c-384"><strong>FIFO method</strong> – The system searches for an expenditure transaction that has an earlier transaction date (smaller order number) and settles it with a receipt transaction that has an earlier transaction date (smaller order number).</span></span></li>
<li><span data-ttu-id="9d48c-385"><strong>Metoda LIFO</strong> — System szuka transakcji wydatków mającej późniejszą datę transakcji (wyższy numer zamówienia) i rozlicza ją względem transakcja przychodu mającej późniejszą datę transakcji (wyższy numer zamówienia).</span><span class="sxs-lookup"><span data-stu-id="9d48c-385"><strong>LIFO method</strong> – The system searches for an expenditure transaction that has a later transaction date (larger order number) and settles it with a receipt transaction that has a later transaction date (larger order number).</span></span></li>
</ul>
<span data-ttu-id="9d48c-386">Rozliczona kwota znajduje odzwierciedlenie w polu <strong>Rozliczona waluta</strong> na stronie <strong>Transakcja kasowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-386">The settled amount is reflected in the <strong>Settled currency</strong> field on the <strong>Cash transaction</strong> page.</span></span> <span data-ttu-id="9d48c-387">W przypadku istnienia różnicy kursowej kwota jest odzwierciedlana w polu <strong>Kwota korekty kursu wymiany</strong>, a transakcja o typie dokumentu <strong>Różnice kursowe</strong> jest generowana w tabeli <strong>Transakcja kasowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-387">If there is an exchange adjustment difference, the amount is reflected in the <strong>Exchange adjustment amount</strong> field, and a transaction of the <strong>Exchange rate difference</strong> document type is generated in the <strong>Cash transaction</strong> table.</span></span> <span data-ttu-id="9d48c-388">Konta księgowe transakcji wynikowych ustawia się w tabeli <strong>Waluta</strong> (w polach <strong>Zysk finansowy z tytułu dodatnich różnic kursowych</strong> i <strong>Strata finansowa z tytułu ujemnych różnic kursowych</strong>).</span><span class="sxs-lookup"><span data-stu-id="9d48c-388">Ledger accounts for profit/loss transactions are set in the <strong>Currency</strong> table (<strong>Exchange rate financial profit</strong> and <strong>Exchange rate financial loss</strong>).</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9d48c-389">Przeszacowanie w walucie obcej — kasa</span><span class="sxs-lookup"><span data-stu-id="9d48c-389">Foreign currency revaluation - Cash</span></span></td>
<td><span data-ttu-id="9d48c-390">Za pomocą tego zadania można uzyskać odpowiednie saldo w walucie domyślnej na dzień sprawozdawczy, jeśli operacje są wprowadzane w walutach obcych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-390">Use this task to have an adequate balance in the default currency on the reporting date when the operations are entered in foreign currencies.</span></span> <span data-ttu-id="9d48c-391">Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ konto kasowe, dla którego ma zostać wykonane zadanie.</span><span class="sxs-lookup"><span data-stu-id="9d48c-391">Use the <strong>Filter</strong> function on the <strong>Records to include</strong> tab to specify the cash account to run the task for.</span></span> <span data-ttu-id="9d48c-392">W oknie dialogowym zadania użyj pól <strong>Z waluty</strong> i <strong>Na walutę</strong>, aby określić waluty transakcji.</span><span class="sxs-lookup"><span data-stu-id="9d48c-392">In the dialog box for the task, use the <strong>From currency</strong> and <strong>To Currency</strong> fields to specify transaction currencies.</span></span> <span data-ttu-id="9d48c-393">System porównuje kwotę w walucie, która została przeliczona przy użyciu kursu wymiany na określony dzień, z kwotą w walucie domyślnej.</span><span class="sxs-lookup"><span data-stu-id="9d48c-393">The system compares the amount in the currency that was converted by using exchange rate on the selected date with the amount in the default currency.</span></span> <span data-ttu-id="9d48c-394">Różnica między tymi dwoma kwotami (z wyłączeniem poprzedniej różnicy kursowej) jest obliczoną różnicą kursową.</span><span class="sxs-lookup"><span data-stu-id="9d48c-394">The difference between the two amounts (excluding the previous exchange adjustment) is the calculated exchange adjustment.</span></span> <span data-ttu-id="9d48c-395">To zadanie powoduje utworzenie zatwierdzonej transakcji kasowej o typie <strong>Różnica kursowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-395">This task creates an approved cash transaction of the <strong>Exchange adjustment</strong> type.</span></span> <span data-ttu-id="9d48c-396">Transakcja finansowa powstaje poprzez użycie konta księgowego dla gotówki oraz konta księgowego określonego w polu <strong>Niezrealizowana dodatnia różnica kursowa</strong> lub <strong>Niezrealizowana ujemna różnica kursowa</strong> w tabeli <strong>Waluta</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d48c-396">The ledger transaction is formed by using the ledger account for cash and the ledger account that is specified in <strong>Unrealized profit</strong> or <strong>Unrealized loss</strong> in the <strong>Currency</strong> table.</span></span></td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a><span data-ttu-id="9d48c-397">Zapytania i raporty</span><span class="sxs-lookup"><span data-stu-id="9d48c-397">Inquiries and reports</span></span>

| <span data-ttu-id="9d48c-398">Zapytanie lub raport</span><span class="sxs-lookup"><span data-stu-id="9d48c-398">Inquiry or report</span></span>                             | <span data-ttu-id="9d48c-399">opis</span><span class="sxs-lookup"><span data-stu-id="9d48c-399">Description</span></span>                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9d48c-400">Widok transakcji kasowych</span><span class="sxs-lookup"><span data-stu-id="9d48c-400">Cash transactions view</span></span>                        | <span data-ttu-id="9d48c-401">Dla wiersza arkusza kasowego przycisk **Zapytania** w okienku akcji pozwala wyświetlić transakcje kasowe, saldo kasowe i inne informacje.</span><span class="sxs-lookup"><span data-stu-id="9d48c-401">For a Slip journal line, use the **Inquiries** button on the Action Pane to view ledger transactions, the cash balance, and other information.</span></span>                                                                                  |
| <span data-ttu-id="9d48c-402">Transakcja kasowa</span><span class="sxs-lookup"><span data-stu-id="9d48c-402">Cash transaction</span></span>                              | <span data-ttu-id="9d48c-403">Aby wyświetlić transakcje kasowe, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Transakcje kasowe**.</span><span class="sxs-lookup"><span data-stu-id="9d48c-403">Go to **Cash and bank management** &gt; **Inquiries and reports** &gt; **Cash transactions** to view cash transactions.</span></span> <span data-ttu-id="9d48c-404">Za pomocą funkcji **Filtr** określ dodatkowe kryteria ograniczające wybór transakcji kasowych.</span><span class="sxs-lookup"><span data-stu-id="9d48c-404">Use the **Filter** function to specify additional criteria to limit the selection of cash transactions.</span></span> |
| <span data-ttu-id="9d48c-405">Arkusz rejestracji (Estonia, Rosja)</span><span class="sxs-lookup"><span data-stu-id="9d48c-405">Journal of registration (for Estonia, Russia)</span></span> | <span data-ttu-id="9d48c-406">Raport w oknie **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Arkusz rejestracji** pokazuje wszystkie wystawione dokumenty KP i KW.</span><span class="sxs-lookup"><span data-stu-id="9d48c-406">The report at **Cash and bank management** &gt; **Inquiries and reports** &gt; **Journal of registration** reflects all cash reimbursement and cash disbursement slips that have been issued.</span></span>                                   |
| <span data-ttu-id="9d48c-407">Księga kasowa (Łotwa, Litwa, Rosja)</span><span class="sxs-lookup"><span data-stu-id="9d48c-407">Cash book (for Latvia, Lithuania, Russia)</span></span>     | <span data-ttu-id="9d48c-408">Raport w oknie **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Raport księgi kasowej** pokazuje rzeczywiste przesunięcia środków pieniężnych (wpływy i wydatki).</span><span class="sxs-lookup"><span data-stu-id="9d48c-408">The report at **Cash and bank management** &gt; **Inquiries and reports** &gt; **Cash book report** reflects actual cash fund movements (receipts and expenditures).</span></span>                                                            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]