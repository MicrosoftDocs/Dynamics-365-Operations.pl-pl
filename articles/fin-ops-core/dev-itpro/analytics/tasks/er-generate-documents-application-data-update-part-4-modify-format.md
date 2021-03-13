---
title: Modyfikowanie formatów w celu generowania dokumentów zawierających dane aplikacji
description: W tym temacie opisano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e820e909bcd80b4747c06ccaaeb05c03f52b6963
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129404"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Modyfikowanie formatów w celu generowania dokumentów zawierających dane aplikacji

[!include [banner](../../includes/banner.md)]

Aby wykonać kroki opisane w tej procedurze, należy najpierw wykonać procedurę „ER Generowanie dokumentów z aktualizacją danych aplikacji (Część 3: Modyfikowanie modelu i mapowania)”.

Etapy w tej procedurze wyjaśniają sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentu elektronicznego i aktualizowania danych aplikacji. W tej procedurze zmodyfikujesz konfiguracje ER, aby były używane nie tylko do generowania dokumentów elektronicznych, ale również do aktualizowania danych aplikacji. Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Modyfikowanie formatu w celu zbierania danych raportowania
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie rozwiń węzeł „Intrastat (model)”.
3. W drzewie zaznacz element „Intrastat (model)\Intrastat (format)”.
4. Kliknij przycisk Konstruktor.
5. W drzewie rozwiń węzeł „Plik”.
6. W drzewie rozwiń węzeł „Plik\Deklaracja”.
7. W drzewie zaznacz element „Plik\Deklaracja\Dane”.
8. W polu Liczebność zaznacz opcję „Jeden wiele”.
    * Skonfiguruj ten element formatu, aby archiwizować szczegóły procesu raportowania Intrastat. Ten element reprezentuje rekord nagłówka archiwum.  
9. W drzewie rozwiń węzeł „Plik\Deklaracja\Dane”.
10. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja”.
11. W polu Liczebność zaznacz opcję „Zero wiele”.
    * Skonfiguruj ten element formatu, aby archiwizować szczegóły procesu raportowania Intrastat. Ten element będzie reprezentował listę zarchiwizowanych wierszy.  
12. W drzewie rozwiń węzeł „Plik\Deklaracja\Dane\Pozycja”.
13. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym1”.
14. W polu Wykluczone wybierz opcję Tak.
    * Te dane nie będą archiwizowane, więc można wykluczyć ten element formatu ze źródła danych szczegółów raportowania Intrastat.  
15. W drzewie rozwiń węzeł „Plik\Deklaracja\Dane\Pozycja\Wym1”.
16. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym1\właściwość”.
17. W polu Wykluczone wybierz opcję Tak.
18. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym1\data”.
19. W polu Wykluczone wybierz opcję Tak.
20. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym2”.
21. W polu Wykluczone wybierz opcję Tak.
22. W drzewie rozwiń węzeł „Plik\Deklaracja\Dane\Pozycja\Wym2”.
23. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym2\właściwość”.
24. W polu Wykluczone wybierz opcję Tak.
25. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym2\kod”.
26. W polu Wykluczone wybierz opcję Tak.
27. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym3”.
    * Kilka elementów formatu może mieć taką samą nazwę. Na przykład Wym. Nie można ich jawnie rozpoznać podczas używania tego formatu jako źródła danych dla archiwizacji szczegółów raportowania Intrastat, dlatego należy zdefiniować alternatywne nazwy tych elementów formatu.   
28. W polu Nazwa wpisz „Kwota”.
    * Ilość  
29. W polu Liczebność zaznacz opcję „Dokładnie jeden”.
30. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja\Wym4”.
31. W polu Nazwa wpisz „Towar”.
    * Element  
32. W polu Liczebność zaznacz opcję „Dokładnie jeden”.
    * Oprócz elementów formatu projektu muszą być archiwizowane również następujące szczegóły raportowania Intrastat: unikatowy identyfikator rekordu każdej zgłoszonej pozycji asortymentu i nazwa wygenerowanego pliku. Ponieważ te dane nie będą wypełniane w raporcie Intrastat, należy dodać format powiązany z tymi elementami szczegółów jako elementy źródła danych.  
33. W drzewie zaznacz element „Plik\Deklaracja\Dane”.
34. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
35. W drzewie zaznacz element „Źródło danych\Pozycja”.
36. W polu Nazwa wpisz „Nazwa pliku”.
    * Nazwa pliku  
37. W polu Typ danych wybierz opcję „Ciąg”.
38. Kliknij przycisk OK.
39. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja”.
40. Kliknij opcję Dodaj pozycję.
41. W polu Nazwa wpisz „Identyfikator rekordu asortymentu”.
    * Identyfikator rekordu asortymentu  
42. W polu Typ danych wybierz opcję „Int64”.
43. Kliknij przycisk OK.
44. Kliknij kartę Mapowanie.
45. W drzewie zaznacz element „Plik\Deklaracja\Dane\Nazwa pliku”.
46. Kliknij opcję Powiąż.
47. W drzewie rozwiń model„”
48. W drzewie rozwiń węzeł „model\Transakcje”.
49. W drzewie zaznacz element „Plik\Deklaracja\Dane\Pozycja = model.Transakcje\Identyfikator rekordu asortymentu”.
50. W drzewie zaznacz element „model\Transakcje\Identyfikator rekordu asortymentu”.
51. Kliknij opcję Powiąż.
52. Kliknij przycisk Zapisz.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Modyfikowanie formatu w celu zapamiętywania danych raportowania

1. Kliknij opcję Mapuj format na model.
2. Kliknij przycisk Nowy.
3. W polu Definicja wprowadź lub wybierz pozycję główną „W celu aktualizacji danych aplikacji”.
    * W celu aktualizacji danych aplikacji.
4. W polu Nazwa wpisz „Mapowanie na dane aktualizacyjne”.
    * Mapowanie na dane aktualizacyjne  
5. Kliknij przycisk Zapisz.
    * To mapowanie określa, jak szczegóły raportu Intrastat są gromadzone w modelu danych, którego struktura jest określana przez wybraną pozycję główną „W celu aktualizacji danych aplikacji”. Te szczegóły, mapowanie modelu z tą samą pozycją główną „W celu aktualizacji danych aplikacji” i kierunek „Do lokalizacji docelowej” zostaną użyte do zaktualizowania danych aplikacji. Aktualizacja danych aplikacji rozpoczyna się natychmiast po wygenerowaniu wychodzącego raportu Intrastat. Można pominąć aktualizację danych aplikacji w czasie wykonywania, ale model danych musi być pusty (tzn. musi zawierać pustą listę rekordów).
6. Kliknij przycisk Konstruktor.
    * Format wychodzącego raportu Intrastat jest dodawany domyślnie jako źródło danych dla tego mapowania modelu.  
    * Powiąż elementy projektowanego raportu (przedstawiane jako źródło danych) z elementami modelu danych wyfiltrowanymi na podstawie pozycji głównej wybranego modelu.  
7. W drzewie rozwiń węzeł „Nagłówek archiwum”.
8. W drzewie rozwiń węzeł „Nagłówek archiwum\Wiersze archiwum”.
9. W drzewie rozwiń węzeł „format”.
10. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)”.
11. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)\Dane: Element XML 1..* (Dane)”.
12. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)\Dane: Element XML 1..* (Dane)\Pozycja: Element XML 0..* (Pozycja)”.
13. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)\Dane: Element XML 1..* (Dane)\Pozycja: Element XML 0..* (Pozycja)\Wym3: Element XML 1..1 (Kwota)”.
14. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)\Dane: Element XML 1..* (Dane)\Pozycja: Element XML 0..* (Pozycja)\Wym4: Element XML 1..1 (Pozycja)”.
15. W drzewie zaznacz element „Nagłówek archiwum\Liczba wierszy”.
16. Kliknij przycisk Edytuj.
17. W drzewie zaznacz element „Lista\COUNT”.
18. Kliknij opcję Dodaj funkcję.
19. W drzewie rozwiń węzeł „format”.
20. W drzewie rozwiń węzeł „format\Deklaracja: Element XML(Deklaracja)”.
21. W drzewie rozwiń węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
22. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
23. Kliknij opcję Dodaj źródło danych.
24. W polu Formuła wpisz „COUNT(format.Deklaracja.Dane.Pozycja)”.
    * COUNT(format.Deklaracja.Dane.Pozycja)  
25. Kliknij przycisk Zapisz.
26. Zamknij stronę.
27. W drzewie zaznacz element „Nagłówek archiwum\Nazwa pliku”.
28. W drzewie zaznacz element „format\Deklaracja: Element XML(Deklaracja)\Dane: Element XML 1..* (Dane)\Nazwa pliku: Ciąg pozycji(Nazwa pliku)”.
29. Kliknij opcję Powiąż.
30. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`.
31. W drzewie zaznacz element „Nagłówek archiwum\Wiersze archiwum\Numer pozycji”.
32. Kliknij opcję Powiąż.
33. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`.
34. W drzewie zaznacz element „Nagłówek archiwum\Wiersze archiwum\Kwota”.
35. Kliknij opcję Powiąż.
36. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`.
37. W drzewie zaznacz element „Nagłówek archiwum\Wiersze archiwum\Identyfikator rekordu asortymentu”.
38. Kliknij opcję Powiąż.
39. W drzewie zaznacz element „Nagłówek archiwum\Wiersze archiwum”.
40. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
41. Kliknij opcję Powiąż.
42. W drzewie zaznacz element „Nagłówek archiwum”.
43. W drzewie zaznacz węzeł `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
44. Kliknij opcję Powiąż.
45. Kliknij przycisk Zapisz.
46. Zamknij stronę.
47. Zamknij stronę.
48. Zamknij stronę.
