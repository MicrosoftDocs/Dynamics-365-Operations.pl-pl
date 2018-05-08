--- 
title: "Używanie obliczeń w celu tworzenia wyników zliczania i sumowania"
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
ms.openlocfilehash: 5b7f0cc5b94ab7be11a013ef3e5909d84847e885
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing"></a>Używanie obliczeń w celu tworzenia wyników zliczania i sumowania 

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 2: Konfigurowanie obliczeń)”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Konfigurowanie tego raportu w celu używania informacji o inwentaryzacji i sumowaniu
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Model Intrastat”.
4. W drzewie rozwiń węzeł „Model Intrastat\Intrastat (Niemcy)”.
5. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)\Intrastat (Niemcy) z inwentaryzacją i sumowaniem”.
6. Kliknij przycisk Konstruktor.
7. Kliknij kartę Mapowanie.
8. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
    * Dodaj nowe źródło danych w celu uzyskania listy zapamiętanych bloków.  
9. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
10. W polu Nazwa wpisz „$BlocksList”.
    * $BlocksList  
11. Kliknij opcję Edytuj formułę.
12. W drzewie zaznacz element „Funkcje gromadzenia danych\COLLECTEDLIST”.
13. Kliknij opcję Dodaj funkcję.
14. Kliknij opcję Dodaj źródło danych.
15. W polu Formuła wpisz „COLLECTEDLIST('$BlockName', ”.
    * COLLECTEDLIST('$BlockName',  
16. W polu Formuła wpisz „COLLECTEDLIST('$BlockName', "*")”.
    * COLLECTEDLIST('$BlockName', "*")  
17. Kliknij przycisk Zapisz.
    * Wzorzec "*" oznacza, że wszystkie bloki zostaną włączone do listy dla tego rekordu.  
18. Zamknij stronę.
19. Kliknij przycisk OK.
20. Kliknij kartę Format.
21. W drzewie zaznacz element „Intrastat\Dane”.
22. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
23. W drzewie zaznacz element „Tekst\Sekwencja”.
24. W polu Nazwa wpisz „Sumy według bloków”.
    * Sumy według bloków  
25. W polu Znaki specjalne wybierz opcję „Nowy wiersz — Windows (CR LF)”.
26. Kliknij przycisk OK.
27. W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków”.
28. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
29. W drzewie zaznacz element „Tekst\Ciąg”.
30. W polu Nazwa wpisz „Kod bloku”.
    * Kod bloku  
31. Kliknij przycisk OK.
32. Kliknij opcję Dodaj ciąg.
33. W polu Nazwa wpisz „Inwentaryzacja wierszy”.
    * Inwentaryzacja wierszy  
34. Kliknij przycisk OK.
35. Kliknij opcję Dodaj ciąg.
36. W polu Nazwa wpisz „Łączna kwota”.
    * Łączna liczba  
37. Kliknij przycisk OK.
38. Kliknij kartę Mapowanie.
39. W drzewie wybierz węzeł „$BlocksList”.
40. Kliknij opcję Powiąż.
    * Utwórz wiersz podsumowania dla każdego zapamiętanego bloku.  
41. Kliknij kartę Format.
42. W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Kod bloku”.
43. Kliknij kartę Mapowanie.
44. Kliknij opcję Edytuj formułę.
45. W polu Formuła wpisz „"Identyfikator bloku: " & ”.
    * "Identyfikator bloku: " &  
46. W drzewie rozwiń węzeł „$BlocksList”.
47. W drzewie zaznacz element „$BlocksList\Wartość”.
48. Kliknij opcję Dodaj źródło danych.
49. Kliknij przycisk Zapisz.
50. Zamknij stronę.
51. Kliknij kartę Format.
52. W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Inwentaryzacja wierszy”.
53. Kliknij kartę Mapowanie.
54. Kliknij opcję Edytuj formułę.
    * Utwórz dane wyjściowe dla liczby wierszy każdego bloku przedstawionej w tym raporcie.  
55. W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & ”.
    * "Liczba wierszy w tym bloku: " &  
56. W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(”.
    * "Liczba wierszy w tym bloku: " & TEXT(  
57. W drzewie zaznacz element „Funkcje gromadzenia danych\COUNTIFS”.
58. Kliknij opcję Dodaj funkcję.
59. Kliknij opcję Dodaj źródło danych.
60. W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', ”.
    * "Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName',  
61. W drzewie rozwiń węzeł „$BlocksList”.
62. W drzewie zaznacz element „$BlocksList\Wartość”.
63. Kliknij opcję Dodaj źródło danych.
64. W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, ”.
    * "Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość,  
65. W drzewie zaznacz element „$RecName”.
66. Kliknij opcję Dodaj źródło danych.
67. W polu Formuła wpisz „"Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "*"))”.
    * "Liczba wierszy w tym bloku: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Wartość, '$RecName', "*"))  
68. Kliknij przycisk Zapisz.
69. Zamknij stronę.
70. Kliknij kartę Format.
71. W drzewie zaznacz element „Intrastat\Dane\Sumy według bloków\Łączna kwota”.
72. Kliknij kartę Mapowanie.
73. Kliknij opcję Edytuj formułę.
    * Utwórz dane wyjściowe, który będą sumą kwot zafakturowanych dla wszystkich bloków przedstawionych w tym raporcie.  
74. W polu Formuła wpisz „"Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "*"))”.
    * "Suma zafakturowanych kwot: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Wartość, '$RecName', "*"))  
75. Kliknij przycisk Zapisz.
76. Zamknij stronę.
77. Kliknij przycisk Zapisz.
78. Zamknij stronę.


