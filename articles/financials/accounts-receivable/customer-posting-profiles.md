---
title: Profile księgowania odbiorców
description: Profile księgowania odbiorców sterują księgowaniem transakcji z odbiorcami w księdze głównej.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bb2784d70e99c3c3443bed1b8cb040552b5b6f6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835122"
---
# <a name="customer-posting-profiles"></a><span data-ttu-id="95a2c-103">Profile księgowania odbiorców</span><span class="sxs-lookup"><span data-stu-id="95a2c-103">Customer posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95a2c-104">Profile księgowania odbiorców sterują księgowaniem transakcji z odbiorcami w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="95a2c-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="95a2c-105">Profile księgowania odbiorców</span><span class="sxs-lookup"><span data-stu-id="95a2c-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="95a2c-106">Profile księgowania odbiorców pozwalają na przypisywanie kont księgi głównej i ustawień dokumentów do wszystkich odbiorców, grupy odbiorców lub jednego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="95a2c-107">Te ustawienia będą obowiązywać podczas tworzenia zamówień sprzedaży, faktur niezależnych, płatności gotówką, ponagleń i not odsetkowych.</span><span class="sxs-lookup"><span data-stu-id="95a2c-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="95a2c-108">W przypadku niektórych transakcji można wybrać profil księgowania, który różni się od profilów księgowania ustawionych dla transakcji na tej stronie i ma względem nich pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="95a2c-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="95a2c-109">Domyślny profil księgowania jest zdefiniowany na skróconej karcie Księga i podatek na stronie parametrów rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="95a2c-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="95a2c-110">Domyślny profil księgowania jest następnie automatycznie uwzględniany w nagłówku nowych dokumentów, gdzie można go zmienić na inny profil księgowania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="95a2c-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="95a2c-111">Można także skojarzyć definicje księgowania transakcji z typami księgowania transakcji na stronie Definicje księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="95a2c-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="95a2c-112">Definicja księgowania umożliwia kontrolowanie księgowania transakcji odbiorcy w księdze głównej zamiast przez profile księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="95a2c-113">Tworzenie profilu księgowania</span><span class="sxs-lookup"><span data-stu-id="95a2c-113">Creating a posting profile</span></span>
<span data-ttu-id="95a2c-114">Służy do określania kont księgowych używanych podczas księgowania transakcji z wybranym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="95a2c-115">Służy do wybierania kodu konta i, jeżeli jest to możliwe, numeru konta lub grupy dla wybranego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="95a2c-116">W procesie księgowania najodpowiedniejszy profil księgowania dla każdej transakcji jest wyszukiwany według najbardziej charakterystycznej kombinacji kodu konta, numeru konta lub numeru grupy z następującym priorytetem:</span><span class="sxs-lookup"><span data-stu-id="95a2c-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="95a2c-117">Wartość pola **Kod konta**</span><span class="sxs-lookup"><span data-stu-id="95a2c-117">**Account code** field value</span></span> | <span data-ttu-id="95a2c-118">Wartość pola **Numer konta/grupy**</span><span class="sxs-lookup"><span data-stu-id="95a2c-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="95a2c-119">Priorytet wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="95a2c-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="95a2c-120">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="95a2c-120">**Table**</span></span>                    | <span data-ttu-id="95a2c-121">Określone konto odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-121">Specific customer account</span></span>                       | <span data-ttu-id="95a2c-122">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="95a2c-122">1</span></span>               |
| <span data-ttu-id="95a2c-123">**Grupa**</span><span class="sxs-lookup"><span data-stu-id="95a2c-123">**Group**</span></span>                    | <span data-ttu-id="95a2c-124">Grupa odbiorców skojarzona z odbiorcą</span><span class="sxs-lookup"><span data-stu-id="95a2c-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="95a2c-125">2</span><span class="sxs-lookup"><span data-stu-id="95a2c-125">2</span></span>               |
| <span data-ttu-id="95a2c-126">**Wszystkie**</span><span class="sxs-lookup"><span data-stu-id="95a2c-126">**All**</span></span>                      | <span data-ttu-id="95a2c-127">Puste</span><span class="sxs-lookup"><span data-stu-id="95a2c-127">Blank</span></span>                                           | <span data-ttu-id="95a2c-128">3</span><span class="sxs-lookup"><span data-stu-id="95a2c-128">3</span></span>               |

<span data-ttu-id="95a2c-129">Jeśli wszystkie transakcje odbiorcy mają mieć ten sam profil księgowania, należy ustawić tylko jeden profil księgowania o wartości Wszystko polu Kod konta.</span><span class="sxs-lookup"><span data-stu-id="95a2c-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="95a2c-130">Określ następujące wartości do konfigurowania profilu księgowania:</span><span class="sxs-lookup"><span data-stu-id="95a2c-130">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="95a2c-131">Pole</span><span class="sxs-lookup"><span data-stu-id="95a2c-131">Field</span></span></th>
<th><span data-ttu-id="95a2c-132">Opis</span><span class="sxs-lookup"><span data-stu-id="95a2c-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="95a2c-133"><strong>Profil księgowania</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="95a2c-134">Umożliwia wprowadzenie kodu profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="95a2c-135">Można na przykład utworzyć 2 profile księgowania, aby korzystać z jednego konta dla sald odbiorcy w walucie krajowej, a z drugiego — dla sald odbiorcy w walucie zagranicznej.</span><span class="sxs-lookup"><span data-stu-id="95a2c-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="95a2c-136">Jedno konto można nazwać Krajowe, a drugie Zagraniczne.</span><span class="sxs-lookup"><span data-stu-id="95a2c-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95a2c-137"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="95a2c-138">Umożliwia wprowadzenie opisu profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="95a2c-139">To jest używane jedynie, aby lepiej określić profil księgowania, podczas przeglądania tej strony.</span><span class="sxs-lookup"><span data-stu-id="95a2c-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95a2c-140"><strong>Kod konta</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="95a2c-141">Umożliwia określenie, czy profil księgowania dotyczy jednego odbiorcy, grupy odbiorców czy wszystkich odbiorców:</span><span class="sxs-lookup"><span data-stu-id="95a2c-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="95a2c-142"><strong>Tabela</strong> — profil księgowania dotyczy jednego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="95a2c-143">Wybierz konto odbiorcy w polu Numer konta/grupy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="95a2c-144"><strong>Grupa</strong> — profil księgowania dotyczy grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="95a2c-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="95a2c-145">Wybierz grupę odbiorców w polu Numer konta/grupy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="95a2c-146"><strong>Wszyscy</strong> — profil księgowania dotyczy wszystkich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="95a2c-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="95a2c-147">Pole Numer konta/grupy zostaw niewypełnione</span><span class="sxs-lookup"><span data-stu-id="95a2c-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95a2c-148"><strong>Numer konta/grupy</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="95a2c-149">W przypadku wybrania opcji Tabela w polu Kod konta należy wybrać numer konta odbiorcy skojarzony z profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="95a2c-150">W przypadku wybrania opcji Grupa zaznacz grupę odbiorców.</span><span class="sxs-lookup"><span data-stu-id="95a2c-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="95a2c-151">W przypadku wybrania opcji Wszystko należy pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="95a2c-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95a2c-152"><strong>Konto rozrachunkowe</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="95a2c-153">Umożliwia wybranie konta księgowego, które będzie używane jako konto rozrachunkowe odbiorcy dla odbiorców skojarzony z tym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95a2c-154"><strong>Konto rozliczeniowe</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="95a2c-155">Umożliwia wybranie konta płynności używanego przy prognozowaniu przepływów pieniężnych.</span><span class="sxs-lookup"><span data-stu-id="95a2c-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="95a2c-156">To pole będzie dostępne tylko wtedy, gdy prognozy przepływów gotówkowych są dozwolone.</span><span class="sxs-lookup"><span data-stu-id="95a2c-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95a2c-157"><strong>Przedpłaty podatku</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="95a2c-158">Wybierz konto dla płatności podatków z góry.</span><span class="sxs-lookup"><span data-stu-id="95a2c-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Uwaga" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="95a2c-160"><strong>Uwaga</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="95a2c-161">Aby określić profil księgowania używany, gdy płatność jest oznaczona jako przedpłata, należy użyć strony parametrów rozrachunków z odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="95a2c-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95a2c-162"><strong>Konto zobowiązań związanych z rabatami</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="95a2c-163">Umożliwia wybranie konta księgowego dla księgowania rabatu.</span><span class="sxs-lookup"><span data-stu-id="95a2c-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="95a2c-164"><strong>Kolejność ponagleń</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="95a2c-165">Umożliwia wybranie identyfikatora kolejności ponagleń dla odbiorców, do których jest przypisany profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="95a2c-166"><strong>Kod odsetek</strong></span><span class="sxs-lookup"><span data-stu-id="95a2c-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="95a2c-167">Umożliwia wstawienie kodu używanego do obliczeń odsetek dla odbiorców, do których jest przypisany profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="95a2c-168">**Restrykcje tabeli**</span><span class="sxs-lookup"><span data-stu-id="95a2c-168">**Table restrictions**</span></span>

<span data-ttu-id="95a2c-169">Dla transakcji z tym profilem księgowania określ, czy transakcje będą rozliczane automatycznie, czy będą obliczane odsetki i czy będą wysyłane ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="95a2c-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="95a2c-170">Można również wybrać konto, które będzie używane podczas zamykania transakcji z wybranym profilem księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="95a2c-171">Określ następujące wartości do konfigurowania profilu księgowania:</span><span class="sxs-lookup"><span data-stu-id="95a2c-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="95a2c-172">Pole</span><span class="sxs-lookup"><span data-stu-id="95a2c-172">Field</span></span>                 | <span data-ttu-id="95a2c-173">Opis</span><span class="sxs-lookup"><span data-stu-id="95a2c-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="95a2c-174">**Rozliczenie**</span><span class="sxs-lookup"><span data-stu-id="95a2c-174">**Settlement**</span></span>        | <span data-ttu-id="95a2c-175">Wybierz tę opcję, aby włączyć automatyczne rozliczanie transakcji, które mają ten profil księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="95a2c-176">Jeśli ta opcja jest wyczyszczona, należy ręcznie rozliczyć transakcje na stronie Rozliczanie otwartych transakcji lub Wprowadzanie płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="95a2c-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="95a2c-177">**Zainteresowania**</span><span class="sxs-lookup"><span data-stu-id="95a2c-177">**Interest**</span></span>          | <span data-ttu-id="95a2c-178">Wybierz tę opcję, jeśli odsetki powinny być obliczane według niezapłaconych sald dla kont odbiorców z tym profilem.</span><span class="sxs-lookup"><span data-stu-id="95a2c-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="95a2c-179">Jeśli ta opcja jest wyczyszczona, odsetki dla tych odbiorców nie będą obliczane.</span><span class="sxs-lookup"><span data-stu-id="95a2c-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="95a2c-180">**Ponaglenie**</span><span class="sxs-lookup"><span data-stu-id="95a2c-180">**Collection letter**</span></span> | <span data-ttu-id="95a2c-181">Wybierz tę opcję, jeśli ponaglenia powinny być generowane dla kont odbiorców z tym profilem.</span><span class="sxs-lookup"><span data-stu-id="95a2c-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="95a2c-182">Jeśli ta opcja jest wyczyszczona, ponaglenia dla tych odbiorców nie będą generowane.</span><span class="sxs-lookup"><span data-stu-id="95a2c-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="95a2c-183">**Zamknij**</span><span class="sxs-lookup"><span data-stu-id="95a2c-183">**Close**</span></span>             | <span data-ttu-id="95a2c-184">Umożliwia wybranie docelowego profilu księgowania, który ma zostać włączony po zamknięciu transakcji bieżącego profilu księgowania.</span><span class="sxs-lookup"><span data-stu-id="95a2c-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="95a2c-185">Transakcja jest traktowana jako zamknięta, jeśli jest w pełni rozliczona.</span><span class="sxs-lookup"><span data-stu-id="95a2c-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="95a2c-186">Aby uzyskać więcej informacji, zobacz [Przegląd płatności odbiorców](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95a2c-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>

