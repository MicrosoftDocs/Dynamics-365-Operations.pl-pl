---
title: ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1 — Projektowanie formatu)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 501936734b6ec970062d0d2cbcc8a3cdc11b934f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142370"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1 — Projektowanie formatu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy. Kroki można wykonać na danych dowolnej firmy.

W ceku wykonania tych kroków najpierw należy wykonać następujące trzy przewodniki po zadaniach: 

„ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”

„ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”

„ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”

Należy także pobrać i zapisać kopię lokalną szablonu z raportem przykładowym dostępnym tutaj, [Przykładowy raport z usługi internetowej wymiarów finansowych](https://go.microsoft.com/fwlink/?linkid=862266).

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-a-new-report-configuration"></a>Tworzenie nowej konfiguracji raportu
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
4. W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.
    * Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.  
5. W polu nazwa wpisz „Przykładowy raport z poziomo rozszerzalnymi zakresami”.
    * Przykładowy raport z poziomo rozszerzalnymi zakresami  
6. W polu Opis wpisz „Generowanie danych wyjściowych programu Excel z dynamicznym dodawaniem kolumn”.
    * Generowanie danych wyjściowych programu Excel z dynamicznym dodawaniem kolumn  
7. W polu Definicja modelu danych zaznacz wartość Wpis.
8. Kliknij przycisk Utwórz konfigurację.

## <a name="design-the-report-format"></a>Projektowanie formatu raportu
1. Kliknij przycisk Konstruktor.
2. Włącz przełącznik „Pokaż szczegóły”.
3. W okienku akcji kliknij pozycję Importuj.
4. Kliknij opcję Importuj z programu Excel.
5. Kliknij opcję Załączniki.
    * Zaimportuj szablon raportu. Użyj do tego pobranego pliku programu Excel.  
6. Kliknij przycisk Nowy.
7. Kliknij opcję Plik.
8. Zamknij stronę.
9. W polu Szablon wprowadź lub wybierz wartość.
    * Zaznacz pobrany szablon.  
10. Kliknij przycisk OK.
    * Dodaj nowy zakres w celu dynamicznego utworzenia pliku wyjściowego programu Excel ze wszystkimi wybranymi kolumnami (w formularzu okna dialogowego użytkownika) dla wymiarów finansowych. Każda komórka w każdej kolumnie będą reprezentować nazwę jednego wymiaru finansowego.  
11. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
12. W drzewie zaznacz element „Excel\Zakres”.
13. W polu Zakres programu Excel wpisz „DimNames”.
    * DimNames  
14. W polu Kierunek replikacji wybierz opcję „Poziomo”.
15. Kliknij przycisk OK.
16. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<DimNames>: Poziomo”.
17. Kliknij przycisk W górę.
18. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Komórka<DimNames>”.
19. Kliknij opcję Wytnij.
20. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<DimNames>: Poziomo”.
21. Kliknij opcję Wklej.
22. W drzewie rozwiń węzeł „Excel = "SampleFinDimWsReport"\Zakres<DimNames>: Poziomo”.
23. W drzewie rozwiń węzeł „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo”.
24. W drzewie rozwiń węzeł „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Vertical\Range<TransactionLine>: Pionowo”.
25. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Vertical\Range<TransactionLine>: Pionowo”.
    * Dodaj nowy zakres w celu dynamicznego utworzenia pliku wyjściowego programu Excel ze wszystkimi wybranymi kolumnami (w formularzu okna dialogowego użytkownika) dla wymiarów finansowych. Każda komórka w każdej kolumnie będą reprezentować wartość jednego wymiaru finansowego dla każdej raportowanej transakcji.  
26. Kliknij opcję Dodaj zakres.
27. W polu Zakres programu Excel wpisz „DimValues”.
    * DimValues  
28. W polu Kierunek replikacji wybierz opcję „Poziomo”.
29. Kliknij przycisk OK.
30. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<DimValues>”.
31. Kliknij opcję Wytnij.
32. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Zakres<DimValues>: Poziomo”.
33. Kliknij opcję Wklej.
34. W drzewie rozwiń węzeł „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Zakres<DimValues>: Poziomo”.

## <a name="map-format-elements-to-data-sources"></a>Mapowanie elementów formatu na źródła danych
1. Kliknij kartę Mapowanie.
2. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.
3. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.
4. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.
5. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.
6. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Zakres<DimValues>: Poziomo\Komórka<DimValues>”.
7. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.
8. Kliknij opcję Powiąż.
9. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Zakres<DimValues>: Poziomo”.
10. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.
11. Kliknij opcję Powiąż.
12. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<Credit>”.
13. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.
14. Kliknij opcję Powiąż.
15. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<Debit>”.
16. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.
17. Kliknij opcję Powiąż.
18. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<Currency>”.
19. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.
20. Kliknij opcję Powiąż.
21. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<TransDate>”.
22. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.
23. Kliknij opcję Powiąż.
24. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<TransVoucher>”.
25. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.
26. Kliknij opcję Powiąż.
27. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Zakres<TransactionLine>: Pionowo\Komórka<TransBatch>”.
28. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.
29. Kliknij opcję Powiąż.
30. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Vertical\Range<TransactionLine>: Pionowo”.
31. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.
32. Kliknij opcję Powiąż.
33. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo\Komórka<Batch>”.
34. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.
35. Kliknij opcję Powiąż.
36. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<JournalLine>: Pionowo”.
37. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.
38. Kliknij opcję Powiąż.
39. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Ustawienie wymiarów: Lista rekordów”.
40. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Ustawienie wymiarów: Lista rekordów\Kod: Ciąg”.
41. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<DimNames>: Poziomo\Komórka<DimNames>”.
42. Kliknij opcję Powiąż.
43. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Ustawienie wymiarów: Lista rekordów”.
44. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Zakres<DimNames>: Poziomo”.
45. Kliknij opcję Powiąż.
46. W drzewie zaznacz element „Excel = "SampleFinDimWsReport"\Komórka<CompanyName>”.
47. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.
48. Kliknij opcję Powiąż.
49. Kliknij przycisk Zapisz.
50. Zamknij stronę.

