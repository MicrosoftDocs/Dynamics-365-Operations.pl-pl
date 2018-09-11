--- 
title: "Tworzenie reguły Kanban dla zdarzenia sprzedaży"
description: "Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f1f66157b2e74ad1b490e10112cbc121ac9826fb
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-event-kanban-rule"></a>Tworzenie reguły Kanban dla zdarzenia sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura jest zorientowana na konfigurację potrzebną do utworzenia reguły Kanban uruchamianej podczas tworzenia zamówienia sprzedaży. Reguła kanban zdarzenia uzupełnia zapotrzebowania wynikające z wierszy zamówienia sprzedaży. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu.




## <a name="create-a-new-kanban-rule"></a>Utwórz nową regułę Kanban
1. Przejdź do okna Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.
    * Wybranie opcji Zdarzenie spowoduje, że reguła Kanban będzie inicjowana przez zdarzenie, na przykład utworzenie wiersza zamówienia sprzedaży.   Ustawienie jest stosowane do obszarów, gdzie każda karta Kanban powinna pokrywać konkretne zapotrzebowanie.  
4. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wybierz opcję Montaż końcowy.  
5. Rozwiń sekcję Szczegóły.
6. W polu Produkt wprowadź lub wybierz wartość.
    * Wybierz opcję L0050.  

## <a name="define-an-event"></a>Definiowanie zdarzenia
1. Rozwiń sekcję Zdarzenia.
2. W polu Zdarzenie sprzedaży wybierz opcję „Automatyczne”.
    * Wybranie zdarzenia sprzedaży Automatyczne spowoduje, że ta reguła Kanban będzie uruchamiana automatycznie, gdy wiersz sprzedaży pasuje do lokalizacji produktu i przyjęcia. W tej procedurze jest to produkt L0050 w magazynie 13.  
3. W polu Ilość minimalna dla zdarzenia ustaw wartość „50”.
    * Przy ilości minimalnej dla zdarzenia wynoszącej 50 reguła Kanban będzie wywoływana tylko przez zdarzenia z ilością 50 lub większą.  
4. Rozwiń sekcję Przepływ produkcji.
    * Należy zauważyć, że lokalizacją przyjęcia jest magazyn 13. Oznacza to, że ta reguła Kanban będzie uruchamiana dla tej lokalizacji.  
    * W tym przykładzie ta reguła Kanban będzie uruchamiana przez wiersz sprzedaży produktu L0050 z ilością 50 lub więcej w magazynie 13.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Tworzenie wiersza sprzedaży w celu wyzwalania reguły Kanban zdarzenia
1. Przejdź do okna Wszystkie zamówienia sprzedaży.
    * Podczas zapisywania reguły Kanban jest wyświetlane ostrzeżenie, co oznacza, że karty Kanban będą tworzone w czasie rzeczywistym podczas tworzenia zamówienia sprzedaży.  
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
    * Na przykład zaznacz US-003.  
4. Kliknij przycisk OK.
5. W polu Numer pozycji wpisz „L0050”.
6. W polu Oddział wpisz wartość „1”.
    * Wybierz Oddział 1, ponieważ magazyn 13 znajduje się w oddziale 1.  
7. W polu Magazyn wprowadź lub wybierz wartość.
    * W polu Magazyn ustaw 13.  
8. W polu Ilość wpisz wartość 75.
    * Wprowadź ilość 50 lub większą, aby wyzwalać utworzoną regułę Kanban.  

## <a name="verify-that-kanban-is-created"></a>Weryfikowanie utworzenia karty Kanban
1. Kliknij opcję Produkt i dostawa.
2. Kliknij opcję Wyświetl drzewo oznaczania transakcji.
    * Zwróć uwagę, że jest tworzona karta Kanban z taką samą ilością, jak ilość w wierszu sprzedaży. Można również wyświetlić wydania materiałów potrzebnych do wytworzenia produktu L0050. Jest to ostatni krok w tej procedurze.  


