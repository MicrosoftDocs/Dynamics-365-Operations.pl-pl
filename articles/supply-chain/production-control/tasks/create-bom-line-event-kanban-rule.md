--- 
title: "Tworzenie reguły Kanban dla zdarzenia wiersza BOM"
description: "To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej."
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a>Tworzenie reguły Kanban dla zdarzenia wiersza BOM

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

To zadanie skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban zdarzenia w celu zapewnienia dostaw dla wierszy BOM produkcji w mieszanym środowisku produkcji oszczędnej i klasycznej. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. Zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.


## <a name="create-a-new-kanban-rule"></a>Utwórz nową regułę Kanban
1. Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Typ zaznacz opcję „Wycofanie”.
    * Typ Wycofanie służy do tworzenia zadań Kanban przeniesienia.  
4. W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.
    * Strategia zdarzenia jest wybierana, aby utworzyć przeniesienie pozycji z kart Kanban na podstawie zdarzenia. W dalszej części przewodnika po zadaniach zainicjujemy tę operację poprzez oszacowanie zlecenia produkcyjnego.  
5. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wpisz lub wybierz czynność ReplenishSpeakerComponents. To działanie przeniesienia ma magazyn przyjęcia (wyjścia) oraz lokalizację 12, co oznacza, że materiał zostanie przeniesiony do lokalizacji 12 w magazynie 12.  
6. Rozwiń sekcję Szczegóły.
7. W polu Produkt wprowadź lub wybierz wartość M0001.
8. Rozwiń sekcję Zdarzenia.
9. W polu Zdarzenie wiersza BOM wybierz opcję „Automatyczne”.
    * Z ustawieniem Automatyczne w polu Zdarzenie wiersza BOM zostanie utworzone zadanie Kanban, aby zaspokoić potrzeby materiałowe wierszy BOM zlecenia produkcyjnego.  
10. Zamknij stronę.

## <a name="create-and-modify-a-new-production-order"></a>Tworzenie i modyfikowanie nowego zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
2. Kliknij opcję Nowe zlecenie produkcyjne.
3. W polu Numer towaru wprowadź lub wybierz wartość.
    * Wprowadź lub wybierz wartość „L0001”. Używamy towaru L0001, ponieważ towar M0001 jest zawarty w BOM towaru L0001.  
4. Kliknij przycisk Utwórz.
5. Na liście kliknij łącze w wierszu towaru L0001.
6. Kliknij opcję BOM.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij przycisk Edytuj.
9. W polu Typ wiersza wybierz opcję „Ustalona dostawa”.
    * Została wybrana opcja Ustalona dostawa, aby spowodować tworzenie dostaw za pomocą karty Kanban.  
10. W polu Zużycie zasobów wybierz opcję Nie.
    * Wyczyszczenie pola wyboru Zużycie zasobów pozwoli nam zmienić magazyn.  
11. Rozwiń sekcję Wymiary magazynowe.
12. W polu Magazyn wpisz wartość „12”.
    * Ustawiono magazyn 12, ponieważ jest to magazyn wyjściowy dla działania wycofania.  
13. W polu Lokalizacja wpisz „12”.
    * Ustawiono lokalizację 12, ponieważ jest to lokalizacja wyjściowa dla działania wycofania.  
14. Zamknij stronę.
15. Zamknij stronę.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Szacowania zlecenia produkcyjnego i wyświetlanie utworzonej karty Kanban
1. Kliknij przycisk Szacuj.
    * Szacowanie zlecenia produkcyjnego wywoła tworzenie powiązanej karty Kanban w celu dostarczenia towaru M0001 .  
2. Kliknij przycisk OK.
3. Zamknij stronę.
4. Zamknij stronę.
5. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
6. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz regułę Kanban zdarzenia utworzoną dla towaru M0001.  
7. Rozwiń sekcję Karty Kanban.
8. Na liście oznacz wybrany wiersz.
    * Zwróć uwagę na kartę Kanban utworzoną w celu dostarczenia towaru M0001 dla szacowanego zlecenia produkcyjnego.  
    * To jest ostatni krok!  


