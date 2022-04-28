---
title: Analizy rozwiązania Commerce (wersja zapoznawcza)
description: W tym temacie opisano sposób instalowania i używania możliwości analitycznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/24/2022
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 63d6e5ef7e883578106495d5ec778bbd686ee92d
ms.sourcegitcommit: 722854cb0d302d01ce3d9580ac80dc7c23d19bf5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2022
ms.locfileid: "8550014"
---
# <a name="commerce-analytics-preview"></a>Analizy rozwiązania Commerce (wersja zapoznawcza)

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób instalowania analizy rozwiązania Commerce (wersja zapoznawcza), funkcjonalności analizy zawartej w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Analizy rozwiązania Commerce (wersja zapoznawcza) — wersja demonstracyjna na żywo

Możesz spróbować [na żywo wersji Commerce Analytics (wersja zapoznawcza)](https://aka.ms/CommerceAnalyticsDemo).

![Podsumowanie analizy rozwiązania Commerce (wersja zapoznawcza)](media/CommerceAnalytics_Summary.png)
![Płatności analizy rozwiązania Commerce (wersja zapoznawcza)](media/CommerceAnalytics_Payments.png)
![Działalność internetowa analizy rozwiązania Commerce (wersja zapoznawcza)](media/CommerceAnalytics_WebActivity.png)

## <a name="commerce-analytics-preview-system-architecture"></a>Architektura systemu analiz rozwiązania Commerce (wersja zapoznawcza)

### <a name="key-components"></a>Najważniejsze składniki

Analizy rozwiązania Commerce (wersja zapoznawcza) składają się z następujących kluczowych składników:

- Gotowe do użycia interakcyjne raporty Power BI
- Widoki SQL w Azure Synapse Analytics
- Jednostki i dane ontologicznie w systemie Azure Data Lake
- Dane pierwotne w usłudze Azure Data Lake

![Kluczowe składniki architektury systemu analiz rozwiązania Commerce](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Przepływ danych

#### <a name="step-1-data-generation"></a>Krok 1: Generowanie danych

Dane pochodzą albo z jednego z poniższych źródeł albo jako dane transakcyjne, albo behawioralne:

- Pracownik centrum obsługi używa klienta centrali Commerce HQ do przetwarzania zamówień sprzedaży.
- Kasjer w kasie w punktu sprzedaży (POS) przetwarza transakcje sprzedaży.
- Sprzedaż jest tworzona w aplikacjach niestandardowych za pomocą rozwiązania Commerce bez kierownictwa (Commerce Scale Unit).
- Nabywca w Internecie przegląda witrynę internetową handlu elektronicznego.
- Nabywca w Internecie składa zamówienie na witrynie internetowej handlu elektronicznego.
- Dane są tworzone przez inne systemy, na przykład rozwiązanie Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Krok 2: Pozyskiwanie i przetwarzanie wstępne

Dane transakcyjne są przenoszone do centrali Commerce HQ bezpośrednio (w przypadku zamówień, które są przechwytywane bezpośrednio w kliencie Commerce HQ) lub za pośrednictwem usługi Commerce Scale Unit (w przypadku zamówień przechwyconych w punkcie sprzedaży, handlu elektronicznym lub w klientach niestandardowych, którzy korzystają z rozwiązania Commerce bez kierownictwa).

Funkcja Eksportuj do danych Data Lake jest następnie używana do kopiowania danych transakcyjnych do danych data lake jako dane pierwotne. W danych data lake dane pierwotne są przechowywane w folderze Tabele.

Dane działania w sieci Web handlu elektronicznego są wysyłane bezpośrednio do danych data lake. Dane produkowane przez inne systemy, takie jak Dynamics 365 Connected Spaces, są przed nie wysyłane bezpośrednio do danych data lake.

#### <a name="step-3-transformation-and-aggregation"></a>Krok 3: Przekształcenie i agregacja

Gdy dane pierwotne zostaną umieszczone w danych data lake, usługa analiz rozwiązania Commerce odczytuje je, przekształca, agreguje i zapisuje z powrotem w danych data lake w postaci jednostek logicznych (w folderze Jednostki) i zagregowanych metryk (w folderze Ontologie).

#### <a name="step-4-querying"></a>Krok 4: Zapytania

Analizy usługi Azure Synapse Analytics służą do zapytań w danych data lake za pośrednictwem interfejsu Transact-SQL (T-SQL). Ten interfejs zawiera widoki SQL. Widoki SQL umożliwiają federacyjne wykonywanie zapytań o dane w data lake za pośrednictwem klienta T-SQL (w celu analizy ad hoc) lub za pomocą narzędzia wizualizacji, takiego jak Power BI.

#### <a name="step-5-modeling-and-serving"></a>Krok 5: Modelowanie i służenie

Dane, o które zapytano przez Azure Synapse Analytics są umieszczane w modelu semantycznym Power BI. W zależności od typu danych są to dane okresowo importowane w pamięci do usługi Power BI lub z bezpośrednich zapytać w trakcie uruchomienia.

Na koniec dane są renderowane w sposób wizualny w usłudze Power BI, dzięki czemu użytkownicy mogą je wyświetlać i z nimi współpracować.

## <a name="commerce-analytics-preview-functional-overview"></a>Omówienie funkcji analiz rozwiązania Commerce (wersja zapoznawcza)

### <a name="summary"></a>Sumarycznie

Aplikacja szablonu analiz rozwiązania Commerce zawiera następujące strony raportów głównych:

1. [Filtry najwyższego poziomu](#TopLevelFilters)
2. [Produkty](#ProductsPage)
3. [Odbiorcy](#CustomersPage)
4. [Kanały](#ChannelsPage)
5. [Sprzedaż](#SalesPage)
6. [Marginesy](#MarginsPage)
7. [Zwroty](#ReturnsPage)
8. [Rabaty](#DiscountsPage)
9. [Płatności](#PaymentsPage)
10. [Odbiorcy](#CustomersPage)
11. [Porównanie](#ComparisonPage)
12. [Działanie w sieci](#WebActivityPage)
13. [Działanie w sieci Web — filtr najwyższego poziomu](#WebActivityTopLevelFilters)

#### <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtry najwyższego poziomu

- Ustawienia daty

    - Rok
    - Kwartał
    - Miesiąc
    - Tydzień
    - Dzień

- Ustawienia kanału

    - Osoba prawna
    - Typ kanału
    - Typ odbiorcy
    - Typ sprzedaży
    - Kanał
    - Hierarchia organizacyjna

- Ustawienia produktu

    - Hierarchia kategorii
    - Kategoria

#### <a name="products"></a><a name="ProductsPage"></a> Produkty

- Sprzedaż
- Margines
- Zwroty

#### <a name="customers"></a><a name="CustomersPage"></a> Klienci

- Sprzedaż
- Margines
- Zwroty

#### <a name="channels"></a><a name="ChannelsPage"></a> Kanały

- Sprzedaż
- Margines
- Zwroty

### <a name="sales"></a>Sprzedaż <a name="SalesPage"></a>

- Według lokalizacji dostawy
- Według kanału / sklepu / terminalu
- Według pracownika etatowego
- Według daty
- Według godziny
- Według kategorii produktów

### <a name="margins"></a><a name="MarginsPage"></a> Marże

- Według lokalizacji dostawy
- Produkt uboczny
- Według daty

### <a name="returns"></a><a name="ReturnsPage"></a> Zwroty

- Zwroty według kwoty

    - Według sklepów
    - Produkt uboczny
    - Według daty

- Zwroty według transakcji

    - Według sklepów
    - Produkt uboczny
    - Według daty

### <a name="discounts"></a><a name="DiscountsPage"></a> Rabaty

- Według sklepów
- Produkt uboczny
- Według daty
- Dekompozycja

    - Osoba prawna
    - Sklep
    - Typ rabatu
    - Nazwa rabatu
    - Produkt

### <a name="payments"></a><a name="PaymentsPage"></a> Płatności

- Według kanału/terminalu
- Według formy/typu płatności
- Według daty
- Dekompozycja

    - Osoba prawna
    - Typ kanału
    - Sklep
    - Terminal
    - Metoda płatności

### <a name="customers"></a><a name="CustomersPage"></a> Klienci

- Wartość okresu istnienia (LTV)

    Wartość LTV jest obliczana na podstawie łącznej kwoty wydatków klienta we wszystkich kanałach sprzedaży rozwiązania Dynamics 365 Commerce (w tym w punkcie sprzedaży, handlu elektronicznym i biurze obsługi).

- Recency

    Data ostatniego zakupu jest obliczana na podstawie liczby dni od ostatniego zobowiązania transakcyjnego klienta z organizacją. Obecnie data ostatniego zakupu nie uwzględnia żadnych sygnałów zobowiązania nietransakcyjnego, takich jak działanie przeglądania handlu elektronicznego.

- Częstotliwość

    Częstotliwość jest obliczana na podstawie zobowiązania transakcyjnego klienta z organizacją. Częstotliwość nie uwzględnia żadnych sygnałów zobowiązania nietransakcyjnego, takich jak działanie przeglądania handlu elektronicznego.

- Czas trwania relacji

    Czas trwania relacji jest obliczany na podstawie liczby dni od utworzenia rekordu klienta w systemie.

- Liczba transakcji

### <a name="comparison"></a><a name="ComparisonPage"></a> Porównanie

- Porównanie produktów według okresów

    - Sprzedaż i różnica sprzedaży
    - Marża i różnica marży

- Klient według okresu

    - Sprzedaż i różnica sprzedaży
    - Marża i różnica marży

### <a name="web-activity"></a><a name="WebActivityPage"></a> Działanie w sieci

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filtry najwyższego poziomu

- Zakres dat
- Typ kanału
- Kanał
- Hierarchia kategorii

#### <a name="acquisitions"></a>Nabycia

- Widoki strony

    - Według kraju lub regionu
    - Produkt uboczny
    - Według stanu zalogowania użytkownika
    - Według daty

- Zamówienia handlu elektronicznego
- Współczynnik konwersji

    - Według daty

- Lejek konwersji

    - Widok strony według typu strony (strona główna, strona kategorii lub strona szczegółów produktu)
    - Dodaj do koszyka
    - Finalizacja zakupu
    - Zakup

#### <a name="sessions"></a>Sesje

Sesja jest wystąpieniem wizyty użytkownika w witrynie internetowej handlu elektronicznego. Sesja jest uważana za zakończoną po 30 minutach nieaktywności lub 24 godzin aktywnego użycia.

- Według kraju lub regionu
- Według źródła (zewnętrzne źródło odwołania)
- Według stanu zalogowania użytkownika
- Liczba sesji

    - Według daty
    - Według stron wpisu

- Zamówienie na sesję

    - Według daty

- Częstotliwość szybkości zwracania sesji

    Zwracanie sesji jest sesją, w której użytkownik opuszcza witrynę handlu elektronicznego zaraz po jej odwiedzeniu. Aby uzyskać więcej informacji, zobacz temat [Szybkość zwracania](https://en.wikipedia.org/wiki/Bounce_rate).

- Kliknięć na sesję

#### <a name="visitors"></a>Odwiedzających

Anonimowy użytkownik w witrynie handlu elektronicznego jest jednoznacznie identyfikowany na podstawie określonej przeglądarki i określonego urządzenia, z których korzysta. Analizy rozwiązania Commerce nie śledzą anonimowych skojarzeń między różnymi przeglądarkami lub urządzeniami. Anonimowy użytkownik, który używa tej samej przeglądarki na tym samym urządzeniu, jest jednoznacznie identyfikowany przez wiele sesji użytkowników, do czasu wyczyszczenia pamięci podręcznej przeglądarki lub minięcia okresu (zazwyczaj 12 miesięcy), w zależności od tego, który z nich nastąpi jako pierwszy.

Jeśli użytkownik przegląda witrynę handlu elektronicznego po zalogowaniu, analizy rozwiązania Commerce mogą dostarczać dodatkowych informacji na jego temat. Te informacje są oparte na istniejącej relacji między organizacji z odwiedzającymi w wyniku ich poprzednich zakupów we wszystkich kanałach sprzedaży rozwiązania Dynamics 365 Commerce (w tym w punkcie sprzedaży, handlu elektronicznym i biurze obsługi). Dodatkowe informacje obejmują datę ostatniego zakupu, długość relacji, wartość okresu istnienia i dane częstotliwości.

- Margines odwiedzających
- Średnia liczba zamówień odwiedzających
- Średnia liczba sprzedaży dla odwiedzających
- Liczba odwiedzających handlu elektronicznego

    - Według daty
    - Według lokalizacji

        Obecnie analizy rozwiązania Commerce mogą dostarczać wyłącznie szczegółowych informacji o lokalizacjach odwiedzających handlu elektronicznego na poziomie kraju/regionu.

    - Według daty ostatniego zakupu

        Data ostatniego zakupu jest obliczana na podstawie liczby dni od ostatniego zobowiązania transakcyjnego klienta z organizacją. Obecnie data ostatniego zakupu nie uwzględnia żadnych sygnałów zobowiązania nietransakcyjnego, takich jak działanie przeglądania handlu elektronicznego.

    - Według czasu trwania relacji

        Czas trwania relacji jest obliczany na podstawie liczby dni od utworzenia rekordu klienta w systemie.

    - Według wartości czasu istnienia (LTV)

        Wartość LTV jest obliczana na podstawie łącznej kwoty wydatków klienta we wszystkich kanałach sprzedaży rozwiązania Dynamics 365 Commerce (w tym w punkcie sprzedaży, handlu elektronicznym i biurze obsługi).

    - Według częstotliwości

        Częstotliwość jest obliczana na podstawie zobowiązania transakcyjnego klienta z organizacją. Częstotliwość nie uwzględnia żadnych sygnałów zobowiązania nietransakcyjnego, takich jak działanie przeglądania handlu elektronicznego.

#### <a name="impressions"></a>Wyświetlenia

Wyświetlenie to pojedyncze wyświetlenie obrazu produktu przez użytkownika korzystającego z handlu elektronicznego. Na przykład odwiedzający handlu elektronicznego przechodzi do strony głównej witryny internetowej handlu elektronicznego i wyświetla produkt maty do jogi w module listy **Najpopularniejsze produkty**. Następnie odwiedzający widzi ten sam produkt maty do jogi w module listy **Wybrane dla Ciebie**. W tym przypadku występują dwa wyświetlenia produktu.

Obecnie wyświetlenia są śledzone na następujących powierzchniach:

- Listy (na przykład **Zalecane**, **Najpopularniejsze produkty**, **Wybrane dla Ciebie** i **Popularne**)
- Moduł koszyka
- Kontener wyników wyszukiwania
- Kontener kategorii wyników wyszukiwania

Obecnie produkty renderowane w module karuzeli lub w wizualizacja niestandardowych nie są liczone w metrykach związanych z wyświetleniami.

Strona **Raport wyświetleń** zawiera następujące metryki:

- Liczba wyświetleń

    - Według typu strony i modułu

        Typ strony jest typem ogólnym strony zdefiniowanej dla poszczególnych stron w witrynie internetowej handlu elektronicznego. Typ modułu to typ modułu wizualnego handlu elektronicznego, w którym jest wyświetlany produkt.

        Aby wyświetlić wyświetlanie według modułu, konieczne może być przejście do strony i wizualizacji modułu.

    - Produkt uboczny
    - Według stanu zalogowania użytkownika
    - Według daty

- Liczba kliknięć wyświetleń

    Kliknięcie z wyświetleniem ma miejsce, gdy użytkownik handlu elektronicznego wybierze wizualizację produktu. Zwykle odwiedzający jest zabierany na stronę szczegółów produktu tego produktu.

- Wskaźnik klikania wyświetleń (CTR)

    Całkowity wskaźnik CTR jest obliczany jako łączna liczba kliknięć wyświetleń podzielona przez łączną liczbę wyświetleń.

## <a name="commerce-analytics-preview-installation"></a>Analizy rozwiązania Commerce (wersja zapoznawcza) — instalacja

> [!NOTE]
> Analizy rozwiązania Commerce (wersja zapoznawcza) są w wersji zapoznawczej w Stanach Zjednoczonych, Kanadzie, Zjednoczonym Królestwie, Europie, Azji Południowo-Wschodniej, Azji Wschodniej, Australii i Japonii. Jeśli środowisko finansowe i operacyjne znajduje się w którymkolwiek z tych regionów, możesz włączyć tę funkcję w swoim środowisku, używając usługi Microsoft Dynamics Lifecycle Services (LCS). Aby można było używać tej funkcji, zobacz temat [Konfiguruj eksport do danych Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Włącz i konfiguruj analizę rozwiązania Commerce (wersja zapoznawcza)

Aby zainstalować analizę rozwiązania Commerce (wersja zapoznawcza), musisz mieć uprawnienia do tworzenia zasobów w subskrypcji systemu Azure. Musisz mieć również uprawnienia do instalowania dodatków w usłudze LCS.

Aby włączyć i skonfigurować analitykę handlową (wersja zapoznawcza), wykonaj następujące kroki.

1. [Prześlij formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)](#joinPreview)
2. [Dodatek Włączanie i konfigurowanie eksportu do Data Lake](#enableExportToDataLake).
3. [Instalowanie i konfigurowanie obszaru roboczego Azure Synapse Workspace](#configureAzureSynapse).
4. [Dodaj do klucza klucz](#addSecrets).
5. [Włącz i konfiguruj dodatek analizy rozwiązania Commerce (wersja zapoznawcza)](#enableCommerceAnalyticsAddin).
6. [Instalowanie aplikacji szablonu Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Prześlij formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)

Prześlij [Formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)](https://forms.office.com/r/vW5VLJGXZ2). Po przetworzeniu zgłoszenia na adres e-mail podany w formularzu zostanie wysłana wiadomość z potwierdzeniem.

### <a name="enable-and-configure-the-export-to-data-lake-add-in"></a><a name="enableExportToDataLake"></a>Dodatek Włączanie i konfigurowanie eksportu do Data Lake.

> [!IMPORTANT]
> Podczas konfigurowania dodatku Eksportuj do Data Lake wyczyść pole wyboru **Zmiany danych w czasie rzeczywistym** na stronie konfiguracji eksportu do Data Lake, aby zagwarantować, że zmiany danych w czasie rzeczywistym nie będą włączone. Funkcja **zmiany danych w czasie rzeczywistym jest** dostępna w wersji Preview, dlatego nie jest obecnie obsługiwana przez usługę Commerce Analytics. Jeśli włączysz tę funkcję, usługa Commerce Analytics nie będzie mogła przetwarzać Twoich danych w data lake, a większość raportów usługi Power BI nie będzie zawierać żadnych danych.

Analizy rozwiązania Commerce (wersja zapoznawcza) zależą od funkcji eksportu do Data Lake, która umożliwia eksportowanie danych centrali Commerce HW do Data Lake i zachowanie świeżości danych. Przed skonfigurowaniem analiz rozwiązania Commerce (wersja zapoznawcza) włącz i skonfiguruj eksport do Data Lake, wykonując kroki w temacie [Konfiguracja eksportu do Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Konfigurując eksport do Data Lake, zanotuj następujące informacje, ponieważ trzeba będzie je wprowadzić później:

- <a name="keyVault"></a>Nazwa systemu nazw domen (DNS) dostarczonego klucza.
- Podane tajnymi nazwami, które zawierają identyfikator aplikacji i tajny identyfikator aplikacji. Aby uzyskać więcej informacji o tej funkcji, zobacz [Dodawanie klucza tajnego do magazynu key vault](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Instalowanie i konfigurowanie obszaru roboczego Azure Synapse Workspace

Usługa Commerce Analytics (Wersja Preview) wymaga, aby w obszarze roboczym Azure Synapse workspace było wymagane inicjowanie obsługi składni SQL na żądanie. Aby zainstalować i skonfigurować obszar roboczy Azure Synapse Workspace, wykonaj następujące kroki.

1. Zainstaluj obszar roboczy Azure Synapse Workspace w subskrypcji systemu Azure. Aby uzyskać więcej informacji, zobacz temat [Szybki start: tworzenie obszaru roboczego Synapse](/azure/synapse-analytics/quickstart-create-workspace).
1. <a name="serverlessep"></a>Po otwarciu obszaru roboczego otwórz stronę przeglądu zasobów i zanotuj **wartość punktu końcowego SQL** bez serwera. Trzeba będzie zapisać tę wartość w kluczu w następnej sekcji.
1. Na stronie przeglądu zaznacz łącze **Otwórz program Syntronic Studio**, aby otworzyć Azure Synapse studio dla obszaru roboczego.
1. Po lewej wybierz pozycję **Zarządzaj**. Aby wyświetlić nazwy menu, może być konieczne wybranie łącza rozwinięcia w menu po lewej stronie.
1. W **obszarze Grupa zabezpieczeń** wybierz pozycję **Kontrola dostępu**. 
1. Wybierz opcję **Dodaj**.
1. W okienku **Dodawanie przypisania roli** skonfiguruj opcje w sposób opisany w poniższej tabeli.

    | Opcja | Wartość |
    |--------|-------|
    | Zakres | Wybieranie **obszaru roboczego**. |
    | Rola | Wybierz pozycję **Synapsa SQL Administrator**.|
    | Wybierz użytkownika | Wyszukaj nazwę aplikacji utworzonej [podczas instalowania dodatku Eksportuj do Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createapplication). Po zaznaczeniu zgłoszenia w wynikach wyszukiwania należy je zaznaczyć. Aplikacja pojawi się teraz w sekcji **Wybrani użytkownicy, grupy lub podmioty główne** usług. |

1. Wybierz **przycisk Zastosuj**, aby zakończyć przypisanie roli. Aplikacja otrzymuje uprawnienia Synapse SQL Administrator. W związku z tym może tworzyć wymagane widoki podczas konfigurowania dodatku LCS usługi Commerce Analytics (Preview).

### <a name="add-secrets-to-the-key-vault"></a><a name="addSecrets"></a>Dodaj do klucza klucz

W tym samym [kluczu](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createkeyvault), który został użyty podczas konfigurowania dodatku Eksportuj do Data Lake, należy dodać kod, który będzie widoczny w poniższej tabeli. Dla każdego tajnych należy podać tajnyą nazwę i określoną wartość.

| Sugerowana tajna nazwa | Wartość wpisu tajnego | Przykładowa wartość tajna |
|---------|---------|---------|
| synapse-sql-server | Wartość punktu końcowego SQL nieskonfigurowana przez użytkownika podczas [konfigurowania obszaru roboczego Azure Synapse workspace](#serverlessep). | `test-ondemand.sql.azuresynapse.net` |
| <a name="roUser"></a>readonly-sql-pwd | Hasło do ustawienia dla użytkownika tylko do odczytu SQL. Raport Power BI użyje tego hasła do nawiązania połączenia z usługą SQL bez serwera. Aby ustawić hasło, postępuj zgodnie z zasadami password organizacji. | |

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Włącz i konfiguruj dodatek analizy rozwiązania Commerce (wersja zapoznawcza)

Aby zainstalować dodatek analiz rozwiązania Commerce (wersja zapoznawcza) w usłudze LCS, musisz być administratorem środowiska w usłudze LCS dla środowiska, którego chcesz użyć.

Aby zainstalować i skonfigurować dodatek analiz rozwiązania Commerce (wersja zapoznawcza), wykonaj następujące kroki.

1. Zaloguj się do [LCS](https://lcs.dynamics.com/) i przejdź do środowiska.
2. Na stronie **Środowisko**, na karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. W oknie dialogowym wybierz pozycję **Analizy rozwiązania Commerce (wersja zapoznawcza)**.
4. W oknie dialogowym **Konfiguruj dodatek** wprowadź następujące informacje.

    | Informacje | Źródło | Przykładową wartość |
    |---|---|---|
    | Identyfikator AAD dzierżawy Azure Active Directory (Azure AD) | Zaloguj się do [portalu Azure](https://portal.azure.com/) i otwórz usługę **Azure Active Directory**. Następnie otwórz stronę **Właściwości** i skopiuj wartość w polu **Identyfikator dzierżawy**. | `72f988bf-0000-0000-00000-2d7cd011db47` |
    | Podaj nazwę DNS usługi Azure Key Vault | Wprowadź nazwę DNS usługi Key Vault. Powinieneś zanotować tę wartość podczas [konfigurowania dodatku Export to Data Lake](#keyVault). | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Nazwa wpisu tajnego, który zawiera identyfikator aplikacji | Wprowadź nazwę wpisu tajnego, która przechowuje identyfikator aplikacji. Powinieneś zanotować tę wartość podczas [konfigurowania dodatku Export to Data Lake](#keyVault). | `app-id` |
    | Nazwa wpisu tajnego, który zawiera wpis tajny aplikacji | Wprowadź nazwę wpisu tajnego, która przechowuje wpis tajny aplikacji. Powinieneś zanotować tę wartość podczas [konfigurowania dodatku Export to Data Lake](#keyVault). | `app-secret` |
    | Tajny nazwa zawierająca nieużytowy punkt końcowy SQL dla systemu Azure Synapse | Wprowadź tajną nazwę, która przechowuje bezserwerowy punkt końcowy SQL. Należy utworzyć tajny klucz podczas dodawana [do wartości klucza](#addSecrets). | `synapse-sql-server` |
    | Tajny nazwa zawierająca hasło, które ma być ustawione dla użytkowników tylko do odczytu SQL w programie Azure Synapse | Wprowadź tajny kod, w którym będzie przechowywane hasło ustawione dla nieużytego użytkownika tylko do odczytu SQL. Ten użytkownik zostanie utworzony dla Ciebie i powinien być używany w raporcie Power BI w celu nawiązania połączenia z serwerem SQL bez serwera. Należy utworzyć tajny klucz podczas dodawana [do wartości klucza](#addSecrets). | `readonly-sql-pwd` |

1. Zaakceptuj warunki oferty, zaznaczając pole wyboru, a następnie opcję **Zainstaluj**.

    System zainstaluje i skonfiguruje dodatek Analizy rozwiązania Commerce (wersja zapoznawcza) dla środowiska. Proces może potrwać kilka minut. Po zakończeniu pracy na stronie **Analizy rozwiązania Commerce (wersja zapoznawcza)** powinna pojawić się na liście strona **Środowisko**, a stan powinien być **Zainstalowano**.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Instalowanie aplikacji szablonu Power BI

Aby zainstalować aplikację szablonu Power BI dla dodatku analiz rozwiązania Commerce (wersja zapoznawcza), wykonaj następujące kroki.

1. Zaloguj się do [portalu Power BI](https://powerbi.microsoft.com/), używając identyfikatora organizacji.
1. Zainstaluj aplikację szablonów Power BI analiz rozwiązania Commerce (wersja zapoznawcza), przechodząc do [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Możesz również odwiedź stronę [AppSource dla analizy Dynamics 365 Commerce](https://appsource.microsoft.com/product/power-bi/dynamics-365-commerce.dydnamics-365-commerce-analytics) i wybierz pozycję **Pobierz teraz**.
1. Jeśli aplikacja jest instalowana po raz pierwszy, przejdź do kroku 5. Jeśli zainstalowałeś ją wcześniej, obowiązują następujące opcje aktualizacji aplikacji:

    - **Aktualizuj obszar roboczy i aplikację** — Zaktualizuj istniejącą aplikację szablonu i zastąp istniejące ustawienia aplikacji, takie jak nazwa wystąpienia aplikacji i konfiguracje uprawnień.
    - **Aktualizuj tylko zawartość obszaru roboczego bez aktualizowania aplikacji** — zaktualizuj istniejącą aplikację szablonu, ale zachowaj istniejące ustawienia aplikacji. *Jest to zalecana opcja aktualizacji aplikacji.*
    - **Zainstaluj inną kopię aplikacji do nowego obszaru roboczego** — utwórz nowy obszar roboczy, a następnie utwórz w nim kopię istniejącej aplikacji szablonu. Istniejący obszar roboczy pozostanie niezmieniony.

1. Wybierz jedną z opcji aktualizacji, a następnie **Zainstaluj**.
1. Otwórz zainstalowaną aplikację, wybierając **Aplikacje** w lewym okienku, a następnie wybierając aplikację.
1. Połącz aplikację ze źródłem danych, wybierając pozycję **Połącz**. Jeśli aplikacja jest już zainstalowana, zaznacz łącze **Połącz dane** na żółtym pasku komunikatów.
1. Ustaw wartości w następujących polach.

    | Pole | Wartość |
    |---|---|
    | Serwer | Wprowadź nieużytkowy punkt końcowy SQL, o którym zanotował użytkownik po utworzeniu [obszaru roboczego Azure Synapse workspace](#serverlessep). |
    | Baza danych | Wprowadź **CommerceAnalytics**. |
    | Język | Zaznacz wartość na liście. To pole jest używane w przypadku zlokalizowanych nazw produktów i kategorii. W wartości jest rozróżniana wielkość liter. |
    | Zakres dat | Zaznacz wartość na liście. Do zestawu danych Power BI zostaną zaimportowane dane z wybranej liczby miesięcy. Wybór wartości wpływa na rozmiar zestawu danych i czas wymagany na synchronizację. |

1. Wybierz pozycję **Następny**. Po wyświetleniu monitu o wprowadzenie poświadczeń na temat połączenia z Azure Synapse bazą danych SQL należy ustawić wartości pól zgodnie z następującą tabelą.

    | Pole | Wartość |
    |---|---|
    | Metoda uwierzytelniania | Wybierz **Podstawowe**. |
    | Nazwa użytkownika | Wprowadź **reportreadonlyuser**. |
    | Hasło | Wprowadź hasło zapisane dla [użytkownika tylko do odczytu SQL w kluczu](#roUser). |

1. Wybierz opcję **Zaloguj i połącz**.
1. Czekaj, aż zestaw danych zostanie pomyślnie zaktualizowany. Następnie wybierz **Edytuj aplikację**, aby otworzyć obszar roboczy aplikacji, w którym możesz przejrzeć stan aktualizacji zestawu danych. W obszarze roboczym Aplikacja można także opcjonalnie skonfigurować harmonogramy automatycznej aktualizacji dla zestawu danych, zarządzać uprawnieniami i zmieniać nazwę wystąpienia aplikacji.

### <a name="privacy"></a><a name="privacy"></a>Prywatność

Prywatność użytkowników jest dla nas bardzo ważna. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
