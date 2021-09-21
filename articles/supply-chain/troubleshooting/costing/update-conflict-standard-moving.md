---
title: Konflikt aktualizacji, gdy metodą inwentaryzacji zapasów jest koszt standardowy lub średnia ruchoma
description: Konflikt aktualizacji występuje, gdy metodą inwentaryzacji zapasów jest koszt standardowy lub średnia ruchoma
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477338"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Konflikt aktualizacji występuje, gdy metodą inwentaryzacji zapasów jest koszt standardowy lub średnia ruchoma

## <a name="symptoms"></a>Objawy

Podczas równoległego księgowania dokumentów, takich jak arkusze magazynowe, faktury zamówień zakupu lub faktury zamówień sprzedaży, w celu uzyskania skalowalności i wydajności, może zostać wyświetlony komunikat o błędzie informujący o konflikcie aktualizacji i niektóre dokumenty mogą nie zostać zaksięgowane. Ten problem występuje, gdy metodą inwentaryzacji zapasów jest *Koszt standardowy* lub *Średnia ruchoma*. Obie te metody są metodami kosztów ciągłych. Innymi słowy, ostateczny koszt jest określony w momencie księgowania.

Jeśli jest stosowana metoda *Średnia ruchoma*, komunikat o błędzie przypomina ten przykład:

> Wartość zapasów xx,xx nie jest oczekiwana po obliczeniu proporcjonalnych wydatków

Jeśli jest stosowana metoda *Koszt standardowy*, komunikat o błędzie przypomina ten przykład:

> Koszt standardowy jest niezgodny z wartością zapasów finansowych po aktualizacji. Wartość = xx,xx, ilość = yy,yy, koszt standardowy = zz,zz

## <a name="workaround"></a>Obejście

Do czasu wydania przez firmę Microsoft rozwiązania problemu należy rozważyć użycie następujących rozwiązań, aby wyeliminować lub zredukować te błędy:

- Zaksięguj ponownie dokumenty, których księgowanie nie powiodło się.
- Utwórz dokumenty z mniejszą liczbą wierszy.
- Unikaj wartości dziesiętnych kosztu standardowego. Spróbuj zdefiniować koszt standardowy, tak aby pole **Ilość dla ceny** było ustawione na *1*. Jeśli musisz określić wartość **ilości dla ceny** większą niż *1*, spróbuj zminimalizować liczbę miejsc dziesiętnych w standardowym koszcie jednostkowym. (Najlepiej, aby było mniej niż dwa miejsca dziesiętne) Na przykład należy unikać definiowania standardowych ustawień kosztu, takich jak **Cena** = *10* i **Ilość dla ceny** = *3*, ponieważ spowoduje to koszt standardowy jednostkowy 3,333333 (gdzie wartość dziesiętna jest powtarzana).
- W większości dokumentów należy unikać sytuacji, w których wiele wierszy zawiera taką samą kombinację wymiarów produktów i wymiarów magazynu finansowego.
- Zmniejsz stopień równoległości. (W takim przypadku system może przyspieszyć, ponieważ występuje mniej konfliktów i ponownych prób aktualizacji).
