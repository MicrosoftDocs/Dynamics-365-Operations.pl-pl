---
title: Zarządzanie aktualizacjami kosztu standardowego
description: Aktualizacjami dotyczącymi danych kosztów standardowych można zarządzać za pomocą dwóch różnych metod — metody jednej wersji lub metody dwóch wersji.
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e72d4e90ac83787ed7c58d91c2102696acfac68
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "367554"
---
# <a name="manage-standard-cost-updates"></a>Zarządzanie aktualizacjami kosztu standardowego

[!include [banner](../includes/banner.md)]

Aktualizacjami dotyczącymi danych kosztów standardowych można zarządzać za pomocą dwóch różnych metod — metody jednej wersji lub metody dwóch wersji. 

Metoda jednej wersji zakłada użycie jednej wersji zawierającej wszystkie rekordy kosztów. Te rekordy obejmują koszty pierwotne i wszystkie aktualizacje kosztów.

Metoda dwóch wersji zakłada użycie jednej wersji z rekordami kosztów pierwotnych i drugiego z rekordami wszystkich aktualizacji kosztów. Główną zaletą metody dwóch wersji jest wyraźne nakreślenie i śledzenie zmian kosztów w oddzielnych wersjach ceny bez naruszania oryginalnej wersji ceny. Metody dwóch wersji można używać do identyfikowania wielu wzrostów kosztów z osobnymi wersjami ceny zawierającymi rekordy wzrostów kosztów. 

**Przykład** 

Poniżej pokazano, jak używać metod jednej i dwóch wersji do aktualizacji kosztów standardowych i środowisku produkcyjnym. Na przykład aktualizacje, które odzwierciedlają nowe pozycje lub korekty. Załóżmy, że metoda jednej wersji przedstawia koszty standardowe w bieżącym roku. Identyfikator dla tej wersji to 2016-STD. Wersja 2016-STD zawiera bieżące aktywne koszty wszystkich pozycji. Oprócz tego zawiera wszystkie kategorie kosztów związanych z marszrutami oraz wzory obliczeń narzutów znane na początku 2016 r. 2016-STD jest pierwotną wersją wyceny.

-   **Aktualizacja danych o kosztach w metodzie jednej wersji** — w metodzie jednej wersji wersja ceny pierwotnej 2016-STD zawiera wszystkie rekordy kosztów. Aktualizacje kosztu są rejestrowane w 2016-STD i otrzymują stan „Oczekujące”. Koszty oczekujące można wprowadzić ręcznie dla nowych zakupionych towarów lub można je uwzględnić w obliczeniach w celu wykazania odchyleń. Gdy używana jest metoda jednej wersji, obliczenia BOM nie wymagają zasady rezerwowości źródła danych, ponieważ wszystkie aktywne koszty są zawarte w tej wersji ceny. Po aktywacji kosztów oczekujących oryginalna wersja ceny 2016-STD będzie znów zawierać aktywne koszty bieżące.
-   **Metoda dwóch wersji** — W metodzie dwóch wersji aktualizacji danych o kosztach jest wymagana dodatkowa wersja ceny zawierająca wyłącznie aktualizacje. Przyjmijmy, że identyfikator będzie wyglądał następująco: 2016-STD-ZMIANY. Aktualizacje kosztu są rejestrowane w 2016-STD-CHANGES i otrzymują stan „Oczekujące”. W przypadku metody dwóch wersji obliczenia BOM kosztów oczekujących produkowanych elementów wymagają zasady rezerwowości źródła danych. Zasada rezerwowości może zostać wyrażona jako koszty aktywne lub określona wersja ceny 2016-STD, ponieważ oba parametry identyfikują źródło danych o kosztach, jeśli nie istnieje ono w wersji ceny 2016-STD-ZMIANY. Zasada rezerwowości może zostać wyrażona jako koszty aktywne lub określona wersja ceny 2016-STD, ponieważ oba parametry identyfikują źródło danych o kosztach, jeśli nie istnieje ono w wersji ceny 2016-STD-ZMIANY. Po aktywacji kosztów oczekujących dodatkowa wersja ceny 2016-STD-ZMIANY będzie zawierać aktywne koszty bieżące odzwierciedlające aktualizację, a oryginalna wersja ceny 2016-STD pozostanie bez zmian.Identyfikator dla tej wersji to 2016-STD-ZMIANY. Zasada dwóch wersji oznacza, że zasady blokowania oryginalnej wersji ceny powinny zapobiegać aktualizacjom. Dodatkowa wersja ceny powinna zawierać dokładnie takie same zasady co oryginalna wersja ceny z wyjątkiem daty początkowej oraz udostępniać selektywne użycie zasad blokowania zezwalających na aktualizacje. Określona data początkowa powinna zostać zaktualizowana o każdy zbiór zmian uwzględniających zaplanowaną datę aktywacji.

W tym przykładzie przedstawiono jedną dodatkową wersję wyceny służącą do zarządzania aktualizacjami za rok 2016. Można użyć więcej niż jedną dodatkową wersję wyceny, na przykład osobną wersję dla poszczególnych zbiorów aktualizacji. Jeśli używanych jest kilka opcji dodatkowej wyceny, domyślnej wyraża się jako koszty aktywne, ponieważ koszty aktywne są rozciągnięte jest na kilka wersji.





