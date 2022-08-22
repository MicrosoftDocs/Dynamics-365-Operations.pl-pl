---
title: Przykładowa integracja jednostki kontrolnej dla Szwecji
description: W tym artykule zawarto ogólne informacje o przykładowej integracji fiskalnej dla Szwecji w Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 3376e6a901b692371a44b5c74c1e6b4afd0cd573
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275074"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Przykładowa integracja jednostki kontrolnej dla Szwecji

[!include [banner](../includes/banner.md)]

W tym artykule zawarto ogólne informacje o przykładowej integracji fiskalnej dla Szwecji w Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Ta przykładowa funkcja integracji fiskalnej zastępuje wcześniejszą [próbkę integracji z programem POS z jednostkami kontrolnymi dla Szwecji](retail-sdk-control-unit-sample.md). Wcześniejszy przykład nie wykorzystuje [struktury integracji fiskalnej](./fiscal-integration-for-retail-channel.md) i utraci aktualność w późniejszych aktualizacjach. Aby uzyskać informacje dotyczące migrowania ze starszego przykładu do przykładu odpowiadającego wersji Dynamics 365 Commerce **10.0.22 i wcześniejszej**, patrz [Migrowanie z wcześniejszej przykładowej integracji](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

Funkcje Commerce dla Szwecji obejmują przykładową integrację systemu punktu sprzedaży (POS) ze specyficznym dla Szwecji urządzeniami fiskalnymi, nazywanymi *jednostkami kontrolnymi*. Ten przykład rozszerza [funkcjonalność integracji fiskalnej](fiscal-integration-for-retail-channel.md). Zakłada się, że jednostka kontrolna jest fizycznie połączona ze stacją sprzętową, ze stacją posadową. Jako przykład zastosowano interfejs programowania aplikacji (API) jednostki kontrolnej [CleanCash Typ A](https://www.retailinnovation.se/produkter) stosowanej przez firmę Retail Innovation HTT AB. Używana jest wersja 1.1.4 interfejsu API CleanCash.

Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Retail.

Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy Retail Innovation HTT AB. Aby dowiedzieć się, jak uzyskać jednostkę kontrolną i jak ją obsługiwać, skontaktuj się z [Retail Innovation HTT A](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Scenariusze

Przykład integracji jednostki kontrolnej dla Szwecji obejmuje następujące możliwości:

- Kopie zamówień sprzedaży, zwrotów i paragonów są automatycznie rejestrowane w jednostce kontrolnej połączonej ze stacją sprzętową, która jest sparowana z programem POS.
- Kod kontrolny i numer produkcji jednostki kontrolnej zarejestrowanej transakcji są przechwytywane z jednostki kontrolnej i zapisywane w transakcji. Dane te są również określane mianem *odpowiedzi fiskalnej*. Odpowiedź fiskalną można wyświetlić na stronie **Transakcje sklepu**.
- Niestandardowe pola kodu kontroli i numeru produkcji jednostki kontrolnej mogą być dodane do układu paragonu. W ten sposób można wydrukować odpowiedź fiskalną dla transakcji na paragonie.
- Odpowiedź fiskalna dla transakcji jest pokazana w **raporcie kanału arkusza elektronicznego** (Szwecja).
- Dostępnych jest kilka opcji obsługi błędów. Oto kilka przykładów:

    - Ponów próbę rejestracji fiskalnej, jeśli jest możliwa ponowna próba. Można ponowić próbę rejestracji fiskalnej, jeśli na przykład jednostka kontrolna nie jest połączona, nie jest gotowa lub nie odpowiada.
    - Odroczenie rejestracji fiskalnej.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Zweryfikuj dostępność jednostki kontrolnej przed otwarciem nowej transakcji sprzedaży lub zakończeniem transakcji sprzedaży.

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

Przykładowa integracja jednostek kontrolnych dla Szwecji nie obsługuje obecnie scenariuszy zamówień odbiorcy.

## <a name="setting-up-the-integration-with-control-units"></a>Konfiguracja integracji z jednostkami kontrolnymi

Aby uzyskać więcej informacji na temat konfiguracji wymaganej dla Szwecji, zobacz temat [Konfiguracja usługi Commerce dla Szwecji](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Konfiguracja paragonów specyficznych dla Szwecji

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurowanie pól niestandardowych, aby można było ich używać w formatach paragonów dla paragonów sprzedaży

Możesz skonfigurować tekst w danym języku oraz pola niestandardowe używane w formatach paragonów dla punktu sprzedaży. Domyślna firma użytkownika, który tworzy konfigurację paragonu, powinna być tą samą osobowością prawną, w której jest tworzone ustawienie tekstu w języku. Alternatywnie, można również utworzyć ten sam tekst językowy w domyślnej firmie użytkownika i dla tego samego bytu prawnego, dla którego utworzono konfigurację.

Na stronie **Tekst w języku** dodaj wymienione poniżej rekordy dla etykiet pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora języka**, **Identyfikatora tekstu** i **Tekst** przedstawione w poniższej tabeli są tylko przykładami. Można je zmienić, aby spełniały wymagania użytkownika. Jednak stosowane wartości **Identyfikatora tekstu** muszą być unikatowe oraz większe lub równe 900001.

Dodaj wymienione poniżej etykiety punktu sprzedaży do obszaru **Punkt sprzedaży** na stronie **Tekst w danym języku**.

| Identyfikator języka | Identyfikator tekstu | Tekst                  |
|-------------|---------|-----------------------|
| en-US       | 900001  | Kod sterowania rejestrem |
| en-US       | 900002  | Urządzenie rejestrujące       |

Na stronie **Pola niestandardowe** dodaj następujące rekordy dla pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora tekstu podpisu** muszą być zgodne z wartościami **Identyfikatora tekstu** określonymi na stronie **Tekst w danym języku**.

| Nazwa                         | Typ    | Identyfikator tekstu podpisu |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Pokwitowanie | 900001          |
| SE_FISCALREGISTERID          | Pokwitowanie | 900002          |

> [!NOTE]
> Ważne jest, aby określić poprawne nazwy pól niestandardowych, tak jak podano w tabeli powyżej. Niepoprawna nazwa pola niestandardowego spowoduje brak danych na paragonach.

#### <a name="configure-receipt-formats"></a>Konfiguracja formatów paragonów

Dla każdego wymaganego formatu paragonu zmień wartość pola **Zachowanie drukowania** na **Zawsze drukuj**.

W projektancie formatów paragonów dodaj wymienione poniżej pola niestandardowe do sekcji **Stopka**. Pamiętaj, że nazwy pól muszą odpowiadać tekstom w języku zdefiniowanym w poprzedniej sekcji tego artykułu.

- **Kod kontroli rejestru** – w tym polu jest drukowany kod kontroli.
- **Urządzenie rejestrujące** – w tym polu jest drukowany numer produkcji jednostki kontrolnej.

Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Szablony paragonów i drukowanie](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Konfiguracja integracji fiskalnej dla Szwecji

Przykład integracji jednostki kontrolnej dla Szwecji jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\CleanCash** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji (starsza wersja)](emea-swe-fi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfiguracja integracji fiskalnej dla kanałów Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Należy zwrócić także uwagę na ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tej jednostki kontrolnej w przykładzie integracji](#set-up-the-registration-process).
1. [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfiguracja składników kanału](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki w celu skonfigurowania centrali w rozwiązaniu Commerce. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji fiskalnej dla kanałów rozwiązania Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji (na przykład **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Otwórz folder **src \> FiscalIntegration \> CleanCash**.
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z lokalizacji **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (na przykład, [plik do release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (na przykład, [plik do release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Plik konfiguracji dostawcy dokumentów fiskalnych:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
    > 
    > Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry handlu**. Na karcie **Ogólne** ustaw dla opcji **Włącz integrację fiskalną** wartość **Tak**.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych** i załaduj pobrany wcześniej plik konfiguracji dostawcy dokumentów fiskalnych.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Łączniki fiskalne** i załaduj pobrany wcześniej plik konfiguracji łącznika fiskalnego.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil funkcjonalny łącznika. Wybierz dostawcę dokumentów oraz łącznik, które załadowano wcześniej. Zaktualizuj [ustawienia mapowania danych](#default-data-mapping) zgodnie z wymaganiami.
1. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil techniczny łącznika i wybierz załadowany wcześniej łącznik fiskalny. Zaktualizuj [ustawienia łącznika](#fiscal-connector-settings) zgodnie z wymaganiami.
6. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Grupy łączników fiskalnych**. Utwórz nową grupę łączników fiskalnych dla utworzonego wcześniej profilu funkcjonalnego łącznika.
7. Wybierz kolejno pozycje **Handel detaliczny i inny \> Ustawienia kanału \> Integracja fiskalna \> Procesy rejestracji fiskalnej**. Utwórz nowy proces rejestracji fiskalnej oraz krok procesu rejestracji fiskalnej, a następnie wybierz utworzoną wcześniej grupę łączników fiskalnych.
8. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Wybierz profil funkcjonalności połączony ze sklepem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz utworzony wcześniej proces rejestracji fiskalnej.
9. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Wybierz profil sprzętu połączony ze stacją sprzętową, z którą będzie połączona drukarka fiskalna. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz utworzony wcześniej profil techniczny łącznika.
10. Otwórz harmonogram dystrybucji (**Handel detaliczny i inny \> Składniki IT w handlu detalicznym i innym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

#### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- **Mapowanie kodów podatku od wartości dodanej (VAT)** – w tym mapowaniu kody podatku VAT są ustawiane na konkretne urządzenia i do odpowiednich kodów podatków. Mapowanie kodu VAT powinno mieć następujący format:

    ```
    1 : code1 ; 2 : code2
    ```

    Oto wyjaśnienie tego formatu:

    - Kody VAT *1* i *2* są specyficzne dla danego urządzenia.
    - Średnik (;) jest stosowany jako separator.
    - *Kod1* i *kod2* to kody podatków konfigurowane w centralach Commerce. Z tego powodu należy zmodyfikować przykładowe mapowanie pod kątem kodów podatkowych skonfigurowanych w Twojej aplikacji.

    Jednostki kontrolne obsługują maksymalnie cztery różne kody VAT. Dlatego mapowanie kodu VAT można skonfigurować w następujący sposób:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Wiele kodów podatków może być mapowanych na ten sam kod PODATKU VAT specyficzny dla urządzenia.

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Ciąg połączeń** – ustawienia połączenia jednostki kontrolnej.
- **Limit czasu** – ilość czasu w milisekundach, przez który sterownik czeka na odpowiedź z jednostki kontrolnej.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji (starsza wersja)](emea-swe-fi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

#### <a name="set-up-the-development-environment"></a>Konfigurowanie środowiska projektowego

Aby skonfigurować środowisko projektowe w celu testowania i rozszerzania przykładu, wykonaj poniższe kroki.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu Retail SDK z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie integracji jednostki kontrolnej w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln** i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji CRT:

    1. Znajdź instalatora rozszerzeń kolekcji CRT:

        - **Commerce Scale Unit:** w folderze **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461** znajdź instalatora **ScaleUnit.CleanCash.Installer**.
        - **Lokalna kolekcja CRT w aplikacji Modern POS:** w folderze **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461** znajdź instalatora **ModernPOS.CleanCash.Installer**.

    2. Uruchom instalatora rozszerzeń kolekcji CRT z poziomu wiersza polecenia:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **Lokalna kolekcja CRT w aplikacji Modern POS:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Zainstaluj rozszerzenia stacji sprzętowej:

    1. W folderze **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461** znajdź instalatora **HardwareStation.CleanCash.Installer**.
    1. Uruchom instalatora rozszerzeń z poziomu wiersza polecenia:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj kroki opisane w artykule [Konfigurowanie potoku kompilacji dla przykładu integracji fiskalnej](fiscal-integration-sample-build-pipeline.md), aby wygenerować i wydać rozwiązanie Cloud Scale Unit oraz samoobsługowe wdrażalne pakiety dla przykładu integracji fiskalnej. Plik YAML szablonu **CleanCash build-pipeline.yml** znajduje się w folderze **Pipeline\\YAML_Files** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Projekt rozszerzeń

Przykład integracji jednostki kontrolnej dla Szwecji jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\CleanCash** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji (starsza wersja)](emea-swe-fi-sample-sdk.md). Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

### <a name="crt-extension-design"></a>Projekt rozszerzenia kolekcji CRT

Celem rozszerzenia, czyli dostawcy dokumentów fiskalnych, jest generowanie dokumentów specyficznych dla usługi i obsługa odpowiedzi z jednostki kontrolnej.

#### <a name="request-handler"></a>Program obsługi żądań

Istnieje jeden program obsługi żądań dla dostawcy dokumentów o nazwie **DocumentProviderCleanCash**. Ten program obsługi służy do generowania dokumentów fiskalnych dla jednostki kontrolnej.

Ten program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który powinien zostać zarejestrowany w jednostce kontrolnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie obsługiwane są zdarzenia sprzedaży i zdarzenia inspekcji.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla dostawcy dokumentów fiskalnych znajduje się w lokalizacji **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Celem rozszerzenia, czyli łącznika fiskalnego, jest komunikowanie się z jednostką kontrolną. Używa ono protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do jednostki kontrolnej. Obsługuje również odpowiedzi odbierane z jednostki kontrolnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **CleanCashHandler** jest punktem wejściowym obsługi żądań kierowanych do jednostki kontrolnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** – to żądanie wysyła dokumenty do jednostki kontrolnej i otrzymuje z niej odpowiedź.
- **IsReadyFiscalDeviceRequest** – to żądanie służy do sprawdzania stanu jednostki kontrolnej.
- **InitializeFiscalDeviceRequest** – to żądanie jest stosowane do inicjowania jednostki kontrolnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla łącznika fiskalnego znajduje się w lokalizacji **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
