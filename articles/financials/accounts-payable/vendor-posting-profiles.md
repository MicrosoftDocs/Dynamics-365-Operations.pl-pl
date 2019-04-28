---
title: Profile księgowania dostawców
description: Profile księgowania dostawców umożliwiają nadzór nad księgowaniem transakcji z dostawcami w księdze głównej.
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e81f8b472e7ac7578c184716dcb4e5f3d7aeb65d
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/25/2019
ms.locfileid: "896541"
---
# <a name="vendor-posting-profiles"></a><span data-ttu-id="ab377-103">Profile księgowania dostawców</span><span class="sxs-lookup"><span data-stu-id="ab377-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab377-104">Profile księgowania dostawców umożliwiają nadzór nad księgowaniem transakcji z dostawcami w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="ab377-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="ab377-105">Profile księgowania dostawców</span><span class="sxs-lookup"><span data-stu-id="ab377-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="ab377-106">Profile księgowania dostawców pozwalają na przypisywanie kont księgi głównej i ustawień dokumentów do wszystkich dostawców, grupy dostawców lub jednego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab377-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="ab377-107">Te ustawienia będą obowiązywać podczas tworzenia zamówień zakupu, faktur od dostawcy i płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="ab377-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="ab377-108">W przypadku niektórych transakcji można wybrać profil księgowania, który różni się od profilów księgowania ustawionych dla transakcji na tej stronie i ma względem nich pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="ab377-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="ab377-109">Domyślny profil księgowania jest zdefiniowany na skróconej karcie Księga i podatek na stronie parametrów rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="ab377-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="ab377-110">Domyślny profil księgowania jest następnie automatycznie uwzględniany w nagłówku nowych dokumentów, gdzie można go zmienić na inny profil księgowania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="ab377-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="ab377-111">Można także skojarzyć definicje księgowania transakcji z typami księgowania transakcji na stronie Definicje księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="ab377-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="ab377-112">Definicja księgowania umożliwia kontrolowanie księgowania transakcji dostawcy w księdze głównej zamiast przez profile księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="ab377-113">Tworzenie profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="ab377-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="ab377-114">**Konfiguracja**</span><span class="sxs-lookup"><span data-stu-id="ab377-114">**Setup**</span></span>

<span data-ttu-id="ab377-115">Służy do określania kont księgowych używanych podczas księgowania transakcji z wybranym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="ab377-116">Służy do wybierania kodu konta i, jeżeli jest to możliwe, numeru konta lub grupy dla wybranego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="ab377-117">W procesie księgowania najodpowiedniejszy profil księgowania dla każdej transakcji jest wyszukiwany według najbardziej charakterystycznej kombinacji kodu konta, numeru konta lub numeru grupy z następującym priorytetem:</span><span class="sxs-lookup"><span data-stu-id="ab377-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="ab377-118">Wartość pola **Kod konta**</span><span class="sxs-lookup"><span data-stu-id="ab377-118">**Account code** field value</span></span> | <span data-ttu-id="ab377-119">Wartość pola **Numer konta/grupy**</span><span class="sxs-lookup"><span data-stu-id="ab377-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="ab377-120">Priorytet wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="ab377-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="ab377-121">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="ab377-121">**Table**</span></span>                    | <span data-ttu-id="ab377-122">Konto określonego dostawcy</span><span class="sxs-lookup"><span data-stu-id="ab377-122">Specific vendor account</span></span>                     | <span data-ttu-id="ab377-123">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="ab377-123">1</span></span>               |
| <span data-ttu-id="ab377-124">**Grupa**</span><span class="sxs-lookup"><span data-stu-id="ab377-124">**Group**</span></span>                    | <span data-ttu-id="ab377-125">Grupa dostawców, do której należy dostawca.</span><span class="sxs-lookup"><span data-stu-id="ab377-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="ab377-126">2</span><span class="sxs-lookup"><span data-stu-id="ab377-126">2</span></span>               |
| <span data-ttu-id="ab377-127">**Wszystkie**</span><span class="sxs-lookup"><span data-stu-id="ab377-127">**All**</span></span>                      | <span data-ttu-id="ab377-128">Puste</span><span class="sxs-lookup"><span data-stu-id="ab377-128">Blank</span></span>                                       | <span data-ttu-id="ab377-129">3</span><span class="sxs-lookup"><span data-stu-id="ab377-129">3</span></span>               |

<span data-ttu-id="ab377-130">Jeśli wszystkie transakcje dostawcy mają mieć ten sam profil księgowania, należy ustawić tylko jeden profil księgowania o wartości Wszystko polu Kod konta.</span><span class="sxs-lookup"><span data-stu-id="ab377-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="ab377-131">Określ następujące wartości do konfigurowania profilu księgowania:</span><span class="sxs-lookup"><span data-stu-id="ab377-131">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ab377-132">Pole</span><span class="sxs-lookup"><span data-stu-id="ab377-132">Field</span></span></th>
<th><span data-ttu-id="ab377-133">Opis</span><span class="sxs-lookup"><span data-stu-id="ab377-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ab377-134"><strong>Profil księgowania</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="ab377-135">Umożliwia wprowadzenie kodu profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="ab377-136">Można na przykład utworzyć 2 profile księgowania, aby korzystać z jednego konta dla sald dostawcy w walucie krajowej, a z drugiego — dla sald dostawcy w walucie zagranicznej.</span><span class="sxs-lookup"><span data-stu-id="ab377-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="ab377-137">Jedno konto można nazwać Krajowe, a drugie Zagraniczne.</span><span class="sxs-lookup"><span data-stu-id="ab377-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ab377-138"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="ab377-139">Umożliwia wprowadzenie opisu profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ab377-140"><strong>Kod konta</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="ab377-141">Umożliwia określenie, czy profil księgowania dotyczy określonego dostawcy, grupy dostawców czy wszystkich dostawców:</span><span class="sxs-lookup"><span data-stu-id="ab377-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="ab377-142"><strong>Tabela</strong> — profil księgowania dotyczy jednego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab377-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="ab377-143">Wybierz konto dostawcy w polu Numer konta/grupy.</span><span class="sxs-lookup"><span data-stu-id="ab377-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="ab377-144"><strong>Grupa</strong> — profil księgowania dotyczy grupy dostawców.</span><span class="sxs-lookup"><span data-stu-id="ab377-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="ab377-145">Wybierz grupę dostawców w polu Numer konta/grupy.</span><span class="sxs-lookup"><span data-stu-id="ab377-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="ab377-146"><strong>Wszyscy</strong> — profil księgowania dotyczy wszystkich dostawców.</span><span class="sxs-lookup"><span data-stu-id="ab377-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="ab377-147">Pole Numer konta/grupy zostaw niewypełnione</span><span class="sxs-lookup"><span data-stu-id="ab377-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ab377-148"><strong>Numer konta/grupy</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="ab377-149">W przypadku wybrania opcji Tabela w polu Kod konta należy wybrać numer konta dostawcy skojarzony z profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="ab377-150">W przypadku wybrania opcji Grupa należy wybrać grupę dostawców.</span><span class="sxs-lookup"><span data-stu-id="ab377-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="ab377-151">W przypadku wybrania opcji Wszystko należy pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="ab377-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ab377-152"><strong>Konto rozrachunkowe</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="ab377-153">Umożliwia wybranie konta księgowego, które będzie używane jako konto rozrachunkowe dostawcy dla dostawców objętych tym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Uwaga" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="ab377-155"><strong>Uwaga</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ab377-156">Po wybraniu przełącznika Użyj definicji księgowania na stronie Parametry księgi głównej transakcja definicji księgowania dla faktur od dostawcy jest używana zamiast konta rozrachunkowego.</span><span class="sxs-lookup"><span data-stu-id="ab377-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ab377-157"><strong>Konto rozliczeniowe</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="ab377-158">Umożliwia wybranie konta płynności używanego przy prognozowaniu przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="ab377-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="ab377-159">To pole jest dostępne tylko po włączeniu prognozowania przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="ab377-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ab377-160"><strong>Przedpłaty podatku</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="ab377-161">Wybierz konto dla płatności podatków z góry.</span><span class="sxs-lookup"><span data-stu-id="ab377-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Uwaga" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="ab377-163"><strong>Uwaga</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ab377-164">Profil księgowania używany, gdy płatność jest oznaczona jako przedpłata jest zaznaczony w profilu księgowania z polem załącznika arkusza zaliczki w księdze i obszarze podatku strony Parametry rozrachunków z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="ab377-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ab377-165"><strong>Przyjęcie</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="ab377-166">Wybierz konto księgowe, na którym zostały zaksięgowane informacje o niezatwierdzonych fakturach od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab377-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="ab377-167">Informacje są wprowadzane w arkuszu rejestru faktur.</span><span class="sxs-lookup"><span data-stu-id="ab377-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="ab377-168">Na przykład użytkownik wprowadza najbardziej podstawowe informacje o otrzymywanych fakturach dostawców w rejestrze faktur.</span><span class="sxs-lookup"><span data-stu-id="ab377-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="ab377-169">Podczas księgowania rejestru faktur transakcje są księgowane na koncie wprowadzonym w tym miejscu oraz w polu Konto przeciwstawne.</span><span class="sxs-lookup"><span data-stu-id="ab377-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="ab377-170">Po zatwierdzeniu faktur zadłużenie jest przenoszone z Konto przybycia na konto rozrachunkowe dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ab377-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ab377-171"><strong>Konto przeciwstawne</strong></span><span class="sxs-lookup"><span data-stu-id="ab377-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="ab377-172">Umożliwia wybranie numeru konta przeciwstawnego używanego do księgowania niezatwierdzonych faktur dostawców, które zostały zaktualizowane przy użyciu rejestru faktur.</span><span class="sxs-lookup"><span data-stu-id="ab377-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="ab377-173">To konto przeciwstawne działa jako konto przeciwstawne dla transakcji, które są księgowane na kontach przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="ab377-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="ab377-174">W związku z tym konto zawiera zakupy u dostawców, które nie zostały jeszcze zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="ab377-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="ab377-175">**Restrykcje tabeli**</span><span class="sxs-lookup"><span data-stu-id="ab377-175">**Table restrictions**</span></span>

<span data-ttu-id="ab377-176">Dla transakcji z tym profilem księgowania określ, czy transakcje będą rozliczane automatycznie, czy będą obliczane odsetki i czy będą wysyłane ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="ab377-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="ab377-177">Można również wybrać konto, które będzie używane podczas zamykania transakcji z wybranym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="ab377-178">Określ następujące wartości do konfigurowania profilu księgowania:</span><span class="sxs-lookup"><span data-stu-id="ab377-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="ab377-179">Pole</span><span class="sxs-lookup"><span data-stu-id="ab377-179">Field</span></span>          | <span data-ttu-id="ab377-180">Opis</span><span class="sxs-lookup"><span data-stu-id="ab377-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ab377-181">**Rozliczenie**</span><span class="sxs-lookup"><span data-stu-id="ab377-181">**Settlement**</span></span> | <span data-ttu-id="ab377-182">Wybierz tę opcję, aby włączyć automatyczne rozliczanie transakcji, które mają ten profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="ab377-183">Jeśli ta opcja jest wyczyszczona, należy ręcznie rozliczyć transakcje na stronie Rozliczanie otwartych transakcji.</span><span class="sxs-lookup"><span data-stu-id="ab377-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="ab377-184">**Anuluj**</span><span class="sxs-lookup"><span data-stu-id="ab377-184">**Cancel**</span></span>     | <span data-ttu-id="ab377-185">Wybierz tę opcję, aby umożliwić anulowanie transakcji, które mają ten profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="ab377-186">**Zamknij**</span><span class="sxs-lookup"><span data-stu-id="ab377-186">**Close**</span></span>      | <span data-ttu-id="ab377-187">Umożliwia wybranie docelowego profilu księgowania, który ma zostać włączony po zamknięciu transakcji bieżącego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="ab377-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="ab377-188">Transakcja jest traktowana jako zamknięta, jeśli jest w pełni rozliczona.</span><span class="sxs-lookup"><span data-stu-id="ab377-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |





