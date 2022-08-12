---
title: Planowanie oparte na popycie
description: Artykuł opisuje, jak generować planowane zamówienia dla pozycji, które są ustawione jako punkty odłączenia.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 4dadd8e258af6e6ffbe8c28fc8f9be511fcdb5bc
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186728"
---
# <a name="demand-driven-planning"></a>Planowanie oparte na popycie

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Artykuł opisuje, jak generować planowane zamówienia dla pozycji, które są ustawione jako punkty odłączenia.

## <a name="net-flow-and-qualified-demand"></a>Przepływ netto i popyt kwalifikowany

Podczas planowania głównego system stosuje koncepcję *przepływu netto*, aby ustalić efektywną ilość dostępną na podstawie aktualnych zapasów na stanie, powiększonych o zapasy zamówione (istniejące zamówienia na dostawy, które nie zostały jeszcze odebrane), pomniejszonych o tzw. *kwalifikowany popyt* (kwalifikowana nadchodząca sprzedaż), jak pokazano na poniższej ilustracji. Kiedy system określa, do której strefy buforowej należy dana pozycja i jaka powinna być zamawiana ilość, ocenia przepływ netto, a nie faktyczne zapasy na stanie.

![Przykład wykresu obliczania przepływu netto.](media/ddmrp-net-flow-example.png "Przykład wykresu obliczania przepływu netto")

Gdy podczas planowania zostanie uruchomione planowane zamówienie, zamówiona ilość będzie równa maksymalnemu poziomowi minus przepływ netto. Aby nadać priorytet zamówieniu, system używa funkcji [planowania opartego na priorytetach](priority-based-planning.md) zamiast dat wymagań. Planowanie zapotrzebowania materiałowego według zapotrzebowania (DDMRP) przypisuje priorytet planowanemu zamówieniu na podstawie zamówionej ilości jako procentu maksymalnych zapasów. Na poprzedniej ilustracji zamówiona ilość to 53% ilości maksymalnej. Dlatego priorytetem kolejności uzupełniania zapasów będzie 53. (W kontekście, 0 to najwyższy priorytet, a 100 to najniższy priorytet).

*Kwalifikowany popyt* to popyt zaległy, plus dzisiejszy popyt, plus kwalifikowane zamówienia w przyszłości. Poniższa ilustracja przedstawia przykładowy poziom zapotrzebowania na dzień dzisiejszy (12 czerwca) i trzy następne dni. DDMRP umożliwia ustawienie progu gwałtownego wzrostu zamówień, aby określić zapotrzebowanie przekraczające normalne oczekiwania. Jeśli próg zostanie ustawiony na 25 sztuk, to dwie z przyszłych dat pokazanych na ilustracji zostaną zakwalifikowane jako skoki zamówień. Musisz przypisać próg pik dla każdego produktu indywidualnie, korzystając z jego strony **Pokrycie artykułu**, jak opisano w [Ustawianie buforów dla pozycji punktu rozłącznego](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Przykład wykresu obliczania zapotrzebowania kwalifikowanego.](media/ddmrp-net-qualified-demand-example.png "Przykład wykresu obliczania zapotrzebowania kwalifikowanego")

Zakładając, że nie ma zapotrzebowania przeterminowanego, możesz teraz dodać dzisiejsze zapotrzebowanie (18) do ilości z dwóch skoków zamówień (29 i 26), aby otrzymać zapotrzebowanie kwalifikowane w wysokości 73. Nawet jeśli istnieje zapotrzebowanie na 23 czerwca, zauważ, że nie jest ono uwzględnione w obliczeniach przepływu netto, ponieważ DDMRP uruchamia planowaną kolejność w inny sposób niż tradycyjne grupy pokrycia planistycznego.

## <a name="generating-planned-orders-with-ddmrp"></a>Generowanie planowanych zamówień za pomocą DDMRP

Podczas planowania system utworzy nowe planowane zamówienie, jeśli przepływ netto dla danej pozycji spadnie poniżej punktu zamawiania. Podczas korzystania z DDMRP planowanie odbywa się zazwyczaj codziennie. Dlatego raz dziennie sprawdzasz poziom zapasów, aby określić, które pozycje należy uzupełnić.

Poniższa ilustracja przedstawia przykład sytuacji, w której 20 czerwca złożono zamówienie na 18 sztuk, 21 czerwca na 29 sztuk, 22 czerwca na 26 sztuk, a 23 czerwca na 20 sztuk. Ponieważ próg kolizji jest ustawiony na 25 sztuk, dwa z tych zleceń są oznaczone jako pik. Na stanie znajduje się 220 sztuk tego przedmiotu.

![Przykład planowania 1.](media/ddmrp-planning-example-1.png "Przykład planowania 1")

Jeśli uruchomisz teraz planowanie główne, wygeneruje ono planowane zamówienie, jeśli okaże się, że przepływ netto spadł poniżej punktu zamawiania (w tym przykładzie 219 sztuk).

![Przykład planowania 2.](media/ddmrp-planning-example-2.png "Przykład planowania 2")

W tym przykładzie powstaje planowane zlecenie zakupu na ilość 130 sztuk, która jest równa poziomowi maksymalnemu minus przepływ netto. Planowane zamówienie ma priorytet 53,07, wynikający z procentowego udziału w ilości maksymalnej. Ponieważ wartości te zostały znalezione 20 czerwca, system tworzy planowane zamówienie, które jest datowane na 20 czerwca plus czas realizacji pozycji (w tym przykładzie pięć dni roboczych). Ponieważ pięć dni roboczych przypada na tydzień od dzisiaj, planowane zlecenie jest datowane na 27 czerwca.

> [!NOTE]
> Optymalizacja Planowania oblicza tylko elementy rozłączne przy użyciu DDMRP. Wszystkie inne pozycje są obliczane przy użyciu standardowego planowania zapotrzebowania materiałowego (MRP).
