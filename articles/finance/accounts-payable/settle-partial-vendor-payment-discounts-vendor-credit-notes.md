---
title: Rozliczanie częściowej płatności dla dostawcy, do której zastosowano rabaty na fakturach korygujących
description: Ten artykuł prowadzi przez scenariusz, w którym faktura korygująca jest rozliczana względem faktury.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
ms.openlocfilehash: b926d94059fb12b143b9c9b4b5c04cb7f39f8e99
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715945"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>Rozliczanie częściowej płatności dla dostawcy, do której zastosowano rabaty na fakturach korygujących

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym faktura korygująca jest rozliczana względem faktury.

Dostawcy firmy Fabrikam dają rabaty gotówkowe na fakturach korygujących. Dostawca 3050 daje firmie Fabrikam rabat gotówkowy w wysokości 1%, jeżeli faktura zostanie opłacona w ciągu 14 dni.

## <a name="invoice-and-credit-memo"></a>Faktura i nota kredytowa
29 czerwca April tworzy fakturę na kwotę 1000,00 dla dostawcy 3050. 2 lipca tworzy fakturę korygującą na 200,00. Na stronie **Dostawcy** April otwiera stronę **rozliczenia transakcji**. Na stronie **rozliczenia transakcji** może zaznaczyć do rozliczenia zarówno fakturę korygującą, jak i fakturę. Rabat w wysokości 2,00 jest wliczony do faktury korygującej. W związku z tym łączna wartość faktury korygującej jest zmniejszona do 198,00.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano                 | Normalna            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070   | -1000,00                      | USD      | -990,00          |
| Zaznaczone i wyróżnione | Normalna            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 |         | 200,00                         | USD      | 198,00           |

Informacje o rabacie na fakturze korygującej pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 7/13/2015 |
| Kwota rabatu gotówkowego         | 2.00      |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 2,00      |

April klika przycisk **Księguj**. Następnie sprawdza zakończone rozliczenie. April widzi, że została zastosowana kwota 198,00 faktury korygującej i uwzględniono 2,00 rabatu. Dlatego suma wynosi 200,00.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura  | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Zaznaczone i wyróżnione | Normalna            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070    | -1000,00                      | USD      | -200,00          |
| Wybrano                 | Normalna            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

April może przejrzeć transakcje dostawcy na stronie **transakcji dostawcy**, wybierając dostawcę na stronie **wszystkich dostawców**, a następnie klikając w okienku akcji pozycję **transakcje**. Na tej stronie April widzi, że faktura ma saldo -800,00. Widzi również fakturę korygującą na 198,00 i rabat 2,00.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Faktura          | 6/29/2015 | 10070   |                                      | 1000,00                              | -800,00 | USD      |
| Inv-10071  |                  | 7/2/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| DISC-10071 |  Rabat gotówkowy   | 7/2/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| DISC-10071 |  Rabat gotówkowy   | 7/2/2015  |         |                                      | 2,00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
