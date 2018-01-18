--- 
title: Podstawa ceny i umowy handlowe
description: "Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d9692ce9ad282b76504588d8f796560c00773a8c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="base-price-and-trade-agreements"></a>Podstawa ceny i umowy handlowe

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Ceny i rabaty > Grupy cenowe > Wszystkie grupy cenowe.
    * Grupy cenowe służą przypisywaniu umów handlowych do określonych kanałów. Używanie grup cenowych, aby przypisać umowy handlowe do kanału, pozwala stosować ceny specyficzne dla kanałów.  
2. Kliknij przycisk Nowy.
3. W polu Grupy cenowe wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.
7. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > Sklepy sieci sprzedaży > Wszystkie sklepy sieci sprzedaży.
8. Na liście wybierz opcję „Nowy Jork”.
9. W okienku akcji kliknij pozycję Sklep.
10. Kliknij opcję Grupy cenowe.
11. Kliknij przycisk Nowy.
12. W polu Grupy cenowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
16. Zamknij stronę.
17. Wybierz kolejno opcje Handel detaliczny i inny > Produkty i kategorie > Zwolnione produkty według kategorii.
18. Na liście kliknij łącze w wybranym wierszu.
19. Kliknij przycisk Edytuj.
20. Przełącz rozwinięcie sekcji Sprzedaż.
21. W polu Cena wpisz liczbę.
    * Ta cena jest używana, gdy nie znaleziono żadnych umów handlowych mających zastosowanie.  
22. Kliknij przycisk Zapisz.
23. W okienku akcji kliknij pozycję Sprzedaż.
24. Kliknij opcję Utwórz umowy handlowe.
25. Kliknij przycisk Nowy.
26. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
27. Z listy wybierz pozycję „Handel detaliczny”.
    * W danych demonstracyjnych arkusz o nazwie „Handel detaliczny” ma domyślną relację „Cena (sprzedaż)”. Oznacza to, że wszystkie nowo tworzone wiersze domyślnie są dla umów handlowych na cenę sprzedaży.  
28. Kliknij przycisk Wiersze.
29. W polu Kod konta wybierz opcję „Grupa”.
30. W polu Wybór konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
31. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zakończy to operację łączenia kanału z grupą cenową, a następnie grupy z umową handlową.  
32. W polu Relacja towaru wpisz wartość.
33. W polu Kwota w walucie wpisz liczbę.
34. Zaznacz pole wyboru Znajdź następny lub usuń jego zaznaczenie.
    * Jeśli opcja Znajdź następny jest ustawiona na wartość „Tak”, aparat kalkulacji cen będzie wyszukiwał odnośne umowy handlowe z niższą ceną sprzedaży. Jeśli opcja Znajdź następny jest ustawiony na „Nie”, aparat kalkulacji cen przestanie szukać i użyje bieżącej umowy handlowej.  
35. Kliknij przycisk Księguj.
36. Kliknij przycisk OK.
37. Zamknij stronę.
38. W okienku akcji kliknij pozycję Sprzedaż.
39. Kliknij opcję Cena sprzedaży.


