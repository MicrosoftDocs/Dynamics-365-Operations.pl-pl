---
title: Obliczanie sugestii liczby kart Kanban
description: Ta procedura skupia się na optymalizowaniu wielkości i liczby kart Kanban dla określonej reguły Kanban poprzez obliczenie liczby kart Kanban.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18d2a8dd2a8c132873744ba890ca6b1eb1fd34b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570137"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Obliczanie sugestii liczby kart Kanban

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na optymalizowaniu wielkości i liczby kart Kanban dla określonej reguły Kanban poprzez obliczenie liczby kart Kanban. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla menedżera strumienia wartości. Wcześniej należy wykonać procedurę Dodawanie nowej zasady obliczania liczby kart Kanban do reguły Kanban.


## <a name="create-a-kanban-quantity-calculation"></a>Tworzenie obliczenia liczby kart Kanban
1. Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Oblicz liczbę kart Kanban.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz „Speaker2016”.
4. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz zasadę utworzoną w procedurze Dodawanie nowej zasady obliczania liczby kart Kanban do reguły Kanban. Na przykład Speaker2016.  
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Reguła aktywna w dniu ustaw datę i godzinę „2012-12-17T08:00:00”.
    * Ta data stanowi podstawę do określenia, które reguły stałych Kanban są brane pod uwagę w obliczaniu liczby kart Kanban.  
7. W polu Data początkowa okresu zaspokojenia popytu ustaw datę i godzinę „2012-11-17T09:00:00”.
    * Data, od kiedy transakcje popytu w przeszłości są brane pod uwagę w obliczaniu liczby kart Kanban.  
8. W polu Data końcowa okresu zaspokojenia popytu ustaw datę i godzinę „2012-12-17T07:59:59”.
    * Data, do kiedy transakcje popytu w przeszłości są brane pod uwagę w obliczaniu liczby kart Kanban.  
9. W polu Data początkowa okresu popytu ustaw datę i godzinę „2012-12-17T08:00:00”.
    * Data, od kiedy transakcje bieżącego popytu są brane pod uwagę w obliczaniu liczby kart Kanban.  
10. W polu Data końcowa okresu popytu ustaw datę i godzinę „2013-01-16T07:59:59”.
    * Data, do kiedy transakcje bieżącego popytu są brane pod uwagę w obliczaniu liczby kart Kanban.  

## <a name="generate-kanban-quantity-proposal"></a>Generowanie propozycji liczby kart Kanban
1. Kliknij przycisk Zapisz.
2. Kliknij przycisk Generuj.
    * Spowoduje to wygenerowanie wiersza propozycji liczby kart Kanban dla reguły Kanban 000020.  

## <a name="run-kanban-quantity-calculation"></a>Obliczanie liczby kart Kanban
1. Kliknij przycisk Oblicz.
    * Spowoduje to obliczenie propozycji liczby kart Kanban.  
2. Kliknij przycisk OK.
3. Na liście oznacz wybrany wiersz.
    * Należy zauważyć, że sugerowana liczba kart Kanban wynosi 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Zmiana ilości produktu i ponowne obliczanie
1. W polu Ilość produktu ustaw wartość „5”.
2. Kliknij przycisk Oblicz.
3. Kliknij przycisk OK.
    * Zwróć uwagę, że przy liczbie kart Kanban 5 sugestia zmienia się na liczbę kart Kanban 4.  
    * Jest to spowodowane przez fakt, że przy mniejszej ilości produktu potrzeba więcej kart Kanban do zaspokojenia popytu.  

## <a name="update-kanban-rule"></a>Aktualizacja reguły Kanban
1. W polu Data aktywacji reguły wprowadź datę i godzinę.
    * W polu „Reguła aktywna w dniu” ustaw datę w przyszłości. Na przykład dzień dzisiejszy + jeden rok.  
2. Kliknij przycisk Aktualizuj.
3. Kliknij przycisk OK.
4. Zamknij stronę.

## <a name="validate-change-on-kanban-rule"></a>Sprawdzanie poprawności zmiany w regule Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz regułę Kanban, która została utworzona w poprzednim podzadaniu. Powinna to być pierwsza reguła Kanban na liście posortowanej według numerów.  
3. Przełącz rozwinięcie sekcji Szczegóły.
    * Zwróć uwagę na data obowiązywania, co oznacza, że ta reguła nie jest aktywowana przed tą datą.  
4. Przełącz rozwinięcie sekcji Ilości.
    * Należy zauważyć, że jest to domyślna ilość wprowadzona w obliczaniu liczby kart Kanban.  
    * Należy zauważyć, że jest to stała liczba kart Kanban 4 z obliczenia liczby kart Kanban.  
5. Kliknij kartę ListPanel.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]