---
title: Wyszukiwanie akcji
description: "W tym artykule opisano funkcję wyszukiwania akcji dostępną w programie Microsoft Dynamics 365 for Finance and Operations. Funkcja pomaga znajdować i wykonywać czynności na stronie."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: cd024f2bc06fca9c21ea41fbed44efbc519cee94
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# <a name="action-search"></a>Wyszukiwanie akcji

[!include[banner](../includes/banner.md)]


W tym artykule opisano funkcję wyszukiwania akcji dostępną w programie Microsoft Dynamics 365 for Finance and Operations. Funkcja pomaga znajdować i wykonywać czynności na stronie.

<a name="introduction"></a>Wprowadzenie
------------

Strony w programie Microsoft Dynamics 365 for Finance and Operations głównie wyświetlają polecenia w okienkach akcji, zarówno w samodzielnym okienku akcji, które wyświetla się u góry strony, jak i na paskach narzędzi, które pojawiają się w różnych częściach strony. W poprzednich wersjach funkcja klawiszy skrótu dawała szybki dostęp do dowolnego przycisku w okienku akcji po naciśnięciu klawisza Alt w kombinacji z właściwą literą. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) W aktualnej wersji programu Finance and Operations klawisze skrótu nie są już dostępne i zostały zastąpione przez funkcję wyszukiwania akcji. Ta nowa funkcja umożliwia szybkie wyszukiwanie i korzystanie z przycisków w dowolnym widocznym okienku akcji.

## <a name="using-action-search"></a>Korzystanie z funkcji wyszukiwania akcji
Aby skorzystać z funkcji wyszukiwania akcji, wykonaj następujące kroki.

1.  W okienku akcji kliknij pole **wyszukiwanie akcji**. (Pole **wyszukiwanie akcji** zawiera ikonę lupy).
2.  Wpisz całość lub część nazwy przycisku, którego chcesz użyć. Można także wyszukiwać za pomocą słów znajdujących się w „ścieżce” przycisku. (Więcej informacji można znaleźć w następnej sekcji tego artykułu). Na ogół przycisk będzie widoczny w górnej części listy wyników po wpisaniu dwóch do czterech znaków.
3.  Znajdź i uruchom przycisk na liście wyników (za pomocą myszy lub klawiatury).

Po uruchomieniu przycisku wyróżnienie na ekranie wraca do poprzedniego miejsca na stronie, umożliwiając kontynuowanie pracy. 

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

Wyszukiwanie akcji można też uruchomić za pomocą kombinacji klawiszy Ctrl+/ lub Alt+Q. Naciśnij skrót klawiaturowy ponownie, aby wyróżnienie wróciło do ostatniej pozycji na stronie.

## <a name="understanding-the-results-list"></a>Opis listy wyników
Często w programie Finance and Operations trzeba znać zarówno lokalizację, jak kontekst przycisku, aby w pełni rozumieć, do czego służy. Dlatego dla każdego elementu na liście wyników wyświetlane są dodatkowe informacje, które pomagają zorientować się, które przyciski są widoczne na liście. W szczególności wyświetlana jest „ścieżka” przycisku. Ścieżka może wyróżniać etykiety następujących elementów interfejsu użytkownika:

-   Karta Okienko akcji
-   Grupa przycisków
-   Przycisk menu (jeśli przycisk jest wewnątrz przycisku menu)
-   Separator menu (jeśli przycisk jest w nazwanej grupie wewnątrz przycisku menu)
-   Grupa lub karta na stronie (na przykład nazwa skróconej karty)

Na przykład w polu **wyszukiwania akcji** wpisujesz **tot** i sprawdzasz listę wyników. Wyróżniony jest pierwszy wpis, dla przycisku o nazwie **Sumy** (ang. Totals). Widoczna jest również ścieżka przycisku **Zamówienie sprzedaży** &gt; **Widok**. Część **Zamówienie sprzedaży** ścieżki odpowiada karcie **Zamówienie sprzedaży** w okienku akcji, a część **Widok** ścieżki odpowiada grupie **Widok** na tej karcie. Podobnie ścieżka przycisku **Rabat końcowy** (ang. Total discount) (**Sprzedaż** &gt; **Oblicz**) informuje, że ten przycisk znajduje się w grupie **Oblicz** na karcie **Sprzedaż** w okienku akcji. Te dane pomagają zrozumieć funkcje przycisków, które będą wywoływane przez wyszukiwanie akcji (jeśli dany zostanie wybrany na liście wyników). 

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

W poprzednim przykładzie wyszukiwanie akcji dało wyniki ze standardowego okienka akcji u góry strony. Wyszukiwanie akcji zawiera jednak również wyniki z widocznych pasków narzędzi umieszczonych w innych miejscach na stronie. Na przykład wyszukujesz przycisk **Dostępne zapasy**, który znajduje się na skróconej karcie **Wiersze zamówienia sprzedaży**. W tym przypadku ścieżka do przycisku na liście wyników (**Wiersze zamówienia sprzedaży** &gt; **Zapasy** &gt; **Widok**) informuje, że ten przycisk znajduje się w nagłówku **Widok** w przycisku menu **Zapasy** na skróconej karcie **Wiersze zamówienia sprzedaży**. 

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Wyszukiwanie akcji a wyszukiwanie nawigacji
Wyszukiwanie akcji służy do znajdowania i wykonywania akcji na stronie, Do znajdowania i elementów i poruszania się na stronach w programie Finance and Operations służy oddzielny mechanizm wyszukiwania. Aby uzyskać więcej informacji na temat tej funkcji, zobacz artykuł [Nawigacja z wyszukiwaniem](navigation-search.md).




