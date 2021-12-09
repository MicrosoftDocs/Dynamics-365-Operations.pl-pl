---
title: Analizy rozwiązania Commerce (wersja zapoznawcza)
description: W tym temacie opisano sposób instalowania i używania możliwości analitycznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862780"
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
- Widoki SQL w analizie Azure Synapse
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

Analizy usługi Azure Synapse służą do zapytań w danych data lake za pośrednictwem interfejsu Transact-SQL (T-SQL). Ten interfejs zawiera widoki SQL. Widoki SQL umożliwiają federacyjne wykonywanie zapytań o dane w data lake za pośrednictwem klienta T-SQL (w celu analizy ad hoc) lub za pomocą narzędzia wizualizacji, takiego jak Power BI.

#### <a name="step-5-modeling-and-serving"></a>Krok 5: Modelowanie i służenie

Dane, o które zapytano przez analizę Azure Synapse są umieszczane w modelu semantycznym Power BI. W zależności od typu danych są to dane okresowo importowane w pamięci do usługi Power BI lub z bezpośrednich zapytać w trakcie uruchomienia.

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

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtry najwyższego poziomu

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

####  <a name="products"></a><a name="ProductsPage"></a> Produkty

- Sprzedaż
- Margines
- Zwroty

####  <a name="customers"></a><a name="CustomersPage"></a> Klienci

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
> Analizy rozwiązania Commerce (wersja zapoznawcza) są w wersji zapoznawczej w Stanach Zjednoczonych, Kanadzie, Zjednoczonym Królestwie, Europie, Azji Południowo-Wschodniej, Azji Wschodniej, Australii i Japonii. Jeśli środowisko Finance and Operations znajduje się w którymkolwiek z tych regionów, możesz włączyć tę funkcję w swoim środowisku, używając usługi Microsoft Dynamics Lifecycle Services (LCS). Aby można było używać tej funkcji, zobacz temat [Konfiguruj eksport do danych Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Włącz i konfiguruj analizę rozwiązania Commerce (wersja zapoznawcza)

Aby zainstalować analizę rozwiązania Commerce (wersja zapoznawcza), musisz mieć uprawnienia do tworzenia zasobów w subskrypcji systemu Azure. Musisz mieć również uprawnienia do instalowania dodatków w usłudze LCS. Poniżej znajduje się omówienie kroków:

1. [Prześlij formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)](#joinPreview).
2. [Włączanie i konfigurowanie eksportu do Data Lake](#enableExportToDataLake).
3. [Włącz i konfiguruj dodatek analizy rozwiązania Commerce (wersja zapoznawcza)](#enableCommerceAnalyticsAddin).
4. [Generuj token sygnatury dostępu współdzielonego (SAS) dla swojego konta magazynu](#getSASToken).
5. [Pobierz skrypty wdrażania dla widoków Azure Synapse](#downloadSynapseDeploymentScripts).
6. [Instalowanie i konfigurowanie obszaru roboczego Azure Synapse Workspace](#configureAzureSynapse).
7. [Instalowanie aplikacji szablonu Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Prześlij formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)

Prześlij [Formularz wdrożenia wersji zapoznawczej dla analiz rozwiązania Commerce (wersja zapoznawcza)](https://forms.office.com/r/vW5VLJGXZ2). Przetwarzanie formularza może zająć maksymalnie trzy dni robocze. Po przetworzeniu zostanie wysłana wiadomość e-mail z potwierdzeniem na adres e-mail podany w formularzu.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>Włączanie i konfigurowanie eksportu do Data Lake

Analizy rozwiązania Commerce (wersja zapoznawcza) zależą od funkcji eksportu do Data Lake, która umożliwia eksportowanie danych centrali Commerce HW do Data Lake i zachowanie świeżości danych. Przed skonfigurowaniem analiz rozwiązania Commerce (wersja zapoznawcza) włącz i skonfiguruj eksport do Data Lake, wykonując kroki w temacie [Konfiguracja eksportu do Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Konfigurując eksport do Data Lake, zanotuj następujące informacje, ponieważ trzeba będzie je wprowadzić później:

- <a name="keyVault"></a>Nazwa systemu nazw domen (DNS) magazynu key vault i nazw tajnych, w których są przechowywane identyfikator aplikacji i nazwa tajna klucza aplikacji. Aby uzyskać więcej informacji o tej funkcji, zobacz [Dodawanie klucza tajnego do magazynu key vault](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>Nazwa konta magazynu dla wystąpienia Data Lake. Aby uzyskać więcej informacji, zobacz temat [Tworzenie konta Data Lake Storage (Gen2) w subskrypcji](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Włącz i konfiguruj dodatek analizy rozwiązania Commerce (wersja zapoznawcza)

Aby zainstalować dodatek analiz rozwiązania Commerce (wersja zapoznawcza) w usłudze LCS, musisz być administratorem środowiska w usłudze LCS dla środowiska, którego chcesz użyć.

Aby zainstalować i skonfigurować dodatek analiz rozwiązania Commerce (wersja zapoznawcza), wykonaj następujące kroki.

1. Zaloguj się do [LCS](https://lcs.dynamics.com/) i przejdź do środowiska.
2. Na stronie **Środowisko**, na karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. W oknie dialogowym wybierz pozycję **Analizy rozwiązania Commerce (wersja zapoznawcza)**.

    Jeśli usługa **Analizy rozwiązania Commerce (wersja zapoznawcza)** nie jest wymieniona, upewnij się, że jesteś użytkownikiem programu Insider.

4. W oknie dialogowym **Konfiguruj dodatek** wprowadź następujące informacje.

    | Informacje | Źródło | Przykładową wartość |
    |---|---|---|
    | Identyfikator dzierżawcy usługi Azure AD dla środowiska | Zaloguj się do [portalu Azure](https://portal.azure.com/) i otwórz usługę **Azure Active Directory**. Następnie otwórz stronę **Właściwości** i skopiuj wartość w polu **Identyfikator katalogu**. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | Podaj nazwę DNS usługi Key Vault | Wprowadź [nazwę DNS](#keyVault) usługi Key Vault. Tę wartość należało zanotować w poprzedniej sekcji. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Wpis tajny, który zawiera identyfikator aplikacji | Wprowadź [nazwę wpisu tajnego, która przechowuje identyfikator aplikacji](#keyVault). Tę wartość należało zanotować w poprzedniej sekcji. | app-id |
    | Wpis tajny, który zawiera wpis tajny aplikacji | Wprowadź [nazwę wpisu tajnego, która przechowuje wpis tajny aplikacji](#keyVault). Tę wartość należało zanotować w poprzedniej sekcji. | app-secret |

5. Zaakceptuj warunki oferty, zaznaczając pole wyboru, a następnie opcję **Zainstaluj**.

    System zainstaluje i skonfiguruje dodatek Analizy rozwiązania Commerce (wersja zapoznawcza) dla środowiska. Proces może potrwać kilka minut. Po zakończeniu pracy na stronie **Analizy rozwiązania Commerce (wersja zapoznawcza)** powinna pojawić się na liście strona **Środowisko**, a stan powinien być **Zainstalowano**.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>Wygeneruj token SAS dla swojego konta magazynu

Token SAS umożliwia podmiotom zewnętrznym dostęp do konta magazynu i ma określony zestaw uprawnień przez ograniczony czas. Azure Synapse użyje tokenu SAS w celu uzyskania dostępu do podstawowych danych źródłowych w Data Lake.

> [!NOTE]
> Z powodu znanego ograniczenia analizy rozwiązania Commerce (wersja zapoznawcza) wystąpienie Azure Synapse utraci dostęp do data lake po wygaśnięciu tokenu SAS. Dlatego podczas generowania tokenu SAS należy ustawić maksymalną datę ważności dozwoloną przez zasady zabezpieczeń organizacji.

Aby wygenerować token SAS, wykonaj następujące kroki.

1. W portalu Azure przejdź do [konta magazynu](#storageAccount) utworzonego podczas konfigurowania eksportu do Data Lake.
2. W lewym okienku, w obszarze konta magazynu wybierz opcję **Sygnatura dostępu współdzielonego**.
3. Na stronie **Opcje SAS** ustaw następujące pola.

    | Pole | Wartość |
    |---|---|
    | Dozwolone usługi | Wybierz obiekt **blob**. |
    | Dozwolone typy zasobów | Wybierz opcję **Usługa**, **Kontener** i **Obiekt**. |
    | Dozwolone uprawnienia | Wybierz opcję **Odczyt**, **Zapis**, **Usuń**, **Lista**, **Dodaj** i **Utwórz**. |
    | Uprawnienia przechowywania wersji obiektów Blob | Wybierz opcję **Umożliwia usuwanie wersji**. |
    | Data i godzina rozpoczęcia i wygaśnięcia | Ustaw odpowiednio datę i czas rozpoczęcia i zakończenia dla tokenu SAS. |
    | Dozwolone adresy IP | To pole należy pozostawić puste. |
    | Dozwolone protokoły | Wybierz **Tylko HTTPS**. |
    | Preferowana warstwa wyznaczania trasy | Wybierz opcję **Podstawowe (domyślne)**. |
    | Klucz podpisywania | W razie potrzeby wybierz **key1** lub **key2**. |

4. Wybierz pozycję **Generuj SAS i parametry połączenia**.
5. Skopiuj wartość w polu **Token SAS** i wklej ją do edytora tekstu, takiego jak Notatnik.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>Pobierz skrypty wdrażania dla widoków Azure Synapse

Aby utworzyć i opublikować wymagane widoki w obszarze roboczym Azure Synapse Workspace, należy uruchomić zestaw skryptów. Aby pobrać skrypty, wykonaj następujące kroki.

1. Na stronie GitHub przejdź do repozytorium (repo) [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) (repo).
2. Pobierz skrypty na komputer lokalny, kopiując repo lub pobierając je jako plik ZIP.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Instalowanie i konfigurowanie obszaru roboczego Azure Synapse Workspace

Aby zainstalować i skonfigurować obszar roboczy Azure Synapse Workspace, wykonaj następujące kroki.

1. Zainstaluj obszar roboczy Azure Synapse Workspace w subskrypcji systemu Azure. Aby uzyskać więcej informacji, zobacz temat [Szybki start: tworzenie obszaru roboczego Synapse](/azure/synapse-analytics/quickstart-create-workspace).
2. W Notatniku lub innym edytorze tekstu otwórz plik skryptu **SetupSynapse.sql** z folderu na lokalnym komputerze, na który skopiowano lub pobrano repo Dynamics365Commerce.Solutions w poprzedniej sekcji. Plik skryptu będzie w folderze /Pipeline/CommerceAnalyticsSynapse/. W skrypcie zastąp tekst symbolu zastępczego wartościami, tak jak to przedstawiono w poniższej tabeli.

    | Tekst zastępczy | Wartość zastępcza |
    |---|---|
    | placeholder_storageaccount | Nazwa [konta magazynu](#storageAccount) utworzonego podczas konfigurowania eksportu do Data Lake. |
    | <a name="phContainer"></a>placeholder_container | Nazwa kontenera magazynu, który został utworzony w Data Lake danych po pomyślnym zainstalowaniu dodatku Eksportuj do Data Lake w usłudze LCS. Aby uzyskać nazwę kontenera, musisz użyć Eksploratora usługi Storage w portalu Azure, aby przeglądać konto magazynu. |
    | placeholder_sastoken | Wygenerowany [token SAS](#getSASToken). Pamiętaj, aby usunąć znak zapytania (**?**) z początku wartości tokenu SAS. |
    | <a name="phUserPwd"></a>placeholder_password | Wybierz silne hasło. Zanotuj to hasło. Zostanie ono ustawione jako hasło nowego konta **reportreadonlyuser**, które utworzy skrypt. **Nie** należy wprowadzać hasła konta **sqladminuser**. |

3. Skopiuj zaktualizowaną zawartość pliku skryptu.
4. W portalu Azure, przejdź do nowego obszaru roboczego Azure Synapse Workspace. Na stronie **Przegląd** wybierz pozycję **Otwórz Synapse Studio**.
5. W programie Synapse Studio wybierz **Nowy \> Skrypt SQL** i wklej zawartość pliku skryptu do edytora skryptów SQL.
6. Upewnij się, że pole **Użyj bazy danych** ma ustawioną wartość **główne**.
7. Wybierz opcję **Uruchom** i poczekaj na zakończenie wykonywania skryptu. Pomyślne wykonanie skryptu spowoduje utworzenie bazy danych do analizy rozwiązania Commerce, poświadczeń dostępu do data lake oraz konta użytkownika tylko do odczytu, którego usługa Power BI będzie używać do nawiązywania połączenia z wystąpieniem Azure Synapse.
8. Na komputerze lokalnym otwórz program Windows PowerShell w trybie administratora i przejdź do folderu /Pipeline/CommerceAnalyticsSynapse/ w folderze, do którego zostało sklonowane lub pobrane repo Dynamics365Commerce.Solutions repo.
9. Skonfiguruj zasady wykonywania w programie Windows PowerShell, uruchamiając następujące polecenie.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Jeśli moduł PowerShell SQL Server nie jest jeszcze zainstalowany, zainstaluj go, uruchamiając następujące polecenie.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > Podczas instalowania modułu może zostać wyświetlony monit o zainstalowanie dostawcy NuGet. W tym przypadku wybierz **T**, aby zainstalować dostawcę NuGet. Może być także wyświetlony monit z prośbą o potwierdzenie zainstalowania modułów z niezaufanego repozytorium. W takim przypadku należy wybrać **T**, aby kontynuować instalację. Opcjonalnie można uruchomić polecenie cmdlet **Set-PSRepository**, aby zaufać repozytorium **PSGallery**.

11. Opublikuj widoki Azure Synapse, uruchamiając następujące polecenie.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    Po uruchomieniu tego polecenia zastąp symbol zastępczy, tak jak to przedstawiono w poniższej tabeli.

    | Wartość symbolu zastępczego | Wartość zastępcza |
    |---|---|
    | SERVER_NAME | Nazwa punktu końcowego bezserwerowego SQL Azure Synapse. Tę wartość można pobrać ze strony **Przegląd** dla obszaru roboczego Azure Synapse Workspace w portalu Azure Portal. |
    | HASŁO | Hasło do konta **sqladminuser**. |
    | STORAGE_ACCOUNT | Nazwa konta magazynu dla Data Lake. |
    | CONTAINER_NAME | Nazwa kontenera utworzonego przez funkcję Eksportuj do Data Lake. Ten kontener jest tym samym kontenerem, który określono w wartości [placeholder_container](#phContainer) w kroku 2. |
    | DATA_ROOT_PATH | Nazwa folderu pod kontenerem, który zawiera wszystkie dane. |

    > [!NOTE]
    > Nazwę konta magazynu, nazwę kontenera i ścieżkę katalogu głównego danych można znaleźć przy użyciu przeglądarki magazynu Azure Storage i konta magazynu Data Lake w portalu Azure Portal.

12. Poczekaj na zakończenie wykonywania skryptu. Pomyślne wykonanie skryptu spowoduje utworzenie widoków SQL w bezserwerowym wystąpieniu SQL Azure Synapse.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Instalowanie aplikacji szablonu Power BI

Aby zainstalować aplikację szablonu Power BI dla dodatku analiz rozwiązania Commerce (wersja zapoznawcza), wykonaj następujące kroki.

1. Zaloguj się do [portalu Power BI](https://powerbi.microsoft.com/), używając identyfikatora organizacji.
2. Zainstaluj aplikację szablonów Power BI analiz rozwiązania Commerce (wersja zapoznawcza), przechodząc do [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Może zostać wyświetlone ostrzeżenie z komunikatem, że aplikacja nie jest wymieniona na liście AppSource. Wybierz **Zainstaluj**.
3. Jeśli aplikacja jest instalowana po raz pierwszy, przejdź do kroku 5. Jeśli ta aplikacja jest już zainstalowana, wyświetlane są następujące opcje jej aktualizacji:

    - **Aktualizuj obszar roboczy i aplikację** — Zaktualizuj istniejącą aplikację szablonu i zastąp istniejące ustawienia aplikacji, takie jak nazwa wystąpienia aplikacji i konfiguracje uprawnień.
    - **Aktualizuj tylko zawartość obszaru roboczego bez aktualizowania aplikacji** — zaktualizuj istniejącą aplikację szablonu, ale zachowaj istniejące ustawienia aplikacji. *Jest to zalecana opcja aktualizacji aplikacji.*
    - **Zainstaluj inną kopię aplikacji do nowego obszaru roboczego** — utwórz nowy obszar roboczy, a następnie utwórz w nim kopię istniejącej aplikacji szablonu. Istniejący obszar roboczy pozostanie niezmieniony.

4. Wybierz jedną z opcji aktualizacji, a następnie **Zainstaluj**.
5. Otwórz zainstalowaną aplikację, wybierając **Aplikacje** w lewym okienku, a następnie wybierając aplikację.
6. Połącz aplikację ze źródłem danych, wybierając pozycję **Połącz**. Jeśli aplikacja jest już zainstalowana, zaznacz łącze **Połącz dane** na żółtym pasku komunikatów.
7. Ustaw wartości w następujących polach.

    | Pole | Wartość |
    |---|---|
    | Serwer | Wprowadź nazwę punktu końcowego bezserwerowej bazy danych SQL Azure Synapse utworzonego w poprzedniej sekcji. Tę wartość można pobrać ze strony **Przegląd** dla obszaru roboczego Azure Synapse Workspace w portalu Azure Portal. |
    | Baza danych | Wprowadź **CommerceAnalytics**. |
    | Język | Zaznacz wartość na liście. To pole jest używane w przypadku zlokalizowanych nazw produktów i kategorii. W wartości jest rozróżniana wielkość liter. |
    | Zakres dat | Zaznacz wartość na liście. Do zestawu danych Power BI zostaną zaimportowane dane z wybranej liczby miesięcy. Wybór wartości wpływa na rozmiar zestawu danych i czas wymagany na synchronizację. |

8. Wybierz pozycję **Następny**. Zostanie wyświetlony monit o wprowadzenie poświadczeń do połączenia z bazą danych SQL Azure Synapse. Ustaw pola, jak pokazano w następującej tabeli.

    | Pole | Wartość |
    |---|---|
    | Metoda uwierzytelniania | Wybierz **Podstawowe**. |
    | Nazwa użytkownika | Wprowadź **reportreadonlyuser**. |
    | Hasło | Wprowadź wartość, której użyto do zastąpienia symbolu zastępczego [placeholder_password](#phUserPwd) w skrypcie SetupSynapse.sql. To hasło jest hasłem dla konta **reportreadonlyuser**. |

9. Wybierz opcję **Zaloguj i połącz**.
10. Czekaj, aż zestaw danych zostanie pomyślnie zaktualizowany. Następnie wybierz przycisk **Edytuj aplikację**, aby otworzyć obszar roboczy aplikacji, w którym możesz przejrzeć stan aktualizacji zestawu danych. W obszarze roboczym Aplikacja można także opcjonalnie skonfigurować harmonogramy automatycznej aktualizacji dla zestawu danych, zarządzać uprawnieniami i zmieniać nazwę wystąpienia aplikacji.

### <a name="privacy"></a><a name="privacy"></a>Prywatność

Prywatność użytkowników jest dla nas bardzo ważna. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
