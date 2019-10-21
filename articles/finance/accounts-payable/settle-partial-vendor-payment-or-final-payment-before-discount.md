---
title: Rozliczanie płatności częściowej i płatności ostatecznej dostawcy w całości przed datą rabatu
description: Ten artykuł prowadzi przez scenariusz, w którym są dokonywane częściowe płatności za fakturę od dostawcy z zastosowaniem rabatu gotówkowego.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d5961b2459a1c43cee24b611cf73879c6e776a4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179474"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Rozliczanie płatności częściowej i płatności ostatecznej dostawcy w całości przed datą rabatu

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym są dokonywane częściowe płatności za fakturę od dostawcy z zastosowaniem rabatu gotówkowego.

Fabrikam kupuje towary od dostawcy 3064 Dostawca udziela firmie Fabrikam rabatu gotówkowego w wysokości 1%, jeśli faktura zostanie zapłacona w ciągu 14 dni. Faktury muszą zostać zapłacone w ciągu 30 dni. Dostawca oferuje też firmie Fabrikam rabaty gotówkowe za uregulowanie płatności. Parametry rozliczenia znajdują się na stronie **Parametry modułu rozrachunków z dostawcami**. 25 czerwca April wprowadza fakturę na kwotę 1000,00 dla dostawcy 3064.

## <a name="vendor-invoice-on-june-25"></a>Faktura od dostawcy z 25 czerwca
25 czerwca April wprowadza i księguje fakturę na kwotę 1000,00 dla dostawcy 3064. April może wyświetlić tę transakcję na stronie **Transakcje dostawcy**.

| Załącznik   | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo   | Waluta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 6/25/2015 | 10010   |                                      | 1000,00                              | -1000,00 | USD      |

Na stronie **Dostawcy** April otwiera stronę **rozliczenia transakcji**. Użytkownik może użyć strony **Rozliczenia transakcji** w celu wyświetlenia daty i kwoty rabatów gotówkowych. Datą należności jest 25 lipca, a rabat gotówkowy w wysokości -10,00 jest dostępny, jeśli faktura zostanie zapłacona do 9 lipca.

| Zaznacz | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normalna            | Inv-10010 | 3064    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 990.00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -10,00    |

April klika kartę **Rabat gotówkowy**, aby wyświetlić kwotę rabatu.

| Data rabatu gotówkowego | Kwota rabatu gotówkowego | Kwota w walucie transakcji |
|--------------------|----------------------|--------------------------------|
| 7/9/2015           | 10,00                | 990,00                         |
| 7/25/2015          | 0,00                 | 1000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Płatność częściowa 1 lipca za pomocą strony Rozliczanie transakcji
April może utworzyć arkusz płatności dla tej płatności, otwierając stronę **Arkusz płatności** w module Rozrachunki z dostawcami. Tworzy nowy arkusz płatności i wprowadza wiersz dla dostawcy 3064. Następnie otwiera stronę **Rozliczenia transakcji**, aby oznaczyć fakturę do rozliczenia. April oznacza fakturę i zmienia wartość w polu **Kwota do rozliczenia** na **-500,00**. Stwierdza, że wartość w polu **Kwota rabatu gotówkowego** wynosi **-10,00** dla pełnej faktury, a wartość w polu **Kwota rabatu gotówkowego do pobrania** wynosi **-5,05**. April rozlicza więc dla tej faktury kwotę -505,05.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | -500,00          |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -5,05     |

April chce rozliczyć dokładnie pół faktury. Dlatego oznacza fakturę i zmienia wartość w polu **Kwota do rozliczenia** na **-495,00**. Łączna kwota, która jest rozliczana wynosi teraz 500,00. Ta kwota obejmuje -5,00 rabatu gotówkowego.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | -495,00          |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | -10,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -5,00     |

April zamyka stronę **Rozliczenie transakcji**. W arkuszu tworzony jest wiersz płatności na kwotę 495,00. Następnie April księguje ten arkusz. April można sprawdzić transakcje z dostawcą na stronie **Transakcji dostawcy**. Widzi, że faktura ma saldo o wartości -500,00. Widzi również płatność w wysokości 495,00 i rabat gotówkowy na kwotę 5,00.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Faktura          | 6/25/2015 | 10010   |                                      | 1000,00                              | -500,00 | USD      |
| APP-10010  | Płatność          | 7/1/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10010 | Rabat gotówkowy    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-amount-paid-on-july-8"></a>Pozostała kwota zapłacona 8 lipca
April płaci dostawcy 3064 resztę faktury 8 lipca, czyli po okresie rabatu gotówkowego. Tworzy arkusz płatności 8 lipca i oznacza transakcję do rozliczenia. Stwierdza, że kwota, która musi zostać rozliczona, wynosi 495.00. Wartość w polu **Szacowany rabat gotówkowy** wynosi **-5.00**, ponieważ poprzednio został podjęty rabat gotówkowy w wysokości 5,00.

|                         |        |
|-------------------------|--------|
| Łącznie oznaczono            | 495.00 |
| Szacowany rabat gotówkowy | -5,00  |

Informacja o zaznaczonej transakcji pojawia się na siatce na stronie **Rozliczanie otwartych transakcji**.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000,00                       | USD      | 495,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**.

|                              |           |
|------------------------------|-----------|
| Data rabatu gotówkowego           | 7/09/2015 |
| Kwota rabatu gotówkowego         | 10,00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 5,00      |
| Kwota rabatu gotówkowego do pobrania | 5,00      |

April księguje arkusz płatności i sprawdza transakcję dostawcy na stronie **Transakcje dostawcy**. Saldo faktury wynosi teraz 0,00 i April widzi dwie płatności i dwa rabaty gotówkowe.

| Załącznik    | Typ transakcji | Data      | Faktura | Kwota debetu w walucie transakcji | Kwota kredytu w walucie transakcji | Saldo | Waluta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Faktura          | 6/25/2015 | 10010   |                                      | 1000,00                              | 0,00    | USD      |
| APP-10010  |  Płatność         | 7/1/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10010 | Rabat gotówkowy    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10011  | Płatność          | 7/8/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10011 | Rabat gotówkowy    | 7/8/2015  |         | 5,00                                 |                                       | 0,00    | USD      |





