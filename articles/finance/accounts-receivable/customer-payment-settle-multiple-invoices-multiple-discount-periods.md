---
title: Użyj jednej płatności do rozliczenia faktur obejmujących wiele okresów rabatowych
description: W tym temacie przedstawiono sposób zapłaty wielu faktur, gdy każda faktura kwalifikuje się do rabatu gotówkowego. Scenariusze w tym artykule pokazują różnice w stosowanych rabatach gotówkowych zależnie od dnia uregulowania płatności.
author: ShivamPandey-msft
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5187835da33d729e50aad9c813d8753d240fb81
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727630"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>Użyj jednej płatności do rozliczenia faktur obejmujących wiele okresów rabatowych

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono sposób zapłaty wielu faktur, gdy każda faktura kwalifikuje się do rabatu gotówkowego. Scenariusze w tym artykule pokazują różnice w stosowanych rabatach gotówkowych zależnie od dnia uregulowania płatności.

Firma Fabrikam sprzedaje towary odbiorcy 4032. Fabrikam oferuje rabat gotówkowy w wysokości 1%, jeśli faktura jest zapłacona w ciągu 14 dni. Fabrikam oferuje też rabaty gotówkowe za rozliczenia częściowe. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="invoices"></a>Faktury
Odbiorca 4032 ma trzy faktury na łączną kwotę 3,000.00:

-   Faktura FTI-10040 na 1000,00, została wprowadzona 15 maja. Do tej faktury przysługuje rabat gotówkowy w wysokości 1%,jeśli zostanie zapłacona w ciągu 14 dni.
-   Faktura FTI-10041 na 1000,00, została wprowadzona 25 czerwca. Do tej faktury przysługuje rabat gotówkowy w wysokości 1%,jeśli zostanie zapłacona w ciągu 14 dni.
-   Faktura FTI-10042 na 1000,00, została wprowadzona 25 czerwca. Do tej faktury przysługuje rabat gotówkowy w wysokości 2%,jeśli zostanie zapłacona w ciągu 5 dni, i 1%, jeśli zostanie zapłacona w ciągu 14 dni.

## <a name="settle-all-invoices-on-june-29"></a>Rozlicz wszystkie faktury 29 czerwca
Jeśli Arnie tworzy arkusz płatności, aby w pełni rozliczyć te faktury 29 czerwca, płatność wynosi 2970,00. Suma wszystkich kwot wynosi 30,00. Arnie tworzy płatność dla odbiorcy 4032, a następnie otwiera stronę **rozliczenia transakcji**. Na stronie **rozliczenia transakcji** oznacza wszystkie wiersze trzech faktur do rozliczenia:

-   Płatności za fakturę FTI 10040 wynosi 1,000.00. Rabat gotówkowy nie został pobrany.
-   Płatności za fakturę FTI-10041 wynosi 990.00. Został pobrany rabat gotówkowy w wysokości 1% lub 10,00.
-   Płatności za fakturę FTI-10042 wynosi 980.00. Został pobrany rabat gotówkowy w wysokości 2% lub 20,00.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano                 | Normalna            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000,00                             |                                       | USD      | 1000,00         |
| Wybrano                 | Normalna            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000,00                             |                                       | USD      | 990,00           |
| Zaznaczone i wyróżnione | Normalna            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000,00                             |                                       | USD      | 980,00           |

Po zaksięgowaniu płatności saldo odbiorcy wynosi 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Rozlicz wszystkie faktury 1 lipca
Jeśli Arnie tworzy arkusz płatności, aby w pełni rozliczyć te faktury 1 lipca, płatność wynosi 2980,00. Arnie tworzy płatność dla odbiorcy 4032, a następnie otwiera stronę **rozliczenia transakcji**. Na stronie **rozliczenia transakcji** oznacza wszystkie wiersze trzech faktur do rozliczenia:

-   Płatności za fakturę FTI 10040 wynosi 1,000.00. Rabat gotówkowy nie został pobrany.
-   Płatności za fakturę FTI-10041 wynosi 990.00. Został pobrany rabat gotówkowy w wysokości 1% lub 10,00.
-   Płatności za fakturę FTI-10042 wynosi 990,00. Został pobrany rabat gotówkowy w wysokości 1% lub 10,00. 1 lipca wypada po zakończeniu okresu kwalifikującego się do rabatu 2%, ale mieści się w okresie uprawniającym do pobrania 1% rabatu.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano                 | Normalna            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000,00                             |                                       | USD      | 1000,00         |
| Wybrano                 | Normalna            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000,00                             |                                       | USD      | 990,00           |
| Zaznaczone i wyróżnione | Normalna            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000,00                             |                                       | USD      | 990,00           |

## <a name="partial-settlement-on-june-29"></a>Rozliczenie częściowe 29 czerwca
Odbiorca 4032 może zapłacić kwotę częściową, np. połowę każdej faktury. Arnie tworzy płatność dla odbiorcy 4032, a następnie otwiera stronę **rozliczenia transakcji**. Na stronie **rozliczenia transakcji** Arnie oznacza wszystkie wiersze trzech faktur do rozliczenia. W każdym wierszu Arnie wprowadza kwotę do rozliczenia, zgodnie z instrukcjami odbiorcy. Gdy Arnie zaznacza wiersz, Arnie widzi kwotę rabatu dla tego wiersza i pobraną kwotę rabatu gotówkowego. Ponieważ odbiorca płaci pół faktury, Arnie widzi, że wartość w polu **kwoty rabatu gotówkowego** dla faktury FTI 10042 wynosi **20,00**, ale wartość w polu **pobrany rabat gotówkowy** wynosi **10,00**. Kwota płatności wynosi 1485,00.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Wybrano                 | Normalna            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000,00                             |                                       | USD      | 500,00           |
| Wybrano                 | Normalna            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000,00                             |                                       | USD      | 495,00           |
| Zaznaczone i wyróżnione | Normalna            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000,00                             |                                       | USD      | 490,00           |

Arnie może także wprowadzić ręcznie kwotę płatności 1485,00, zanim otworzy stronę **Rozlicz transakcje**. Jeśli Arnie ręcznie wprowadzi kwotę płatności, a następnie oznaczy wszystkie trzy transakcje, ale nie zmieni wartości w polu **Kwota do rozliczenia** dla każdej transakcji, po zamknięciu strony Arnie zobaczy następujący komunikat:

> Suma z zaznaczonych transakcji jest różna od kwoty arkusza. Czy zmienić kwotę arkusza?

Jeśli Arnie chce, aby kwota płatności wynosiła tylko 1485,00, Arnie klika **Nie**, a następnie księguje arkusz. Transakcje są rozliczane w następujący sposób:

1.  Faktura FTI-10040 jest całkowicie rozliczona na kwotę 1,000,00, ponieważ została wprowadzona 15 maja i jest najstarszą fakturą. Rabat gotówkowy nie został pobrany. Pozostała kwota transakcji płatności wynosi 485,00.
2.  Faktura FTI-10041 nie jest w ogóle rozliczona. Faktury FTI-10041 i FTI 10042 zostały wprowadzone w tym samym dniu. Dla faktury FTI 10041 przysługuje 1% rabatu, a dla faktury FTI 10042 przysługuje 2-procentowy rabat. Ponieważ większy rabat przysługuje za fakturę FTI 10042, pozostała kwota 485,00 jest rozliczana za pomocą faktury FTI 10042.
3.  Faktura FTI-10042 jest rozliczana z pozostałą kwotą 485.00. Firma Fabrikam oferuje zniżki częściowe. W takim przypadku rabat wynosi 9,90 (= 485,00 ÷ 0.98 × 0,02). Kwota (485,00) jest dzielona przez 0,98, ponieważ występuje 2% rabatu (w związku z tym, odbiorca płaci 98 procent faktury). Wynik jest następnie mnożony przez procent rabatu, który wynosi 2%. Płatność 485,00 z rabatem z 9,90 jest równa 494,90. Kwota oryginalnej faktury to 1,000.00. Z tego względu transakcja ma saldo 505,10 (= 1000,00 - 494,90).

Arnie wyświetla informacje na stronie **Transakcje dostawcy**.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Faktura          | 5/15/2015 | 10040   | 1000,00                             |                                       | 0,00     | USD      |
| FTI-10041  | Faktura          | 6/25/2015 | 10041   | 1000,00                             |                                       | 1000,00 | USD      |
| FTI-10042  | Faktura          | 6/25/2015 | 10042   | 1000,00                             |                                       | 505,10   | USD      |
| ARP-10040  | Płatność          | 6/29/2015 |         |                                      | 1485,00                              | 0,00     | USD      |
| DISC-10040 | Rabat gotówkowy    | 6/29/2015 |         |                                      | 9,90                                  | 0,00     | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
