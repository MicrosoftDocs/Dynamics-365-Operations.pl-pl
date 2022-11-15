---
title: Planowanie z wyborem zasobu na podstawie zdolności produkcyjnych
description: W tym artykule opisano wybór zasobów podczas nieskończonego planowania zdolności produkcyjnych, gdy zdolności produkcyjne są określone jako wymagania dotyczące zasobów dla operacji.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 176f40ad8cd1aa1831bbe50c0ebd91ec0cc3bc89
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739906"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Planowanie z wyborem zasobu na podstawie zdolności produkcyjnych

[!include [banner](../../includes/banner.md)]

Określając wymagania dotyczące zasobów dla operacji w marszrucie produkcji, definiujesz, co jest wymagane do wykonania tej operacji. Na przykład operacja może wymagać użycia określonego zasobu lub grupy zasobów albo kombinacji umiejętności lub zdolności produkcyjnych. W tym artykule opisano wybór zasobów podczas nieskończonego planowania zdolności produkcyjnych, gdy zdolności produkcyjne są określone jako wymagania dotyczące zasobów dla operacji.

## <a name="turn-the-capability-based-scheduling-feature-on-or-off"></a>Włącz lub wyłącz funkcję planowania opartego na zdolnościach produkcyjnych

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Planowanie nieskończonych zdolności produkcyjnych dla optymalizacji planowania* w obszarze roboczym [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Aby uzyskać więcej informacji o tej funkcji, zobacz temat [Planowanie z nieskończoną zdolnością produkcyjną](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Planowanie oparte na zdolności produkcyjnej

Zdolność produkcyjna to zdolność zasobu operacyjnego do wykonania określonego działania. Pojedynczy zasób operacyjny może mieć więcej niż jedną przypisaną zdolność produkcyjną, a pojedyncza zdolność produkcyjna może być przypisana do więcej niż jednego zasobu. Zdolności produkcyjne można przypisać do wszystkich zasobów, takich jak narzędzia, dostawcy, maszyny, lokalizacje, zakłady lub zasoby ludzkie.

Określając zdolności produkcyjne jako wymagania dotyczące zasobów, można odroczyć alokację zasobów do czasu zaplanowania zamówień. Zamiast przypisywać określone zasoby lub grupy zasobów do operacji marszruty, można zdefiniować zdolności produkcyjne wymagane dla każdej operacji marszruty. Następnie podczas planowania system dopasowuje do wymaganych zdolności produkcyjnych zdolności zdefiniowane dla zasobów. System wybiera tylko zasoby, które spełniają wymagania.

Aby przypisać zdolności produkcyjne do zasobu operacyjnego, użyj skróconej karty **Zdolności produkcyjne** na stronie **Zasoby**. Aby przypisać zasoby do zdolności produkcyjnych, użyj skróconej karty **Zasoby** na stronie **Zdolności produkcyjne zasobów**. Obie strony są dostępne w obszarze **Kontrola produkcji \> Ustawienia \> Zasoby** w okienku nawigacji. Obie skrócone karty zawierają siatkę z listą zasobów skojarzonych z wybranym zasobem lub zdolnością produkcyjną. Obie skrócone karty zawierają również pasek narzędzi, który umożliwia dodawanie, usuwanie i edytowanie wierszy w siatce. Siatka zawiera następujące kolumny:

- **Zasób** lub **Zdolność produkcyjna** — wybierz zasób lub zdolności produkcyjne, które są przypisywane przez wiersz.
- **Opis** — wprowadź krótki opis zasobu lub zdolności produkcyjnych.
- **Ważność** — umożliwia określenie pierwszej daty, od kiedy obowiązuje przypisanie zasobu lub zdolności produkcyjnej. Podczas planowania system nie użyje zasobu ani zdolności produkcyjnej, których zdolność produkcyjna utraciła ważność, nawet jeśli ten zasób w inny sposób zaspokaja wymagania.
- **Wygaśnięcie** — umożliwia określenie ostatniej daty, kiedy obowiązuje przypisanie zasobu lub zdolności produkcyjnej. Podczas planowania system nie użyje zasobu ani zdolności produkcyjnej, których zdolność produkcyjna utraciła ważność, nawet jeśli ten zasób w inny sposób zaspokaja wymagania.
- **Poziom** — umożliwia określenie poziomu wydajności, który zasób musi mieć dla zdolności produkcyjnych. Następnie, po określeniu **minimalnego poziomu wymaganej** wartości zasobu lub zapotrzebowania na zdolności produkcyjne, aparat planowania uwzględnia poziom wydajności podczas wyboru zasobu. System wybiera tylko te zasoby, które mają wymagane możliwości na poziomie równym lub przewyższającym poziom określony w wymaganiu źródłowym.
- **Priorytet** — to pole nie jest jeszcze obsługiwane przez optymalizację planowania. Jednakże, jeśli używasz przestarzałego silnika planowania głównego, możesz użyć pola **Priorytet** w przypisaniu zasobu lub zdolności produkcyjnych do zdefiniowania priorytetu zasobu. Następnie jeśli zostanie wybrana wartość *Priorytet* w polu **Wybór zasobu głównego** na stronie **Parametry planowania**, system wybierze najpierw zasób, który ma najwyższy priorytet (czyli najniższą wartość liczbową w polu **Priorytet**) podczas planowania.

## <a name="example"></a>Przykład

W tym przykładzie pokazano, jak aparat planowania wybiera zasoby na podstawie zdolności produkcyjnych.

Marszruta produkcji ma pięć operacji: *10*, *20*, *30*, *40* i *50*. Każda operacja marszruty wymaga zasobu, który ma inne zdolności produkcyjne. Na przykład operacja marszruty *10* wymaga zasobu, który jest w stanie zmontować głośnik (*0050 Montaż głośnika*) i zdolność produkcyjną obróbki drewna (*1010 Możliwość obróbki drewna*). Operacja marszruty *50* wymaga zasobu, który ma zdolność produkcyjną pakowania produktu (*0070 Pakowa zdolność produkcyjna*).

![Zdolności produkcyjne używane do planowania.](media/capability-based-scheduling.png "Zdolności produkcyjne używane do planowania.")

Podczas planowania aparat wyszukuje zasoby spełniające wymagania dotyczące operacji. Na przykład aparat planowania wybiera zasób *00101* do wykonania operacji *10*, ponieważ ten zasób jest pierwszym zasobem, który ma obie wymagane zdolności produkcyjne. Aparat planowania wybiera zasób *00301* do wykonania operacji *50*, ponieważ ten zasób jest jedynym zasobem, który ma pakowe zdolności produkcyjne.

Następnie należy wziąć pod uwagę wpływ tego przykładu na używane poziomy wydajności:

- Operacja *10* wymaga minimalnego poziomu wydajności *7* dla zdolności produkcyjnej *0059 Montaż*.
- Zasób *00101* ma poziom wydajności *5* dla zdolności produkcyjnej *0059 Montaż*.
- Zasób *00102* ma poziom wydajności *10* dla zdolności produkcyjnej *0059 Montaż*.

W tym przypadku podczas nieograniczonego planowania zdolności produkcyjnych aparat planowania wybiera zasób *00102* do wykonania operacji *10*, ponieważ ten zasób, w przeciwieństwie do zasobu *00101*, ma wymagany poziom wydajności zdolności produkcyjnych.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
