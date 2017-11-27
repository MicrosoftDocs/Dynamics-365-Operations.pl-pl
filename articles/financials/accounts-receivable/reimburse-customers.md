---
title: "Zwroty do odbiorców"
description: "W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców. Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 01c9dcebe82544624c6dd0feb3672d1c5bdfe2d1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="reimburse-customers"></a><span data-ttu-id="f4931-104">Zwroty do odbiorców</span><span class="sxs-lookup"><span data-stu-id="f4931-104">Reimburse customers</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f4931-105">W tym artykule wyjaśniono, jak tworzyć transakcje zwrotu nadpłaty dla grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f4931-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="f4931-106">Jeśli odbiorca ma saldo dodatnie, można zwrócić mu wartość salda.</span><span class="sxs-lookup"><span data-stu-id="f4931-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="f4931-107">W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="f4931-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="f4931-108">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="f4931-108">Prerequisite</span></span>                                                            | <span data-ttu-id="f4931-109">Opis</span><span class="sxs-lookup"><span data-stu-id="f4931-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f4931-110">Określanie minimalnej kwoty zwrotu pieniędzy dla firmy.</span><span class="sxs-lookup"><span data-stu-id="f4931-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="f4931-111">Na stronie **Parametry modułu rozrachunków z odbiorcami** w obszarze **Ogólne** w polu **Minimalny zwrot** wprowadź minimalną kwotę, jaka może zostać zwrócony odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f4931-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="f4931-112">Opcjonalnie: Dodaj konto dostawcy do każdego odbiorcy, dla którego mogą zostać zwrócone nadpłaty</span><span class="sxs-lookup"><span data-stu-id="f4931-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="f4931-113">Na stronie **Odbiorcy** na skróconej karcie **Dodatkowe szczegóły** w polu **Konto dostawcy** wybierz konto dostawcy dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f4931-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="f4931-114">Podczas tworzenia transakcji zwrotu, tworzona jest faktura od dostawcy na kwotę salda kredytu.</span><span class="sxs-lookup"><span data-stu-id="f4931-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="f4931-115">Proces zwrotu nadpłaty usuwa saldo kredytu dla konta odbiorcy i tworzy saldo należne dla konta dostawcy, odpowiadającego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f4931-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="f4931-116">W module Rozrachunki z odbiorcami uruchom proces **Zwrot nadpłaty**.</span><span class="sxs-lookup"><span data-stu-id="f4931-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="f4931-117">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="f4931-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="f4931-118">Aby dokonać zwrotu nadpłaty na określone konta, należy kliknąć opcję **Wybierz** i wprowadzić w kwerendzie właściwe konta odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f4931-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="f4931-119">Aby dokonać zwrotu nadpłaty na wszystkie konta, należy kliknąć przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4931-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="f4931-120">Wartości kredytów są transferowane na konta dostawców odpowiedających odbiorcom i są przetwarzane jak zwykłe płatności.</span><span class="sxs-lookup"><span data-stu-id="f4931-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="f4931-121">Jeśli odbiorca nie posiada konta dostawcy, zostanie automatycznie utworzone dla tego odbiorcy tymczasowe konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="f4931-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="f4931-122">Aby wyświetlić utworzone transakcje zwrotu nadpłaty, użyj strony **Zwrot nadpłaty**.</span><span class="sxs-lookup"><span data-stu-id="f4931-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="f4931-123">W module Rozrachunki z dostawcami należy utworzyć płatność dla faktur od dostawcy utworzonych w wyniku procesu zwrotu nadpłaty.</span><span class="sxs-lookup"><span data-stu-id="f4931-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>





