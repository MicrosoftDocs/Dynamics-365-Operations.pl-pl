---
title: Rabaty gotówkowe w przypadku nadpłat
description: Ten artykuł zawiera scenariusze pokazujące sposób obsługi płatności, gdy odbiorca ma rabat gotówkowy, a mimo to nawet nadpłaca.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7740d64166e08d9347ea4648b1fd3c60c6d6ee21
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232544"
---
# <a name="cash-discounts-for-overpayments"></a>Rabaty gotówkowe w przypadku nadpłat

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera scenariusze pokazujące sposób obsługi płatności, gdy odbiorca ma rabat gotówkowy, a mimo to nawet nadpłaca. 

Faktura jest uznawana za nadpłaconą, gdy kwota płatności jest większa niż kwota faktury pomniejszona o rabat gotówkowy. Aby określić sposób obsługi różnicy możliwego do uzyskania rabatu gotówkowego, jeśli faktura jest nadpłacona, użyj pól **Zarządzanie rabatami gotówkowymi** i **Maksymalna nadpłata lub niedopłata** na stronie **Parametry modułu rozrachunków z odbiorcami**. W poniższym przykładzie odbiorca nadpłacił fakturę o 0,50.

| Suma faktury | Dostępny rabat gotówkowy | Kwota do zapłaty po uwzględnieniu rabatu gotówkowego | Kwota rzeczywiście płacona przez odbiorcę |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00 zł        | 10,50 zł                   | 94,50 zł                                               | 95,00 zł                             |

## <a name="cash-discount-administration--specific"></a>Zarządzanie rabatem gotówkowym = Określone
Po wybraniu opcji **Określone** w polu **Zarządzanie rabatami gotówkowymi** na stronie **Konta dla transakcji automatycznych** pobierana jest pełna kwota rabatu gotówkowego. Kwota nadpłaty jest księgowana na koncie księgowym jako różnica rabatu gotówkowego lub pozostaje jako saldo na koncie odbiorcy. Zachowanie zależy od tego, czy kwota nadpłaty mieści się w przedziale między 0,00, a kwotą wprowadzoną w polu **Maksymalna nadpłata lub niedopłata** lub czy kwota nadpłaty jest wyższa od kwoty **Maksymalna nadpłata lub niedopłata**.

### <a name="scenario-1"></a>Scenariusz 1

W tym scenariuszu kwota nadpłaty mieści się między 0,00 a kwotą maksymalnej nadpłaty lub niedopłaty. Wprowadzana jest faktura na kwotę 105,00 z dostępnym rabatem gotówkowym, jeśli faktura zostanie zapłacona w ciągu 7 dni.

| Suma faktury | Dostępny rabat gotówkowy | Kwota do zapłaty po uwzględnieniu rabatu gotówkowego |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00 zł        | 10,50 zł                   | 94,50 zł                                               |

Odbiorca dokonuje płatności na kwotę 95,00 w okresie gwarantującym przyznanie rabatu gotówkowego. Płatność jest rozliczana na podstawie faktury na kwotę 105,00. Po rozliczeniu faktury i płatności następne transakcje dla odbiorcy są tworzone dla odbiorcy w module Rozrachunki z odbiorcami.

| Transakcja   | Kwota | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 zł | 0,00    |
| Płatność       | -95,00 | 0,00    |
| Rabat gotówkowy | -10,50 | 0,00    |

Poniższe zapisy księgowe są generowane dla płatności i rozliczeń. **Płatność**

| Konto             | Kwota debetu | Kwota kredytu |
|---------------------|--------------|---------------|
| Kasa                | 95,00 zł        |               |
| Rozrachunki z odbiorcami |              | 95,00 zł         |

**Rozliczenie**

| Konto                                                                                                          | Kwota debetu | Kwota kredytu |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Rabat gotówkowy (pole **Konto główne rabatów odbiorcy** na stronie **Rabat gotówkowy**)                 | 10,50 zł        |               |
| Rozrachunki z odbiorcami                                                                                              |              | 10,50 zł         |
| Rabat gotówkowy odbiorcy (pole **Rabat gotówkowy odbiorcy** na stronie **Konto dla transakcji automatycznych**) |              | 0.50          |
| Rozrachunki z odbiorcami                                                                                              | 0.50         |               |

### <a name="scenario-2"></a>Scenariusz 2

W tym scenariuszu kwota nadpłaty przekracza maksymalną wysokość nadpłaty lub niedopłaty. Wprowadzana jest faktura na kwotę 105,00 z dostępnym rabatem gotówkowym, jeśli faktura zostanie zapłacona w ciągu 7 dni.

| Suma faktury | Dostępny rabat gotówkowy | Kwota do zapłaty po uwzględnieniu rabatu gotówkowego |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00 zł        | 10,50 zł                   | 94,50 zł                                               |

Odbiorca dokonuje płatności na kwotę 95,00 w okresie gwarantującym przyznanie rabatu gotówkowego. Płatność jest rozliczana na podstawie faktury na kwotę 105,00. Po rozliczeniu faktury i płatności następne transakcje dla odbiorcy są tworzone dla odbiorcy w module Rozrachunki z odbiorcami.

| Transakcja   | Kwota | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 zł | 0,00    |
| Płatność       | -95,00 | -0,50   |
| Rabat gotówkowy | -10,50 | 0,00    |

Kwota nadpłaty w wysokości 0,50 pozostanie jako otwarte saldo płatności i można ją rozliczyć według innej faktury. Poniższe zapisy księgowe są generowane dla płatności i rozliczeń. **Płatność**

| Konto             | Kwota debetu | Kwota kredytu |
|---------------------|--------------|---------------|
| Kasa                | 95,00 zł        |               |
| Rozrachunki z odbiorcami |              | 95,00 zł         |

**Rozliczenie**

| Konto                                                                                          | Kwota debetu | Kwota kredytu |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Rabat gotówkowy (pole **Konto główne rabatów odbiorcy** na stronie **Rabat gotówkowy**) | 10,50 zł        |               |
| Rozrachunki z odbiorcami                                                                              |              | 10,50 zł         |

## <a name="cash-discount-administration--unspecific"></a>Zarządzanie rabatem gotówkowym = Nieokreślone
Po wybraniu opcji **Nieokreślone** w polu **Zarządzanie rabatami gotówkowymi** na stronie **Konta dla transakcji automatycznych** kwota rabatu gotówkowego jest redukowana przez kwotę nadpłaty. Zachowanie to stosowane jest zawsze, niezależnie od tego, czy kwota nadpłaty jest większa czy mniejsza od ilości wprowadzonej w polu **Maksymalna nadpłata lub niedopłata**.

### <a name="scenario-3"></a>Scenariusz 3

W tym scenariuszu wprowadzana jest faktura na kwotę 105,00 z dostępnym rabatem gotówkowym, jeśli faktura zostanie zapłacona w ciągu 7 dni.

| Suma faktury | Dostępny rabat gotówkowy | Kwota do zapłaty po uwzględnieniu rabatu gotówkowego |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00 zł        | 10,50 zł                   | 94,50 zł                                               |

Odbiorca dokonuje płatności na kwotę 95,00 w dniu gwarantującym przyznanie rabatu gotówkowego. Płatność jest rozliczana na podstawie faktury na kwotę 105,00. Po rozliczeniu faktury i płatności następne transakcje dla odbiorcy są tworzone dla odbiorcy w module Rozrachunki z odbiorcami.

| Transakcja   | Kwota | Saldo |
|---------------|--------|---------|
| Faktura       | 105,00 zł | 0,00    |
| Płatność       | -95,00 | -0,00   |
| Rabat gotówkowy | -10,00 | 0,00    |

Kwota rabatu gotówkowego zostanie zmniejszona z 10,50 do 10,00. Płatność i faktura są uznawane za rozliczone. **Płatność**

| Konto             | Kwota debetu | Kwota kredytu |
|---------------------|--------------|---------------|
| Kasa                | 95,00 zł        |               |
| Rozrachunki z odbiorcami |              | 95,00 zł         |

**Rozliczenie**

| Konto                                                                                          | Kwota debetu | Kwota kredytu |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Rabat gotówkowy (pole **Konto główne rabatów odbiorcy** na stronie **Rabat gotówkowy**) | 10,50 zł        |               |
| Rozrachunki z odbiorcami                                                                              |              | 10,50 zł         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]