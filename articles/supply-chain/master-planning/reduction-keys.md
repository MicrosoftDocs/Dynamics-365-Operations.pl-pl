---
title: Klucze redukcji
description: "Ten artykuł zawiera przykłady pokazujące konfigurowanie klucza redukcji. Zawiera informacje o różnych ustawieniach kluczy redukcji i wynikach ich zastosowania. Za pomocą klucza redukcji można określić sposób zmniejszania prognozowanych zapotrzebowań."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 30634b0af343ad171c385a95c4ba0934180f70cf
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="reduction-keys"></a>Klucze redukcji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera przykłady pokazujące konfigurowanie klucza redukcji. Zawiera informacje o różnych ustawieniach kluczy redukcji i wynikach ich zastosowania. Za pomocą klucza redukcji można określić sposób zmniejszania prognozowanych zapotrzebowań.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Przykład 1: Procent — zasada redukcji prognozy klucza redukcji
---------------------------------------------------------------

W tym przykładzie pokazano, jak klucz redukcji zmniejsza wymagania dotyczące prognozy popytu według wartości procentowych i okresów, które są definiowane według klucza redukcji.

1.  Na stronie **Klucz redukcji** ustaw następujące wiersze.
    | Reszta | Jednostka  | Procent |
    |--------|-------|---------|
    | 1 przypada na wpłatę z zysku na rzecz budżetu państwa      | Miesiąc | 100     |
    | 2      | Miesiąc | 75      |
    | 3      | Miesiąc | 50      |
    | 4      | Miesiąc | 25      |

2.  Połącz klucz redukcji z grupą zapotrzebowania dla towaru.
3.  Na stronie **Plany główne** w polu **Reguła redukcji** zaznacz **Procent — klucz redukcji**.
4.  Utwórz prognozę redukcji dla 1000 szt. na miesiąc.

Uruchomienie planowania w dniu 1 stycznia spowoduje, że wymagania prognozy popytu zostaną zużyte według wartości procentowych ustawionych na stronie **Klucze redukcji**. Następujące ilości wymagania są przenoszone do planu głównego.

| Miesiąc                | Wymagana liczba sztuk |
|----------------------|---------------------------|
| Styczeń              | 0                         |
| Luty             | 250                       |
| Marzec                | 500                       |
| kwiecień                | 750                       |
| Od maja do grudnia | 1 000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Przykład 2: Transakcja — zasada redukcji prognozy klucza redukcji
W tym przykładzie pokazano, jak rzeczywiste zamówienia występujące w okresach zdefiniowanych przez klucz redukują wymagania prognozy popytu.

-   Na stronie **Plany główne** w polu **Reguła redukcji** zaznacz **Transakcje — klucz redukcji**.

1 stycznia istnieją następujące zamówienia sprzedaży.

| Miesiąc    | Zamówiona liczba sztuk |
|----------|--------------------------|
| Styczeń  | 956                      |
| Luty | 1,176                    |
| Marzec    | 451                      |
| Kwiecień    | 119                      |

Przy tej samej prognozie popytu dla 1000 sztuk na miesiąc do planu głównego przesyłane są następujące ilości wymagania.

| Miesiąc                | Wymagana liczba sztuk |
|----------------------|---------------------------|
| Styczeń              | 44                        |
| Luty             | 0                         |
| Marzec                | 549                       |
| kwiecień                | 881                       |
| Od maja do grudnia | 1 000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Przykład 3: Transakcja — zasada redukcji prognozy okresu dynamicznego
W większości przypadków systemy są skonfigurowane tak, aby transakcje zmniejszały prognozy popytu w określonych okresach prognozy: tygodnie, miesiąca itd. Te okresy są definiowane w kluczu redukcji. Jednak czas między dwoma wierszami popytu mogą również *implikować* okresu.

1.  Utwórz prognozę popytu dla następujących dat i ilości.
    | Data       | Prognoza popytu |
    |------------|-----------------|
    | 1 stycznia  | 1 000           |
    | 5 stycznia  | 500             |
    | 12 stycznia | 1 000           |

    W tej prognozie wyraźnie widać okres między datami prognozy: między pierwszą i drugą datą są 4 dni, a między drugą i trzecią jest 7 dni. Te różne zakresy to są okresy dynamiczne.
2.  Utwórz wiersze zamówienia sprzedaży w następujący sposób.
    | Data                             | Ilość dla zamówienia sprzedaży |
    |----------------------------------|----------------------|
    | 15 grudnia w poprzednim roku | 500                  |
    | 3 stycznia                        | 100                  |
    | 10 stycznia                       | 200                  |

Prognoza będzie ograniczona w następujący sposób:

-   Pierwsze zamówienie sprzedaży nie mieści się w żadnym okresie, więc nie będzie ograniczona przez żadną prognozę.
-   Drugie zamówienie sprzedaży mieści się w dniach 1-5 stycznia, więc ograniczy prognozę dla 1 stycznia o 100.
-   Trzecie zamówienie sprzedaży mieści się w dniach 5-12 stycznia, więc ograniczy prognozę dla 5 stycznia o 200.

Zostanie utworzone następujące planowane zamówienie w celu wypełnienia prognozy.

| Data prognozy popytu | Zmniejszona ilość |
|----------------------|------------------|
| 1 stycznia            | 900              |
| 5 stycznia            | 300              |
| 12 stycznia           | 1 000            |

Poniżej przedstawiono podsumowanie redukcji **transakcji — okres dynamiczny**:

-   Wymagania prognozy są ograniczone przez rzeczywiste transakcje zamówienia występujące w okresie dynamicznym. Okres dynamiczny obejmuje aktualne daty prognozy i kończy się na początku kolejnej prognozy.
-   Ta metoda nie używa ani nie wymaga klucza redukcji.
-   Ta opcja jest używana, występują następujące zachowania:
    -   Jeśli prognoza zostanie zmniejszona do zera, wymagania prognozy dla bieżącej prognozy przybierają wartość 0 (zero).
    -   Jeśli nie ma żadnej przyszłej prognozy, wymagania prognozy z ostatnio wprowadzonej prognozy są redukowane.
    -   Horyzonty czasowe są uwzględniane w obliczeniach redukcji prognozy.
    -   Dni pasywne są uwzględniane w obliczeniach redukcji prognozy.
    -   Jeśli transakcje rzeczywistego zamówienia przekraczają prognozowane zapotrzebowanie, pozostałe transakcje nie są przekazywane do następnego okresu prognozy.


<a name="see-also"></a>Informacje dodatkowe
--------

[Plany główne](master-plans.md)




