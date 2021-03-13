---
title: Konfigurowanie reguł dla prowizji od sprzedaży
description: W tej procedurze pokazano, jak skonfigurować oraz włączyć obliczanie i śledzenie prowizji od sprzedaży.
author: omulvad
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b49865cf9d4073c2da7aa6ccc610b92055c711c1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010728"
---
# <a name="set-up-sales-commission-rules"></a>Konfigurowanie reguł dla prowizji od sprzedaży

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak skonfigurować oraz włączyć obliczanie i śledzenie prowizji od sprzedaży. W procedurze pokazano, jak utworzyć grupy odbiorców i prowizji za towary, a następnie jak połączyć wybranego odbiorcę i produkt z odpowiednimi grupami. Te grupy są następnie używane w konfiguracji obliczania prowizji do tworzenia kombinacji odbiorcy, towaru i przedstawicieli handlowych, które muszą pasować do zamówienia sprzedaży, aby uprawniać sprzedawców do prowizji. Tworzenie grup odbiorców i prowizji za towary jest opcjonalne, ponieważ można obliczenia prowizji można również wykonywać dla poszczególnych odbiorców i/lub towarów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-commission-groups-and-commission-rates"></a>Konfigurowanie grup prowizji i stawek prowizji
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły >Sprzedaż i marketing > Prowizje > Grupy odbiorców dla prowizji**.
2. Wybierz pozycję **Nowy**.
3. W polu **Grupa** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. Wybierz opcję **Zapisz**.
6. Zamknij stronę.
7. Wybierz kolejno opcje **Okienko nawigacji > Moduły >Sprzedaż i marketing > Prowizje > Grupy towarów**.
8. Wybierz pozycję **Nowy**.
9. W polu **Grupa** wpisz wartość.
10. W polu **Nazwa** wpisz wartość.
11. Wybierz opcję **Zapisz**.
12. Zamknij stronę.
13. Wybierz kolejno opcje **Sprzedaż i marketing > Prowizje > Grupy sprzedaży**.
    - Grupa prowizji sprzedaży określa pracowników mających role przedstawicieli handlowych, którzy kwalifikują się do otrzymywania prowizji, gdy odbiorca skojarzony z właściwą grupą sprzedaży kupuje określone towary.  
    - W danych firmy demonstracyjnej USMF jest grupa sprzedaży o nazwie „Przedstawicieli handlowi w Stanach Zjednoczonych”.  
14. W **okienku akcji** wybierz pozycję **Ogólne**.
15. Kliknij opcję **Przedstawiciel handlowy**. Na stronie Przedstawiciel handlowy jest wyświetlana lista sprzedawców w firmie, którzy są skojarzeni z określoną grupą prowizji. Do tej samej grupy można przypisać wielu przedstawicieli handlowych oraz zdefiniować ich odpowiednie udziały w całkowitej wartości prowizji jako wartości procentowe. Łączny udział wszystkich pracowników w prowizji nie może przekraczać 100. 
16. Na liście oznacz wybrany wiersz.
17. Wybierz opcję **Edycja**.
18. W polu **Wielkość prowizji** ustaw wartość „50”.
19. Kliknij przycisk **Nowy**.
20. W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
21. Skorzystaj z opcji **szybkiego filtrowania**, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „Susan Burk”.
22. Kliknij opcję **Wybierz**.
23. W polu **Wielkość prowizji** ustaw wartość „50”.
24. Kliknij przycisk **Zapisz**.
25. Wybierz kolejno opcje **Sprzedaż i marketing > Prowizje > Naliczanie prowizji**. Na stronie **Naliczanie prowizji** można zdefiniować stawkę prowizji, którą pracownik będzie otrzymywał za transakcję sprzedaży, jeśli zawiera ona wstępnie zdefiniowaną kombinację odbiorcy i produktu. W ramach konfiguracji stawki prowizji należy określić podstawę obliczania prowizji oraz wskazać, czy uwzględnić lub wykluczyć rabaty. Można również wprowadzić okres ważności wskazujący, kiedy stawka prowizji jest aktywna.  
26. Kliknij przycisk **Nowy**.
27. W polu **Kod towaru** zaznacz opcję „Grupa”.
28. W polu **Powiązanie produktu** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
29. Na liście odszukaj i zaznacz utworzoną wcześniej grupę.
30. W polu **Kod odbiorcy** wybierz opcję „Grupa”.
31. W polu **Relacja odbiorcy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
32. Na liście zaznacz utworzoną wcześniej grupę.
33. W polu **Relacja przedstawiciela handlowego** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
34. Na liście znajdź i zaznacz odpowiedni rekord.
    - Zachowaj opcję „Przed rabatem wiersza”.  
    - Zachowaj opcję „Przychód” jako podstawę obliczania wartości prowizji.    
35. W polu Procent prowizji wpisz liczbę.
36. Kliknij przycisk **Zapisz**.

## <a name="setting-up-commission-posting"></a>Konfigurowanie księgowania prowizji
1. Wybierz kolejno opcje **Okienko nawigacji > Sprzedaż i marketing > Prowizje > Księgowanie prowizji**. Prowizje są płatne na rzecz pracowników i dlatego muszą być tak skonfigurowane, aby zapewniać poprawne księgowanie finansowe na odpowiednich kontach w **księdze głównej**. Służy do tego strona **Księgowanie prowizji**. Przejrzyj konfigurację dostępną dla bieżącej firmy. Na ogół kwoty prowizji są księgowane na dedykowanym koncie wydatków i kompensowane na dedykowanym koncie rozrachunków z dostawcami. Jeśli nie masz skonfigurowanych reguł księgowania prowizji, system nie będzie w stanie wykonać fakturowania zamówienia sprzedaży zawierającego uprawnione prowizje.  
2. Zamknij stronę.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Przypisywanie grupy prowizji do odbiorcy i produktu
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Sprzedaż i marketing > Odbiorcy > Wszyscy odbiorcy**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk **Edytuj**.
5. Rozwiń sekcję **Ustawienia domyślne zamówienia sprzedaży**.
6. W polu **Grupa prowizji** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście zaznacz utworzoną wcześniej grupę.
8. W polu **Grupa sprzedaży** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Kliknij przycisk **Zapisz**.
11. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.
12. Skorzystaj z opcji **filtrowania**, aby znaleźć rekordy. Na przykład wyfiltruj według pola Numer towaru z wartością „T0020”.
13. Na liście kliknij łącze w wybranym wierszu.
14. Kliknij przycisk **Edytuj**.
15. Rozwiń sekcję **Sprzedaż**.
16. W polu **Grupa prowizji** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
17. Na liście zaznacz utworzoną wcześniej grupa prowizji.
18. Wybierz opcję **Zapisz**.

