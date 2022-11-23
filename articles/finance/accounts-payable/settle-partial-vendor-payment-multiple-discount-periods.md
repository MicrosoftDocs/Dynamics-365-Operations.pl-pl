---
title: Rozliczenie płatności częściowej dostawcy, która ma wiele okresów rabatu
description: Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele częściowych płatności do dostawcy oferującego wiele różnych rabatów gotówkowych.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da69d61c657ddc168a27a97fe16909d5f60eb4fd
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778045"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Rozliczenie płatności częściowej dostawcy, która ma wiele okresów rabatu

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele częściowych płatności do dostawcy oferującego wiele różnych rabatów gotówkowych. 

Dostawca 3054 oferuje firmie Fabrikam 2-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 5 dni, i 1-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 14 dni.

## <a name="invoice"></a>Faktura
28 czerwca April tworzy fakturę na kwotę 1000,00 dla dostawcy 3054. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo   | Waluta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 28/06/2020 | 10060   |                                      | 1,000.00                              | -1000,00 | USD      |

Następujące daty rabatu gotówkowego i kwoty są dostępne dla tej faktury.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 3/07/2020           | 20.00                | 980.00                         |
| 12/07/2020          | 10,00                | 990.00                         |
| 25/07/2020          | 0,00                 | 1,000.00                       |

## <a name="payment-on-july-2"></a>Płatność 2 lipca
2 lipca April chce zapłacić 300,00 dla tej faktury. Tworzy jednorazową płatność na stronie **Arkusz płatności** w module Rozrachunki z dostawcami. Dodaje wiersz dla dostawcy 3054 i wprowadza kwotę płatności **300.00**. April otwiera stronę **rozliczenia transakcji**, aby oznaczyć fakturę, która zostanie rozliczona. Zmienia wartość w polu **Kwota do rozliczenia** na **300,00** i zauważa, że wartość w polu **Kwota rabatu gotówkowego do pobrania** zmieniła się na **6,12**. Ponieważ ta płatność zostanie dokonana w pierwszym okresie rabatu, zostanie pobrany rabat w wysokości 2%.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 28/06/2020 | 28/07/2020 | 10060   | 1,000.00                       | USD      | 300,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 2/07/2020 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -6.12     |

Ponieważ rabat gotówkowy jest dostępny, April chce zmienić kwotę płatności, tak aby łączna rozliczona kwota wynosiła 300.00 zarówno dla płatności, jak i rabatu gotówkowego. Zmienia wartość w polu **Kwota do rozliczenia** na **294,00** i zauważa, że wartość w polu **Kwota rabatu gotówkowego do pobrania** zmieniła się na **6,00**.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 28/06/2020 | 28/07/2020 | 10060   | 1,000.00                       | USD      | 294,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 2/07/2020 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -6,00     |

Następnie April księguje płatność. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**. Stwierdza, że kwota 300,00 została uwzględnione na fakturze. Ta kwota obejmuje 6,00 rabatu gotówkowego. Dlatego pozostałe wynosi 700,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/06/2020 | 10060   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10060  | 2/07/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/07/2020  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Płatność 8 lipca
8 lipca April dokonuje kolejnej płatności za fakturę. W celu wprowadzenia kwoty otwiera stronę **Rozlicz transakcje**, a następnie klika kartę **Rabat gotówkowy**. Widzi daty i kwoty dla dwóch dostępnych rabatów gotówkowych. Ponieważ ta płatność zostanie dokonana w drugim okresie rabatu, zostanie pobrany rabat w wysokości 1%. To kwota jest obliczana jako pół 1-procentowego rabatu na 1000,00 lub pół z 10,00.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 3/07/2020           | 20.00                | 680,00                         |
| 12/07/2020          | 10,00                | 690,00                         |
| 25/07/2020          | 0,00                 | 700,00                         |

April decyduje się zapłacić 495,00 i pobrać 5,00 rabatu gotówkowego. Łączna kwota, która jest rozliczana wynosi teraz 500,00.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 28/06/2020 | 28/07/2020 | 10060   | 1,000.00                       | USD      | 495.00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 12/07/2020 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | -6,00     |
| Kwota rabatu gotówkowego do pobrania | -5,00     |

Na stronie **transakcji dostawcy** April widzi, że nowe saldo ma wartość 200,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/06/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 2/07/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/07/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/07/2020 |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/07/2020 |         | 5.00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Płatność 20 lipca
W dniu 20 lipca April tworzy ostatnią płatność na kwotę 200,00. Rabat gotówkowy nie jest pobierany, ponieważ płatność przypada po obu datach rabatu. Saldo faktury wynosi teraz 0,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/06/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 2/07/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/07/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/07/2020 |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/07/2020 |         | 5.00                                 |                                       | 0,00    | USD      |
| APP-10062  | 20/07/2020 |         | 200.00                               |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
