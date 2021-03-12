---
title: Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów
description: Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19b4f80c6afa2634c469a23dfcd8dd8f151dd6cc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998710"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>Tworzenie reguły Kanban przy użyciu zdarzenia minimalnych zapasów

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na konfiguracji potrzebnej do utworzenia reguły Kanban za pomocą zdarzenia minimalnych zapasów, aby upewnić się, że określony produkt jest zawsze dostępny w określonej lokalizacji. Reguła kanban jest tworzona w celu przenoszenia materiału do lokalizacji, gdy poziom zapasów spadnie poniżej 200 sztuk. Uruchomienie przetwarzania powiązania zlecenia z popytem źródłowym powoduje utworzenie niezbędnych kart Kanban. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.


## <a name="create-a-new-kanban-rule"></a>Utwórz nową regułę Kanban
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

## <a name="set-the-minimum-quantity-for-the-item"></a>Ustawianie minimalnej ilości pozycji
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

## <a name="run-the-batch-event-creation-job"></a>Wykonywanie zadania tworzenia partii dla zdarzenia
1. Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Przetwarzanie wsadowe zadań Kanban > Przetwarzanie powiązań zlecenia z popytem źródłowym.
2. Kliknij przycisk OK.
3. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
4. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz utworzoną wcześniej regułę Kanban.  
5. Rozwiń sekcję Karty Kanban.
    * Należy zauważyć, że została utworzona karta Kanban w celu przeniesienia potrzebnego materiału do magazynu 12.  

