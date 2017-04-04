---
title: Wyszukiwanie akcji
description: "W tym artykule opisano działanie funkcji wyszukiwania w usłudze Microsoft Dynamics 365 dla operacji. Akcja wyszukiwania pomoże Ci, znajdowanie i wykonywania czynności na stronie."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Wyszukiwanie akcji

W tym artykule opisano działanie funkcji wyszukiwania w usłudze Microsoft Dynamics 365 dla operacji. Akcja wyszukiwania pomoże Ci, znajdowanie i wykonywania czynności na stronie.

<a name="introduction"></a>Wprowadzenie
------------

Strony w programie Microsoft Dynamics 365 dla operacji przede wszystkim wystawiać polecenia na okienka akcji, zarówno standardowe okienko akcji, która pojawia się u góry strony i paski narzędzi, które pojawiają się w różnych częściach strony. W poprzednich wersjach funkcja poradami dotyczącymi klawiszy pozwalają szybko uzyskać dostęp do dowolnego przycisku w okienku akcji, naciskając klawisz Alt, a następnie liter. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) jednak w aktualnej wersji systemu Dynamics 365 dla operacji poradami dotyczącymi klawiszy nie są już dostępne, lecz zostały zastąpione przez działanie funkcji wyszukiwania. Ta nowa funkcja umożliwia szybkie wyszukiwanie i korzystanie z przycisków w dowolnym widocznym okienku akcji.

## <a name="using-action-search"></a>Korzystanie z funkcji wyszukiwania akcji
Aby skorzystać z funkcji wyszukiwania akcji, wykonaj następujące kroki.

1.  W okienku akcji kliknij pole **wyszukiwanie akcji**. (Pole **wyszukiwanie akcji** zawiera ikonę lupy).
2.  Wpisz całą nazwę lub część nazwy przycisku, który chcesz uruchomić. Można także wyszukiwać za pomocą słów z przycisku "Ścieżka". (Aby uzyskać więcej informacji, zobacz następną sekcję tego artykułu). Zazwyczaj przycisk pojawi się w górnej części listy wyników po wpisaniu dwóch do czterech znaków.
3.  Znajdź i uruchom przycisk na liście wyników (za pomocą myszy lub klawiatury).

Po uruchomieniu przycisku wyróżnienie na ekranie wraca do poprzedniego miejsca na stronie, umożliwiając kontynuowanie pracy. 

[![działanie pola wyszukiwania](./media/action-search-field.png)](./media/action-search-field.png)

Wyszukiwanie akcji można też uruchomić za pomocą kombinacji klawiszy Ctrl+/ lub Alt+Q. Naciśnij skrót klawiaturowy ponownie, aby wyróżnienie wróciło do ostatniej pozycji na stronie.

## <a name="understanding-the-results-list"></a>Opis listy wyników
Często Dynamics 365 dla operacji, trzeba znać zarówno lokalizację i kontekst przycisku, aby lepiej zrozumieć celem tego przycisku. W związku z tym dodatkowe informacje są wyświetlane dla każdej pozycji na liście wyników, aby pomóc Ci zrozumieć dokładnie przyciski pojawiające się na liście. W szczególności wyświetlana jest „ścieżka” przycisku. Ścieżka może wyróżniać etykiety następujących elementów interfejsu użytkownika:

-   Karta Okienko akcji
-   Grupa przycisków
-   Przycisk menu (jeśli przycisk jest wewnątrz przycisku menu)
-   Separator menu (jeśli przycisk jest w nazwanej grupie wewnątrz przycisku menu)
-   Grupa lub karta na stronie (na przykład nazwa skróconej karty)

Na przykład w polu **wyszukiwania akcji** wpisujesz **tot** i sprawdzasz listę wyników. Pierwszy wpis dla przycisku o nazwie **sumy**, jest wyróżniony. Ścieżka przycisk **zamówienie sprzedaży**&gt;**widoku** jest także pokazana. **Zamówienie sprzedaży** części ścieżki odpowiada **zamówienie sprzedaży** karty w okienku akcji i **widoku** części ścieżki odpowiada **widoku** grupy na tej karcie. Podobnie, ścieżka **Rabat końcowy** przycisk (**sprzedaży**&gt;**Oblicz**) informuje, że ten przycisk znajduje się w **Oblicz** grupy na **sprzedaży** karty w okienku akcji. W związku z tym te informacje pomagają zrozumieć dokładnie który przycisk zostanie wywołane przez akcję wyszukiwania (po zaznaczeniu tego przycisku na liście Wyniki). 

[![Akcja search--z dane pola](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

W poprzednim przykładzie wyszukiwanie akcji dało wyniki ze standardowego okienka akcji u góry strony. Wyszukiwanie akcji zawiera jednak również wyniki z widocznych pasków narzędzi umieszczonych w innych miejscach na stronie. Na przykład szukasz **zapasów** przycisk, który znajduje się na **zamówienia sprzedaży, wiersze** skróconej. W tym przypadku ścieżki przycisku na liście wyników (**wiersze zamówienia sprzedaży**&gt;**zapasów**&gt;**widoku**) informuje, że ten przycisk znajduje się w obszarze **widoku** na **zapasów** przycisk menu na **wiersze zamówienia sprzedaży** skróconej. 

[![na--zapasy](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Wyszukiwanie akcji a wyszukiwanie nawigacji
Celem działania wyszukiwania znaleźć i uruchomić akcji na stronie znajduje się mechanizm wyszukiwania do znajdowania i przechodzenia do stron w usłudze Dynamics 365 dla operacji. Aby uzyskać więcej informacji dotyczących tej funkcji, zobacz [nawigacji wyszukiwania](navigation-search.md) art.


