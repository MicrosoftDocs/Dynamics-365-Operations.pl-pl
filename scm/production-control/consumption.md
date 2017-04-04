---
title: "Obliczanie zużycia materiałów"
description: "Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 2225707329c67a30d9234bef5282d49834ea042a
ms.lasthandoff: 03/31/2017


---

# <a name="calculate-material-consumption"></a>Obliczanie zużycia materiałów

Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów. 

Następujące opcje, które odnoszą się do obliczania zużycia materiałów są dostępne na kartach **ustawienia** i **zużycie etapowe** na skróconej karcie **szczegóły wiersza** strony **BOM**.

## <a name="variable-and-constant-consumption"></a>Zużycie stałe i zmienne
W **zużycie jest** pola, można wybrać, czy zużycie powinna być obliczana jako ilość stała lub zmienna ilość. Wybierz **stałej** Jeśli stała ilość lub objętość jest potrzebna do produkcji, niezależnie od ilości, który jest produkowany. Wybierz **zmienne** (ustawienie domyślne), gdy wymagana ilość materiału do towarów gotowych jest proporcjonalna do liczby gotowych towarów, które są produkowane.

## <a name="calculating-consumption-from-a-formula"></a>Wzór do obliczania zużycia
W polu **formuła** można skonfigurować różne formuły do obliczania zużycia materiału. W przypadku korzystania z wartości domyślnej **Standardowa**, zużycie nie jest obliczana na podstawie formuły. Poniższe formuły współpracują z polami **wysokość**, **szerokość**, **głębokość**, **gęstość**, i **stała**:

-   Wysokość \*stała
-   Wysokość \*szerokość \*stała
-   Wysokość \*szerokość \*głębokość \*stała
-   (Wysokość \*szerokość \*głębokość / gęstość) \*Stała

## <a name="rounding-up-and-multiples"></a>Zaokrąglenie i wielokrotności
Razem pola **zaokrąglanie w górę** i **wielokrotności** umożliwiają zaokrąglanie w górę do wartości zużycia materiału. Można na przykład zaokrąglać wartości na podstawie jednostki załadunkowej, w której surowiec jest pobierany dla produkcji. Dostępne są następujące opcje w polu **zaokrąglanie w górę**: **ilość**, **miara** i **zużycie**.

### <a name="quantity"></a>Ilość

W przypadku wybrania opcji **ilość** jako mechanizmu zaokrąglenia w górę, ilość musi być wielokrotnością określonej ilości. Jeśli na przykład są wymagane liczby całkowite, wybierz **1** polu **Wielokrotność**. Liczby są następnie zaokrąglane w górę do ilości, która dzieli się przez 1.

### <a name="measurement"></a>Miara

Zazwyczaj, zaznacza się **miarę** jako mechanizm zaokrąglania w górę, gdy surowce są dostarczane w określonych wymiarach. Na przykład: do wyprodukowania gotowego towaru potrzeba 2-metrowej metalowej rury, ale rury są fabrycznie cięte na kawałki o długości 4,5 m. W takim przypadku **miary** mechanizm zaokrąglania w górę może być używany do obliczenia, ile metalowych rur potrzeba do wyprodukowania określonej liczby gotowego produktu. Na przykład **formuła** pole jest ustawione na **wysokość \*stałej**. **Wysokość** pole jest ustawione na **2** do wskazania długość rury, który jest wymagany do wyrobu gotowego. W polu **Wielokrotność** ustawiono opcję **4,5**, co wskazuje, że rura jest dostarczana w kawałkach o długości 4,5 m. Obliczenie ma następującą postać:

1.  Liczba wielokrotności, które są wymagane w przypadku 10 sztuk towaru gotowego: 10 / 2 = 5 sztuk
2.  Suma zużycia: 4.5 x 5 = 22,5 m rury metalowej

Oznacza to, że z każdych pięciu sztuk zużytej rury zostaje odpadek o długości 0,5 m.

### <a name="consumption"></a>Zużycie

Zazwyczaj wybiera się **Zużycie** jako mechanizm zaokrąglania, gdy surowiec musi być pobrany w określonej jednostce załadunkowej. Na przykład do wyprodukowania jednej sztuki towaru gotowego potrzeba 2 litrów farby, a jedna puszka farby zawiera 25 litrów. W takim przypadku mechanizm zaokrąglania w górę **Zużycia** pozwala na zaokrąglanie w górę do liczby całkowitej 25-litrowych puszek. Poniżej znajduje się obliczenie ilości farby wymaganej do wyprodukowania 180 sztuk towaru gotowego:

1.  Wymagana farba bez odpadków: 180 x 2 = 360 litrów
2.  Liczba puszek: 360 / 25 = 14,4, która jest zaokrąglana do 15
3.  Wymagana farba z uwzględnieniem odpadków: 15 x 25 = 375 litrów

## <a name="step-consumption"></a>Zużycie etapowe
Zużycie etapowe jest używane do obliczania zużycia stałego w interwałach ilości. Wybranie opcji **Zużycie etapowe** w polu **formuły** na karcie **ustawienia** umożliwia dodanie informacji o krokach na karcie **Zużycie etapowe**. Stała ilość zużytej ilości może być ustawiona w interwałach wyprodukowanej ilości. Na przykład Zużycie etapowe skonfigurowano jak pokazano w poniższej tabeli.

| Od serii | Ilość |
|-------------|----------|
| 0,00        | 10 0000  |
| 100,00      | 20 0000  |
| 200,00      | 40 0000  |

Ilość BOM wynosi 1, a ilość produkcji — 110. Formuła zużycia: Od serii (ilość) = zużycie. Ponieważ wielkość produkcji wynosi 110, należy do zakresu Od serii 100. Zatem ilość wynosi 20.


