---
title: Przeszacowanie waluty w konsolidowanej firmie
description: W tym temacie opisano sposób przeszacowania waluty w konsolidowanej firmie.
author: roschlom
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81de31ee75b4be38256505bc7b875dc15473c75a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212236"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Przeszacowanie waluty w konsolidowanej firmie

[!include [banner](../includes/banner.md)]

Podczas konsolidowania danych z jednej waluty rozliczeniowej do innej należy wykonać przeszacowanie waluty, jeśli nastąpiła zmiana kursów wymiany, tak aby salda kont zostały poprawnie przeszacowane. Podczas pierwszej konsolidacji danych użyj karty **przeliczania waluty**, aby wybrać początkowe kursy wymiany do przeszacowania podczas procesu konsolidacji. Po wprowadzeniu nowego kursu wymiany (na przykład w kolejnym miesiącu) można przeszacować salda konta. Niezrealizowane dodatnie różnice kursowe zostaną odpowiednio zaktualizowane na podstawie nowego kursu wymiany i daty. Poniższy przykład ilustruje zapisy księgowe utworzone podczas tego procesu.

## <a name="company-setup"></a>Konfiguracja firmy
-   **Źródło/ firma (USMF)** — jako waluta raportowania i księgowania używane są dolary amerykańskie (USD).
-   **Konsolidowana firma (CON)** — jako waluta raportowania i księgowania używane jest euro (EUR).
    -   **Zrealizowana dodatnia różnica kursowa** — konto księgowe 801500
    -   **Zrealizowana ujemna różnica kursowa** — konto księgowe 801600
    -   **Niezrealizowana dodatnia różnica kursowa**— konto księgowe 801600
    -   **Niezrealizowana ujemna różnica kursowa**— konto księgowe 801400

## <a name="original-transactions"></a>Oryginalne transakcje
### <a name="cash-receipt-transactions-in-usmf"></a>Transakcje za pomocą blankietów kasowych w USMF

| Data       | Konto księgowe               | Waluta | Kwota |
|------------|------------------------------|----------|--------|
| 10/11/2015 | 110110 – Kasa                | USD      | 500    |
| 10/11/2015 | 130100 – Rozrachunki z odbiorcami | USD      | -500   |

## <a name="exchange-rates"></a>Kursy wymiany

| Z waluty | Na walutę | Data początkowa | Kurs wymiany |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 10/1/2015  | 200           |
| EUR           | USD         | 11/1/2015  | 150           |
| EUR           | USD         | 12/1/2012  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>Wykonywanie konsolidacji dla października 2015
### <a name="balances-in-the-consolidation-company"></a>Salda w konsolidowanej firmie

| Konto księgowe | Waluta | Kwota | Obliczanie    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 USD × 50%  |
| 130100         | EUR      | -250   | -500 USD × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 30 listopada 2015 roku.
### <a name="balances-in-the-consolidation-company"></a>Salda w konsolidowanej firmie

| Konto księgowe | Waluta | Kwota  | Obliczanie                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333.33  | Pierwotna kwota 500 × 66.6667%  |
| 130100         | EUR      | -333.33 | Pierwotna kwota -500 × 66.6667% |
| 801400         | EUR      | 83.33   | 333.33 – 250                       |
| 801600         | EUR      | -83.33  | -333.33 – (-250)                   |

Zobaczysz dodatkowe transakcje dla kwot w walucie raportowania.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>Wykonaj przeszacowanie w walucie dla kont od 1 października 2015 do 31 grudnia 2015 roku.
### <a name="balances-in-the-consolidation-company"></a>Salda w konsolidowanej firmie

| Konto księgowe | Waluta | Kwota  | Obliczanie                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Pierwotna kwota 500 × 1                           |
| 130100         | EUR      | -500,00 | Pierwotna kwota -500 × 1%                          |
| 801400         | EUR      | 250     | 500 – 333.33 = 166.67 166.67 + 83.33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]