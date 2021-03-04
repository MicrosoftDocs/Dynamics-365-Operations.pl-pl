---
title: Tworzenie reguły Kanban ze stałą ilością dla produkcji
description: Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia stałej reguły Kanban produkcji w celu wyzwalania działań przekształcających w komórce roboczej w środowisku produkcji oszczędnej.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24eb705bf2de0d175a8a03a4e89ad11c51f15d15
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434946"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Tworzenie reguły Kanban ze stałą ilością dla produkcji

[!include [banner](../../includes/banner.md)]

Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia stałej reguły Kanban produkcji w celu wyzwalania działań przekształcających w komórce roboczej w środowisku produkcji oszczędnej. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.


## <a name="create-new-kanban-rule"></a>Tworzenie nowej reguły Kanban
1. Przejdź do okna Reguły Kanban.
2. Kliknij przycisk Nowy.
    * Zauważ, że domyślnym typem jest Produkcja, a pole Strategia uzupełniania ma wartość Stały. Nie trzeba zmieniać tych parametrów.  
3. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Jest to działanie, które będzie wykonywane dla kart Kanban opartych na tej regule Kanban.  Wybierz opcję „SpeakerTestAndPackaging”.  
4. Rozwiń sekcję Szczegóły.
5. W polu Produkt wprowadź lub wybierz wartość.
    * Wybierz opcję L0050.  
6. W polu Jednostka miary wprowadź lub wybierz wartość.
    * Wybierz opcję Minuty.  
7. W polu Czas realizacji wpisz liczbę.
    * Wpisz 5.  

## <a name="set-quantities"></a>Konfigurowanie ilości
1. Rozwiń sekcję Ilości.
2. W polu Ilość domyślna ustaw wartość „10”.
    * Jest to ilość, która zostanie przeniesiona za pomocą każdej karty Kanban.  
3. Zaznacz pole wyboru Odchylenie ilości produktów.
    * Dzięki temu zaznaczone karty Kanban można wypełnić z odchyleniem od domyślnej ilości.  Aby umożliwić wypełnianie kart Kanban ilościami od 8 do 12, ustaw dla obu odchyleń wartość 2.  
4. W polu Odchylenie poniżej ustaw wartość „2”.
    * Umożliwi to wypełnienie ilością 10-2 = 8.  
5. W polu Odchylenie powyżej ustaw wartość „2”.
    * Umożliwi to wypełnienie ilością 10+2 = 12.  
6. W polu Stała liczba kart Kanban wprowadź liczbę.
    * Jest to ilość kart Kanban, które powinny być aktywne. W tym przypadku jest to 5 kart Kanban, każda na ilość 10.  
7. W polu Minimum graniczne alertu wpisz „2”.
    * Służy do śledzenia minimalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym. Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.  
8. W polu Maksimum graniczne alertu wpisz „4”.
    * Służy do śledzenia maksymalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym. Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.  
9. W polu Ilość w automatycznym planowaniu wpisz „1”.
    * Ustawienie wartości 1 oznacza, że każda karta kanban będzie automatycznie planowana.   Jeśli wprowadzono by liczbę 3, karty Kanban byłyby planowane dopiero wtedy, gdy istniałyby 3 puste karty Kanban gotowe do planowania. Jest to przydatne do grupowania pracy i unikania zbyt wielu czynności konfiguracyjnych.  

## <a name="create-kanbans"></a>Tworzenie kart Kanban
1. Rozwiń sekcję Karty Kanban.
2. Kliknij przycisk Zapisz.
    * Aby można było tworzyć karty Kanban, musi być zapisana reguła Kanban.  
3. Kliknij przycisk Dodaj.
    * Należy zauważyć, że nie ma żadnych aktywnych kart Kanban. Z tego powodu sugerowana wartość w polu „Liczba nowych kart Kanban” wynosi 5. Jest to równe wartości w polu „Stała liczba kart Kanban”.  
4. Kliknij przycisk Utwórz.
    * Spowoduje to utworzenie 5 kart Kanban.  
    * Należy zwrócić uwagę, że dla tej reguły Kanban produkcji zostało utworzonych 5 kart Kanban, każda na 10 sztuk. Jest to ostatni krok w tej procedurze.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]