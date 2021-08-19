---
title: Oznaczenie transakcji produkcji oszczędnej z zamówień sprzedaży
description: Ta procedura skupia się na sprawdzeniu poprawności drzewa oznaczania transakcji z poziomu wiersza sprzedaży, gdzie towar jest produkowany za pomocą kart Kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63d3b17d5a5a387d000fbac7f7bbf4431d4febca75cc2a85c2c359ed479c911e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714891"
---
# <a name="lean-pegging-from-sales-orders"></a>Oznaczenie transakcji produkcji oszczędnej z zamówień sprzedaży

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na sprawdzeniu poprawności drzewa oznaczania transakcji z poziomu wiersza sprzedaży, gdzie towar jest produkowany za pomocą kart Kanban. Po weryfikacji drzewa oznaczania transakcji wszystkie zadania w systemie Kanban są zaplanowane. Jest to przydatne w scenariuszach zamawiania, gdzie osoba przyjmująca zamówienie musi się upewnić, że produkcja może zostać od razu rozpoczęta. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla specjalistów ds. przyjmowania zamówień pracujących w firmie stosującej zasady produkcji oszczędnej.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Tworzenie zamówienia sprzedaży dla towaru kontrolowanego w systemie Kanban
1. Przejdź do okna Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
    * Użyj wartości USA-001.  
4. Kliknij przycisk OK.
5. W polu Numer pozycji wpisz „L0001”.
6. W polu Ilość wpisz wartość 30.
    * Jest ważne, aby ilość była większa niż 24, co zapewni wyzwalanie reguły Kanban zdarzenia.  

## <a name="open-a-pegging-tree"></a>Otwieranie drzewa oznaczania transakcji 
1. Kliknij opcję Produkt i dostawa.
2. Kliknij opcję Wyświetl drzewo oznaczania transakcji.
    * Należy zauważyć, że drzewo oznaczania transakcji pokazuje wszystkie poziomy oznaczania transakcji potrzebne dla wiersza zamówienia sprzedaży. W tym przypadku istnieją dwa poziomy kart Kanban i wszystkie wymagane składniki.  

## <a name="plan-the-pegging-tree"></a>Planowanie drzewa oznaczania transakcji
1. W drzewie zaznacz element „Wiersz sprzedaży 000832\Kanban 000558”.
2. Rozwiń sekcję Zadania Kanban.
    * Należy zauważyć, że stan zadania w systemie Kanban to Niezaplanowane.  
3. Kliknij opcję Zaplanuj całe drzewo oznaczania transakcji.
    * Spowoduje to zaplanowanie wszystkich zadań w systemie Kanban w drzewie oznaczania transakcji oraz zmianę stanu zadania z Niezaplanowane na Zaplanowane.  
4. Odśwież stronę.
    * Należy zauważyć, że stan zadania w systemie Kanban zmienił się z Niezaplanowane na Zaplanowane.  
5. W drzewie zaznacz element „Wiersz sprzedaży 000832\Kanban 000558\Wydanie towaru L0001\Kanban 000559”.
    * Zadanie na drugiej karcie Kanban jest również zaplanowane, ponieważ całe drzewo oznaczania transakcji jest zaplanowane. Należy zauważyć, że stan zadania w systemie Kanban zmienił się z Niezaplanowane na Zaplanowane.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]