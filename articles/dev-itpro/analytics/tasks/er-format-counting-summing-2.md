--- 
title: "Konfigurowanie obliczeń służących do zliczania i sumowania"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d41ce101c0b038627e2baf6b5eac2410095af7ce
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="configure-computations-to-do-counting-and-summing"></a>Konfigurowanie obliczeń służących do zliczania i sumowania

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1: Tworzenie formatu)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Tworzenie konfiguracji formatu w celu dodania szczegółów inwentaryzacji i sumowania
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Model Intrastat”.
4. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.
    * Załóżmy, że trzeba dostosować format dostarczony przez firmę Microsoft, dodając wiersze zawierające szczegóły podsumowania na końcu raportu Intrastat. Należy to zrobić poprzez utworzenie własnej pochodnej konfiguracji Intrastat na podstawie wystąpienia otrzymanego od Microsoft i w niej wprowadzić modyfikacje.  
5. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
6. W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Intrastat (Niemcy), Microsoft”.
7. W polu Nazwa wpisz wyrażenie „Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
8. Kliknij przycisk Utwórz konfigurację.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Konfigurowanie tego raportu w celu wykonania inwentaryzacji i sumowania na podstawie szczegółów danych wyjściowych
1. Kliknij przycisk Konstruktor.
2. W polu Pobierz szczegóły rezultatu zaznacz opcję Tak.
    * Ta flaga będzie w czasie wykonywania uaktywniać proces gromadzenia szczegółów wyjściowych w celu wygenerowania pliku Intrastat.  
    * Musisz wykonać inwentaryzację dla różnych kierunków Intrastat, dlatego dodasz dedykowane wyliczenie modelu do tej konfiguracji formatu używanej przez listę źródeł danych.  
3. Kliknij kartę Mapowanie.
4. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
5. W drzewie zaznacz element „Model danych\Wyliczenie”.
6. W polu Nazwa wpisz „Kierunek”.
7. W polu Wyliczenie modeli wpisz lub wprowadź wartość.
    * Wybierz wartość Kierunek.  
8. Kliknij przycisk OK.
9. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
10. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
11. W polu Nazwa wpisz „$BlockName”.
12. Kliknij opcję Edytuj formułę.
13. W polu Formuła wpisz „blok”.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
16. Kliknij przycisk OK.
17. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
18. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
19. W polu Nazwa wpisz „$RecName”.
20. Kliknij opcję Edytuj formułę.
21. W polu Formuła wpisz „rekord”.
22. Kliknij przycisk Zapisz.
23. Zamknij stronę.
24. Kliknij przycisk OK.
25. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
26. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
27. W polu Nazwa wpisz „$InvName”.
28. Kliknij opcję Edytuj formułę.
29. W polu Formuła wpisz „InvoicedAmountEUR”.
30. Kliknij przycisk Zapisz.
31. Zamknij stronę.
32. Kliknij przycisk OK.
33. W drzewie zaznacz element „Intrastat\Dane”.
34. Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.
35. Kliknij opcję Dodaj źródło danych.
    * $BlockName  
36. Kliknij przycisk Zapisz.
37. Zamknij stronę.
38. Kliknij przycisk Edytuj obok pola Wartość pobranego klucza danych.
39. W polu Formuła wpisz wyrażenie „IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")”.
    * IF(Intrastat.CommodityRecord.Direction=Kierunek.Import, "Import", "Eksport")  
40. Kliknij przycisk Zapisz.
41. Zamknij stronę.
    * Liczenie wierszy tej kolejnej sesji. Wyniki zostaną użyte z nazwą „blok” oddzielnie dla różnych kierunków. Wartość „Import” będzie używana dla wszelkich transakcji Intrastat przyjęcia. Wartość „Eksport” będzie używana dla wszelkich transakcji Intrastat wysyłki. Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel. Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”.  
42. W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja”.
43. W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Przyjęcia?”.
44. Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.
    * Liczenie wierszy tej kolejnej sesji. Wyniki zostaną zapamiętane pod nazwą „rekord”.  
45. W drzewie zaznacz element „$RecName”.
46. Kliknij opcję Dodaj źródło danych.
47. Kliknij przycisk Zapisz.
48. Zamknij stronę.
49. Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.
50. W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.
51. Kliknij przycisk Zapisz.
52. Zamknij stronę.
    * Liczenie wierszy tej kolejnej sesji. Wyniki zostaną użyte z nazwą „rekord” oddzielnie dla różnych kodów asortymentu. Potraktuj to jako wirtualny arkusz kalkulacyjny programu Excel. Dla każdej transakcji jest tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”, a drugi blok „rekord” jest wypełniany wartością kodu asortymentu.  
53. W drzewie zaznacz element „Intrastat\Dane: Sekwencja\Wysyłki?”.
54. Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.
55. W drzewie zaznacz element „$RecName”.
56. Kliknij opcję Dodaj źródło danych.
57. Kliknij przycisk Zapisz.
58. Zamknij stronę.
59. Kliknij przycisk Edytuj obok pola „Wartość pobranego klucza danych”.
60. W polu Formuła wprowadź wyrażenie „Intrastat.CommodityRecord.CommodityCode”.
61. Kliknij przycisk Zapisz.
62. Zamknij stronę.
63. W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?”.
64. W drzewie rozwiń węzeł „Intrastat\Dane: Sekwencja\Wysyłki: Sekwencja?\Rekord = Intrastat.CommodityRecord”.
65. Kliknij kartę Format.
66. W drzewie zaznacz element „Intrastat\Dane\Wysyłki\Rekord\Kwota faktury w EUR”.
67. Kliknij kartę Mapowanie.
68. Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.
69. W drzewie zaznacz element „$InvName”.
70. Kliknij opcję Dodaj źródło danych.
71. Kliknij przycisk Zapisz.
72. Zamknij stronę.
    * Podsumowanie wartości kwot zafakturowanych dla wierszy tej kolejnej sesji. Wyniki zostaną użyte z nazwą „InvoicedAmountEUR” oddzielnie dla różnych kierunków Intrastat kodów asortymentu. Potraktuj to jak tworzenie wirtualnego arkusza kalkulacyjnego w programie Excel. Dla każdej transakcji będzie tworzony wiersz, gdzie pierwsza kolumna „blok” jest wypełniana odpowiednio wartościami „Import” i „Eksport”. Drugi blok „rekord” jest wypełniony wartością kodu asortymentu, a trzecia kolumna „InvoicedAmountEUR” jest wypełniona wartością kwoty faktury.  
73. W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?”.
74. W drzewie rozwiń węzeł „Intrastat\Dane\Przyjęcia?\Rekord = Intrastat.CommodityRecord”.
75. Kliknij kartę Format.
76. W drzewie zaznacz element „Intrastat\Dane\Przyjęcia\Rekord\Kwota faktury w EUR”.
77. Kliknij kartę Mapowanie.
78. Kliknij przycisk Edytuj obok pola „Nazwa pobranego klucza danych”.
79. W drzewie zaznacz element „$InvName”.
80. Kliknij opcję Dodaj źródło danych.
81. Kliknij przycisk Zapisz.
82. Zamknij stronę.
83. Kliknij przycisk Zapisz.
84. Zamknij stronę.


