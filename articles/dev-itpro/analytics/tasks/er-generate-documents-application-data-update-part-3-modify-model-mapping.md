--- 
title: "Modyfikowanie modelu i mapowania w celu generowania dokumentów z aktualizacjami danych aplikacji na potrzeby raportowania elektronicznego (ER)"
description: "Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 2 — Generowanie dokumentów)”."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a29e273e5ef377826c0002a9a0a956defef6aa77
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="modify-model-and-mapping-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Modyfikowanie modelu i mapowania w celu generowania dokumentów z aktualizacjami danych aplikacji na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 2: Generowanie dokumentów)”. 

Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji. W tej procedurze zmodyfikujesz konfiguracje ER, aby zacząć ich używać do generowania dokumentów elektronicznych i aktualizowania danych aplikacji. Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy DEMF.


## <a name="modify-data-model"></a>Modyfikowanie modelu danych
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz element „Intrastat (model)”.
    * Rozszerzysz zakres stosowania modelu danych. Oprócz używania jako źródło danych do generowania raportu Intrastat model danych będzie również wykorzystywany do zbierania szczegółów o procesie raportowania Intrastat. Szczegóły zostaną następnie użyte do zaktualizowania danych aplikacji.   
3. Kliknij przycisk Konstruktor.
4. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
5. W polu Nowy węzeł jako wpisz „Element główny modelu”.
6. W polu Nazwa wpisz „W celu aktualizacji danych aplikacji”.
    * W celu aktualizacji danych aplikacji  
7. Kliknij przycisk Dodaj.
8. W drzewie zaznacz element „W celu aktualizacji danych aplikacji”.
    * Ta nowa pozycja główna jest dodawana w celu określenia przepływu przenoszenia danych z raportu Intrastat (używanego jako źródło danych) do tabel aplikacji (lokalizacji docelowej aktualizacji). Należy zauważyć, że muszą być stosowane różne pozycje główne do pobierania danych, które są księgowane w dokumencie wychodzącym, i do pobierania danych z dokumentu używanego do aktualizowania danych aplikacji.   
9. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
10. W polu Nazwa wpisz „Nagłówek archiwum”.
    * Nagłówek archiwum  
11. W polu Typ elementu wybierz opcję „Lista rekordów”.
12. Kliknij przycisk Dodaj.
    * Ponieważ utworzysz rekord dla każdego generowanego raportu Intrastat, należy utworzyć do tego nową pozycję.  
13. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
14. W polu Nazwa wpisz „Nazwa pliku”.
    * Nazwa pliku  
15. W polu Typ elementu wybierz opcję „Ciąg”.
16. Kliknij przycisk Dodaj.
17. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
18. W polu Nazwa wpisz „Liczba wierszy”.
    * Liczba wierszy  
19. W polu Typ elementu wybierz opcję „Liczba całkowita”.
20. Kliknij przycisk Dodaj.
    * Dodaj tę pozycję w celu reprezentowania liczby transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.  
21. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
22. W polu Nazwa wpisz „Wiersze archiwum”.
    * Wiersze archiwum  
23. W polu Typ elementu wybierz opcję „Lista rekordów”.
24. Kliknij przycisk Dodaj.
    * Dodaj tę pozycję w celu reprezentowania listy transakcji Intrastat, które są zgłaszane podczas bieżącego procesu raportowania.  
25. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
26. W polu Nazwa wpisz „Kwota”.
    * Ilość  
27. W polu Typ elementu wybierz opcję „Liczba rzeczywista”.
28. Kliknij przycisk Dodaj.
29. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
30. W polu Nazwa wpisz „Identyfikator rekordu asortymentu”.
    * Identyfikator rekordu asortymentu  
31. W polu Typ elementu wybierz opcję „Int64”.
32. Kliknij przycisk Dodaj.
33. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
34. W polu Nazwa wpisz „Numer towaru”.
    * Identyfikator towaru  
35. W polu Typ elementu wybierz opcję „Ciąg”.
36. Kliknij przycisk Dodaj.
37. Kliknij przycisk Zapisz.
38. Zamknij stronę.

## <a name="modify-model-mapping"></a>Modyfikowanie mapowania modelu
1. W drzewie rozwiń węzeł „Intrastat (model)”.
2. W drzewie zaznacz element „Intrastat (model)\Intrastat (mapowanie)”.
    * Zmodyfikuj istniejące mapowanie modelu, aby rozpocząć jego używanie do aktualizowania danych aplikacji i zarchiwizować szczegóły raportowania Intrastat.  
3. Kliknij przycisk Konstruktor.
4. Kliknij przycisk Nowy.
5. W polu Nazwa wpisz „Aktualizacja archiwum”.
    * Aktualizacja archiwum  
6. W polu Kierunek wybierz opcję „Do lokalizacji docelowej”.
7. Kliknij przycisk Zapisz.
    * To nowe mapowanie określa przepływ przenoszenia danych (szczegółów raportowania Intrastat) z modelu danych do tabel aplikacji (miejsca docelowego aktualizacji). Należy zauważyć, że należy użyć różnych pozycji głównych modelu do pobierania danych z aplikacji dla procesu raportowania, a następnie użyć danych z modelu danych do zaktualizowania danych aplikacji.   
8. Kliknij przycisk Konstruktor.
9. W drzewie zaznacz element „Model danych\Model danych”.
    * Dodaj wymagane źródło danych. Jest to model danych zawierający szczegóły raportowanych transakcji Intrastat, które muszą zostać zarchiwizowane.  
10. Kliknij opcję Dodaj element główny.
11. W polu Nazwa wpisz „model”.
    * model  
12. W polu Definicja wprowadź lub wybierz wartość „W celu aktualizacji danych aplikacji”.
    * W celu aktualizacji danych aplikacji  
13. Kliknij przycisk OK.
14. W drzewie rozwiń model„”
15. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
16. W drzewie zaznacz element „model\Nagłówek archiwum”.
17. Kliknij przycisk Dodaj.
    * Ponieważ chcesz utworzyć wartości stałotekstowe dla raportowanych transakcji Intrastat w celu zarchiwizowania, trzeba dodać odpowiednie źródło danych.  
18. W polu Nazwa wpisz „Wiersze stałotekstowe”.
    * Wiersze stałotekstowe  
19. Kliknij opcję Edytuj formułę.
20. W drzewie zaznacz element „Lista\ENUMERATE”.
21. Kliknij opcję Dodaj funkcję.
22. W drzewie rozwiń model„”
23. W drzewie rozwiń węzeł „model\Nagłówek archiwum”.
24. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze archiwum”.
25. Kliknij opcję Dodaj źródło danych.
26. W polu Formuła wprowadź „ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')”.
    * ENUMERATE(model.'Nagłówek archiwum'.'Wiersze archiwum')  
27. Kliknij przycisk Zapisz.
28. Zamknij stronę.
29. Kliknij przycisk OK.
30. Kliknij opcję Dodaj lokalizację docelową.
    * Dodaj tabele aplikacji jako obowiązkowe miejsca docelowe wymagające aktualizacji, aby archiwizować szczegóły raportowanych transakcji Intrastat.  
31. W polu nazwa wpisz „Archiwum”.
    * Archiwizuj  
32. W polu Nazwa tabeli wpisz „IntrastatArchiveGeneral”.
    * IntrastatArchiveGeneral  
    * Zachowaj akcję rekordu „Wstaw”, aby móc dodawać rekordy w trakcie archiwizowania szczegółów każdego procesu raportowania Intrastat.  
33. W polu Dziennik informacyjny rekordu zaznacz opcję Tak.
    * Wybierz opcję Tak, aby uzyskać informacje o problemach z aktualizacją danych aplikacji.  
34. W polu Pomiń weryfikację akcji rekordu wybierz opcję Tak.
    * Wybierz opcję Tak, aby pomijać błędy sprawdzania poprawności o pustym polu „Identyfikator archiwum Intrastat”. Będzie się to odbywało po dodaniu rekordów na podstawie ustawień numeracji skonfigurowanych dla tej tabeli w formularzu Parametry handlu zagranicznego.  
35. Kliknij przycisk OK.
    * Powiąż elementy dodanego źródła danych (modelu wyfiltrowanego na podstawie wybranej pozycji głównej) z elementami w dodanym miejscu docelowym.  
36. W drzewie rozwiń węzeł „Archiwum”.
37. W drzewie rozwiń węzeł „Archiwum\<Relacje”.
38. W drzewie rozwiń węzeł „Archiwum\<Relacje\IntrastatArchiveDetail”.
39. W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Kwota(AmountMST)”.
40. W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe”.
41. W drzewie rozwiń węzeł „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość”.
42. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Kwota”.
43. Kliknij opcję Powiąż.
44. W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Asortyment(IntrastatCommodity)”.
45. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Identyfikator rekordu asortymentu”.
46. Kliknij opcję Powiąż.
47. W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer towaru(ItemId)”.
48. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Wartość\Numer towaru”.
49. Kliknij opcję Powiąż.
50. W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail\Numer wiersza(LineNumber)”.
51. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe\Numer”.
52. Kliknij opcję Powiąż.
53. W drzewie zaznacz element „Archiwum\<Relacje\IntrastatArchiveDetail”.
54. W drzewie zaznacz element „model\Nagłówek archiwum\Wiersze stałotekstowe”.
55. Kliknij opcję Powiąż.
56. W drzewie zaznacz element „Archiwum\Nazwa pliku(FileName)”.
57. W drzewie zaznacz element „model\Nagłówek archiwum\Nazwa pliku”.
58. Kliknij opcję Powiąż.
59. W drzewie zaznacz element „Archiwum\Liczba wierszy(NumberOfLines)”.
60. W drzewie zaznacz element „model\Nagłówek archiwum\Liczba wierszy”.
61. Kliknij opcję Powiąż.
62. W drzewie zaznacz element „Archiwum”.
63. W drzewie zaznacz element „model\Nagłówek archiwum”.
64. Kliknij opcję Powiąż.
65. Kliknij przycisk Zapisz.
66. Zamknij stronę.
67. Zamknij stronę.


