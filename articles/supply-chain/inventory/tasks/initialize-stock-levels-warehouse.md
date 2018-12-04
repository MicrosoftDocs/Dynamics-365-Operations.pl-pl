--- 
title: "Inicjowanie poziomów zapasów w magazynie"
description: "W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych)."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45c93febbbc4ea78fe2b87735ed96fd773605d96
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Inicjowanie poziomów zapasów w magazynie

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak ręcznie zaktualizować dostępne zapasy przy użyciu arkusza przesunięć zapasów (można również aktualizować dostępne zapasy przez importowanie transakcji w jednostkach danych). Zadania z przewodnika można wykonać na danych firmy demonstracyjnej USMF, gdzie wszystkie warunki wstępne, takie jak nazwa arkusza, ustawienia towaru, profile księgowania i konta, są dostępne. Przewodnik proponuje określone wartości dla używanego towaru i wymiarów. Jeśli wybierzesz inny towar, może być konieczne wprowadzenie wartości dla innych wymiarów.

1. Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Przesunięcie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz opcję IMov.
    * Najlepiej korzystać z różnych szablonów nazw arkuszy do różnych celów służbowych.  
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Konto przeciwstawne wpisz wartość „140200”.
    * To jest konto przeciwstawne, które będzie kontem domyślnym w wierszach arkusza. Istnieje możliwość zastąpienia wartości domyślnej, aby przypisać różne konta przeciwstawne poszczególnym wierszom.  
7. Kliknij przycisk OK.
8. Kliknij przycisk Nowy.
9. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Wybierz towar A0001.
11. Na liście kliknij łącze w wybranym wierszu.
12. Kliknij kartę Wymiary magazynowe.
13. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Wybierz oddział 1.
15. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
16. Wybierz magazyn 13.
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Wybierz lokalizację 13.
20. Wprowadź liczbę w polu Ilość.
21. Kliknij przycisk Zapisz.
22. Kliknij przycisk Księguj.
23. Zaznacz lub usuń zaznaczenie pola wyboru Przenoszenie wszystkich błędów księgowania do nowego arkusza.
    * Jeśli ta opcja jest włączona, wszystkie wiersze, których księgowanie się nie powiedzie, będą kopiowane do nowego arkusza. Informacje w dzienniku mogą służyć do rozwiązywania problemów i ponownego księgowania wierszy.  
24. Kliknij przycisk OK.
25. Zamknij stronę.
26. Zamknij stronę.


