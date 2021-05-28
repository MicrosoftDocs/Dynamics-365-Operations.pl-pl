---
title: Rozliczenia międzyokresowe zakupu, które mają zerową kwotę, są księgowane dla przyjęcia produktów o wartości zerowej
description: Po zaksięgowaniu przyjęcia produktów, które ma wartość zerową, system tworzy księgowanie międzyokresowe zakupu, w którym kwota wynosi 0 (zero).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026829"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="869bf-103">Rozliczenia międzyokresowe zakupu, które mają zerową kwotę, są księgowane dla przyjęcia produktów o wartości zerowej</span><span class="sxs-lookup"><span data-stu-id="869bf-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="869bf-104">Numer artykułu z bazy wiedzy: 4612588</span><span class="sxs-lookup"><span data-stu-id="869bf-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="869bf-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="869bf-105">Symptoms</span></span>

<span data-ttu-id="869bf-106">Po zaksięgowaniu przyjęcia produktów, które ma wartość zerową, system tworzy księgowanie międzyokresowe zakupu, w którym kwota wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="869bf-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="869bf-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="869bf-107">Resolution</span></span>

<span data-ttu-id="869bf-108">Domyślnie w przypadku księgowania w księdze dla typu *Zakup, rozliczenie międzyokresowe* `IsTransferredIndetail`  to pole ma zawsze wartość *Podsumowanie* w transakcjach księgi podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="869bf-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="869bf-109">W związku z tym system utworzy powiązany wpis załącznika nawet wtedy, gdy kwota wynosi 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="869bf-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="869bf-110">Aby pominąć ten typ księgowania, gdy kwota wynosi 0 (zero), rozszerz metodę `subledgerJournalizer.markDoNotTransferEntries`, tak aby zawierała `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="869bf-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
