---
title: Rozlicz w całości płatności częściowe i końcowe przed datą rabatu
description: Ten artykuł zawiera scenariusze pokazujące metody rejestrowania częściowych płatności od odbiorcy oraz stosowania rabatów gotówkowych w trakcie okresu rabatu gotówkowego.
author: abruer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ac544c86804a54aaad5038e0c470095ee145346b337a5a66d5450562da2cffc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737168"
---
# <a name="settle-partial-and-final-payments-in-full-before-the-discount-date"></a>Rozlicz w całości płatności częściowe i końcowe przed datą rabatu

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera scenariusze pokazujące metody rejestrowania częściowych płatności od odbiorcy oraz stosowania rabatów gotówkowych w trakcie okresu rabatu gotówkowego.

Firma Fabrikam sprzedaje towary odbiorcy 4028. Fabrikam oferuje rabat gotówkowy w wysokości 1%, jeśli faktura jest zapłacona w ciągu 14 dni. Faktury muszą zostać zapłacone w ciągu 30 dni. Fabrikam oferuje też rabaty gotówkowe za rozliczenia częściowe. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z odbiorcami**.

## <a name="customer-invoice"></a>Faktura dla odbiorcy
25 czerwca Arnie wprowadza i księguje fakturę na kwotę 1000,00 dla odbiorcy 4028. Arnie może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo  | Waluta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Faktura          | 6/25/2015 | 10010   | 1000,00                             |                                       | 1000,00 | USD      |

Na stronie **Odbiorcy** lub **Transakcje odbiorcy** Arnie może otworzyć stronę **Rozlicz transakcje** w celu wyświetlenia daty i kwoty rabatów gotówkowych, które są dostępne dla faktury. Datą należności jest 25 lipca, a rabat gotówkowy w wysokości 10,00 jest dostępny, jeśli faktura zostanie zapłacona do 9 lipca.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 990,00           |

Informacje o rabacie dla oznaczonej faktury pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 10,00     |

Arnie klika kartę **Rabat gotówkowy**, aby wyświetlić kwotę rabatu.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 7/9/2015           | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1000,00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Płatność częściowa przy użyciu strony Wprowadzanie płatności odbiorcy
Odbiorca 4028 wysyła płatność w kwocie 500,00 w dniu 1 lipca. Aby wprowadzić tę płatność, Arnie nie klika pozycji **Wiersze**. Zamiast tego Arnie rejestruje płatność, tworząc nowy arkusz płatności, a następnie otwierając stronę **Wprowadzanie płatności odbiorcy**. Arnie wprowadza informacje o płatności i oznacza wprowadzoną fakturę. Gdy Arnie wprowadza **500,00** jako kwotę, wprowadza także **500,00** w polu **Kwota do zapłaty** w siatce. Ponieważ Fabrikam zezwala na stosowanie rabatu gotówkowego do płatności częściowych, Arnie zauważa, że zostanie także uwzględniony częściowy rabat gotówkowy w wysokości 5,05. Wzór do obliczeń dla tego rabatu: 500,00 ÷ 0,99 x 0,01 = 5,05. (W tych obliczeniach kwota 500,00 jest dzielona przez 0,99, ponieważ rabat wynosi 1%. W związku z tym odbiorca płaci 99 procent faktury. Wynik jest następnie mnożony przez procent rabatu, który wynosi 1% lub 0,01. Jeśli odbiorca skorzysta z rabatu w pełnej wysokości 10,00, kwotą, która musi zostać rozliczona, będzie 990,00). Informacja o rabacie zostanie wyświetlona w siatce w dolnej części strony **Wprowadzanie płatności odbiorcy**.

| Kwota rabatu gotówkowego do pobrania | Pobrany rabat gotówkowy | Kwota do zapłaty |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Płatność częściowa za pomocą wierszy arkusza
Zamiast otwierania strony **Wprowadzanie płatności odbiorcy** w arkuszu płatności Arnie może kliknąć **Wiersze** w celu wprowadzenia płatności. Zostanie wyświetlony arkusz płatności, w którym Arnie może wprowadzić wiersz dla odbiorcy 4028. Arnie otwiera stronę **Rozliczenia transakcji**, dzięki czemu Arnie może oznaczyć fakturę do rozliczenia. Arnie oznacza fakturę i zmienia wartość w polu **Kwota do rozliczenia** na **500,00**. Arnie stwierdza, że wartość w polu **Kwota rabatu gotówkowego** wynosi **10,00** dla pełnej faktury, a wartość w polu **Kwota rabatu gotówkowego do pobrania** wynosi **5,05**. Arnie rozlicza więc dla tej faktury kwotę 505,05.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 500,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 5,05      |

Jeśli odbiorca chce rozliczyć dokładnie pół faktury, przesyła płatność w wysokości 495,00. W takim przypadku Arnie wprowadza **49500** w polu **kwota do rozliczenia**. Rabat gotówkowy w wysokości 5,00 również zostanie pobrany, tak aby łączna kwota rozliczenia wyniosła 500,00.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 495,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 5,00      |

Arnie zamyka stronę **Rozliczenie transakcji**. W arkuszu tworzony jest wiersz płatności na kwotę 495,00. Następnie Arnie księguje ten arkusz. Arnie może wyświetlić transakcję odbiorcy na stronie **Transakcje odbiorcy**. Na tej stronie Arnie widzi, że faktura ma saldo 500,00. Arnie widzi również płatność w wysokości 495,00 i rabat na kwotę 5,00.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Faktura          | 6/25/2015 | 10010   | 1000,00                             |                                       | 500,00  | USD      |
| ARP-10010  |  Płatność         | 7/1/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 |  Rabat gotówkowy   | 7/1/2015  |         |                                      | 5,00                                  | 0,00    | USD      |

## <a name="payment-for-the-remaining-amount"></a>Płatność pozostałej kwoty
Odbiorca 4028 zapłacił pozostałą kwotę 495,00 8 lipca, czyli w okresie rabatu gotówkowego. Arnie tworzy arkusz płatności 8 lipca i oznacza transakcję do rozliczenia. Arnie stwierdza, że kwota, która musi zostać rozliczona, wynosi 495,00. Wartość w polu **Szacowany rabat gotówkowy** wynosi **5,00**, ponieważ poprzednio został podjęty rabat gotówkowy w wysokości 5,00.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| Łącznie oznaczono            | 495,00 |
| Szacowany rabat gotówkowy | 5,00   |

Informacja o zaznaczonej transakcji pojawia się na siatce na stronie **Rozliczanie otwartych transakcji**.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 495,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 5,00      |
| Kwota rabatu gotówkowego do pobrania | 5,00      |

Arnie księguje arkusz i sprawdza transakcję odbiorcy na stronie **Transakcje odbiorcy**. Saldo faktury wynosi teraz 0,00 i Arnie widzi dwie płatności i dwa rabaty gotówkowe.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Faktura          | 6/25/2015 | 10010   | 1000,00                             |                                       | 0,00    | USD      |
| ARP-10010  | Płatność          | 7/1/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 | Rabat gotówkowy    | 7/1/2015  |         |                                      | 5,00                                  | 0,00    | USD      |
| ARP-10011  | Płatność          | 7/8/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10011 | Rabat gotówkowy    | 7/8/2015  |         |                                      | 5,00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]