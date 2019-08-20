---
title: Konfigurowanie reguł dla prowizji od sprzedaży
description: W tej procedurze pokazano, jak skonfigurować oraz włączyć obliczanie i śledzenie prowizji od sprzedaży.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16b0525c0fd133b2f41013e9b7daf47466e15ffe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833937"
---
# <a name="set-up-sales-commission-rules"></a>Konfigurowanie reguł dla prowizji od sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak skonfigurować oraz włączyć obliczanie i śledzenie prowizji od sprzedaży. W procedurze pokazano, jak utworzyć grupy odbiorców i prowizji za towary, a następnie jak połączyć wybranego odbiorcę i produkt z odpowiednimi grupami. Te grupy są następnie używane w konfiguracji obliczania prowizji do tworzenia kombinacji odbiorcy, towaru i przedstawicieli handlowych, które muszą pasować do zamówienia sprzedaży, aby uprawniać sprzedawców do prowizji. Tworzenie grup odbiorców i prowizji za towary jest opcjonalne, ponieważ można obliczenia prowizji można również wykonywać dla poszczególnych odbiorców i/lub towarów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-commission-groups-and-commission-rates"></a>Konfigurowanie grup prowizji i stawek prowizji
1. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy odbiorców dla prowizji.
2. Kliknij przycisk Nowy.
3. W polu Grupa wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.
7. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy towarów.
8. Kliknij przycisk Nowy.
9. W polu Grupa wpisz wartość.
10. W polu Nazwa wpisz wartość.
11. Zamknij stronę.
12. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Grupy sprzedaży.
    * Grupa prowizji sprzedaży określa pracowników mających role przedstawicieli handlowych, którzy kwalifikują się do otrzymywania prowizji, gdy odbiorca skojarzony z właściwą grupą sprzedaży kupuje określone towary.  
    * W danych firmy demonstracyjnej USMF jest grupa sprzedaży o nazwie „Przedstawicieli handlowi w Stanach Zjednoczonych”.  
13. W okienku akcji kliknij pozycję Ogólne.
14. Kliknij opcję Przedstawiciel handlowy.
    * Na stronie Przedstawiciel handlowy jest wyświetlana lista sprzedawców w firmie, którzy są skojarzeni z określoną grupą prowizji. Do tej samej grupy można przypisać wielu przedstawicieli handlowych oraz zdefiniować ich odpowiednie udziały w całkowitej wartości prowizji jako wartości procentowe. Łączny udział wszystkich pracowników w prowizji nie może przekraczać 100.  
15. Na liście oznacz wybrany wiersz.
16. Kliknij przycisk Edytuj.
17. W polu Wielkość prowizji ustaw wartość „50”.
18. Kliknij przycisk Nowy.
19. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
20. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „Susan Burk”.
21. Kliknij opcję Wybierz.
22. W polu Wielkość prowizji ustaw wartość „50”.
23. Kliknij przycisk Zapisz.
24. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Naliczanie prowizji.
    * Na stronie Naliczanie prowizji można zdefiniować stawkę prowizji, którą pracownik będzie otrzymywał za transakcję sprzedaży, jeśli zawiera ona wstępnie zdefiniowaną kombinację odbiorcy i produktu. W ramach konfiguracji stawki prowizji należy określić podstawę obliczania prowizji oraz wskazać, czy uwzględnić lub wykluczyć rabaty. Można również wprowadzić okres ważności wskazujący, kiedy stawka prowizji jest aktywna.  
25. Kliknij przycisk Nowy.
26. W polu Kod towaru zaznacz opcję „Grupa”.
27. W polu Relacja towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
28. Na liście odszukaj i zaznacz utworzoną wcześniej grupę.
29. Na liście kliknij łącze w wybranym wierszu.
30. W polu Kod odbiorcy wybierz opcję „Grupa”.
31. W polu Relacja odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
32. Na liście zaznacz utworzoną wcześniej grupę.
33. W polu Relacja przedstawiciela handlowego kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
34. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zachowaj opcję „Przed rabatem wiersza”.  
    * Zachowaj opcję „Przychód” jako podstawę obliczania wartości prowizji.    
35. W polu Procent prowizji wpisz liczbę.
36. Kliknij przycisk Zapisz.

## <a name="setting-up-commission-posting"></a>Konfigurowanie księgowania prowizji
1. Wybierz kolejno opcje Sprzedaż i marketing > Prowizje > Księgowanie prowizji.
    * Prowizje są płatne na rzecz pracowników i dlatego muszą być tak skonfigurowane, aby zapewniać poprawne księgowanie finansowe na odpowiednich kontach w księdze głównej. Służy do tego strona Księgowanie prowizji. Przejrzyj konfigurację dostępną dla bieżącej firmy. Na ogół kwoty prowizji są księgowane na dedykowanym koncie wydatków i kompensowane na dedykowanym koncie rozrachunków z dostawcami. Jeśli nie masz skonfigurowanych reguł księgowania prowizji, system nie będzie w stanie wykonać fakturowania zamówienia sprzedaży zawierającego uprawnione prowizje.  
2. Zamknij stronę.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Przypisywanie grupy prowizji do odbiorcy i produktu
1. Wybierz kolejno opcje Sprzedaż i marketing > Odbiorcy > Wszyscy odbiorcy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. Rozwiń sekcję Ustawienia domyślne zamówienia sprzedaży.
6. W polu Grupa prowizji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście zaznacz utworzoną wcześniej grupę.
8. W polu Grupa sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Kliknij przycisk Zapisz.
11. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
12. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Numer towaru z wartością „T0020”.
13. Na liście kliknij łącze w wybranym wierszu.
14. Kliknij przycisk Edytuj.
15. Rozwiń sekcję Sprzedaż.
16. W polu Grupa prowizji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
17. Na liście zaznacz utworzoną wcześniej grupa prowizji.

