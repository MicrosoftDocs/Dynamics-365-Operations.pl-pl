---
title: Nawigacja z wyszukiwaniem
description: "W tym temacie wyjaśniono, jak za pomocą funkcji wyszukiwania przechodzić do stron w programie Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 04/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 431165d541c9a3b63100a93108ee770df8e88aa8
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Nawigacja z wyszukiwaniem
<a id="navigation-search" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak za pomocą funkcji wyszukiwania przechodzić do stron w programie Microsoft Dynamics 365 for Finance and Operations.

Finance and Operations oferuje funkcje dla szerokiego zakresu branż. Aplikacja zawiera szereg obszarów i stron ułatwiających wykonywanie różnych zadań. Aby szybko znaleźć strony z informacjami o odpowiednich zadaniach, użyj funkcji nawigacji z wyszukiwaniem. 

Aby użyć tej funkcji, kliknij ikonę **wyszukiwania**, aby wyświetlić pole **wyszukiwania**. Następnie można wpisać jedno lub więcej słów w polu. System natychmiast wyszukuje odpowiednie stron w aplikacji, które pasują do wpisanych wyrazów. Na przykład można wpisać „faktura od dostawcy”, a system wyświetli wyniki, które pasują do tego zapytania. 

**Uwaga:** pole **wyszukiwania** ułatwia znajdowanie i przechodzenie do stron. Nie pomaga w wyszukiwaniu konkretnych danych ani akcji. 

[![search-box](media/navigation-search.png "Pole wyszukiwania") 

## Szybkie przechodzenie do określonej strony
<a id="quickly-navigate-to-a-particular-page" class="xliff"></a>
Funkcja nawigacji z wyszukiwaniem z pozwala również szybko przechodzić do określonej strony. Na przykład jeśli obsługujesz rozrachunki z dostawcami i często używasz strony **Arkusz płatności**, możesz wpisać w polu **Szukaj** frazę „Arkusz płatności”. Ponieważ dane wejściowe są dokładnie dopasowanie do tytułu strony, strona jest wyświetlana u góry wyników wyszukiwania i można szybko do niej przejść. 

Lista wyników wyszukiwania zawiera tytuł strony, a także ścieżkę nawigacji. Wskazuje umiejscowienie strony w aplikacji. Pomaga także w rozróżnieniu między podobnymi stronami w wynikach. 

Podczas wyszukiwania strony wprowadzone dane są dopasowywane do tytułu strony i jej ścieżki nawigacji. Na przykład jeśli wprowadzisz „z odbiorcami” w polu **Szukaj**, w wynikach pojawią się strony dostępne w obszarze Rozrachunki z odbiorcami — mimo że tytuły stron nie zawierają wyrażenia „z odbiorcami”. 

## Szybkie przechodzenie do strony na podstawie technicznej nazwy formularza
<a id="quickly-navigate-to-a-page-based-on-the-technical-form-name" class="xliff"></a>
Funkcja wyszukiwania z nawigacją obejmuje też funkcję bardzo potrzebną dla użytkowników zaawansowanych: możliwość szybkiego przechodzenia do stron na podstawie nazwy technicznej formularza. Wielu użytkowników tak dobrze zna system, że zna dokładne nazwy techniczne formularzy, z którymi pracuje. Jeśli jesteś takim użytkownikiem, możesz wpisać **formularz:** z nazwą szukanego formularza. Na przykład po wprowadzeniu **formularz: vendinvoice** wyniki wyszukiwania pokażą wszystkie strony, na których nazwa formularza zaczyna się od **vendinvoice**. 

## Administracja i zabezpieczenia
<a id="administration-and-security" class="xliff"></a>
Z punktu widzenia administracji i bezpieczeństwa funkcja nawigacja z wyszukiwaniem wyświetla tylko dwa typy wyników:

-   Strony, które są włączone w bieżącej konfiguracji (przy użyciu kluczy konfiguracji).
-   Strony, do których dany użytkownik ma dostęp w zależności od roli użytkownika.

Lista wyników wyszukiwania jest ograniczona do 10 pozycji. Jeśli w wynikach nie widać szukanego elementu, należy spróbować zawęzić zapytanie lub wpisać nowe. 

## Programowanie
<a id="development" class="xliff"></a> 
Z programistycznego punktu widzenia funkcja nawigacji z wyszukiwaniem jest łatwa do wykorzystania, ponieważ wdrażane elementy menu mogą pojawiać się w wynikach wyszukiwania niemal natychmiast. Jeśli tylko elementy menu mają łącza do okienka nawigacji lub pulpitu nawigacyjnego, automatycznie stają się one dostępne do wyszukiwania. 

