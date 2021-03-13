---
title: Używanie konfiguracji mapowań modeli do obliczeń agregujących na poziomie bazy danych
description: W tym temacie opisano sposób projektowania nowego mapowania modelu raportowania elektronicznego i zastosowanie wbudowanych funkcji ER w celu efektywnego obliczania agregacji.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a392697f6b91bc6555d0d72d09ecd7da32e1a3f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094272"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Używanie konfiguracji mapowań modeli do obliczeń agregujących na poziomie bazy danych

[!include [banner](../../includes/banner.md)]

Ta procedura zawiera informacje na temat projektowania nowego mapowania modelu raportowania elektronicznego (ER) i stosowania wbudowanych funkcji ER w celu efektywnego obliczania agregacji. Ta procedura dotyczy tworzenia konfiguracji dla przykładowej firmy Litware, Inc. 

Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki te można wykonać przy użyciu dowolnego zestawu danych.

 Aby wykonać tę procedurę, należy najpierw wykonać kroki opisane w procedurze „Poprawa wydajności obliczeń agregacji przy użyciu ER poprzez wykonywanie ich na poziomie bazy danych (część 1: Przygotowywanie konfiguracji)”.

1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Model Intrastat”.
3. W drzewie wybierz kolejno elementy „Model Intrastat\Przykładowe mapowanie Intrastat”.
4. Kliknij przycisk Konstruktor.
5. Kliknij przycisk Konstruktor.
6. W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.
7. Kliknij opcję Dodaj element główny.
    * Dodaj nowe źródło danych reprezentujące rekordy, które chcesz zgrupować.  
8. W polu Nazwa wpisz „Transakcje”.
    * Transakcje  
9. W polu Tabela wpisz „Intrastat”.
    * Intrastat  
10. Kliknij przycisk OK.
11. W drzewie zaznacz element „Funkcje\Grupuj wg”.
    * Ten typ źródła danych jest używany do wprowadzania nowego źródła danych w czasie procesu w celu grupowania rekordów i obliczania wymaganych agregacji.  
12. Kliknij opcję Dodaj element główny.
13. W polu Nazwa wpisz „TransactionsGroups”.
    * Grupy transakcji  
14. Kliknij opcję Edytuj grupę według.
15. W drzewie zaznacz element „Transakcje”.
    * Wybierz dodane źródło danych typu „Lista rekordów” reprezentujące rekordy, które chcesz grupować.  
16. Kliknij opcję Dodaj pole do.
17. Kliknij opcję Jakie elementy do grupowania.
18. W drzewie rozwiń węzeł „Transakcje”.
19. W drzewie wybierz kolejno elementy „Transakcje\Kierunek”.
20. Kliknij opcję Dodaj pole do.
21. Kliknij opcję Zgrupowane pola.
    * Zaznacz to pole, aby określić poziom grupowania. W zależności od tego zaznaczenia źródło danych będzie zwracać w czasie procesu tyle grup transakcji, ile jest kodów kierunku, które zostaną uwzględnione w tabeli Intrastat.  
22. W drzewie wybierz kolejno elementy „Transakcje\Kwota faktury(AmountMST)”.
    * Zaznacz to pole, aby określić źródło do obliczania agregacji.  
23. Kliknij opcję Dodaj pole do.
24. Kliknij opcje Pola agregacji.
25. Na liście oznacz wybrany wiersz.
26. W polu Metoda wybierz wartość „Suma”.
    * Wybierz typ agregacji.  
27. W polu nazwa wpisz „SumOfAmountMST”.
    * Określ nazwę tej agregacji w skonfigurowanym źródle danych.  
28. Kliknij przycisk Zapisz.
    * Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że grupowanie będzie wykonywane w czasie procesu w bazie danych SQL.  
29. Zamknij stronę.
30. Kliknij przycisk OK.
31. W drzewie rozwiń węzeł „Sumy”.
32. W drzewie rozwiń węzeł „Grupy transakcji”.
33. W drzewie rozwiń węzeł „Grupy transakcji\Zagregowane”.
34. W drzewie wybierz kolejno elementy „Grupy transakcji\Zagregowane\SumOfAmountMST”.
35. W drzewie wybierz kolejno elementy „Sumy\Łączna wartość faktury(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')”.
36. Kliknij opcję Powiąż.
    * Na podstawie tego ustawienia to źródło danych będzie obliczać sumę wartości w polu „AmountMST” dla poszczególnych grup transakcji. To obliczenie agregacji będzie dostępne jako pozycja TransactionsGroups.aggregated.TotalAmount.  
37. W drzewie rozwiń węzeł „Grupy transakcji”.
38. W drzewie wybierz element „Grupy transakcji”.
39. Kliknij przycisk Edytuj.
40. Kliknij opcję Edytuj grupę według.
41. W drzewie rozwiń węzeł „Transakcje”.
42. W drzewie wybierz kolejno elementy „Transakcje\Kwota faktury(AmountMST)”.
43. Kliknij opcję Dodaj pole do.
44. Kliknij opcje Pola agregacji.
45. Na liście oznacz wybrany wiersz.
46. W polu Metoda wybierz wartość „Maks.”.
47. W polu Nazwa wpisz „MaxOfAmountMST”.
48. Kliknij przycisk Zapisz.
    * Obecnie wykonywanie źródeł danych GROUPBY można z pewnymi ograniczeniami przekładać na poziom bazy danych SQL. Translację można wykonać dla źródeł danych typu „Lista rekordów” lub źródeł danych reprezentowanych jako wyrażenie przy użyciu funkcji FILTR. Można ją również wykonać, gdy dla pojedynczego pola rekordów grupowania skonfigurowano tylko jedną agregację.  
    * Należy zauważyć, że nawet jeśli dla pola AmountMST skonfigurowano więcej niż jedną agregację, pole „Wykonanie w” nadal wskazuje, że dane grupowanie zostanie wykonane w czasie procesu w bazie danych SQL. Wynika to z faktu, że z daną pozycją modelu danych powiązana jest tylko jedna agregacja, która zostanie użyta w czasie procesu do pobrania danych z takiego źródła danych.  
49. Zamknij stronę.
50. Kliknij przycisk OK.
51. W drzewie rozwiń węzeł „Grupy transakcji”.
52. W drzewie rozwiń węzeł „Grupy transakcji\Zagregowane”.
53. W drzewie wybierz kolejno elementy „Grupy transakcji\Zagregowane\MaxOfAmountMST”.
54. W drzewie wybierz kolejno elementy „Sumy\Łączna wartość statystyczna(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')”.
55. Kliknij opcję Powiąż.
56. W drzewie rozwiń węzeł „Grupy transakcji”.
57. W drzewie wybierz element „Grupy transakcji”.
58. Kliknij przycisk Edytuj.
59. Kliknij opcję Edytuj grupę według.
    * Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że to grupowanie zostanie wykonane w czasie procesu w pamięci, ponieważ obydwie agregacje tego samego pola są powiązane z pozycjami modelu danych.   
60. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
61. Kliknij przycisk Usuń.
62. Kliknij przycisk Tak.
63. Kliknij przycisk Usuń.
64. Kliknij przycisk Tak.
65. Kliknij opcję Dodaj pole do.
66. Kliknij opcję Jakie elementy do grupowania.
67. W drzewie rozwiń węzeł „Rekord asortymentu (Intrastat)”.
68. Kliknij przycisk Zapisz.
    * Należy zwrócić uwagę, że pole „Wykonanie w” wskazuje, że to grupowanie będzie wykonane w czasie procesu w pamięci, nawet jeśli nie zdefiniowano żadnych agregacji, a wybrane źródło danych typu „Rekordy w tabeli” odnosi się do tej samej tabeli „Intrastat”. Dzieje się tak, ponieważ źródło danych zawiera kilka pól obliczeniowych, których jeszcze nie można przełożyć na poziom bazy danych SQL.  

