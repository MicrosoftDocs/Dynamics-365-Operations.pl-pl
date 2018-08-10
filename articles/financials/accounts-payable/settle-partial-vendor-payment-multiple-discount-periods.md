---
title: "Rozliczenie płatności częściowej dostawcy, która ma wiele okresów rabatu"
description: "Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele częściowych płatności do dostawcy oferującego wiele różnych rabatów gotówkowych."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d88630a62cfdebf0daf19d3bb6af7fcc6e877876
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Rozliczenie płatności częściowej dostawcy, która ma wiele okresów rabatu

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele częściowych płatności do dostawcy oferującego wiele różnych rabatów gotówkowych. 

Dostawca 3054 oferuje firmie Fabrikam 2-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 5 dni, i 1-procentowy rabat gotówkowy w przypadku zapłacenia faktury w ciągu 14 dni.

## <a name="invoice"></a>Faktura
28 czerwca April tworzy fakturę na kwotę 1000,00 dla dostawcy 3054. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo   | Waluta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 6/28/2015 | 10060   |                                      | 1000,00                              | -1000,00 | USD      |

Następujące daty rabatu gotówkowego i kwoty są dostępne dla tej faktury.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 7/3/2015           | 20,00                | 980,00                         |
| 7/12/2015          | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1000,00                       |

## <a name="payment-on-july-2"></a>Płatność 2 lipca
2 lipca April chce zapłacić 300,00 dla tej faktury. Tworzy jednorazową płatność na stronie **Arkusz płatności** w module Rozrachunki z dostawcami. Dodaje wiersz dla dostawcy 3054 i wprowadza kwotę płatności **300.00**. April otwiera stronę **rozliczenia transakcji**, aby oznaczyć fakturę, która zostanie rozliczona. Zmienia wartość w polu **Kwota do rozliczenia** na **300,00** i zauważa, że wartość w polu **Kwota rabatu gotówkowego do pobrania** zmieniła się na **6,12**. Ponieważ ta płatność zostanie dokonana w pierwszym okresie rabatu, zostanie pobrany rabat w wysokości 2%.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1000,00                       | USD      | 300,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/02/2015 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -6.12     |

Ponieważ rabat gotówkowy jest dostępny, April chce zmienić kwotę płatności, tak aby łączna rozliczona kwota wynosiła 300.00 zarówno dla płatności, jak i rabatu gotówkowego. Zmienia wartość w polu **Kwota do rozliczenia** na **294,00** i zauważa, że wartość w polu **Kwota rabatu gotówkowego do pobrania** zmieniła się na **6,00**.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1000,00                       | USD      | 294,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/02/2015 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -6,00     |

Następnie April księguje płatność. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**. Stwierdza, że kwota 300,00 została uwzględnione na fakturze. Ta kwota obejmuje 6,00 rabatu gotówkowego. Dlatego pozostałe wynosi 700,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1000,00                              | -700,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Płatność 8 lipca
8 lipca April dokonuje kolejnej płatności za fakturę. W celu wprowadzenia kwoty otwiera stronę **Rozlicz transakcje**, a następnie klika kartę **Rabat gotówkowy**. Widzi daty i kwoty dla dwóch dostępnych rabatów gotówkowych. Ponieważ ta płatność zostanie dokonana w drugim okresie rabatu, zostanie pobrany rabat w wysokości 1%. To kwota jest obliczana jako pół 1-procentowego rabatu na 1000,00 lub pół z 10,00.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 7/3/2015           | 20,00                | 680,00                         |
| 7/12/2015          | 10,00                | 690,00                         |
| 7/25/2015          | 0,00                 | 700,00                         |

April decyduje się zapłacić 495,00 i pobrać 5,00 rabatu gotówkowego. Łączna kwota, która jest rozliczana wynosi teraz 500,00.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10060 | 3054    | 6/28/2015 | 7/28/2015 | 10060   | 1000,00                       | USD      | 495,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/12/2015 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | -6,00     |
| Kwota rabatu gotówkowego do pobrania | -5,00     |

Na stronie **transakcji dostawcy** April widzi, że nowe saldo ma wartość 200,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1000,00                              | -200,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2015 |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Płatność 20 lipca
W dniu 20 lipca April tworzy ostatnią płatność na kwotę 200,00. Rabat gotówkowy nie jest pobierany, ponieważ płatność przypada po obu datach rabatu. Saldo faktury wynosi teraz 0,00.

| Załącznik    | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2015 | 10060   |                                      | 1000,00                              | -200,00 | USD      |
| APP-10060  | 7/2/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2015 |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10062  | 7/20/2015 |         | 200,00                               |                                       | 0,00    | USD      |






