---
title: "Rozliczanie płatności częściowej dostawcy przed datą rabatu z ostateczną datą płatności po dacie rabatu"
description: "Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele płatności częściowych — niektóre w okresie rabatu gotówkowego, a inne poza okresem rabatu gotówkowego."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 33851ff7c9ee2c50544589ade0191798a13706e7
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Rozliczanie płatności częściowej dostawcy przed datą rabatu z ostateczną datą płatności po dacie rabatu

[!include[banner](../includes/banner.md)]


Ten artykuł prowadzi przez scenariusz, w którym jest dokonywanych wiele płatności częściowych — niektóre w okresie rabatu gotówkowego, a inne poza okresem rabatu gotówkowego.

Firma Fabrikam nabywa towary od dostawcy 3057. Fabrikam otrzymuje rabat gotówkowy w wysokości 1%, jeśli faktura jest zapłacona w ciągu 14 dni. Faktury muszą zostać zapłacone w ciągu 30 dni. Dostawca oferuje też firmie Fabrikam rabaty gotówkowe za uregulowanie płatności. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z dostawcami**.

## <a name="invoice-on-june-25"></a>Faktura z 25 czerwca
25 czerwca April wprowadza i księguje fakturę na kwotę 1000,00 dla dostawcy 3057. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo   | Waluta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Faktura          | 6/25/2015 | 10020   |                                      | 1000,00                              | -1000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Częściowa płatność 2 lipca
2 lipca April chce zapłacić kwotę 300.00 z tej faktury. Taka płatność upoważnia do rabatu, ponieważ firma Fabrikam oferuje rabaty w przypadku częściowych płatności. Dlatego April płaci 297,00 i otrzymuje rabat w wysokości 3,00. Tworzy arkusz płatności i wprowadza wiersz dla dostawcy 3057. Następnie otwiera stronę **Rozliczenia transakcji**, aby oznaczyć fakturę do rozliczenia.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | -1000,00                      | USD      | -297,00          |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -3,00     |

Następnie April księguje płatność. Teraz saldo faktury wynosi 700,00. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Faktura          | 6/25/2015 | 10020   |                                      | 1000,00                              | -700,00 | USD      |
| APP-10020  | Płatność          | 7/1/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Rabat gotówkowy    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Pozostała płatność 15 lipca, użyj rabatu gotówkowego = zwykły
April płaci resztę faktury 15 lipca, czyli po okresie rabatu. Na stronie **Rozliczanie otwartych transakcji** nie są wyświetlane żadne kwoty w polu **Szacowany rabat gotówkowy**, a wartość w polu **Kwota rabatu gotówkowego** wynosi **0,00**. Gdy April płaci pozostałą kwotę 700,00, nie zostanie przyznany nowy rabat.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | -700,00                        | USD      | -700,00          |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**. April możne sprawdzić, czy rabat 3,00 został już wzięty.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 0,00      |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | -3,00     |
| Kwota rabatu gotówkowego do pobrania | 0,00      |

Następnie April księguje płatność. Gdy otwiera stronę **Transakcje dostawcy**, stwierdza, że faktura ma saldo 0,00. Stwierdza też, że istnieją dwie płatności. Jedna płatność na kwotę 297,00 z rabatem 3,00 i druga na kwotę 700,00.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Faktura          | 6/25/2015 | 10020   |                                      | 1000,00                              | 0,00    | USD      |
| APP-10020  | Płatność          | 7/1/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Rabat gotówkowy    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Płatność          | 7/15/2015 |         | 700.00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Pozostała płatność 15 lipca, użyj rabatu gotówkowego = zawsze
Jeśli dostawca oferuje April rabat mimo zapłacenia po dacie rabatu, może ona zmienić wartość w polu **Użyj rabatu gotówkowego** na **Zawsze**. Ustawienie **Oblicz rabaty gotówkowe dla częściowych zapłat** jest zastępowane i przyznawany jest rabat. Kwota płatności wynosi 693,00, a pozostałe 7,00 to rabat.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano | Zawsze            | Inv-10020 | 3057    | 6/25/2015 | 7/25/2015 | 10020   | 700.00                               |                                       | USD      | -693,00          |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 7,00      |
| Użyj rabatu gotówkowego            | Zawsze    |
| Pobrany rabat gotówkowy          | -3,00     |
| Kwota rabatu gotówkowego do pobrania | -7,00     |

Następnie April księguje płatność. Gdy otwiera stronę **Transakcje dostawcy**, stwierdza, że faktura ma saldo 0,00. Stwierdza też, że istnieją dwie płatności. Jedna płatność na kwotę 297,00 z rabatem 3,00 i druga na kwotę 693,00 i 7,00 rabatu.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Faktura          | 6/25/2015 | 10020   |                                      | 1000,00                              | 0,00    | USD      |
| APP-10020  | Płatność          | 7/1/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Rabat gotówkowy    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Płatność          | 7/15/2015 |         | 693.00                               |                                       | 0,00    | USD      |
| DISC-10021 | Rabat gotówkowy    | 7/15/2015 |         | 7,00                                 |                                       | 0,00    | USD      |






