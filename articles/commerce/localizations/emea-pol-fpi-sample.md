---
title: Przykładowa integracja drukarki fiskalnej dla Polski
description: W tym temacie zawarto ogólne informacje o przykładowej integracji fiskalnej dla Polski w Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: 43d9a54334d97a65a1f9a356daf54154f6c069b3
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076843"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Przykładowa integracja drukarki fiskalnej (Polska)

[!include[banner](../includes/banner.md)]

W tym temacie zawarto ogólne informacje o przykładowej integracji fiskalnej dla Polski w Microsoft Dynamics 365 Commerce.

Funkcja programu Dynamics 365 Commerce dla Polski obejmuje przykładową integrację punktu sprzedaży (POS) z drukarką fiskalną. Przykładowa integracja rozszerza [funkcję integracji fiskalnej](fiscal-integration-for-retail-channel.md) i obsługuje protokół POSNET THERMAL HD 2.02 dla drukarek fiskalnych z [Posnet Polska S.A.](https://www.posnet.com.pl) Przykład umożliwia komunikację z drukarką fiskalną połączoną przez port COM przy użyciu natywnego oprogramowania sterownika. Implementację i testy przeprowadzono przy użyciu emulatora oprogramowania dostarczonego przez Posnet dla drukarki fiskalnej Posnet Thermal HD FV EJ. Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Retail.

Microsoft nie udostępnia żadnego sprzętu, oprogramowania ani dokumentacji firmy Posnet. Aby dowiedzieć się, jak uzyskać drukarkę fiskalną i jak ją obsługiwać, skontaktuj się z [Posnet Polska S.A.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Scenariusze

Poniższe scenariusze są objęte próbką integracją drukarki fiskalnej dla Polski:

- Scenariusze sprzedaży:

    - Drukowanie paragonu fiskalnego dla sprzedaży i zwrotów zapłaty przy kasie.
    - Rejestrowanie odpowiedzi z drukarki fiskalnej i zapisywanie jej w bazie danych kanału.
    - Podatki:

        - Mapowanie kodów podatku drukarki fiskalnej (działy).
        - Przesyłanie zamapowanych danych podatku do drukarki fiskalnej.

    - Płatności:

        - Mapowanie metod płatności drukarki fiskalnej.
        - Drukowanie płatności na paragonie fiskalnym.
        - Drukowanie informacji o zmianie.

    - Drukowanie rabatów dla pozycji.
    - Karty upominkowe:

        - Wykluczanie pozycji wydanej/doładowanej karty upominkowej z paragonu fiskalnego dla sprzedaży.
        - Drukowanie płatności używającej karty upominkowej jako zwykłej metody płatności.

    - Drukowanie paragonów fiskalnych dla operacji zamówień odbiorcy:

        - Paragon fiskalny nie jest drukowany dla wypłaty za zamówienie odbiorcy.
        - Drukowanie paragonu fiskalnego dla wierszy przeprowadzenia hybrydowego zamówienia odbiorcy.
        - Drukowanie paragonu fiskalnego dla operacji pobrania zamówienia odbiorcy.
        - Drukowanie paragonu fiskalnego dla zamówienia zwrotu.

    - Umożliwia drukowanie [informacji o odbiorcy](emea-pol-customer-information.md), które zostały określone dla transakcji sprzedaży w paragonie fiskalnym. Przykładem tej informacji jest numer VAT odbiorcy.

- Zestawienia na koniec dnia (raporty fiskalne X i końcowy raport sprzedaży).
- Obsługa błędów, np. następujących opcji:

    - Ponowienie próby rejestracji fiskalnej, jeśli ponownie jest możliwe, np. jeśli drukarka fiskalna nie jest podłączona, jest niegodowa lub nie odpowiada, w drukarce nie ma papieru lub występuje zakleszczenie papieru.
    - Odroczenie rejestracji fiskalnej.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Sprawdź dostępność drukarki fiskalnej przed otwarciem nowej transakcji sprzedaży lub zakończeniem transakcji sprzedaży.

### <a name="gift-cards"></a>Karty upominkowe

Przykładowa integracja drukarki fiskalnej implementuje następujące reguły związane z kartami upominkowymi:

- Wyłączenie z paragonu fiskalnego wierszy sprzedaży, które są związane z operacjami *Wystaw kartę upominkową* i *Dodaj do karty upominkowej*.
- Niedrukowanie paragonu fiskalnego, jeśli zawiera tylko wiersze karty upominkowej.
- Odjęcie łącznej kwoty kart upominkowych, które zostały wystawione lub doładowane w ramach transakcji z wierszy płatności paragonu fiskalnego.
- Zapisanie obliczanych korekt wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej.
- Płatność kartą upominkową jest traktowana jako zwykła płatność.

### <a name="customer-deposits-and-customer-order-deposits"></a>Obsługa wpłat odbiorcy i wpłat za zamówienie odbiorcy

Przykładowa integracji drukarki fiskalnej implementuje następujące reguły, które są związane z wpłatami odbiorcy i wpłatami za zamówienie odbiorcy:

- Nie drukuj paragonu fiskalnego, jeśli transakcja jest wpłatą odbiorcy.
- Nie drukuj paragonu fiskalnego, jeśli transakcja zawiera tylko wpłatę za zamówienie klienta lub zwrot takiej wpłaty.
- Drukuj kwotę wcześniej zapłaconej wpłaty na paragonie fiskalnym dla operacji odebrania zamówienia odbiorcy.
- Odejmij kwotę wpłaty za zamówienie odbiorcy od wiersza płatności, kiedy tworzone jest zamówienie hybrydowe odbiorcy.
- Zapisz obliczane korekty wierszy płatności w bazie danych kanału w odniesieniu do odpowiedniej transakcji fiskalnej dla hybrydowego zamówienia odbiorcy.

### <a name="limitations-of-the-sample"></a>Ograniczenia przykładowej integracji

- Drukarka fiskalna obsługuje tylko scenariusze, w których podatek od sprzedaży jest uwzględniony w cenie. Z tego względu opcja **Cena zawiera podatek** musi być ustawiona na **Tak** zarówno dla sklepów, jak i odbiorców.
- Raporty dzienne (fiskalne X i końcowy raport sprzedaży)są drukowane przy użyciu osadzonego formatu *Raport zmiany*.
- Drukowanie kodu kreskowego na paragonach fiskalnych jest traktowane jako potencjalne dostosowanie, ponieważ ta funkcja nie jest obsługiwana w formatach osadzonych i jej wprowadzenie może nastąpić wyłącznie przy użyciu dostosowywanego raportu **Super-format**.
- Mieszane transakcje nie są obsługiwane przez drukarkę fiskalną. Opcja **Zabraniaj umieszczania sprzedaży i zwrotów na jednym paragonie** powinna być ustawiona na **Tak** w profilach funkcji POS.

## <a name="set-up-fiscal-integration-for-poland"></a>Konfiguracja integracji fiskalnej dla Polski

Przykład integracji drukarki fiskalnej dla Polski jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Posnet** repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji Commerce Runtime (CRT), oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski (starsze)](emea-pol-fpi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfiguracja integracji fiskalnej dla kanałów Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Należy zwrócić także uwagę na ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tej drukarki fiskalnej w przykładzie integracji](#set-up-the-registration-process).
1. [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfiguracja składników kanału](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki w celu skonfigurowania centrali w rozwiązaniu Commerce. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji fiskalnej dla kanałów rozwiązania Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Pobierz pliki konfiguracji dla dostawcy dokumentów fiskalnych i łącznika fiskalnego:

    1. Otwórz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji (na przykład **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Otwórz folder **src \> FiscalIntegration \> Posnet**.
    1. Pobierz plik konfiguracji dostawcy dokumentów fiskalnych z lokalizacji **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml** (na przykład, [plik do release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Pobierz plik konfiguracji łącznika fiskalnego z lokalizacji **HardwareStation \> ThermalDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml** (na przykład, [plik do release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Pliki konfiguracji dla tego przykładu integracji fiskalnej znajdują się w wymienionych poniżej folderach zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS:
    >
    > - **Plik konfiguracji dostawcy dokumentu fiskalnego:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml
    > - **Plik konfiguracji łącznika fiskalnego:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml
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

- **Mapowanie stawek podatku od wartości dodanej (VAT)** – Mapowanie wartości procentowych podatków, które zostały ustawione dla kodów podatków do specyficznych dla drukarki fiskalnej stawek VAT. Poniżej pokazano mapowanie domyślne:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Pierwszy składnik w każdej parze reprezentuje numer stawki VAT konfigurowany w drukarce fiskalnej. Drugi składnik reprezentuje odpowiadającą jej stawkę podatku VAT. Aby uzyskać więcej informacji o konfiguracji stawek VAT drukarki fiskalnej, zobacz dokumentację sterowników programu POSNET.

- **Mapowanie typów metod płatności** — mapowanie metod płatności skonfigurowanych dla sklepu na formy płatności obsługiwane przez drukarkę fiskalną. Poniżej pokazano mapowanie domyślne:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Pierwszy składnik w każdej parze reprezentuje metodę płatności skonfigurowaną dla sklepu. Drugi składnik reprezentuje odpowiadającą jej formę płatności, która jest obsługiwana przez drukarkę fiskalną. Aby uzyskać więcej informacji o formach płatności obsługiwanych przez drukarkę fiskalną, zobacz dokumentację sterowników programu POSNET. Z tego powodu należy zmodyfikować przykładowe mapowanie pod kątem metod płatności skonfigurowanych w Twojej aplikacji.

#### <a name="fiscal-connector-settings"></a>Ustawienia łącznika fiskalnego

Wymienione poniżej ustawienia wchodzą w skład konfiguracji łącznika fiskalnego dostarczanej jako część przykładu integracji fiskalnej:

- **Ciąg połączenia** – ciąg opisuje szczegóły połączenia z urządzeniem w formacie obsługiwanym przez sterownik urządzenia. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją sterownika POSNET.
- **Data i godzina synchronizacji** – wartość określająca, czy należy zsynchronizować datę i godzinę drukarki ze stacją połączoną Hardware Station.
- **Limit czasu urządzenia** — ilość czasu, w milisekundach, przez który sterownik czeka na odpowiedź z urządzenia. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją sterownika POSNET.

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski (starsze)](emea-pol-fpi-sample-sdk.md).
>
> Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

#### <a name="set-up-the-development-environment"></a>Konfigurowanie środowiska projektowego

Aby skonfigurować środowisko projektowe w celu testowania i rozszerzania przykładu, wykonaj poniższe kroki.

1. Sklonuj lub pobierz repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions). Wybierz poprawną wersję odgałęzienia wydania zgodnie ze swoją wersją zestawu SDK / aplikacji. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładów i pakietów referencyjnych zestawu Retail SDK z witryn GitHub i NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Otwórz rozwiązanie integracji drukarki fiskalnej w lokalizacji **Dynamics365Commerce.Solutions\\FiscalIntegration\\Posnet\\Posnet.sln**, i skompiluj je.
1. Zainstaluj rozszerzenia kolekcji CRT:

    1. Znajdź instalatora rozszerzeń kolekcji CRT:

        - **Commerce Scale Unit:** w folderze **Posnet\\ScaleUnit\\ScaleUnit.Posnet.Installer\\bin\\Debug\\net461** znajdź instalatora **ScaleUnit.Posnet.Installer**.
        - **Lokalna kolekcja CRT w aplikacji Modern POS:** w folderze **Posnet\\ModernPOS\\ModernPOS.Posnet.Installer\\bin\\Debug\\net461** znajdź instalatora **ModernPOS.Posnet.Installer**.

    1. Uruchom instalatora rozszerzeń kolekcji CRT z poziomu wiersza polecenia:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **Lokalna kolekcja CRT w aplikacji Modern POS:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Zainstaluj rozszerzenia stacji sprzętowej:

    1. W folderze **Posnet\\HardwareStation\\HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\bin\\Debug\\net461** znajdź instalatora **HardwareStation.PosnetThermalFVFiscalPrinter.Installer**.
    1. Uruchom instalatora rozszerzeń z poziomu wiersza polecenia:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj kroki opisane w artykule [Konfigurowanie potoku kompilacji dla przykładu integracji fiskalnej](fiscal-integration-sample-build-pipeline.md), aby wygenerować i wydać rozwiązanie Cloud Scale Unit oraz samoobsługowe wdrażalne pakiety dla przykładu integracji fiskalnej. Plik YAML szablonu **Posnet build-pipeline.yml** znajduje się w folderze **Pipeline\\YAML_Files** repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji drukarki fiskalnej dla Polski jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md) i stanowi część zestawu Retail SDK. Przykład znajduje się w folderze **src\\FiscalIntegration\\Posnet** repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (na przykład [przykład w folderze release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). Przykład [składa się](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) z dostawcy dokumentów fiskalnych, który stanowi rozszerzenie kolekcji CRT, oraz łącznika fiskalnego, który stanowi rozszerzenie stacji sprzętowej rozwiązania Commerce. Aby uzyskać więcej informacji dotyczących sposobu używania zestawu Retail SDK, zobacz [Architektura zestawu Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) oraz [Konfigurowanie potoku kompilacji dla zestawu SDK do niezależnego pakowania](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Z powodu ograniczeń [nowego modelu niezależnego pakowania i rozszerzeń](../dev-itpro/build-pipeline.md), nie można go obecnie używać na potrzeby tego przykładu integracji fiskalnej. Musisz użyć poprzedniej wersji zestawu Retail SDK na maszynie wirtualnej dewelopera w usłudze LCS. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski (starsze)](emea-pol-fpi-sample-sdk.md). Wprowadzenie obsługi nowego modelu niezależnego pakowania i rozszerzenia dla przykładów integracji fiskalnej jest planowane w przyszłych wersjach.

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Celem rozszerzenia (dostawcy dokumentów fiskalnych) jest generowanie dokumentów specyficznych dla drukarki i obsługa odpowiedzi z drukarki fiskalnej. To rozszerzenie generuje zestaw poleceń specyficznych dla drukarki, które są definiowane przez specyfikację POSNET 19-3678 w formacie JavaScript Object Notation (JSON).

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **DocumentProviderPosnetProtocol** jest punktem wejścia dla żądania generowania dokumentów z drukarki fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla drukarki, który powinien zostać zarejestrowany w drukarce fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie są obsługiwane następujące zdarzenia: sprzedaż, drukowanie raportu X i drukowanie końcowego raportu sprzedaży.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla dostawcy dokumentów fiskalnych znajduje się w lokalizacji **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** w repozytorium [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów fiskalnych z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Zastosowaniem rozszerzenia (łącznika fiskalnego) jest do komunikowanie się z drukarką fiskalną. To rozszerzenie przesyła polecenia, które rozszerzenie CRT generuje na drukarce fiskalnej, przez wywołanie funkcji POSNET sterownika dostarczonego przez producenta. Obsługuje również błędy urządzenia.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **FiscalPrinterHandler** jest punktem wejściowym dla obsługi żądania przez fiskalne urządzenie peryferyjne.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do drukarek i zwraca odpowiedzi z drukarki fiskalnej.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania stanu urządzenia.
- **InitializeFiscalDeviceRequest** — to żądanie jest używane do inicjowania drukarki.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji dla łącznika fiskalnego znajduje się w lokalizacji **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** repozytorium [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
