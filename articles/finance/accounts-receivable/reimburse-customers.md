---
title: Zwroty do odbiorców
description: W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd8b32e04743fdde3cc339e1535f8ae58c518aed
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816299"
---
# <a name="reimburse-customers"></a><span data-ttu-id="f7345-104">Zwroty do odbiorców</span><span class="sxs-lookup"><span data-stu-id="f7345-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7345-105">W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f7345-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="f7345-106">Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda.</span><span class="sxs-lookup"><span data-stu-id="f7345-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="f7345-107">W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="f7345-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="f7345-108">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="f7345-108">Prerequisite</span></span>                                                            | <span data-ttu-id="f7345-109">Opis</span><span class="sxs-lookup"><span data-stu-id="f7345-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="f7345-110">Określanie minimalnej kwoty zwrotu pieniędzy dla firmy.</span><span class="sxs-lookup"><span data-stu-id="f7345-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="f7345-111">Na stronie **Parametry modułu rozrachunków z odbiorcami** w obszarze **Ogólne** w polu **Minimalny zwrot** wprowadź minimalną kwotę, jaka może zostać zwrócony odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f7345-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="f7345-112">Opcjonalnie: Dodaj konto dostawcy do każdego odbiorcy, dla którego mogą zostać zwrócone nadpłaty</span><span class="sxs-lookup"><span data-stu-id="f7345-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="f7345-113">Na stronie **Odbiorcy** na skróconej karcie **Dodatkowe szczegóły** w polu **Konto dostawcy** wybierz konto dostawcy dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f7345-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="f7345-114">Podczas tworzenia transakcji zwrotu, tworzona jest faktura od dostawcy na kwotę salda kredytu.</span><span class="sxs-lookup"><span data-stu-id="f7345-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="f7345-115">Proces zwrotu nadpłaty usuwa saldo kredytu dla konta odbiorcy i tworzy saldo należne dla konta dostawcy, odpowiadającego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f7345-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="f7345-116">W module Rozrachunki z odbiorcami uruchom proces **Zwrot nadpłaty** (**Rozrachunki z odbiorcami \> Zadania okresowe \> Zwrot nadpłaty**).</span><span class="sxs-lookup"><span data-stu-id="f7345-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="f7345-117">Aby grupować wszystkie transakcje, niezależnie od wymiarów księgowych, dla opcji **Sumuj odbiorcę** określ wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f7345-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="f7345-118">Aby grupować tylko transakcje o podobnych wymiarach księgowych, ustaw w opcji wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="f7345-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="f7345-119">Wybierz opcję **Uwzględnij odbiorców z zaległymi transakcjami debetowymi**, aby zaznaczyć odbiorców, którzy mają nierozliczone kwoty obciążeń.</span><span class="sxs-lookup"><span data-stu-id="f7345-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="f7345-120">Aby zwrócić nadpłaty na określone konta odbiorców, na skróconej karcie **Rekordy do uwzględnienia** kliknij opcję **Filtruj**, a następnie określ konta odbiorców w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="f7345-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="f7345-121">Wartości kredytów są transferowane na konta dostawców odpowiedających odbiorcom i są przetwarzane jak zwykłe płatności.</span><span class="sxs-lookup"><span data-stu-id="f7345-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="f7345-122">Jeśli odbiorca nie posiada konta dostawcy, zostanie automatycznie utworzone dla tego odbiorcy tymczasowe konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f7345-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="f7345-123">Aby wyświetlić utworzone transakcje zwrotu nadpłaty, skorzystaj z raportu **Zwrot nadpłaty** (**Rozrachunki z odbiorcami \> Zapytania i raporty \> Raport Zwrot nadpłat**).</span><span class="sxs-lookup"><span data-stu-id="f7345-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="f7345-124">W module Rozrachunki z dostawcami należy utworzyć płatność dla faktur od dostawcy utworzonych w wyniku procesu zwrotu nadpłaty.</span><span class="sxs-lookup"><span data-stu-id="f7345-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="f7345-125">Aby uzyskać informacje o sposobach płacenia dostawcom, zapoznaj się z tematem [Omówienie płatności dla dostawców](../accounts-payable/Vendor-payments-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="f7345-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]