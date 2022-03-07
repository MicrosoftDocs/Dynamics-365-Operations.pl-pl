---
title: Amortyzacja ręczna
description: Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja ręczna.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5b62bbdd5d745bc9d0745cc6fa6d6e8034a61e3
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674834"
---
# <a name="manual-depreciation"></a>Amortyzacja ręczna

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja ręczna.

Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu opcji **Ręczna** w polu **Metoda** na stronie **Profile amortyzacji**, amortyzacja środków trwałych przypisanych do tego profilu amortyzacji jest określana przez wartości procentowe wprowadzone dla poszczególnych interwałów w roku kalendarzowym. Interwały, dla których zostały ustawione wartości procentowe, są księgowane na podstawie wartości wybranej w polu **Częstotliwość okresu** na skróconej karcie **Ogólne** na stronie **Profile amortyzacji**. Można wybrać następujące wartości:

- Co rok
- Miesięczne
- Kwartalna
- Półrocznie
- Dziennie

Po wybraniu częstotliwości okresu kliknij opcję **Planowanie ręczne** i ustaw wartości procentowe dla poszczególnych interwałów księgowania. Harmonogramy ręczne i interwały księgowania razem określają kwotę amortyzacji, co pokazano w poniższych przykładach w tym artykule. Amortyzacja ręczna jest zawsze obliczana jako wartość procentowa ceny nabycia. W przypadku amortyzacji ręcznej suma wartości procentowych wprowadzonych w interwałach amortyzacji nie musi wynosić 100%. Amortyzacja ręczna jest to elastyczna metoda amortyzacji, która jest zwykle używana do definiowania dodatkowego profilu amortyzacji na stronie **Księga**, jak np. amortyzacji nieokresowej dla celów specjalnych (np. podatkowych).

## <a name="examples"></a>Przykłady
Cena nabycia: 11,000.00 oczekiwana wartość likwidacji: 1,000.00. W poniższej tabeli przedstawiono interwały i wartości procentowe określane na stronie **Plany amortyzacji środków trwałych dla profilów**.

| Numer zakresu | Wartość procentowa |
|-----------------|------------|
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa               | 10,00      |
| 2               | 50,00      |
| 3               | 8.00       |

W poniższej tabeli pokazano sposób obliczania amortyzacji dla każdego interwału.

|  Numer zakresu | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa netto na koniec interwału |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1 przypada na wpłatę z zysku na rzecz budżetu państwa                | (11,000 – 1,000) × 10% = 1,000                | 10,000 (11,000 – 1,000)                   |
| 2                | (11,000 – 1,000) × 50% = 5,000                | 5,000 (10,000 – 5,000)                    |
| 3                | (11,000 – 1,000) × 8% = 800                   | 4,200 (5,000 – 800)                       |

Jeśli w polu **Częstotliwość okresu** wybierzesz opcję **Miesięcznie**, ustawisz 12 interwałów harmonogramu ręcznego. W poniższej tabeli przedstawiono kwoty amortyzacji dla pierwszych dwóch interwałów.

| Interwał | Kwota amortyzacji            |
|----------|--------------------------------|
| Styczeń  | (11,000 – 1,000) × 10% = 1,000 |
| Luty | (11,000 – 1,000) × 50% = 5,000 |

Jeśli w polu *<strong><em>Częstotliwość okresu</em>*</strong> wybierzesz opcję <strong>Półrocznie</strong>, ustawisz 2 interwały harmonogramu ręcznego. W poniższej tabeli przedstawiono kwoty amortyzacji dla tych dwóch interwałów.

| Interwał    | Kwota amortyzacji            |
|-------------|--------------------------------|
| 30 czerwca     | (11,000 – 1,000) × 10% = 1,000 |
| 31 grudnia | (11,000 – 1,000) × 50% = 5,000 |

Suma wartości procentowych dla wszystkich interwałów nie musi być równa 100. Jednakże wyświetlany jest komunikat, jeśli wartość w polu **Suma wartości procentowych** na stronie **Plany amortyzacji środków trwałych dla profilów** nie jest równa **100**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
