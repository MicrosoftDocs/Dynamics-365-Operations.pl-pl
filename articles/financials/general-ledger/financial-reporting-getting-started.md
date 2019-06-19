---
title: Raporty finansowe
description: W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej w programie Microsoft Dynamics 365 for Finance and Operations i jak korzystać z funkcji raportowania finansowego. Zawiera opis domyślnych raportów finansowych, które są zawarte w programie.
author: aprilolson
manager: AnnBe
ms.date: 05/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8d3630e60fb2f1a8ca7e3610bbb4fcd32c17dec
ms.sourcegitcommit: 06c8dc5bc4e1c41f68e1cda141d61529768be958
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2019
ms.locfileid: "1594967"
---
# <a name="financial-reporting"></a>Raporty finansowe

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej w programie Microsoft Dynamics 365 for Finance and Operations i jak korzystać z funkcji raportowania finansowego. Zawiera opis domyślnych raportów finansowych, które są zawarte w programie.

<a name="accessing-financial-reporting"></a>Uzyskiwanie dostępu do raportowania finansowego
-----------------------------

Menu **Raporty finansowe** można znaleźć w następujących miejscach w programie Finance and Operations:

-   **Księga główna** &gt; **Zapytania i raporty**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Budżetowanie podstawowe**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Planowanie budżetu**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Kontrola budżetu**
-   Konsolidacje

Aby tworzyć i generować raporty finansowe firmy, należy ustawić następujące informacje o tej firmie:

-   Kalendarz obrachunkowy
-   Księga
-   Plan kont
-   Waluta

Funkcje raportowania finansowego są dostępne dla użytkowników, którzy mają odpowiednie uprawnienia i obowiązki przypisane za pomocą ich ról zabezpieczeń. W poniższych sekcjach wymieniono te uprawnienia i obowiązki, łącznie z powiązanymi rolami.

### <a name="duties"></a>Obowiązki

| Etykieta cła                            | Opis                                                             | Nazwa drzewa obiektów aplikacji (AOT)                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Obsługa zabezpieczeń raportowania finansowego | Obsługa zabezpieczeń raportowania finansowego oraz wykonywanie zadań administracyjnych. | FinancialReportsSecurityMaintain |
| Obsługa raportów finansowych            | Projektowanie i obsługa raportów finansowych.                                  | FinancialReportsMaintain         |
| Generowanie raportów finansowych            | Generowanie i odświeżanie raportów finansowych.                                 | FinancialReportsGenerate         |
| Przeglądanie wyników finansowych          | Przeglądanie i analizowanie wyników finansowych.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Uprawnienia

| Uprawnienie etykiety                       | Opis                                                             | Nazwa drzewa obiektów aplikacji (AOT)                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Obsługa zabezpieczeń raportowania finansowego | Obsługa zabezpieczeń raportowania finansowego oraz wykonywanie zadań administracyjnych. | FinancialReportsSecuritySystemMaintain |
| Obsługa raportów finansowych            | Projektowanie i obsługa raportów finansowych.                                  | FinancialReportsMaintainReports  |
| Generowanie raportów finansowych            | Generowanie i odświeżanie raportów finansowych.                                 | FinancialReportsGenerateReports  |
| Wyświetlanie raportów finansowych                | Wyświetlanie raportów finansowych.                                                 | FinancialReportsView             |

### <a name="roles"></a>Role

| Uprawnienie etykiety                       | Obowiązek                                  | Role                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Obsługa zabezpieczeń raportowania finansowego | Obsługa zabezpieczeń raportowania finansowego | Administrator zabezpieczeń                                                          |
| Obsługa raportów finansowych            | Obsługa raportów finansowych            | Menedżer ds. księgowania, Kierownik ds. księgowania, Kontroler finansowy, Menedżer budżetu |
| Generowanie raportów finansowych            | Generowanie raportów finansowych            | Dyrektor generalny, Dyrektor finansowy, Księgowy                                                            |
| Wyświetlanie raportów finansowych                | Przeglądanie wyników finansowych          | Nie przypisano                                                                   |

Po dodaniu użytkownika lub zmianie roli, użytkownik powinien mieć dostęp do raportów finansowych za kilka minut. **Uwaga:** Rola sysadmin jest dodawana do wszystkich ról w module sprawozdawczości finansowej.

## <a name="default-reports"></a>Raporty domyślne
Raporty finansowe to 22 domyślne raporty. Każdy raport używa domyślnych kategorii konta głównego w programie Finance and Operations. Raporty te można wykorzystywać w takiej formie, w jakiej są lub jako bazy do utworzenia własnego raportu finansowego. Oprócz tradycyjnych sprawozdań finansowych, takich jak Zestawienie przychodów i Bilans, te domyślne raporty obejmują raporty, które pokazują różne typy raportów finansowych, które możesz utworzyć. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Raport domyślny                                                                                         | Opis                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 12-miesięczne kroczące jednokolumnowe zestawienie przychodów — domyślny | Służy do wyświetlania dochodowości organizacji przez okres 12 miesięcy w jednej kolumnie.                                                                                                                                                                                                                                      |
| 12-miesięczne zestawienie trendów przychodów — domyślny                 | Służy do wyświetlania dochodowości organizacji przez okres 12 miesięcy w jednej kolumnie. Te 12 miesięcy może obejmować więcej niż jeden rok obrachunkowy.                                                                                                                                                                                             |
| Rzeczywiste a budżet — domyślne                                | Służy do wyświetlania informacji szczegółowych salda dla wszystkich kont dla pierwotnego budżetu i porównywania skorygowanego budżetu do wartości rzeczywistych, w których zanotowano odchylenia.                                                                                                                                                                          |
| Szczegóły inspekcji — domyślny                                  | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Ten raport przedstawia salda po stronie debetowej i kredytowej w walucie raportowania i walucie lokalnej, wraz z dodatkowymi informacjami o transakcji, takimi jak identyfikator użytkownika, użytkownik, który jako ostatni zmodyfikował dane, data ostatniej modyfikacji i identyfikator arkusza. |
| Lista salda — domyślna                                   | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Ten raport przedstawia otwierające i zamykające salda oraz salda po stronie kredytowej i debetowej dla bieżącego okresu i roku do danego dnia, wraz z dodatkowymi informacjami o transakcji, takimi jak załącznik.                                                                    |
| Bilans — domyślne                                   | Oferuje widok pozycji finansowej organizacji w danym roku.                                                                                                                                                                                                                                                             |
| Bilans i rachunek wyników obok siebie — domyślny | Służy do wyświetlania sytuacji finansowej organizacji i rentowności na rok obok siebie.                                                                                                                                                                                                                              |
| Przepływy pieniężne — domyślny                                       | Lepszy wgląd w środki pieniężne przychodzące i wychodzącą organizacji.                                                                                                                                                                                                                                   |
| Szczegółowe JE i Przegląd TB — domyślne                      | Widok otwarcia salda i informacje o działaniach dla wszystkich kont.                                                                                                                                                                                                                                                      |
| Szczegółowy bilans próbny — domyślne                         | Wyświetla informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.                                                                                                                                  |
| Trend kwartalny wydatków z trzech lat — domyślne             | Lepszy wgląd w wydatki w poprzednich 12 kwartałach w ciągu ostatnich 3 lat.                                                                                                                                                                                                                                   |
| Podpisy finansowe JE i Przegląd TB — domyślne            | Wyświetlanie przeglądu sald i działania dla środków trwałych, zobowiązań, kapitału własnego właściciela, przychodu, wydatków, zysków i strat.                                                                                                                                                                           |
| Zestawienie przychodów — domyślne                                | Pokazuje rentowność organizacji w bieżącym okresie i od początku roku.                                                                                                                                                                                                                                   |
| Lista transakcji księgi — domyślne                        | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Raport ten zawiera salda debetu i kredytu, łącznie dodatkowymi informacjami o transakcji, takimi jak data transakcji, numer arkusza, załącznik, typ księgowania i numer śledzenia.                                                                            |
| Współczynniki — domyślne                                          | Pokazuje współczynniki wypłacalności, rentowności i efektywności organizacji w bieżącym roku.                                                                                                                                                                                                                           |
| Kroczące wydatki 12-miesięczne — domyślne                       | Lepszy wgląd w wydatki dla każdego z ostatnich 12 miesięcy. Te 12 miesięcy może obejmować więcej niż jeden rok obrachunkowy.                                                                                                                                                                                                       |
| Kroczące kwartalne zestawienie przychodów — domyślne               | Służy do wyświetlania rentowności organizacji co kwartał za miniony rok i od początku bieżącego roku.                                                                                                                                                                                                                   |
| Obok arkusza bilansowego — domyślna                      | Oferuje widok pozycji finansowej organizacji w danym roku. Ten raport pokazuje aktywa i pasywa oraz kapitał własny udziałowców są pokazane równolegle.                                                                                                                                                                                |
| Sumaryczny bilans próbny — domyślny                          | Oferuje informacje o saldzie dla wszystkich kont zawierających salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.                                                                                                                                                                  |
| Sumaryczny bilans próbny rok do roku — domyślny           | Oferuje informacje o saldzie dla wszystkich kont zawierających salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego.                                                                                                                           |
| Tygodniowa sprzedaż i rabaty — domyślne                     | Lepszy wgląd w sprzedaż i rabaty dla każdego tygodnia w miesiącu. Ten raport zawiera sumę z czterech tygodni.                                                                                                                                                                                                              |
| Dostępne środki budżetowe — domyślny                         | Wyświetlanie szczegółowego porównania skorygowanego budżetu, rzeczywistych rozchodów, rezerwacji budżetu i środków budżetowych dostępnych dla wszystkich kont                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Otwieranie raportów finansowych
Po kliknięciu menu **Raporty finansowe** jest wyświetlana lista domyślnych raportów finansowych firmy. Następnie można otworzyć lub zmodyfikować raport. Aby otworzyć jeden z domyślnych raportów, należy wybrać nazwę raportu. Kiedy raport zostanie otwarty po raz pierwszy, zostanie automatycznie wygenerowany raport za poprzedni miesiąc. Na przykład jeśli raport zostanie otwarty po raz pierwszy w sierpniu 2016, jest generowany raport na 31 lipca 2016 r. Po otwarciu raportu, możesz zapoznać się ze szczegółowymi danymi i opcjami modyfikacji.

## <a name="creating-and-modifying-financial-reports"></a>Tworzenie i modyfikowanie raportów finansowych
Z listy raportów finansowych można utworzyć nowy raport lub zmodyfikować istniejący raport. Jeśli masz odpowiednie uprawnienia, możesz utworzyć nowy raport finansowy, klikając przycisk **Nowy** w okienku akcji. Projektant raportów zostanie pobrany na Twoje urządzenie i uruchomiony. Po uruchomieniu projektanta raportów można utworzyć nowy raport. Po zapisaniu nowego raportu będzie on widoczny na liście raportów finansowych. Na liście są wyświetlane tylko raporty, które zostały utworzone dla firmy używanej w programie Finance and Operations. 

> [!NOTE] 
> Komputer, do którego pobierasz aplikację kliencką projektanta raportów, musi mieć zainstalowane oprogramowanie Microsoft .NET Framework w wersji 4.6.2. Tę wersję programu Microsoft .NET Framework można pobrać i zainstalować z witryny [Centrum pobierania Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta projektanta raportów. Jeśli pracujesz w trybie incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb incognito. Po zapisaniu nowego raportu będzie on widoczny na liście raportów finansowych. Po wybraniu obszaru wokół nazwy raportu kliknij przycisk **Edytuj** w okienku akcji. Zostanie uruchomiony projektant raportów.

## <a name="additional-resources"></a>Dodatkowe zasoby
- [Wyświetlanie raportów finansowych](view-financial-reports.md)



