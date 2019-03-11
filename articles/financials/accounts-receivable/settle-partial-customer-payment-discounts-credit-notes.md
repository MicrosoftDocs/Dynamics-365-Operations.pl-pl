---
title: Rozliczenie płatności częściowej odbiorcy, do której zastosowano rabaty na fakturach korygujących dostawcy
description: Ten artykuł prowadzi przez scenariusz, w którym rabat gotówkowy jest stosowany do faktury korygującej w sytuacji, gdy również oryginalna faktura miała rabat gotówkowy.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa641f996d1ee516f588fcd1520bdc23d5d25f86
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "333445"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Rozliczenie płatności częściowej odbiorcy, do której zastosowano rabaty na fakturach korygujących dostawcy

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym rabat gotówkowy jest stosowany do faktury korygującej w sytuacji, gdy również oryginalna faktura miała rabat gotówkowy. 

Firma Fabrikam oferuje odbiorcom rabaty gotówkowe za częściowe zapłaty, a także za faktury korygujące. Rabat gotówkowy może zostać podjęty po wystawieniu faktury korygującej dla faktury, dla której odbiorca podjął już rabat gotówkowy. Zamiast oferowania kredytu na pełną kwotę można obciążyć saldo odbiorcy na kwotę, która nie obejmuje procenta rabatu gotówkowego podjętego przez odbiorcę. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="invoice-and-credit-note"></a>Faktura zwykła i faktura korygująca
Odbiorca 4035 ma fakturę na 1000,00 i fakturę korygującą na 100,00. Obie oferują 1 procent rabatu w przypadku zapłaty w ciągu 14 dni. Arnie może wyświetlić tę informację na stronie **Transakcje dostawcy**.

| Załącznik    | Typ transakcji | Data      | Faktura  | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Faktura          | 6/28/2015 | 10050    | 1000,00                             |                                       | 1000,00 | USD      |
| CCRN-10050 | Faktura korygująca      | 6/28/2015 | CR-10050 |                                      | 100,00                                | -100,00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Rozliczanie faktur korygujących z fakturą
Na stronie **Transakcje dostawcy** Arnie otwiera stronę **Rozliczenie transakcji**. Na stronie **Rozliczanie transakcji** może rozliczyć fakturę i fakturę korygującą. W ramach procesu rozliczania wyświetla daty i kwoty rabatu gotówkowego. Zaznacza dwa dokumenty, a następnie klika **Księguj**, aby rozliczyć transakcje. Na fakturze korygującej jest rabat -1,00, ponieważ Fabrikam oferuje rabaty dla faktur korygujących.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik    | Konto | Data      | Data wymagalności  | Faktura  | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10050  | 4035    | 6/28/2015 | 7/28/2015 | 10050    | 1000,00                       | USD      | 990,00           |
| Wybrano | Normalna            | CCRN-10050 | 4035    | 6/28/2015 | 7/28/2015 | CR-10050 | -100,00                        | USD      | -99,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/12/2015 |
| Kwota rabatu gotówkowego         | -1,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -1,00     |

Rozliczenie będzie miało wartość 100,00 i będzie obejmowało płatność 99,00 i rabat w wysokości 1,00.



