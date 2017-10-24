--- 
title: Tworzenie harmonogramu dostaw
description: "W tej procedurze pokazano sposób tworzenia harmonogramu dostaw na podstawie zamówienia sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 02/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 956edeac33f8531ecebef64301f2318333000429
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-delivery-schedule"></a>Tworzenie harmonogramu dostaw

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia harmonogramu dostaw na podstawie zamówienia sprzedaży. Harmonogram dostaw jest używany w reakcji na żądanie dostarczenia ilości z zamówienia lub oferty w kilku dostawach. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="create-delivery-schedule"></a>Tworzenie harmonogramu dostaw
1. Przejdź do okna Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.
5. W polu Numer towaru wprowadź lub wybierz wartość.
6. W polu Ilość wprowadź liczbę większą niż 1.
7. Kliknij wiersz Zamówienie sprzedaży.
8. Kliknij przycisk Harmonogram dostaw.
    * Strona Harmonogram dostaw to miejsce, gdzie można określić liczbę wysyłek, w których łączna ilość z wiersza zamówienia zostanie dostarczona do odbiorcy.    
    * Domyślnie system kopiuje łączną ilość i inne szczegóły dostawy z oryginalnego wiersza sprzedaży do pierwszego wiersza harmonogramu dostawy. W tym przykładzie utworzymy harmonogram dla dwóch wysyłek, gdzie data drugiej wysyłki będzie przesunięta o tydzień względem daty pierwszej wysyłki.  
9. W polu Ilość wprowadź liczbę będącą częścią całkowitej ilości.
10. Kliknij przycisk Nowy.
11. W polu Ilość wprowadź pozostałą ilość.
12. W polu Żądana data wysyłki wprowadź datę przypadającą tydzień po dacie z pierwszego wiersza dostawy.
    * Dwie opcje na skróconej karcie Konwersja opłat kontrolują sposób rozdziału opłat między wiersze harmonogramu dostawy po przypisaniu do oryginalnego wiersza zamówienia. Jeśli wybierzesz opcję Kopiuj kwoty brutto, ta sama kwota opłaty zostanie skopiowana do każdego wiersza. Opcja Przenieś do wierszy dostawy rozdziela opłatę równo między wszystkie wierszy dostawy.  
    * Można dzielić tylko opłaty stałe, natomiast opłaty zmienne zostaną skopiowane do wierszy.  
13. Odsuń kursor z drugiego wiersza dostawy, a nastąpi aktualizacja zawartości strony.
    * Ilość całkowitą przydzieloną do wierszy harmonogramu dostaw można śledzić w polach Razem i Pozostałe. Jeśli pozostała ilość wynosi zero, cała ilość z oryginalnego wiersza została przydzielona do harmonogramu.   
14. Kliknij przycisk OK.
    * Harmonogram dostaw został skopiowany do wierszy zamówienia.   
    * Oryginalny wiersz zamówienia, nazywany wierszem handlowym, został przekonwertowany na wiersz zamówienia z wieloma dostawami. Jest oznaczony specjalną ikoną i pełni rolę nagłówka wierszy dostawy.  
    * Te dwa nowe wiersze, nazywane wierszami dostawy, tworzą jeden harmonogram dostaw. Zamówienie będzie przetwarzane dla tych wierszy, a nie dla oryginalnego wiersza. Jeśli są drukowane dokumenty takie jak potwierdzenia, listy pobrania, dokumenty dostawy lub faktury, wyświetlane są tylko wiersze dostaw.   
    * Wiersze dostawy mogą mieć różne daty dostawy, ilości, metody dostawy i wymiary magazynowania, takie jak oddział i magazyn. Jednak wymiary produktów zawsze muszą być takie same jak w wierszu handlowym i nie można ich zmienić.  
15. W polu Ilość wprowadź liczbę większą niż obecna.
16. Zaznacz wiersz handlowy, aby zobaczyć wynik ponownego obliczania ilości.
17. W okienku akcji kliknij opcję Pobierz i zapakuj.
18. Kliknij opcję Księguj dokument dostawy.
19. Rozwiń sekcję Parametry.
20. W polu Ilość zaznacz opcję Wszystko.
    * Należy zauważyć, że dokument dostawy będzie tworzony dla dwóch wierszy harmonogramu dostaw, a nie oryginalnego wiersza zamówienia.  
21. W polu Drukuj dokument dostawy zaznacz opcję Tak.
22. Kliknij przycisk OK.
23. Kliknij przycisk Tak.
24. Zamknij stronę.


