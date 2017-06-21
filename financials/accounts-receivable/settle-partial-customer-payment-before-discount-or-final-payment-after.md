---
title: "Rozliczanie płatności częściowej odbiorcy przed datą rabatu z ostateczną datą płatności po dacie rabatu"
description: "W tym artykule omówiono wpływ rozliczania płatności za faktury dla odbiorców. Scenariusz koncentruje się na skutkach w księdze podrzędnej, a nie w księdze głównej."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4399cf66e423d2e6436c664e6485a77d9ad75d69
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="settle-a-partial-customer-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Rozliczanie płatności częściowej odbiorcy przed datą rabatu z ostateczną datą płatności po dacie rabatu

[!include[banner](../includes/banner.md)]


W tym artykule omówiono wpływ rozliczania płatności za faktury dla odbiorców. Scenariusz koncentruje się na skutkach w księdze podrzędnej, a nie w księdze głównej.

Firma Fabrikam sprzedaje towary odbiorcy 4027. Fabrikam oferuje rabat gotówkowy w wysokości 1%, jeśli faktura jest zapłacona w ciągu 14 dni. Faktury muszą zostać zapłacone w ciągu 30 dni. Fabrikam oferuje też rabaty gotówkowe za rozliczenia częściowe. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="invoice"></a>Faktura
25 czerwca Arnie wprowadza i księguje fakturę na kwotę 1000,00 dla odbiorcy 4027. Arnie może wyświetlić tę fakturę za pomocą przycisku **Transakcje** na stronie **Odbiorcy**.

| Załącznik   | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Faktura          | 6/25/2015 | 10020   | 1000,00                             |                                       | 1000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Częściowe rozliczenie przed zakończeniem pierwszego okresu rabatu gotówkowego
2 lipca odbiorca 4027 dokonuje częściowej płatności faktury na kwotę 297,00. Płatność uprawnia do podjęcia rabatu gotówkowego, ponieważ firma Fabrikam oferuje rabaty gotówkowe dla częściowych zapłat, a częściowa płatność zostanie dokonana w okresie rabatu gotówkowego. Dlatego odbiorca 4027 podejmuje rabat gotówkowy o wartości 3,00. Arnie rejestruje płatność dla odbiorcy 4027 za pomocą arkusza płatności. Arnie otwiera stronę **Rozliczenia transakcji**, aby oznaczyć fakturę do rozliczenia.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 1000,00                             | USD      | 297.00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**. Jeśli nie zmienisz wartości **Kwota do rozliczenia** na 297,00, wyświetlane wartości **Kwota rabatu gotówkowego** będą różne. Jednak wartość 3,00 będzie brana za wartość rabatu gotówkowego po zaksięgowaniu płatności, ponieważ rozliczenie automatycznie dostosowuje wartość **Kwota do rozliczenia**.

|                              |           |
|------------------------------|-----------|
| Data rabatu           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 3,00      |

Arnie księguje tę płatność. Teraz saldo faktury wynosi 700,00. Następujące transakcje są widoczne dla odbiorcy.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 6/25/2015 | 10020   | 1000,00                             |                                       | 700,00  | USD      |
| ARP-10020  |  Płatność         | 7/1/2015  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |  Rabat gotówkowy   | 7/1/2015  |         |                                      | 3,00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Pozostała płatność po okresie rabatu gotówkowego
11 lipca, po upływie okresu rabatu, odbiorca 4027 płaci resztę tej faktury. Na stronie **Rozliczanie otwartych transakcji** nie są wyświetlane żadne kwoty w polu **Szacowany rabat gotówkowy**, a wartość w polu **Kwota rabatu gotówkowego** wynosi **0,00**. Gdy odbiorca 4027 płaci pozostałą kwotę 700,00, nie jest podejmowany nowy rabat.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 700,00                               | USD      | 700,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 0,00      |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 3,00      |
| Kwota rabatu gotówkowego do pobrania | 0,00      |

Jeśli Arnie zmieni wartość w polu **Użyj rabatu gotówkowego** na **Zawsze**, ustawienie **Oblicz rabaty gotówkowe dla częściowych zapłat** jest zastępowane, a rabat gotówkowy jest podejmowany. Kwota płatności zmienia się na 693,00, a rabat gotówkowy to pozostałe 7,00.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano | Zawsze            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 700,00                               |                                       | USD      | 693,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 7,00      |
| Użyj rabatu gotówkowego            | Zawsze    |
| Pobrany rabat gotówkowy          | 3,00      |
| Kwota rabatu gotówkowego do pobrania | 7,00      |

Arnie zmienia wartość w polu **Użyj rabatu gotówkowego** z powrotem na **Normalny**, ponieważ nie zezwala temu odbiorcy na podjęcie pozostałego rabatu gotówkowego w kwocie 7.00. Następnie Arnie księguje płatność. Gdy Arnie otwiera stronę **Transakcje odbiorcy**, stwierdza, że faktura ma saldo 0,00. Stwierdza też, że istnieją dwie płatności. Jedna płatność na kwotę 297,00 z rabatem gotówkowym 3,00 i druga na kwotę 700,00.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Faktura          | 6/25/2015 | 10020   | 1000,00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 7/1/2015  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |                  | 7/1/2015  |         |                                      | 3,00                                  | 0,00    | USD      |
| ARP-10021  |                  | 7/11/2015 |         |                                      | 700,00                                | 0,00    | USD      |






