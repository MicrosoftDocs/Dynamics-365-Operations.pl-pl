---
title: Nawigacja z wyszukiwaniem
description: "W tym artykule wyjaśniono, jak za pomocą funkcji wyszukiwania przechodzić do stron w programie Microsoft Dynamics 365 for Operations."
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

[!include[banner](../includes/banner.md)]


W tym artykule wyjaśniono, jak za pomocą funkcji wyszukiwania przechodzić do stron w programie Microsoft Dynamics 365 for Operations.

Dynamics 365 for Operations oferuje funkcje dla szerokiego zakresu branż. Aplikacja zawiera szereg obszarów i stron ułatwiających wykonywanie różnych zadań. Aby szybko znaleźć strony z informacjami o odpowiednich zadaniach, użyj funkcji nawigacji z wyszukiwaniem. Aby użyć tej funkcji, kliknij ikonę **wyszukiwania**, aby wyświetlić pole **wyszukiwania**. Następnie można wpisać jedno lub więcej słów w polu. System natychmiast wyszukuje odpowiednie stron w aplikacji, które pasują do wpisanych wyrazów. Na przykład można wpisać „faktura od dostawcy”, a system wyświetli wyniki, które pasują do tego zapytania. **Uwaga:** pole **wyszukiwania** ułatwia znajdowanie i przechodzenie do stron. Nie pomaga w wyszukiwaniu konkretnych danych ani akcji. 

[![search-box](./media/search-box.png)](./media/search-box.png) Funkcja nawigacji z wyszukiwaniem z pozwala również szybko przechodzić do określonej strony. Na przykład jeśli obsługujesz rozrachunki z dostawcami i często używasz strony **Arkusz płatności**, możesz wpisać w polu wyszukiwania frazę „Arkusz płatności”. Ponieważ dane wejściowe są dokładnie dopasowanie do tytułu strony, strona jest wyświetlana u góry wyników wyszukiwania i można szybko do niej przejść. 

[![searching-for-payment-journal](./media/searching-for-payment-journal.png)](./media/searching-for-payment-journal.png) 

Lista wyników wyszukiwania zawiera tytuł strony, a także ścieżkę nawigacji. To pomaga zorientować się, gdzie w aplikacji znajduje się dana strona. Pomaga także w rozróżnieniu między podobnymi stronami w wynikach. Podczas wyszukiwania strony wprowadzone dane są dopasowywane do tytułu strony i jej ścieżki nawigacji. Na przykład jeśli wprowadzisz „z dostawcami”** **w polu wyszukiwania, w wynikach pojawią się strony dostępne w obszarze Rozrachunki z odbiorcami — mimo że tytuły stron nie zawierają wyrażenia „z dostawcami”. 

[![search-for-the-word-receivable](./media/search-for-the-word-receivable.png)](./media/search-for-the-word-receivable.png) 

Z punktu widzenia administracji i bezpieczeństwa funkcja nawigacji z wyszukiwaniem wyświetla tylko:

-   Strony, które są włączone w bieżącej konfiguracji (przy użyciu kluczy konfiguracji).
-   Strony, do których dany użytkownik ma dostęp w zależności od roli użytkownika

Lista wyników wyszukiwania jest ograniczona do 10 pozycji. Jeśli w wynikach nie widać szukanego elementu, należy spróbować zawęzić zapytanie lub wpisać nowe. Z programistycznego punktu widzenia funkcja nawigacji z wyszukiwaniem jest bardzo łatwa do wykorzystania, ponieważ wdrażane elementy menu mogą pojawiać się w wynikach wyszukiwania niemal natychmiast. Jeśli tylko elementy menu mają łącza do okienka nawigacji lub pulpitu nawigacyjnego, automatycznie stają się one dostępne do wyszukiwania. Funkcja wyszukiwania z nawigacją obejmuje też funkcję bardzo potrzebną dla użytkowników zaawansowanych: możliwość szybkiego przechodzenia do stron na podstawie nazwy technicznej formularza. Wielu użytkowników tak dobrze zna system, że zna dokładne nazwy techniczne formularzy, z którymi pracuje. Jeśli jesteś takim użytkownikiem, możesz wpisać **formularz:** z nazwą szukanego formularza. Na przykład po wprowadzeniu **formularz: vendinvoice** wyniki wyszukiwania pokażą wszystkie strony, na których nazwa formularza zaczyna się od **vendinvoice**. 

[![search-for-form-vendinvoice](./media/search-for-form-vendinvoice.png)](./media/search-for-form-vendinvoice.png)




