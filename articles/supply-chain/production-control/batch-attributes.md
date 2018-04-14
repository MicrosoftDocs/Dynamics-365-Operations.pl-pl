---
title: Atrybuty partii
description: "Ten temat zawiera informacje o atrybutach partii. Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów. W temacie wyjaśniono też, jak przypisywać atrybuty partii i jak szukać według nich podczas rezerwowania partii."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6c18b007a72686b1ede69b750e930d72e86f0aba
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="batch-attributes"></a>Atrybuty partii

[!INCLUDE [banner](../includes/banner.md)]

Ten temat zawiera informacje o atrybutach partii. Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów. W temacie wyjaśniono też, jak przypisywać atrybuty partii i jak szukać według nich podczas rezerwowania partii.

Atrybuty partii to cechy surowców i produktów gotowych wchodzących w skład partii zapasów. Atrybuty partii mogą się różnić w zależności od czynników, takich jak warunki środowiskowe, jakość surowców używanych w procesie produkcji danej partii czy wyniku gotowego produktu. Liczba i typ stosowanych atrybutów partii może się znacznie różnić między poszczególnymi sektorami gospodarki. Poniżej przedstawiono dwa przykłady pokazujące sposób korzystania z atrybutów partii:

-   W firmach produkujących ser mleko będące surowcem do produkcji serów może mieć przypisane atrybuty takie jak zawartość tłuszczu lub procent wagi. Ser produkowany z takiego mleka może mieć natomiast inne atrybuty (np. wilgotność lub wiek).
-   W branży stalowej żelazo może mieć przypisane atrybuty takie jak procent zawartości magnezu, procent zawartości srebra lub procent zawartości cynku.

Aby lepiej zarządzać liczbą i typami atrybutów, można stosować grupy atrybutów partii. Dzięki temu nie trzeba dodawać atrybutów pojedynczo.

## <a name="assign-batch-attributes"></a>Przypisywanie atrybutów partii
Atrybuty partii można przypisać do poszczególnych produktów znajdujących się w partiach zapasów lub można przypisywać je do produktów skojarzonych z konkretnymi odbiorcami. Przed przypisaniem atrybutu partii na poziomie odbiorcy, należy najpierw przypisać go na poziomie produktu. Produkt musi być mieć wymiar partii **Aktywny** w grupie wymiarów śledzenia. Aby przypisać atrybut partii do danego produktu, użyj strony określonego produktu. Jeśli atrybut jest właściwe dla produktu dla danego odbiorcy, użyj strony określonego odbiorcy. Po dodaniu atrybutu do produktu, można również zdefiniować inne parametry. Oto kilka przykładów:

-   Minimalne i minimalne zakresy dla atrybutu typu **Liczba całkowita** lub **Ułamek**.
-   Działania związane z przekroczeniem tolerancji dla atrybutów typu **Liczba całkowita** lub **Ułamek**. Jeśli wartość atrybutu wykracza poza minimalny lub maksymalny zakres, działanie może polegać na wyświetleniu ostrzeżenia lub komunikatu o błędzie.
-   Wartość docelowa atrybutu. Ta wartość jest optymalną wartość atrybutu i odnosi się do wszystkich typów atrybutów.

Dostępne są strony produktów wybranych na stronie **Zwolnione produkty** w module Zarządzanie informacjami o produktach. Po przypisaniu atrybutów partii do produktu można dodać konkretne wartości atrybutów na stronie **Atrybuty partii zapasów**.

## <a name="reserve-batches"></a>Rezerwowanie partii
Można wyszukiwać atrybuty partii podczas rezerwowania partii dla zamówienia sprzedaży w celu wypełnienia zamówienia odbiorcy lub podczas odbierania i rezerwowania partii dla zlecenia produkcyjnego. To ułatwia znajdowanie partii zapasów zawierającej produkt, który ma atrybut partii, którego szukasz. Po znalezieniu partii możesz zarezerwować produkt w wierszu źródłowej transakcji magazynowej.




