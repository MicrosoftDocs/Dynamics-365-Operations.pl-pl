---
title: "Rozliczenie płatności częściowej odbiorcy, która ma wiele okresów rabatu"
description: "W tym artykule przedstawiono sposób rozliczania częściowych płatności od odbiorców w przypadku istnienia wielu okresów rabatu."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 048a4ca44d457849e2f632da1686dfbeb81dd61b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Rozliczenie płatności częściowej odbiorcy, która ma wiele okresów rabatu

[!include[banner](../includes/banner.md)]


W tym artykule przedstawiono sposób rozliczania częściowych płatności od odbiorców w przypadku istnienia wielu okresów rabatu.

Fabrikam oferuje odbiorcy 4031 dwa okresy rabatu gotówkowego. Odbiorca otrzymuje 2-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 5 dni, i 1-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 14 dni. Fabrikam oferuje też rabaty gotówkowe za rozliczenia częściowe. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="invoice"></a>Faktura
25 czerwca Arnie wprowadza i księguje fakturę na kwotę 1.000,00 dla odbiorcy 4031. Gdy sprawdza rabaty gotówkowe dla tej faktury, widzi, że odbiorca 4031 może otrzymać rabat w wysokości 20,00, jeśli zapłaci fakturę do 30 czerwca. Jeśli faktura zostanie zapłacona do 9 lipca, odbiorca otrzyma rabat w wysokości 10,00.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 6/30/2015          | 20,00                | 980,00                         |
| 7/9/2015           | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1000,00                       |

Arnie może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Faktura          | 6/25/2015 | 10030   | 1000,00                             |                                       | 1000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Częściowe rozliczenie przed zakończeniem pierwszego okresu rabatu gotówkowego
28 czerwca Odbiorca 4031 dokonuje częściowego rozliczenia w wysokości 294,00. Ponieważ 28 czerwca mieści się w pierwszym okresie rabatu gotówkowego, odbiorca podejmuje rabat o wartości 6,00. Na stronie **Rozliczenia transakcji** wartość **Kwota rabatu gotówkowego** wynosi 20,00 a wartość **Kwota rabatu gotówkowego do pobrania** wynosi 6,00.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10030 | 4031    | 6/25/2015 | 7/25/2015 | 10030   | 1000,00                       | USD      | 294,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**. Jeśli nie zmienisz wartości **Kwota do rozliczenia** na **294,00**, wyświetlane wartości **Kwota rabatu gotówkowego** będą różne. Jednak wartość 6,00 będzie brana za wartość rabatu gotówkowego po zaksięgowaniu płatności, ponieważ rozliczenie automatycznie dostosowuje wartość **Kwota do rozliczenia**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 6/30/2015 |
| Kwota rabatu gotówkowego         | 20,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 6,00      |

Po zaksięgowaniu płatności saldo faktury wynosi 700,00.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Częściowe rozliczenie przed zakończeniem drugiego okresu rabatu gotówkowego
8 lipca odbiorca płaci pozostałą kwotę faktury. Podejmuje rabat w wysokości 7.00 (% 1), ponieważ dokonano płatności w ramach drugiego okresu rabatu gotówkowego.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10030 | 4031    | 6/25/2015 | 7/25/2015 | 10030   | 700,00                               |                                       | USD      | 693,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 30,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 6,00      |
| Kwota rabatu gotówkowego do pobrania | 7,00      |

Saldo faktury wynosi teraz 0,00. Arnie wyświetla informacje na stronie **Transakcje dostawcy**.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Faktura          | 6/25/2015 | 10030   | 1000,00                             |                                       | 0,00    | USD      |
| ARP 10030  |  Płatność         | 6/28/2015 |         |                                      | 294,00                                | 0,00    | USD      |
| DISC-10030 |  Rabat gotówkowy   | 6/28/2015 |         |                                      | 6,00                                  | 0,00    | USD      |
| ARP-10031  |  Płatność         | 7/8/2015  |         |                                      | 693,00                                | 0,00    | USD      |
| DISC-1031  |  Rabat gotówkowy   | 7/8/2015  |         |                                      | 7,00                                  | 0,00    | USD      |






