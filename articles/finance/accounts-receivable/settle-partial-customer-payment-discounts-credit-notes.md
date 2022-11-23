---
title: Rozliczenie płatności częściowej odbiorcy, do której zastosowano rabaty na fakturach korygujących dostawcy
description: Ten artykuł prowadzi przez scenariusz, w którym rabat gotówkowy jest stosowany do faktury korygującej w sytuacji, gdy również oryginalna faktura miała rabat gotówkowy.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f64b9b9cd4fa65d17ba30fb87a688411becd5a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780558"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Rozliczenie płatności częściowej odbiorcy, do której zastosowano rabaty na fakturach korygujących dostawcy

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym rabat gotówkowy jest stosowany do faktury korygującej w sytuacji, gdy również oryginalna faktura miała rabat gotówkowy. 

Firma Fabrikam oferuje odbiorcom rabaty gotówkowe za częściowe zapłaty, a także za faktury korygujące. Rabat gotówkowy może zostać podjęty po wystawieniu faktury korygującej dla faktury, dla której odbiorca podjął już rabat gotówkowy. Zamiast oferowania kredytu na pełną kwotę można obciążyć saldo odbiorcy na kwotę, która nie obejmuje procenta rabatu gotówkowego podjętego przez odbiorcę. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="invoice-and-credit-note"></a>Faktura zwykła i faktura korygująca
Odbiorca 4035 ma fakturę na 1000,00 i fakturę korygującą na 100,00. Obie oferują 1 procent rabatu w przypadku zapłaty w ciągu 14 dni. Arnie może wyświetlić tę informację na stronie **Transakcje dostawcy**.

| Załącznik    | Typ transakcji | Data      | Faktura  | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Faktura          | 28/06/2020 | 10050    | 1,000.00                             |                                       | 1,000.00 | USD      |
| CCRN-10050 | Faktura korygująca      | 28/06/2020 | CR-10050 |                                      | 100.00                                | -100,00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Rozliczanie faktur korygujących z fakturą
Na stronie **Transakcje dostawcy** Arnie otwiera stronę **Rozliczenie transakcji**. Na stronie **Rozliczanie transakcji** Arnie może rozliczyć fakturę i fakturę korygującą. W ramach procesu rozliczania Arnie wyświetla daty i kwoty rabatu gotówkowego. Arnie zaznacza dwa dokumenty, a następnie klika **Księguj**, aby rozliczyć transakcje. Na fakturze korygującej jest rabat -1,00, ponieważ Fabrikam oferuje rabaty dla faktur korygujących.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik    | Konto | Data      | Data wymagalności  | Faktura  | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Wybrane | Normalna            | FTI-10050  | 4035    | 28/06/2020 | 28/07/2020 | 10050    | 1,000.00                       | USD      | 990.00           |
| Wybrane | Normalna            | CCRN-10050 | 4035    | 28/06/2020 | 28/07/2020 | CR-10050 | -100,00                        | USD      | -99,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.

- **Data rabatu**: 7/12/2020 
- **Kwota rabatu gotówkowego**: -1.00     
- **Użyj rabatu gotówkowego**: Normalne    
- **Pobrany rabat gotówkowy**: 0.00      
- **Kwota rabatu gotówkowego do pobrania**: -1.00     

Rozliczenie będzie miało wartość 100,00 i będzie obejmowało płatność 99,00 i rabat w wysokości 1,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
