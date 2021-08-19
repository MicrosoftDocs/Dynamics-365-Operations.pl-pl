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
ms.openlocfilehash: 304609e065389d4f56913ae3f2f7fc562de2eadc9f0885ddbe2c8f4747081c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722182"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>Rozliczenia międzyokresowe zakupu, które mają zerową kwotę, są księgowane dla przyjęcia produktów o wartości zerowej

Numer artykułu z bazy wiedzy: 4612588

## <a name="symptoms"></a>Objawy

Po zaksięgowaniu przyjęcia produktów, które ma wartość zerową, system tworzy księgowanie międzyokresowe zakupu, w którym kwota wynosi 0 (zero).

## <a name="resolution"></a>Rozdzielczość

Domyślnie w przypadku księgowania w księdze dla typu *Zakup, rozliczenie międzyokresowe* `IsTransferredIndetail`  to pole ma zawsze wartość *Podsumowanie* w transakcjach księgi podrzędnej. W związku z tym system utworzy powiązany wpis załącznika nawet wtedy, gdy kwota wynosi 0 (zero).

Aby pominąć ten typ księgowania, gdy kwota wynosi 0 (zero), rozszerz metodę `subledgerJournalizer.markDoNotTransferEntries`, tak aby zawierała `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, jak pokazano w poniższym przykładzie.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
