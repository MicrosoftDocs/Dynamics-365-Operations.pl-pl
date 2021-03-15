---
title: Obliczanie zużycia materiału
description: Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acccc677c855fc675d52814d7f6f0a5141bbc8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001680"
---
# <a name="calculate-material-consumption"></a>Obliczanie zużycia materiału

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów. 

Następujące opcje, które odnoszą się do obliczania zużycia materiałów są dostępne na kartach **ustawienia** i **zużycie etapowe** na skróconej karcie **szczegóły wiersza** strony **BOM**.

## <a name="variable-and-constant-consumption"></a>Zużycie stałe i zmienne
W polu **Zużycie jest** można określić, czy zużycie powinno być obliczane jako wartości stałe, czy zmienne. Wybierz opcję **Stała**, jeśli stała ilość lub objętość towaru jest potrzebna do produkcji, bez względu na ilość produkowanych pozycji. Wybierz **zmienne** (ustawienie domyślne), gdy wymagana ilość materiału do towarów gotowych jest proporcjonalna do liczby gotowych towarów, które są produkowane.

## <a name="calculating-consumption-from-a-formula"></a>Wzór do obliczania zużycia
W polu **formuła** można skonfigurować różne formuły do obliczania zużycia materiału. W przypadku korzystania z wartości domyślnej **Standardowa**, zużycie nie jest obliczana na podstawie formuły. Poniższe formuły współpracują z polami **wysokość**, **szerokość**, **głębokość**, **gęstość**, i **stała**:

-   Wysokość \* Stała
-   Wysokość \* Szerokość \* Stała
-   Wysokość \* Szerokość \* Długość \* Stała
-   (Wysokość \* Szerokość \* Długość/Gęstość) \* Stała

## <a name="rounding-up-and-multiples"></a>Zaokrąglenie i wielokrotności
Razem pola **zaokrąglanie w górę** i **wielokrotności** umożliwiają zaokrąglanie w górę do wartości zużycia materiału. Można na przykład zaokrąglać wartości na podstawie jednostki załadunkowej, w której surowiec jest pobierany dla produkcji. Dostępne są następujące opcje w polu **zaokrąglanie w górę**: **ilość**, **miara** i **zużycie**.

### <a name="quantity"></a>Ilość

W przypadku wybrania opcji **ilość** jako mechanizmu zaokrąglenia w górę, ilość musi być wielokrotnością określonej ilości. Jeśli na przykład są wymagane liczby całkowite, wybierz **1** polu **Wielokrotność**. Liczby są następnie zaokrąglane w górę do ilości, która dzieli się przez 1.

### <a name="measurement"></a>Miara

Zazwyczaj, zaznacza się **miarę** jako mechanizm zaokrąglania w górę, gdy surowce są dostarczane w określonych wymiarach. Na przykład: do wyprodukowania gotowego towaru potrzeba 2-metrowej metalowej rury, ale rury są fabrycznie cięte na kawałki o długości 4,5 m. W takim przypadku **miary** mechanizm zaokrąglania w górę może być używany do obliczenia, ile metalowych rur potrzeba do wyprodukowania określonej liczby gotowego produktu. W tym przykładzie pole **Formuła** jest ustawione jako **Wysokość \* Stała**. Pole **Wysokość** jest ustawione jako **2**, co wskazuje długość rury wymaganą dla towaru gotowego. W polu **Wielokrotność** ustawiono opcję **4,5**, co wskazuje, że rura jest dostarczana w kawałkach o długości 4,5 m. Obliczenie ma następującą postać:

1.  Liczba wielokrotności, które są wymagane w przypadku 10 sztuk towaru gotowego: 10 / 2 = 5 sztuk
2.  Suma zużycia: 4.5 x 5 = 22,5 m rury metalowej

Oznacza to, że z każdych pięciu sztuk zużytej rury zostaje odpadek o długości 0,5 m.

### <a name="consumption"></a>Zużycie

Zazwyczaj wybiera się **Zużycie** jako mechanizm zaokrąglania, gdy surowiec musi być pobrany w określonej jednostce załadunkowej. Na przykład do wyprodukowania jednej sztuki towaru gotowego potrzeba 2 litrów farby, a jedna puszka farby zawiera 25 litrów. W takim przypadku mechanizm zaokrąglania w górę **Zużycia** pozwala na zaokrąglanie w górę do liczby całkowitej 25-litrowych puszek. Poniżej znajduje się obliczenie ilości farby wymaganej do wyprodukowania 180 sztuk towaru gotowego:

1.  Wymagana farba bez odpadków: 180 x 2 = 360 litrów
2.  Liczba puszek: 360 / 25 = 14,4, która jest zaokrąglana do 15
3.  Wymagana farba z uwzględnieniem odpadków: 15 x 25 = 375 litrów

## <a name="step-consumption"></a>Zużycie etapowe
Zużycie etapowe jest używane do obliczania zużycia stałego w interwałach ilości. Jeżeli wybrano opcję **Zużycie etapowe** w polu **Formuła** na karcie **Ustawienia**, można dodać informacje o etapach na karcie **Zużycie etapowe**. Stałą zużywaną ilość można ustawić w interwałach produkowanej ilości. Na przykład Zużycie etapowe skonfigurowano jak pokazano w poniższej tabeli.

| Od serii | Ilość |
|-------------|----------|
| 0,00        | 10 0000  |
| 100,00      | 20 0000  |
| 200,00      | 40 0000  |

Ilość BOM wynosi 1, a ilość produkcji — 110. Formuła zużycia: Od serii (ilość) = zużycie. Ponieważ wielkość produkcji wynosi 110, należy do zakresu Od serii 100. Zatem ilość wynosi 20.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]