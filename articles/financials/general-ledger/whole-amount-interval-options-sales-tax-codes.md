---
title: Opcje Cała kwota i Obliczanie interwału dla kodów podatku
description: W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d16ea19a6d3cfea325281f301e0502bb051381d9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "344071"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Opcje Cała kwota i Obliczanie interwału dla kodów podatku

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

W tym artykule opisano opcje dostępne w polu Metoda obliczania w ustawieniach kodów podatków oraz wyjaśniono sposób obliczania podatku dla interwałów kwot i całych kwot.

można skonfigurować kod podatku, który ma być obliczany na podstawie jednej całej kwoty lub kwoty interwału. Na stronie Kody podatków użyj pola Metoda obliczania na karcie skróconej Obliczanie, aby wybrać, jak ma być obliczany kod podatku.
- Cała kwota — stawka podatku jest stosowana do całej kwoty opodatkowanej.
- Interwał — kwota opodatkowana jest dzielona na części, z których każda mieści się w zakresie o określonej stawce podatku. Część tej kwoty należąca do danego interwału jest opodatkowana według stawki podatku określonej dla tego interwału. Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.
  > [!NOTE]                                                                                                                              
  > Opcja Interwał jest dostępna tylko po wybraniu opcji Wiersz w polu Obliczanie w obszarze Podatek na stronie Parametry księgi głównej. 

Interwały są konfigurowane na stronie Wartości kodu podatku poprzez wprowadzanie kwot Minimalna i Maksymalna dla stawki podatkowej. Aby podatki były obliczane dla wszystkich kwot opodatkowanych — niezależnie od wyboru metody obliczania — interwały muszą podlegać następującym regułom:
-   Pierwszy interwał musi mieć Minimalny limit zero.
-   Ostatni interwał musi mieć Maksymalny limit zero, który oznacza nieskończoność.
-   Maksymalny limit interwału musi być Minimalnym limitem następnego interwału.

Jeśli kwota jest równa Maksymalnemu limitowi poprzedniego interwału i Minimalnemu limitowi następnego interwału, stosowany jest do niej podatek pierwszego interwału. Jeśli kwota nie należy do żadnego z interwałów określonych przez górne i dolne limity, stosowana jest stawka podatku równa 0.

## <a name="example-whole-amount-method-of-calculation"></a>Przykład: Metoda obliczania wg całej kwoty
Na stronie Wartości kodu podatku stawki podatku są skonfigurowane przy użyciu następujących interwałów:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Dolny limit** | **Maksymalny limit** | **Stawka podatku** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Podatek jest obliczany według pełnej stawki opodatkowania.

| Kwota opodatkowana (cena) | Obliczenie    | Podatek |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | 10,50 zł     |
| 50,00                  | 50,00 \* 0,30  | 15,00     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a> Przykład: Metoda obliczania wg interwału
Na stronie Wartości stawki podatku są skonfigurowane przy użyciu następujących interwałów:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Dolny limit** | **Maksymalny limit** | **Stawka podatku** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Podatek jest sumą kwot podatku obliczonych dla poszczególnych interwałów kwoty.

| Kwota opodatkowana (cena) | Obliczenie                                                               | Podatek |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | 10,50 zł     |
| 50,00                  | 50,00 \* 0,30                                                             | 15,00     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45,50     |



Aby uzyskać więcej informacji, zobacz [Ustalanie stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md).





