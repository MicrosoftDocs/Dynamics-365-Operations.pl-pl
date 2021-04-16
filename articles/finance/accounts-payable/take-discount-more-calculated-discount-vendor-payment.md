---
title: Weź więcej niż obliczony rabat na płatność dostawcy
description: Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze. Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810253"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>Weź więcej niż obliczony rabat na płatność dostawcy

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez scenariusz, w którym do kwoty jest stosowany rabat gotówkowy większy niż rabat pierwotnie dostępny na fakturze. Taki scenariusz może wystąpić, jeśli organizacja zawrze z dostawcą umowę, aby zapłacić kwotę mniejszą niż podana na fakturze. 

Dostawca 3051 daje firmie Fabrikam rabat gotówkowy w wysokości 4%, jeżeli faktura zostanie opłacona w ciągu 7 dni. 29 czerwca April wprowadza fakturę na kwotę 1000,00. Dostawca zgadza się na przyznanie rabatu w wysokości 60,00 zamiast kwoty 40,00 dostępnej dla tej faktury. April rejestruje jednorazową płatność za pomocą arkusza płatności rozrachunków z dostawcami. Wprowadza dostawcę dla płatności, a następnie otwiera stronę **Rozliczanie transakcji**. Oznacza fakturę i zmienia wartość w polu **Kwota rabatu gotówkowego** na **-60,00**.

| Zaznacz     | Użyj rabatu gotówkowego | Załącznik   | Konto | Data      | Data wymagalności  | Faktura | Kwota w walucie transakcji | Waluta | Kwota do rozliczenia |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Wybrano | Normalna            | Inv-10040 | 3051    | 6/29/2015 | 7/29/2015 | 10040   | 1000,00                       | USD      | 940,00           |

Informacje o rabacie pojawiają się w dolnej części strony **Rozliczanie transakcji**.

| Pole                        | Wartość     |
|------------------------------|-----------|
| Data rabatu           | 7/12/2015 |
| Kwota rabatu gotówkowego         | 60.00     |
| Użyj rabatu gotówkowego            | Normalna    |
| Pobrany rabat gotówkowy          | 0,00      |
| Kwota rabatu gotówkowego do pobrania | 60,00     |

Następnie April arkusz płatności. Faktura jest całkowicie rozliczona przy użyciu płatności 940,00 i rabatu 60,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]