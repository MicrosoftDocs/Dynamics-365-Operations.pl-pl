---
title: Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban
description: Ta procedura skupia się na tworzeniu zasady obliczania liczby kart Kanban oraz dodaniu jej do reguły Kanban w celu zoptymalizowania wielkości i liczby kart Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fffd623104dc403e230128c9234521ad1e39c7bb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "352144"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na tworzeniu zasady obliczania liczby kart Kanban oraz dodaniu jej do reguły Kanban w celu zoptymalizowania wielkości i liczby kart Kanban. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla menedżera strumienia wartości. Procedura jest warunkiem wstępnym tworzenia procedury Obliczanie sugestii liczby kart Kanban. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Tworzenie nowej zasady obliczania liczby kart Kanban
1. Wybierz kolejno opcje Kontrola produkcji > Zadania okresowe > Obliczanie ilości na karcie Kanban > Zasady obliczania ilości na karcie Kanban.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
    * Na przykład wpisz Speaker2016.  
4. W polu Plan główny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz plan statyczny, aby obliczyć popyt.  
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk Zapisz.
8. W polu Minimalna ilość na karcie Kanban wpisz „1”.
    * Jest to dodatkowa liczba kart Kanban uwzględniona w obliczeniu liczby kart Kanban.  
9. W polu Współczynnik bezpieczeństwa ustaw wartość „1”.
    * Jest to współczynnik używany do obliczania dodatkowej ilości zapasu bezpieczeństwa.  
10. W polu Liczba dni w przód wpisz „30”.
    * Jest to liczba dni poprzedzających datę obliczenia liczby kart Kanban uwzględniona w obliczaniu popytu.  
11. W polu Liczba dni wstecz wpisz „30”.
    * Jest to liczba dni po dacie obliczenia liczby kart Kanban uwzględniona w obliczaniu popytu.  Wzór używany do obliczania jest wyświetlane z wartościami rzeczywistymi. Na przykład liczba kart Kanban = ((średni dzienny popyt x czas realizacji x 2,00) / ilość produktu na magazynową jednostkę obsługi) + 1  
12. Zamknij stronę.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Dodawanie zasady obliczania liczby kart Kanban do reguły Kanban
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Produkcja oszczędna > Reguły Kanban.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz regułę Kanban 000020 do wykonania tej procedury.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Przełącz rozwinięcie sekcji Zasady obliczania ilości na karcie Kanban.
5. Kliknij przycisk Dodaj.
    * Dodaj zasadę obliczania liczby kart Kanban, którą utworzono w poprzednim podzadaniu.  
6. Na liście oznacz wybrany wiersz.
7. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz zasadę Speaker2016, którą utworzono w poprzednim podzadaniu.  

