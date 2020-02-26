---
title: Definiowanie programów lojalnościowych
description: W tej procedurze pokazano sposób konfigurowania programu lojalnościowego z dwoma warstwami lojalnościowymi.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b178f1c6a71b34b70db4dbcd1765117215a4d2a1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023668"
---
# <a name="define-loyalty-programs"></a>Definiowanie programów lojalnościowych

[!include [task guide banner](../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania programu lojalnościowego z dwoma warstwami lojalnościowymi. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Retail i Commerce > .. > Programy lojalnościowe.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij przycisk Dodaj wiersz.
6. W polu Poziom wprowadź liczbę.
7. W polu Warstwa nadaj nazwę warstwie lojalnościowej.
8. W polu Opis wpisz wartość.
9. W polu Zakres dat kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Ten zakres dat powinien sięgać w przyszłość. Na przykład jeśli wybrany interwał dat dla warstwy Gold ma jeden rok, wszyscy odbiorcy, którzy kwalifikują się do warstwy Gold, mogą otrzymać nagrody przypisane do warstwy Gold poziomu przez okres jednego roku. Jeśli odbiorca kwalifikuje się ponownie do warstwy Gold, kiedy jest w tej warstwie, data wygaśnięcia jego statusu w tej warstwie zostaje przedłużona o kolejny rok od daty ponownej kwalifikacji.  
10. Na liście kliknij łącze w wybranym wierszu.
11. Kliknij przycisk Dodaj wiersz.
12. W polu Poziom wprowadź liczbę.
13. W polu Warstwa nadaj nazwę warstwie lojalnościowej.
14. W polu Opis wpisz wartość.
15. W polu Zakres dat kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
16. Na liście kliknij łącze w wybranym wierszu.
17. Kliknij przycisk Zapisz.
18. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zasady warstwy definiują minimalną liczbę punktów lojalnościowych, jaką należy uzyskać w przedziale czasu, aby kwalifikować się do warstwy.  
19. Przełącz rozwinięcie sekcji Zasady warstwy.
20. Kliknij przycisk Nowy.
    * Można mieć kilka zasad warstwy w jednej warstwie. Na przykład można mieć trzy różne kryteria osiągnięcia warstwy: wydanie 500 USD w ciągu miesiąca, wydanie 1000 USD w ciągu roku i zawarcie 20 transakcji w ciągu roku. W tym celu należałoby utworzyć trzy zasady warstwy.  
21. W polu Punkty lojalnościowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Powinien to być niewymienialny punkt lojalnościowy.  
22. Na liście kliknij łącze w wybranym wierszu.
23. W polu Minimalna liczba przyznanych punktów lojalnościowych wpisz liczbę.
    * Jeśli wszyscy odbiorcy mogą kwalifikować się do najniższej warstwy lojalnościowej po prostu przez uczestnictwo w programie, wprowadź „0”.  
24. W polu Zakres dat oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Ten zakres dat powinien sięgać w przeszłość. Tylko punkty zdobyte w tym przedziale dat wliczają się do minimalnej wartości przyznanych punktów.  
25. Na liście kliknij łącze w wybranym wierszu.
26. Kliknij przycisk Zapisz.
27. Na liście znajdź i zaznacz odpowiedni rekord.
28. Kliknij przycisk Nowy.
29. W polu Punkty lojalnościowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
30. Na liście kliknij łącze w wybranym wierszu.
31. W polu Minimalna liczba przyznanych punktów lojalnościowych wpisz liczbę.
32. W polu Zakres dat oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Ten zakres dat powinien sięgać w przeszłość.  
33. Na liście kliknij łącze w wybranym wierszu.
34. Kliknij przycisk Zapisz.
35. Kliknij opcję Grupy cenowe.
    * Jeśli chcesz przyznać odbiorcom rabaty lojalnościowe, musisz przypisać jedną lub więcej grup cenowych do programu lojalnościowego i do rabatów. Najlepiej nie mieszać grup cenowych między różnymi typami rozwiązań rabatowych.  Na przykład nie używaj jednej grupy cenowej dla rabatu lojalnościowego i rabat kanału.  
36. W polu Grupa cenowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Łącze Grupy cenowe u góry strony jest dla programu lojalnościowego. Łącze Grupy cenowe na skróconej karcie Warstwy programu jest tylko dla określonej warstwy lojalności.  
37. Na liście kliknij łącze w wybranym wierszu.
38. Kliknij przycisk Zapisz.
39. Zamknij stronę.
40. Kliknij przycisk Zapisz.

