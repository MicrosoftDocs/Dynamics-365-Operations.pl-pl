---
title: Zastosowanie rabatu gotówkowego poza okresem rabatu gotówkowego
description: Ten artykuł zawiera dwa scenariusze pokazujące stosowanie rabatu gotówkowego nawet w przypadku, gdy płatność jest dokonywana poza okresem rabatu gotówkowego.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780596"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Zastosowanie rabatu gotówkowego poza okresem rabatu gotówkowego

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera dwa scenariusze pokazujące stosowanie rabatu gotówkowego nawet w przypadku, gdy płatność jest dokonywana poza okresem rabatu gotówkowego.

28 czerwca April tworzy fakturę na kwotę 2000,00 dla dostawcy 3052. Faktura ma rabat gotówkowy w wysokości 1%, jeśli faktura jest zapłacona w ciągu 14 dni.

## <a name="use-cash-discount-option--always"></a>Użyj opcji rabatu gotówkowego = Zawsze
April tworzy płatność 1 lipca — po dacie rabatu. April otwiera stronę **Rozliczenia transakcji**, aby wyświetlić transakcje, które można rozliczyć. 

Oznacza fakturę do płatności. Rabat gotówkowy nie jest pobierany, ponieważ płatność przypada po dacie rabatu. Jednak dostawca wyraził zgodę na zastosowanie przez April z rabatu gotówkowego mimo to. Zatem April zmienia wartość w polu **Użyj rabatu gotówkowego** na **Zawsze**.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data rabatu gotówkowego | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Wybrane | Zawsze            | Inv-10030 | 3052    | 28/06/2020          | 12/07/2020 | 10030   | -2000,00                      | USD      | -1980,00        |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 12/07/2020 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Zawsze    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Data używana do obliczania rabatów = Wybrana data
Po zaksięgowaniu faktury i płatności rabat gotówkowego nadal może zostać pobrany, gdy transakcje są rozliczone na stronie **Rozliczenia transakcji**. April zmienia wartość w polu **Data używana do obliczania rabatów** na **Wybrana data**. Następnie wprowadza datę czerwca 28, która znajduje się w okresie rabatu gotówkowego dla faktury. Ta data jest używana do obliczania rabatu gotówkowego dla transakcji. Na stronie **Rozliczanie otwartych transakcji** April widzi, że domyślnie pojawia się pełny rabat w wysokości 20,00. Wiersz faktury wskazuje, że kwota do rozliczenia wynosi 1980,00.

| Zaznacz          | Użyj rabatu gotówkowego | Załącznik   | Konto | Data rabatu gotówkowego | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Zaznaczone i wyróżnione | Normalna    | Inv-10030 | 3052    | 28/06/2020         | 12/07/2020 | 10030   | -2000,00                      | USD      | -1980,00        |
| Wybrane                 | Normalna    | APP-10030 | 3052    | 15/07/2020          | 15/07/2020 |         | 500.00                         | USD      | 500.00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**. Kwota pobranego rabatu gotówkowego wynosi 20.00, ponieważ kwota do rozliczenia dla faktury jest wartością domyślną: 1,980.00.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 12/07/2020 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -20,00    |

April zmienia wartość w polu **Kwota do rozliczenia** na **500.00**. Wartość w polu **Kwota rabatu gotówkowego do pobrania** zostaje obliczona jako **5.05**.

| Zaznacz                     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Zaznaczone i wyróżnione | Normalna            | Inv-10030 | 3052    | 28/06/2020 | 12/07/2020 | 10030   | 2,000.00                       | USD      | -500,00          |
| Wybrane                 | Normalna            | APP-10030 | 3052    | 15/07/2020 | 15/07/2020 |         | 500.00                         | USD      | 500.00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie otwartych transakcji**. Wartość w polu **Kwota rabatu gotówkowego do pobrania** wynosi **5,05**, ponieważ kwota do rozliczenia dla faktury została zmieniona na kwotę płatności, 500,00.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 12/07/2020 |
| Kwota rabatu gotówkowego         | -20,00    |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
