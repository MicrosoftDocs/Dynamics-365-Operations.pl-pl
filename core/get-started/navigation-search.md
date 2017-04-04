---
title: Nawigacja z wyszukiwaniem
description: "W tym artykule wyjaśniono, jak użyć funkcji wyszukiwania w celu przejścia do strony w programie Microsoft Dynamics 365 dla operacji."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Nawigacja z wyszukiwaniem

W tym artykule wyjaśniono, jak użyć funkcji wyszukiwania w celu przejścia do strony w programie Microsoft Dynamics 365 dla operacji.

Dynamics 365 dla operacji zapewnia funkcje szeroki wachlarz gałęzi przemysłu i branż. Aplikacja zawiera szereg obszarów i stron ułatwiających wykonywanie różnych zadań. Aby szybko znaleźć strony trzeba wykonać zadania, użyj funkcji wyszukiwania nawigacji. Aby użyć tej funkcji, kliknij ikonę **wyszukiwania**, aby wyświetlić pole **wyszukiwania**. Następnie można wpisać jedno lub więcej słów w polu. System natychmiast wyszukuje odpowiednie stron w aplikacji, które pasują do wpisanych wyrazów. Na przykład można wpisać „faktura od dostawcy”, a system wyświetli wyniki, które pasują do tego zapytania. **Uwaga:** pole **wyszukiwania** ułatwia znajdowanie i przechodzenie do stron. Nie pomaga w wyszukiwaniu konkretnych danych ani akcji. 

[![pole wyszukiwania](./media/search-box.png)](./media/search-box.png) funkcji wyszukiwania nawigacji służy również jako doskonały sposób, aby szybko przejść do określonej strony. Na przykład, jeśli jesteś rozrachunków z dostawcami urzędnik kto często używa **arkusza płatności** stronę, można wprowadzić "arkusza płatności" w polu wyszukiwania. Ponieważ dane wejściowe są dokładne dopasowanie do tytułu strony, strony znajduje się u góry wyników wyszukiwania i można szybko przejść do niego. 

[![wyszukiwanie do--Arkusz płatności](./media/searching-for-payment-journal.png)](./media/searching-for-payment-journal.png) 

Z listy wyników wyszukiwania Wyświetla tytuł strony, a także ścieżki nawigacji. To pomaga zorientować się, gdzie w aplikacji znajduje się dana strona. Pomaga także w rozróżnieniu między podobnymi stronami w wynikach. Podczas wyszukiwania strony wprowadzone dane są dopasowywane do tytułu strony i jej ścieżki nawigacji. Na przykład, jeśli wprowadzisz "należności" Wytwarzanie Wytwarzanie pola wyszukiwania, można zobaczyć wyniki dla stron, które są dostępne w obszarze Rozrachunki z odbiorcami — nawet jeśli tytuły stron nie zawierają wyraz "należności". 

[![wyszukiwanie dla-word-z odbiorcami](./media/search-for-the-word-receivable.png)](./media/search-for-the-word-receivable.png) 

Od administracji i perspektywy bezpieczeństwa nawigacji wyszukiwania tylko powierzchnie funkcjonalności:

-   Strony, które są włączone w bieżącej konfiguracji (przy użyciu kluczy konfiguracji).
-   Strony, do których dany użytkownik ma dostęp w zależności od roli użytkownika

Lista wyników wyszukiwania jest ograniczona do 10 pozycji. Jeśli w wynikach nie widać szukanego elementu, należy spróbować zawęzić zapytanie lub wpisać nowe. Z programistycznego punktu widzenia funkcja nawigacji z wyszukiwaniem jest bardzo łatwa do wykorzystania, ponieważ wdrażane elementy menu mogą pojawiać się w wynikach wyszukiwania niemal natychmiast. Jeśli tylko elementy menu mają łącza do okienka nawigacji lub pulpitu nawigacyjnego, automatycznie stają się one dostępne do wyszukiwania. Funkcja wyszukiwania z nawigacją obejmuje też funkcję bardzo potrzebną dla użytkowników zaawansowanych: możliwość szybkiego przechodzenia do stron na podstawie nazwy technicznej formularza. Wielu użytkowników tak dobrze zna system, że zna dokładne nazwy techniczne formularzy, z którymi pracuje. Jeśli jesteś takim użytkownikiem, możesz wpisać **formularz:** z nazwą szukanego formularza. Na przykład po wprowadzeniu **formularz: vendinvoice** wyniki wyszukiwania pokażą wszystkie strony, na których nazwa formularza zaczyna się od **vendinvoice**. 

[![Szukaj dla formularza vendinvoice](./media/search-for-form-vendinvoice.png)](./media/search-for-form-vendinvoice.png)


