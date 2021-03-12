---
title: Podstawa ceny i umowy handlowe
description: Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db3a91807c0cfb51426c03eeaf7785168e6ad0de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006065"
---
# <a name="base-price-and-trade-agreements"></a>Podstawa ceny i umowy handlowe

[!include [banner](../includes/banner.md)]

Ta procedura poprowadzi przez proces tworzenia umów handlowych na cenę sprzedaży specyficznych dla kanału. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. W **okienku nawigacji** przejdź do **Moduły > Retail i Commerce > Zarządzanie cenami i rabatami > Grupy cenowe > Wszystkie grupy cenowe**. Grupy cenowe służą przypisywaniu umów handlowych do określonych kanałów. Używanie grup cenowych, aby przypisać umowy handlowe do kanału, pozwala stosować ceny specyficzne dla kanałów.  
2. Kliknij przycisk **Nowy**.
3. W polu **Grupy cenowe** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. Kliknij przycisk **Zapisz**.
6. Zamknij stronę.
7. W **okienku nawigacji** kliknij kolejno opcje **Moduły > Retail i Commerce > Kanały > Sklepy > Wszystkie sklepy**.
8. Na liście wybierz opcję „Nowy Jork”.
9. W okienku akcji kliknij pozycję **Sklep**.
10. Kliknij opcję **Grupy cenowe**.
11. Kliknij przycisk **Nowy**.
12. W polu **Grupy cenowe** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. Kliknij przycisk **Zapisz**.
15. Zamknij stronę.
16. Zamknij stronę.
17. W **okienku nawigacji** przejdź do **Moduły > Retail i Commerce > Produkty i kategorie > Zwolnione produkty według kategorii**.
18. Na liście kliknij łącze w wybranym wierszu.
19. Kliknij przycisk **Edytuj**.
20. Rozwiń skróconą kartę **Sprzedaż**.
21. W polu **Cena** wpisz liczbę. Ta cena jest używana, gdy nie znaleziono żadnych umów handlowych mających zastosowanie.  
22. Kliknij przycisk **Zapisz**.
23. W **Panelu akcji** kliknij **Sprzedaj**.
24. Kliknij opcję **Utwórz umowy handlowe**.
25. Kliknij przycisk **Nowy**.
26. W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
27. Na liście wybierz **Commerce**. W danych demonstracyjnych arkusz o nazwie **Commerce** ma domyślną relację **Cena (sprzedaż)**. Oznacza to, że wszystkie nowo tworzone wiersze domyślnie są dla umów handlowych na cenę sprzedaży.  
28. W **okienku akcji** kliknij pozycję **Wiersze**.
29. W polu **Typ kodu strony** wybierz opcję „Grupa”.
30. W polu **Wybór konta** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
31. Na liście znajdź i zaznacz odpowiedni rekord. Zakończy to operację łączenia kanału z grupą cenową, a następnie grupy z umową handlową.  
32. W polu **Relacja produktu** wpisz wartość.
33. W polu **Kwota w walucie** wpisz liczbę.
34. W skróconej karcie **Szczegóły** zaznacz lub usuń zaznaczenie pola wyboru **Znajdź następny**. Jeśli opcja **Znajdź następny** jest ustawiona na wartość „Tak”, aparat kalkulacji cen będzie wyszukiwał odpowiednie umowy handlowe z niższą ceną sprzedaży. Jeśli opcja **Znajdź następny** jest ustawiony na „Nie”, aparat kalkulacji cen przestanie szukać i użyje bieżącej umowy handlowej.  
35. Kliknij przycisk **Księguj**.
36. Kliknij przycisk **OK**.
37. Zamknij stronę.
38. W **okienku akcji** kliknij pozycję Sprzedaż.
39. Kliknij opcję **Cena sprzedaży**.

