---
title: Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban
description: Ta procedura tworzy regułę Kanban poprzez użycie ustawienia zdarzenia wiersza Kanban w celu zainicjowania ssania z działania procesu.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bff5f16c1911739a29d50c546c3c2a9ab85c2371
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "350235"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura tworzy regułę Kanban poprzez użycie ustawienia zdarzenia wiersza Kanban w celu zainicjowania ssania z działania procesu. Reguła Kanban jest wyzwalana przez działania procesu Kanban, każde z ilością większą lub równą 25. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. To zadanie jest przeznaczone dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni wytwarzanie nowego lub zmodyfikowanego produktu w środowisku produkcji oszczędnej.


## <a name="create-a-kanban-rule"></a>Tworzenie reguły Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Strategia uzupełniania wybierz opcję „Zdarzenie”.
    * Spowoduje to wygenerowanie kart Kanban bezpośrednio z popytu. Operacja służy do ustawiania reguł, które definiują scenariusz produkcji na zamówienie.  
4. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wpisz lub wybierz czynność SpeakerAssemblyAndPolish. Pierwsze działanie produkcyjnej reguły Kanban musi być działaniem procesu w przepływie produkcji. Po wybraniu działania daty ważności działania są kopiowane do pola dat ważności reguły Kanban.  
5. Rozwiń sekcję Szczegóły.
6. W polu Produkt wpisz „L0001”.
7. Rozwiń sekcję Zdarzenia.
8. W polu Zdarzenie wiersza Kanban wybierz opcję „Automatyczne”.
    * Spowoduje to wygenerowanie kart Kanban dla zdarzenia na żądanie.  Pole służy do konfigurowania reguł Kanban, które uzupełniają materiały wymagane do obsługi działań od dostawcy do odbiorcy. Po wybraniu opcji Automatyczne karty Kanban zdarzeń są tworzone z popytem. To ustawienie jest zalecane, jeśli oczekujesz, że produkcja zostanie wykonana tego samego dnia.  
9. W polu Ilość minimalna dla zdarzenia ustaw wartość „25”.
    * Karty Kanban zdarzeń są generowane, gdy ilość zapotrzebowania jest równa lub wyższa niż wartość w tym polu. Jest to przydatne, jeśli chcesz wyprodukować ilość z zamówienia mniejszą niż wartość w tym polu na jednej maszynie, a większą niż wartość w tym polu na innej maszynie.  
10. Kliknij przycisk Zapisz.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Tworzenie zamówienia sprzedaży i wyzwalanie łańcucha Kanban
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
    * W ustawieniu Konto odbiorcy zaznacz wartość US-003, Forest Wholesales.  
4. Kliknij przycisk OK.
5. W polu Numer pozycji wpisz „L0001”.
    * L0001 to towar, dla którego utworzono regułę Kanban.  
6. W polu Ilość wpisz wartość 27.
    * Ponieważ 27 jest większe niż ilość minimalna 25 określona w regule Kanban, spowoduje to wygenerowanie karty Kanban zdarzenia.  
7. W polu Oddział wpisz wartość „1”.
8. W polu Magazyn wprowadź lub wybierz wartość.
    * Wybierz magazyn 13.  
9. Kliknij przycisk Zapisz.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Wyświetlanie karty Kanban wygenerowanej przez regułę Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Rozwiń sekcję Karty Kanban.
    * Należy zauważyć, że karta Kanban dla ilości 27 została utworzona w celu przetwarzania działania na podstawie utworzonej reguły Kanban.  
    * To jest ostatni krok.  

