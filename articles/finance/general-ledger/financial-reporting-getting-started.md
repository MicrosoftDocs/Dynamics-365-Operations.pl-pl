---
title: Omówienie raportowania finansowego
description: W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej w Microsoft Dynamics 365 Finance i jak korzystać z funkcji raportowania finansowego.
author: aprilolson
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 363ce16b31a199e519c969746c4f10430d9d7497
ms.sourcegitcommit: 165e082e59ab783995c16fd70943584bc3ba3455
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "3967265"
---
# <a name="get-started-with-financial-reporting"></a>Rozpoczynanie pracy z Financial reporting 

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak uzyskać dostęp do modułu sprawozdawczości finansowej i jak korzystać z funkcji raportowania finansowego. Zawiera też opis domyślnych raportów finansowych, które są zawarte w programie.

<a name="accessing-financial-reporting"></a>Uzyskiwanie dostępu do raportowania finansowego
-----------------------------

Menu **Raportowanie finansowe** można znaleźć w następujących lokalizacjach:

-   **Księga główna** &gt; **Zapytania i raporty**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Budżetowanie podstawowe**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Planowanie budżetu**
-   **Budżetowanie** &gt; **Zapytania i raporty** &gt; **Kontrola budżetu**
-   Konsolidacje

Aby tworzyć i generować raporty finansowe firmy, należy ustawić następujące informacje o tej firmie:

-   Kalendarz obrachunkowy
-   Ledger
-   Plan kont
-   Waluta

## <a name="granting-security-access-to-financial-reporting"></a>Udzielanie zabezpieczeń do Raportowania finansowego
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

Po dodaniu użytkownika lub zmianie roli, użytkownik powinien mieć dostęp do raportów finansowych za kilka minut. 

> [!NOTE]
> Rola sysadmin jest dodawana do wszystkich ról w module raportowania finansowego.

## <a name="report-deletions-and-expirations"></a>Usuwanie i wygasanie raportów
Użytkownicy, którzy generują raport, mogą usuwać własne raporty. Użytkownicy, których obowiązkiem jest **utrzymywanie bezpieczeństwa raportowania finansowego** mogą usuwać raporty innych osób. 

W wersji 10.0.8 zostało wprowadzone pojęcie dat wygaśnięcia. Nowa wymagana funkcja jest włączona na stronie **Wszystkie** w obszarze roboczym zarządzanie funkcjami. Funkcja **Zasad zatrzymania raportu finansowego** zawiera następujące zmiany:
* Nowo wygenerowane raporty będą automatycznie oznaczane jako posiadające datę wygaśnięcia 90 dni od daty wygenerowania.
* Wszystkie istniejące raporty sprzed zainstalowania tej funkcji będą miały okres ważności 90 dni. Data może być pusta przez krótki okres do czasu uruchomienia usługi raportowania finansowego, generowany jest raport, a usługa przeprowadza aktualizację do istniejących raportów z pustą datą wygaśnięcia. 
* Użytkownicy odpowiedzialni za **Utrzymywanie bezpieczeństwa financial reporting** mają dostęp do tej funkcji. Każdy użytkownik z obowiązkiem **utrzymywania raportu finansowego** i przyznanym uprawnieniem **Utrzymanie wygaśnięcia raportu finansowego** będzie również mieć możliwość modyfikowania okresu wygaśnięcia. Obecnie dostępne są dwie opcje przechowywania: 
  * Wygaśnięcie wynoszące 90 dni.
  * Opcja ustawiania raportu tak, aby nigdy nie wygasał.
  
W przypadku wybrania terminu wygaśnięcia, na przykład 90 dni, obowiązuje 90 dni od dzisiaj. Jest to zachowanie inne niż 90 dni od pierwotnej daty wygenerowania ustawionej podczas generowania raportu. 
  
Dodatkowe opcje będą brane pod uwagę w przyszłych funkcjach. Okres ważności wynoszący 90 dni będzie określony jako domyślny, a użytkownicy z odpowiednimi uprawnieniami mogą zastąpić domyślne ustawienia na stronie listy **Raportów finansowych**.    

## <a name="default-reports"></a>Raporty domyślne
Raporty finansowe to 22 domyślne raporty. Każdy raport korzysta z domyślnych kategorii kont głównych. Raporty te można wykorzystywać w takiej formie, w jakiej są lub jako bazy do utworzenia własnego raportu finansowego. Oprócz tradycyjnych sprawozdań finansowych, takich jak Zestawienie przychodów i Bilans, te domyślne raporty obejmują raporty, które pokazują różne typy raportów finansowych, które możesz utworzyć. 

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
Po wybraniu menu **Raportowanie finansowe** jest wyświetlana lista domyślnych raportów finansowych firmy. Następnie można otworzyć lub zmodyfikować raport. Aby otworzyć jeden z domyślnych raportów, należy wybrać nazwę raportu. Kiedy raport zostanie otwarty po raz pierwszy, zostanie automatycznie wygenerowany raport za poprzedni miesiąc. Na przykład jeśli raport zostanie otwarty po raz pierwszy w sierpniu 2019, jest generowany raport na 31 lipca 2019 r. Po otwarciu raportu, możesz zapoznać się ze szczegółowymi danymi i opcjami modyfikacji.

## <a name="creating-and-modifying-financial-reports"></a>Tworzenie i modyfikowanie raportów finansowych
Z listy raportów finansowych można utworzyć nowy raport lub zmodyfikować istniejący raport. Jeśli masz odpowiednie uprawnienia, możesz utworzyć nowy raport finansowy, wybierając przycisk **Nowy** w okienku akcji. Projektant raportów zostanie pobrany na Twoje urządzenie i uruchomiony. Po uruchomieniu projektanta raportów można utworzyć nowy raport. Po zapisaniu nowego raportu będzie on widoczny na liście raportów finansowych. Na liście są wyświetlane tylko raporty, które zostały utworzone dla firmy używanej w Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Definicje drzew raportowania 
Jednym z składników używanych do tworzenia raportów finansowych jest definicja drzewa raportowania. Drzewo definicji raportowania pomaga zdefiniować strukturę i hierarchię organizacji. To międzywymiarowa hierarchiczna struktura oparta na powiązaniach wymiarów w danych finansowych. Dostarcza informacji na poziomie jednostki raportowania oraz na poziomie podsumowania dla wszystkich jednostek w drzewie.

Można utworzyć dowolną liczbę drzew raportowania, aby wyświetlić dane firmy na różne sposoby. Każde drzewo raportowania może zawierać dowolną kombinację działów i jednostek podsumowujących, ale definicja raportu może być połączona tylko z jednym drzewem raportowania naraz. 


## <a name="troubleshooting-issues-opening-report-designer"></a>Rozwiązywanie problemów z otwieraniem projektanta raportów
Istnieje kilka typowych problemów, które mogą być przyczyną problemów podczas otwierania projektanta raportów. Poniżej wymieniono zagadnienia związane z tymi problemami i czynności, które należy rozwiązać.

Wydanie 1: Projektant raportów nie rozpoczyna się po wybraniu opcji **Nowy** lub **Edytuj**.

* W obszarze Internet Explorer wybierz opcję **Ustawienia**, a następnie wybierz **Opcje internetowe**. Wybierz kartę **Zabezpieczenia**. Wybierz opcję Zaufane witryny, a następnie wybierz opcję **Witryny**. W obszarze **Dodaj tę witrynę sieci Web do strefy** wprowadź „\*\.dynamics.com” (bez znaków cudzysłowu), a następnie wybierz pozycję **Dodaj**. 
* W obszarze Internet Explorer wybierz opcję **Ustawienia**, a następnie wybierz **Opcje internetowe**. Wybierz kartę **Zabezpieczenia**. Wybierz opcję Zaufane witryny. W obszarze o nazwie poziom zabezpieczeń dla tej strefy Zmień opcję na **Średni — niski**.
* Wyłącz funkcję blokowania wyskakujących okienek w przeglądarce.
* Do zainstalowania Struktury Microsoft .NET 4.6.2 lub nowszej wymagane są stacje robocze. Tę wersję programu Microsoft .NET Framework można pobrać i zainstalować z witryny [Centrum pobierania Microsoft](https://www.microsoft.com/download/details.aspx?id=53345).
* Jeśli używasz programu Microsoft Edge z przeglądarką Chrome, należy zainstalować rozszerzenie ClickOnce, aby można było pobrać klienta Projektanta raportów. Jeśli pracujesz w trybie incognito, upewnij się, że w rozszerzeniu ClickOnce również włączono tryb incognito. 
     1. Otwórz nową przeglądarkę w programie Microsoft Edge.
     2. Wprowadź **edge://flags** i wybierz **Enter**.
     3. Wyszukaj opcję **Obsługa ClickOnce** lub skorzystaj z tego bezpośredniego łącza: **edge://flags/#edge-click-once**.
     4. Ustaw opcję menu rozwijanego na **Włączone**.
     5. Wybierz opcję **Uruchom ponownie przeglądarkę**.

Wydanie 2: użytkownik nie został przypisany do wymaganych uprawnień do korzystania z Raportowania finansowego. 

* Aby sprawdzić, czy użytkownik nie ma uprawnienia, należy wybrać opcję **Tak** dla błędu, a „Nie można połączyć się z serwerem Raportowania finansowego. Wybierz opcję Tak, jeśli chcesz kontynuować, i podaj inny adres serwera”. Następnie wybierz **Testuj połączenie**. Jeśli nie masz uprawnień, zostanie wyświetlony komunikat „Próba połączenia nie powiodła się. Użytkownik nie ma odpowiednich uprawnień, aby połączyć się z serwerem. Skontaktuj się z administratorem systemu”.
* Powyższe uprawnienia są wymienione powyżej w celu [Udzielanie zabezpieczeń do Raportowania finansowego](#granting-security-access-to-financial-reporting). Zabezpieczenia w Raportowaniu finansowym są oparte na tych uprawnieniach. Nie będziesz mieć dostępu, dopóki nie zostaną przypisane te uprawnienia (lub inna rola zabezpieczeń zawierająca te uprawnienia). 
* Zadanie integracji **Dostawca firmowych użytkowników dla firmy** (które jest również odpowiedzialne i znane jako integracja użytkowników) jest uruchamiane co 5 minut. Wprowadzenie zmian uprawnień w Raportowaniu finansowym może potrwać do 10 minut. 
  Jeśli inny użytkownik może otworzyć Projektanta raportów, wybierz menu **Narzędzia**, a następnie wybierz polecenie **Stan integracji**. Sprawdź, czy mapa integracji „Dostawca firmowych użytkowników dla firmy” została pomyślnie uruchomiona, ponieważ przypisano Ci uprawnienia do korzystania z funkcji Raportowania finansowego. 
* Może być możliwe, że inny błąd zabronił **Integracja użytkowników Dynamics z użytkownikami Raportowania finansowego** z jego zakończeniem. Możliwe, że resetowanie składni danych zostało zainicjowane i nie zostało jeszcze zakończone lub wystąpił inny błąd systemu. Spróbuj uruchomić proces ponownie później. Jeśli problem będzie się powtarzał, skontaktuj się z administratorem systemu.

Wydanie 3: na stronie rejestracja projektanta raportów ClickOnce można kontynuować pracę, ale nie można zakończyć logowania w oknie Projektanta raportów. 

* Czas określony na komputerze lokalnym podczas wprowadzania poświadczeń logowania musi zawierać się w ciągu pięciu minut od czasu na serwerze Financial Reporting. Jeśli występuje różnica ponad 5 minut, system nie pozwoli na zarejestrowanie się. 
* W takim przypadku zalecamy włączenie opcji systemu Windows w celu automatycznego ustawienia czasu na komputerze. 

## <a name="additional-resources"></a>Dodatkowe zasoby
- [Wyświetlanie raportów finansowych](view-financial-reports.md)
- [Definicje drzewa raportowania w raportach finansowych](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)
