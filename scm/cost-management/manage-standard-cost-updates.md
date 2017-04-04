---
title: "Zarządzanie aktualizacjami na koszt standardowy"
description: "Aktualizacje danych standardowych kosztów można zarządzać za pomocą dwóch różnych podejść - podejście jednej wersji i dwie wersje."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7e0f0817ff37c82ed98a51f10bcdde7e785a19a3
ms.lasthandoff: 03/31/2017


---

# <a name="manage-standard-cost-updates"></a>Zarządzanie aktualizacjami na koszt standardowy

Aktualizacje danych standardowych kosztów można zarządzać za pomocą dwóch różnych podejść - podejście jednej wersji i dwie wersje. 

Metoda jednej wersji zakłada użycie jednej wersji zawierającej wszystkie rekordy kosztów. Te rekordy obejmują koszty pierwotne i wszystkie aktualizacje kosztów.
Metoda dwóch wersji zakłada użycie jednej wersji z rekordami kosztów pierwotnych i drugiego z rekordami wszystkich aktualizacji kosztów. Główną zaletą metody dwóch wersji jest wyraźne nakreślenie i śledzenie zmian kosztów w oddzielnych wersjach ceny bez naruszania oryginalnej wersji ceny. Metody dwóch wersji można używać do identyfikowania wielu wzrostów kosztów z osobnymi wersjami ceny zawierającymi rekordy wzrostów kosztów. **Przykład** Poniżej pokazano, jak używać metod jednej i dwóch wersji do aktualizacji kosztów standardowych i środowisku produkcyjnym. Na przykład aktualizacje, które odzwierciedlają nowe pozycje lub korekty. Załóżmy, że metoda jednej wersji przedstawia koszty standardowe w bieżącym roku. Identyfikator dla tej wersji to 2016-STD. Wersja 2016-STD zawiera bieżące aktywne koszty wszystkich pozycji. Ponadto zawiera wszystkie kategorie kosztów związanych z routingiem i narzutów obliczenia formuły, które były znane na początku roku 2016. 2016-STD jest oryginalnej wersji wyceny.
-   **Aktualizacja danych o kosztach w metodzie jednej wersji ** — w metodzie jednej wersji wersja ceny pierwotnej 2016-STD zawiera wszystkie rekordy kosztów. Aktualizacje kosztu są rejestrowane w 2016 STD i są ustawione na stan "Oczekujące". Oczekujące kosztów można wprowadzić ręcznie dla nowych towarów zakupionych lub może być obliczona do wyprodukowania towaru w celu odzwierciedlenia korekt. Gdy zostanie zastosowane podejście jedna wersja obliczeń BOM nie wymagają źródła danych rezerwowej ponieważ wszystkie koszty aktywne są zawarte w tej wersji wyceny. Po aktywacji kosztów oczekujących oryginalna wersja ceny 2016-STD będzie znów zawierać aktywne koszty bieżące.
-   **Metoda dwóch wersji** — W metodzie dwóch wersji aktualizacji danych o kosztach jest wymagana dodatkowa wersja ceny zawierająca wyłącznie aktualizacje. Przyjmijmy, że identyfikator będzie wyglądał następująco: 2016-STD-ZMIANY. Aktualizacje kosztów będą wprowadzane w dodatkowej wersji ceny jako rekordy kosztów oczekujących. W metodzie dwóch wersji obliczenia BOM (kosztów oczekujących) jest wymagana zasada rezerwowości, ponieważ dodatkowa wersja ceny zawiera tylko podzestaw danych o kosztach. Zasada rezerwowości może zostać wyrażona jako koszty aktywne lub określona wersja ceny 2016-STD, ponieważ oba parametry identyfikują źródło danych o kosztach, jeśli nie istnieje ono w wersji ceny 2016-STD-ZMIANY. Zasada rezerwowości może zostać wyrażona jako koszty aktywne lub określona wersja ceny 2016-STD, ponieważ oba parametry identyfikują źródło danych o kosztach, jeśli nie istnieje ono w wersji ceny 2016-STD-ZMIANY. Po aktywacji kosztów oczekujących wersja ceny 2016-STD-ZMIANY będzie zawierać aktywne koszty bieżące odzwierciedlające aktualizację, a oryginalna wersja ceny 2016-STD pozostanie bez zmian. Zasada dwóch wersji oznacza, że zasady blokowania oryginalnej wersji ceny powinny zapobiegać aktualizacjom. Dodatkowa wersja ceny powinna zawierać dokładnie takie same zasady co oryginalna wersja ceny z wyjątkiem daty początkowej oraz udostępniać selektywne użycie zasad blokowania zezwalających na aktualizacje. Określona data początkowa powinna zostać zaktualizowana o każdy zbiór zmian uwzględniających zaplanowaną datę aktywacji.

W tym przykładzie używany jeden dodatkowy wersji wyceny do zarządzania aktualizacjami w ciągu całego roku 2016. Więcej niż jedną wersję wyceny dodatkowe może służyć, takich jak oddzielną wersję dla każdej partii aktualizacje. Jeśli używanych jest kilka opcji dodatkowej wyceny, domyślnej wyraża się jako koszty aktywne, ponieważ koszty aktywne są rozciągnięte jest na kilka wersji.




