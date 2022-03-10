---
title: ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1 — Projektowanie formatu)
description: W tym temacie opisano sposób konfigurowania formatu raportowania elektronicznego w celu generowania raportów jako plików arkuszy OPENXML (Excel). (część 1)
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab360c259af37ce3995d3cd2560bc2e765e0bceb
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2021
ms.locfileid: "7551783"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Używanie poziomo rozszerzalnych zakresów w celu dynamicznego dodawania kolumn w raportach programu Excel (Część 1 — Projektowanie formatu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może skonfigurować format raportowania elektronicznego (ER) do generowania raportów jako plików arkuszy OPENXML(Excel), w których wymagane kolumny mogą być tworzone dynamicznie jako poziomo rozszerzalne zakresy. Kroki można wykonać na danych dowolnej firmy.

W ceku wykonania tych kroków najpierw należy wykonać następujące trzy przewodniki po zadaniach:

„ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”

„ER Używanie wymiarów finansowych jako źródła danych (Część 1: Projektowanie modelu danych)”

„ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”

Należy także pobrać i zapisać kopię lokalną szablonu z raportem przykładowym dostępnym tutaj, [Przykładowy raport z usługi internetowej wymiarów finansowych](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx).

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

## <a name="create-a-new-report-configuration"></a>Tworzenie nowej konfiguracji raportu

1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz węzeł `Financial dimensions sample model`.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
4. W polu Nowe wprowadź wartość `Format based on data model Financial dimensions sample model`.
    * Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.  
5. W polu Nazwa wpisz `Sample report with horizontally expandable ranges`.
    * Przykładowy raport z poziomo rozszerzalnymi zakresami  
6. Wprowadź Opis wpisz `To make Excel output with dynamically adding columns`.
    * Generowanie danych wyjściowych programu Excel z dynamicznym dodawaniem kolumn  
7. W polu Definicja modelu danych zaznacz wartość Wpis.
8. Kliknij przycisk Utwórz konfigurację.

## <a name="design-the-report-format"></a>Projektowanie formatu raportu

1. Kliknij przycisk Konstruktor.
2. Włącz przełącznik `Show details`.
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
12. W drzewie zaznacz węzeł `Excel\Range`.
13. W polu Zakres programu Excel wpisz `DimNames`.
    * DimNames  
14. W polu Kierunek replikacji wybierz opcję `Horizontal`.
15. Kliknij przycisk OK.
16. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
17. Kliknij przycisk W górę.
18. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Cell<DimNames>`.
19. Kliknij opcję Wytnij.
20. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
21. Kliknij opcję Wklej.
22. W drzewie rozwiń węzeł `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
23. W drzewie rozwiń węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
24. W drzewie rozwiń węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
25. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
    * Dodaj nowy zakres w celu dynamicznego utworzenia pliku wyjściowego programu Excel ze wszystkimi wybranymi kolumnami (w formularzu okna dialogowego użytkownika) dla wymiarów finansowych. Każda komórka w każdej kolumnie będą reprezentować wartość jednego wymiaru finansowego dla każdej raportowanej transakcji.  
26. Kliknij opcję Dodaj zakres.
27. W polu Zakres programu Excel wpisz `DimValues`.
    * DimValues  
28. W polu Kierunek replikacji wybierz opcję `Horizontal`.
29. Kliknij przycisk OK.
30. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`.
31. Kliknij opcję Wytnij.
32. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
33. Kliknij opcję Wklej.
34. W drzewie rozwiń węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.

## <a name="map-format-elements-to-data-sources"></a>Mapowanie elementów formatu na źródła danych

1. Kliknij kartę Mapowanie.
2. W drzewie rozwiń węzeł `model: Data model Financial dimensions sample model`.
3. W drzewie rozwiń węzeł `model: Data model Financial dimensions sample model\Journal: Record list`.
4. W drzewie rozwiń węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
5. W drzewie rozwiń węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
6. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`.
7. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`.
8. Kliknij opcję Powiąż.
9. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
10. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
11. Kliknij opcję Powiąż.
12. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`.
13. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`.
14. Kliknij opcję Powiąż.
15. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`.
16. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`.
17. Kliknij opcję Powiąż.
18. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`.
19. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`.
20. Kliknij opcję Powiąż.
21. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`.
22. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`.
23. Kliknij opcję Powiąż.
24. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`.
25. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`.
26. Kliknij opcję Powiąż.
27. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`.
28. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
29. Kliknij opcję Powiąż.
30. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
31. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
32. Kliknij opcję Powiąż.
33. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`.
34. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
35. Kliknij opcję Powiąż.
36. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
37. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Journal: Record list`.
38. Kliknij opcję Powiąż.
39. W drzewie rozwiń węzeł `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
40. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`.
41. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`.
42. Kliknij opcję Powiąż.
43. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
44. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
45. Kliknij opcję Powiąż.
46. W drzewie zaznacz węzeł `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`.
47. W drzewie zaznacz węzeł `model: Data model Financial dimensions sample model\Company: String`.
48. Kliknij opcję Powiąż.
49. Kliknij przycisk Zapisz.
50. Zamknij stronę.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
