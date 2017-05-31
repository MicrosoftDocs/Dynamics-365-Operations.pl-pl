---
title: Raporty finansowe
description: "W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej w programie Microsoft Dynamics 365 for Operations i jak korzystać z funkcji raportowania finansowego. Zawiera opis domyślnych raportów finansowych, które są zawarte w programie."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 39db754df7edeca414752ce1844d7f9e85df0b36
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="financial-reporting"></a>Raporty finansowe

[!include[banner](../includes/banner.md)]


W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej w programie Microsoft Dynamics 365 for Operations i jak korzystać z funkcji raportowania finansowego. Zawiera opis domyślnych raportów finansowych, które są zawarte w programie.

<a name="accessing-financial-reporting"></a>Uzyskiwanie dostępu do raportowania finansowego
-----------------------------

Menu **Raporty finansowe** można znaleźć w następujących miejscach w programie Dynamics 365 for Operations:

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
| Obsługa zabezpieczeń raportowania finansowego | Obsługa zabezpieczeń raportowania finansowego oraz wykonywanie zadań administracyjnych. | FinancialReportsSecurityMaintain |
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
Raporty finansowe to 22 domyślne raporty. Każdy raport używa domyślnych kategorii konta głównego w programie Dynamics 365 for Operations. Raporty te można wykorzystywać w takiej formie, w jakiej są lub jako bazy do utworzenia własnego raportu finansowego. Oprócz tradycyjnych sprawozdań finansowych, takich jak Zestawienie przychodów i Bilans, te domyślne raporty obejmują raporty, które pokazują różne typy raportów finansowych, które możesz utworzyć. Wpis każdego raportu w poniższej tabeli prowadzi do prezentacji Office Mix o danym raporcie.

| Raport domyślny                                                                                         | opis                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12-miesięczne kroczące jednokolumnowe zestawienie przychodów — domyślny](https://mix.office.com/watch/76kc7bm3wnt1) | Służy do wyświetlania dochodowości organizacji przez okres 12 miesięcy w jednej kolumnie.                                                                                                                                                                                                                                      |
| [12-miesięczne zestawienie trendów przychodów — domyślny](https://mix.office.com/watch/12brmfge5p8r)                 | Służy do wyświetlania dochodowości organizacji przez okres 12 miesięcy w jednej kolumnie. Te 12 miesięcy może obejmować więcej niż jeden rok obrachunkowy.                                                                                                                                                                                             |
| [Rzeczywiste a budżet — domyślne](https://mix.office.com/watch/fi439lkwr0no)                                | Służy do wyświetlania informacji szczegółowych salda dla wszystkich kont dla pierwotnego budżetu i porównywania skorygowanego budżetu do wartości rzeczywistych, w których zanotowano odchylenia.                                                                                                                                                                          |
| [Szczegóły inspekcji — domyślny](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Ten raport przedstawia salda po stronie debetowej i kredytowej w walucie raportowania i walucie lokalnej, wraz z dodatkowymi informacjami o transakcji, takimi jak identyfikator użytkownika, użytkownik, który jako ostatni zmodyfikował dane, data ostatniej modyfikacji i identyfikator arkusza. |
| [Lista salda — domyślna](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Ten raport przedstawia otwierające i zamykające salda oraz salda po stronie kredytowej i debetowej dla bieżącego okresu i roku do danego dnia, wraz z dodatkowymi informacjami o transakcji, takimi jak załącznik.                                                                    |
| [Bilans — domyślne](https://mix.office.com/watch/zkgq0u7visw9)                                   | Oferuje widok pozycji finansowej organizacji w danym roku.                                                                                                                                                                                                                                                             |
| [Bilans i rachunek wyników obok siebie — domyślny](https://mix.office.com/watch/zkgq0u7visw9) | Służy do wyświetlania sytuacji finansowej organizacji i rentowności na rok obok siebie.                                                                                                                                                                                                                              |
| [Przepływy pieniężne — domyślny](https://mix.office.com/watch/jd3go9pz6390)                                       | Lepszy wgląd w środki pieniężne przychodzące i wychodzącą organizacji.                                                                                                                                                                                                                                   |
| [Szczegółowe JE i Przegląd TB — domyślne](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Widok otwarcia salda i informacje o działaniach dla wszystkich kont.                                                                                                                                                                                                                                                      |
| [Szczegółowy bilans próbny — domyślne](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Wyświetla informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.                                                                                                                                  |
| [Trend kwartalny wydatków z trzech lat — domyślne](https://mix.office.com/watch/gwm4zu7tmtj8)             | Lepszy wgląd w wydatki w poprzednich 12 kwartałach w ciągu ostatnich 3 lat.                                                                                                                                                                                                                                   |
| [Podpisy finansowe JE i Przegląd TB — domyślne](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Wyświetlanie przeglądu sald i działania dla środków trwałych, zobowiązań, kapitału własnego właściciela, przychodu, wydatków, zysków i strat.                                                                                                                                                                           |
| [Zestawienie przychodów — domyślne](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Pokazuje rentowność organizacji w bieżącym okresie i od początku roku.                                                                                                                                                                                                                                   |
| [Lista transakcji księgi — domyślne](https://mix.office.com/watch/19h9v2rmh48vy)                        | Służy do wyświetlania szczegółowych danych salda dla wszystkich kont. Raport ten zawiera salda debetu i kredytu, łącznie dodatkowymi informacjami o transakcji, takimi jak data transakcji, numer arkusza, załącznik, typ księgowania i numer śledzenia.                                                                            |
| [Współczynniki — domyślne](https://mix.office.com/watch/b08hfc5h92me)                                          | Pokazuje współczynniki wypłacalności, rentowności i efektywności organizacji w bieżącym roku.                                                                                                                                                                                                                           |
| [Kroczące wydatki 12-miesięczne — domyślne](https://mix.office.com/watch/iywod5qmqhz7)                       | Lepszy wgląd w wydatki dla każdego z ostatnich 12 miesięcy. Te 12 miesięcy może obejmować więcej niż jeden rok obrachunkowy.                                                                                                                                                                                                       |
| [Kroczące kwartalne zestawienie przychodów — domyślne](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Służy do wyświetlania rentowności organizacji co kwartał za miniony rok i od początku bieżącego roku.                                                                                                                                                                                                                   |
| [Obok arkusza bilansowego — domyślna](https://mix.office.com/watch/zkgq0u7visw9)                      | Oferuje widok pozycji finansowej organizacji w danym roku. Ten raport pokazuje aktywa i pasywa oraz kapitał własny udziałowców są pokazane równolegle.                                                                                                                                                                                |
| [Sumaryczny bilans próbny — domyślny](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Oferuje informacje o saldzie dla wszystkich kont zawierających salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.                                                                                                                                                                  |
| [Sumaryczny bilans próbny rok do roku — domyślny](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Oferuje informacje o saldzie dla wszystkich kont zawierających salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego.                                                                                                                           |
| [Tygodniowa sprzedaż i rabaty — domyślne](https://mix.office.com/watch/112ng0hy5de0j)                     | Lepszy wgląd w sprzedaż i rabaty dla każdego tygodnia w miesiącu. Ten raport zawiera sumę z czterech tygodni.                                                                                                                                                                                                              |
| [Dostępne środki budżetowe — domyślny](https://mix.office.com/watch/15hcpezcbx7tv)                         | Wyświetlanie szczegółowego porównania skorygowanego budżetu, rzeczywistych rozchodów, rezerwacji budżetu i środków budżetowych dostępnych dla wszystkich kont                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Otwieranie raportów finansowych
Po kliknięciu menu **Raporty finansowe** jest wyświetlana lista domyślnych raportów finansowych firmy. Następnie można otworzyć lub zmodyfikować raport. Aby otworzyć jeden z domyślnych raportów, należy wybrać nazwę raportu. Kiedy raport zostanie otwarty po raz pierwszy, zostanie automatycznie wygenerowany raport za poprzedni miesiąc. Na przykład jeśli raport zostanie otwarty po raz pierwszy w sierpniu 2016, jest generowany raport na 31 lipca 2016 r. Po otwarciu raportu, możesz zapoznać się ze szczegółowymi danymi i opcjami modyfikacji.

## <a name="creating-and-modifying-financial-reports"></a>Tworzenie i modyfikowanie raportów finansowych
Z listy raportów finansowych można utworzyć nowy raport lub zmodyfikować istniejący raport. Jeśli masz odpowiednie uprawnienia, możesz utworzyć nowy raport finansowy, klikając przycisk **Nowy** w okienku akcji. Projektant raportów zostanie pobrany na Twoje urządzenie i uruchomiony. Po uruchomieniu projektanta raportów można utworzyć nowy raport. Po zapisaniu nowego raportu będzie on widoczny na liście raportów finansowych. Na liście są wyświetlane tylko raporty, które zostały utworzone dla firmy używanej w programie Dynamics 365 for Operations. Aby uzyskać więcej informacji na temat procesu tworzenia i modyfikowania raportów finansowych w programie Dynamics 365 for Operations, zobacz następujące [wpisy](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) na blogu o module sprawozdawczości finansowej w systemie Dynamics. **Uwaga:** Komputer, do którego pobierasz aplikację kliencką projektanta raportów, musi mieć zainstalowane oprogramowanie Microsoft .NET Framework w wersji 4.6.2. Tę wersję programu Microsoft .NET Framework można pobrać i zainstalować [stąd](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Jeśli używasz przeglądarki Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta projektanta raportów. Jeśli pracujesz w trybie incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb incognito. Po zapisaniu nowego raportu będzie on widoczny na liście raportów finansowych. Po wybraniu obszaru wokół nazwy raportu kliknij przycisk **Edytuj** w okienku akcji. Zostanie uruchomiony projektant raportów.

<a name="see-also"></a>Informacje dodatkowe
--------

[Wyświetlanie raportów finansowych](view-financial-reports.md)

[Blog o sprawozdawczości finansowej w systemie Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




