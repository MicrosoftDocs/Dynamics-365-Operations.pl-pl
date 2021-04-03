---
title: Wyszukiwanie akcji
description: W tym artykule opisano działanie funkcji wyszukiwania. Funkcja pomaga znajdować i wykonywać czynności na stronie.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb268c2643b45f6797793dbc5b7cc2e33d5218d9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564221"
---
# <a name="action-search"></a>Wyszukiwanie akcji

[!include [banner](../includes/banner.md)]

W tym artykule opisano działanie funkcji wyszukiwania. Funkcja pomaga znajdować i wykonywać czynności na stronie.

## <a name="introduction"></a>Wprowadzenie

Strony w produkcie głównie wyświetlają polecenia w okienkach akcji, zarówno w standardowym okienku akcji, które wyświetla się u góry strony, jak i na paskach narzędzi, które pojawiają się w różnych częściach strony. W poprzednich wersjach funkcja klawiszy skrótu dawała szybki dostęp do dowolnego przycisku w okienku akcji po naciśnięciu klawisza Alt w kombinacji z właściwą literą.

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)

Funkcja wyszukiwania akcji zastępuje klawisze skrótu, które są już niedostępne. Ta nowa funkcja umożliwia szybkie wyszukiwanie i korzystanie z przycisków w dowolnym widocznym okienku akcji.

## <a name="using-action-search"></a>Korzystanie z funkcji wyszukiwania akcji

Aby skorzystać z funkcji wyszukiwania akcji, wykonaj następujące kroki.

1. W okienku akcji kliknij pole **wyszukiwanie akcji**. (Pole **wyszukiwanie akcji** zawiera ikonę lupy).
2. Wpisz całość lub część nazwy przycisku, którego chcesz użyć. Można także wyszukiwać za pomocą słów znajdujących się w „ścieżce” przycisku. (Więcej informacji można znaleźć w następnej sekcji tego artykułu). Na ogół przycisk będzie widoczny w górnej części listy wyników po wpisaniu dwóch do czterech znaków.
3. Znajdź i uruchom przycisk na liście wyników (za pomocą myszy lub klawiatury).

Po uruchomieniu przycisku wyróżnienie na ekranie wraca do poprzedniego miejsca na stronie, umożliwiając kontynuowanie pracy.

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

Wyszukiwanie akcji można też uruchomić za pomocą kombinacji klawiszy Ctrl+/ lub Alt+Q. Naciśnij skrót klawiaturowy ponownie, aby wyróżnienie wróciło do ostatniej pozycji na stronie.

## <a name="understanding-the-results-list"></a>Opis listy wyników

Często trzeba znać zarówno lokalizację, jak kontekst przycisku, aby w pełni rozumieć, do czego służy. Dlatego dla każdego elementu wyświetlane są dodatkowe informacje, które pomagają zorientować się, które przyciski są widoczne na liście. W szczególności wyświetlana jest „ścieżka” przycisku. Ścieżka może wyróżniać etykiety następujących elementów interfejsu użytkownika:

- Karta Okienko akcji
- Grupa przycisków
- Przycisk menu (jeśli przycisk jest wewnątrz przycisku menu)
- Separator menu (jeśli przycisk jest w nazwanej grupie wewnątrz przycisku menu)
- Grupa lub karta na stronie (na przykład nazwa skróconej karty)

Na przykład w polu **wyszukiwania akcji** wpisujesz **tot** i sprawdzasz listę wyników. Wyróżniony jest pierwszy wpis, dla przycisku o nazwie **Sumy** (ang. Totals). Widoczna jest również ścieżka przycisku **Zamówienie sprzedaży** &gt; **Widok**. Część **Zamówienie sprzedaży** w ścieżce odpowiada karcie **Zamówienie sprzedaży** w okienku akcji, a część **Widok** ścieżki odpowiada grupie **Widok** na tej karcie. Podobnie ścieżka przycisku **Rabat końcowy**(**Sprzedaj** &gt; **Oblicz**) informuje, że ten przycisk znajduje się w grupie **Oblicz** na karcie **Sprzedaj** okienka akcji. Te dane pomagają zrozumieć funkcje przycisków, które będą wywoływane przez wyszukiwanie akcji (jeśli dany zostanie wybrany na liście wyników).

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

W poprzednim przykładzie wyszukiwanie akcji dało wyniki ze standardowego okienka akcji u góry strony. Wyszukiwanie akcji zawiera jednak również wyniki z widocznych pasków narzędzi w innych miejscach na stronie. Na przykład wyszukujesz przycisk **Dostępne zapasy** na skróconej karcie **Wiersze zamówienia sprzedaży**. W tym przypadku ścieżka do przycisku na liście wyników (**Wiersze zamówienia sprzedaży** &gt; **Zapasy** &gt; **Widok**) informuje, że ten przycisk znajduje się w nagłówku **Widok** w przycisku menu **Zapasy** na skróconej karcie **Wiersze zamówienia sprzedaży**.

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

> [!NOTE]
> Istnieje kilka przycisków, które nie są wyświetlane w wyszukiwaniu akcji. Obejmują one przyciski okna dialogowego i przyciski z podformularzy. 

## <a name="action-search-vs-navigation-search"></a>Wyszukiwanie akcji a wyszukiwanie nawigacji

Wyszukiwanie akcji służy do znajdowania i wykonywania akcji na stronie, do wyszukiwania i poruszania się na stronach służy oddzielny mechanizm wyszukiwania. Aby uzyskać więcej informacji na temat tej funkcji, zobacz artykuł [Nawigacja z wyszukiwaniem](navigation-search.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]