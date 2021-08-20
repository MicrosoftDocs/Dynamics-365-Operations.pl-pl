---
title: Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban
description: Ta procedura tworzy regułę Kanban poprzez użycie ustawienia zdarzenia wiersza Kanban w celu zainicjowania ssania z działania procesu.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b6a589d95fde61cbd6743f9e3e3170a1b8d6f91613cde0df94037872b491018
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746898"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Tworzenie reguły Kanban przy użyciu zdarzenia wiersza karty Kanban

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]