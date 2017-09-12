--- 
title: "Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów"
description: "Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0c480b518925a8536ebb77d60fcf1f1a548b097f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji. Reguła kanban jest tworzona w celu przenoszenia materiału do lokalizacji, gdy poziom zapasów spadnie poniżej 200 sztuk. Uruchomienie przetwarzania powiązania zlecenia z popytem źródłowym powoduje utworzenie niezbędnych kart Kanban. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.


## Utwórz nową regułę Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Typ zaznacz opcję „Wycofanie”.
    * Ten typ służy do tworzenia kart Kanban przeniesienia.  
4. W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.
    * Strategia zdarzenia służy do tworzenia kart Kanban przeniesienia na podstawie zdarzenia. W dalszej części procedury zainicjujesz karty Kanban przeniesienia przy użyciu procesu uzupełniania zapasów.  
5. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wpisz lub wybierz czynność ReplenishSpeakerComponents. To działanie przeniesienia ma magazyn przyjęcia (wyjścia) oraz lokalizację 12, co oznacza, że materiały zostaną przeniesione do lokalizacji 12 w magazynie 12.  
6. Rozwiń sekcję Szczegóły.
7. W polu Produkt wprowadź lub wybierz wartość.
    * Wybierz opcję M0007.  
8. Rozwiń sekcję Zdarzenia.
9. W polu Zdarzenie uzupełniania zapasów wybierz opcję „Partia”.
    * Spowoduje to utworzenie kart Kanban w celu zaspokojenia potrzeb materiałowych w powiązanej lokalizacji podczas przetwarzania powiązania zlecenia z popytem źródłowym.  

## Ustawianie minimalnej ilości pozycji
1. Kliknij, aby śledzić łącze w polu Produkt.
2. Kliknij, aby otworzyć łącze znajdujące się w polu Numer towaru.
3. Rozwiń pole informacji Obraz produktu.
4. W okienku akcji kliknij opcję Plan.
5. Kliknij opcję Zapotrzebowanie na towary.
6. Kliknij przycisk Nowy.
7. Na liście oznacz wybrany wiersz.
8. W polu Magazyn wprowadź lub wybierz wartość.
    * W polu Magazyn ustaw 12.  
9. W polu Minimum ustaw wartość „200”.

## Wykonywanie zadania tworzenia partii dla zdarzenia
1. Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Przetwarzanie wsadowe zadań Kanban > Przetwarzanie powiązań zlecenia z popytem źródłowym.
2. Kliknij przycisk OK.
3. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
4. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz utworzoną wcześniej regułę Kanban.  
5. Rozwiń sekcję Karty Kanban.
    * Należy zauważyć, że została utworzona karta Kanban w celu przeniesienia potrzebnego materiału do magazynu 12.  


