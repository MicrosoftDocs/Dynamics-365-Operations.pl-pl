--- 
title: "Tworzenie reguły Kanban dla wypłaty"
description: "W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c3172f5c932b94b2a9e442286eb61159286297fb
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a>Tworzenie reguły Kanban dla wypłaty

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano konfigurację niezbędną do utworzenia reguły Kanban wycofania w celu przeniesienia materiałów w środowisku produkcji oszczędnej. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura jest przeznaczona dla inżyniera procesu lub menedżera strumienia wartości, gdy przygotowują oni uzupełnienie zapasów nowego lub zmodyfikowanego materiału.


## <a name="create-new-kanban-rule"></a>Tworzenie nowej reguły Kanban
1. Przejdź do okna Reguły Kanban.
2. Kliknij przycisk Nowy.
3. W polu Typ zaznacz opcję „Wycofanie”.
    * Typ Wycofanie jest używany w regułach Kanban do przenoszenia materiałów lub towarów.  
4. W polu Pierwsze działanie planu wprowadź lub wybierz wartość.
    * Wybierz opcję ReplenishSpeakerComponents.   Konfiguracja tego działania przewiduje przeniesienie składników z lokalizacji 11 w magazynie 11 do lokalizacji 12 w magazynie 12.  
5. W polu Produkt wprowadź lub wybierz wartość.
    * Wybierz opcję M0007.  
6. W polu Czas realizacji wpisz liczbę.
    * Na przykład 60.  
7. W polu Jednostka miary wprowadź lub wybierz wartość.
    * Na przykład Minuty.  

## <a name="set-quantities-for-kanban"></a>Ustawianie ilości dla karty Kanban
1. W polu Ilość domyślna ustaw wartość „5”.
    * Jest to ilość, która zostanie przeniesiona za pomocą każdej karty Kanban.  
2. W polu Stała liczba kart Kanban wpisz „2”.
    * Jest to ilość kart Kanban, które powinny być aktywne. W tym przypadku 2 karty Kanban przenoszą każda po 5 sztuk.  
3. W polu Minimum graniczne alertu wpisz „1”.
    * Służy do śledzenia minimalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym. Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.  
4. W polu Maksimum graniczne alertu wpisz „2”.
    * Służy do śledzenia maksymalnej liczby pełnych kart Kanban, które powinny istnieć w miejscu docelowym. Informacja ta jest na przykład wykorzystywana w przeglądach liczby kart Kanban.  

## <a name="create-kanbans"></a>Tworzenie kart Kanban
1. Kliknij przycisk Zapisz.
    * Aby można było tworzyć karty Kanban, musi być zapisana reguła Kanban.  
2. Kliknij przycisk Dodaj.
    * Należy zauważyć, że nie ma żadnych aktywnych kart Kanban, ponieważ sugerowana wartość w polu „Liczba nowych kart Kanban” wynosi 2, czyli jest równa wartości w polu „Stała liczba kart Kanban”.  
3. Kliknij przycisk Utwórz.
    * Spowoduje to utworzenie 2 kart Kanban.  
    * Należy zwrócić uwagę, że dla tej reguły Kanban wycofania zostały utworzone 2 karty Kanban, każda na 5 sztuk.  Jest to ostatni krok w tej procedurze.  


