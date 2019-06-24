---
title: Przykładowa integracja drukarki fiskalnej dla Polski
description: W tym temacie zawarto ogólne informacje o przykładowej integracji dla Polski.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Poland
ms.search.industry: Retail
ms.author: v-dmpere
ms.search.validFrom: 2019-2-1
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: aa65438412bb0e16b06a58ffc8136f08388429fa
ms.sourcegitcommit: 574d4dda83dcab94728a3d35fc53ee7e2b90feb0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2019
ms.locfileid: "1595469"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Przykładowa integracja drukarki fiskalnej dla Polski

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Wprowadzenie

Funkcja programu Microsoft Dynamics 365 for Retail dla Polski obejmuje przykładową integrację punktu sprzedaży (POS) z drukarką fiskalną. Przykładowa integracja rozszerza [funkcję integracji fiskalnej](fiscal-integration-for-retail-channel.md) i obsługuje protokół POSNET THERMAL HD 2.02 dla drukarek fiskalnych z [Posnet Polska S.A.](https://www.posnet.com.pl) Przykład umożliwia komunikację z drukarką fiskalną połączoną przez port COM przy użyciu natywnego oprogramowania sterownika. Implementację i testy przeprowadzono przy użyciu emulatora oprogramowania dostarczonego przez Posnet dla drukarki fiskalnej Posnet Thermal HD FV EJ. Przykładowa integracja ma formę kodu źródłowego i jest częścią zestawu SDK modułu Retail.

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

- Zestawienia na koniec dnia (raporty fiskalne X i końcowy raport sprzedaży).
- Obsługa błędów, np. następujących opcji:

    - Ponowienie próby rejestracji fiskalnej, jeśli ponownie jest możliwe, np. jeśli drukarka fiskalna nie jest podłączona, jest niegodowa lub nie odpowiada, w drukarce nie ma papieru lub występuje zakleszczenie papieru.
    - Odroczenie rejestracji fiskalnej.
    - Pominięcie rejestracji fiskalnej lub oznaczenie transakcji jako zarejestrowanej i wprowadzenie kodów informacji oznaczających przyczynę błędu oraz dodatkowe informacje.
    - Sprawdź dostępność drukarki fiskalnej przed otwarciem nowej transakcji sprzedaży lub zakończeniem transakcji sprzedaży.

### <a name="default-data-mapping"></a>Domyślne mapowanie danych

Następujące domyślne mapowanie danych jest uwzględnione w bieżącej konfiguracji dostawcy dokumentu fiskalnego dostarczanego jako część przykładowej integracji fiskalnej:

- Mapowanie podatku od towarów i usług (VAT):

    *0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00*

- Mapowanie typów metod płatności:

    *0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0*

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

- Drukarka fiskalna obsługuje tylko scenariusze, w których podatek od sprzedaży jest uwzględniony w cenie. Z tego względu opcja **Cena zawiera podatek** musi być ustawiona na **Tak** zarówno dla sklepów detalicznych, jak i odbiorców.
- Raporty dzienne (fiskalne X i końcowy raport sprzedaży)są drukowane przy użyciu osadzonego formatu *Raport zmiany*.
- Drukowanie kodu kreskowego na paragonach fiskalnych jest traktowane jako potencjalne dostosowanie, ponieważ ta funkcja nie jest obsługiwana w formatach osadzonych i jej wprowadzenie może nastąpić wyłącznie przy użyciu dostosowywanego raportu **Super-format**.
- Mieszane transakcje nie są obsługiwane przez drukarkę fiskalną. Opcja **Zabraniaj umieszczania sprzedaży i zwrotów na jednym paragonie** powinna być ustawiona na **Tak**w profilach funkcji POS.

## <a name="set-up-retail-for-poland"></a>Konfigurowanie modułu Retail dla Polski

### <a name="configure-fiscal-integration"></a>Konfiguracja integracji fiskalnej

Wykonaj kroki konfiguracji integracji fiskalnej w sposób opisany w [Konfigurowanie integracji fiskalnej dla kanałów sprzedaży detalicznej](setting-up-fiscal-integration-for-retail-channel.md):

- [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Należy zauważyć również ustawienia dla procesu rejestracji fiskalnej [specyficzne dla tej drukarki fiskalnej w przykładzie integracji](#set-up-the-registration-process).
- [Określanie ustawienia ustawień obsługi błędów](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
- [Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- [Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="enable-extensions"></a>Włączanie rozszerzeń

#### <a name="commerce-runtime-extension-components"></a>Komponentu rozszerzenia środowiska uruchomieniowego Commerce

Komponenty rozszerzenia Commerce Runtime (CRT) znajdują się w zestawie SDK modułu Retail. Aby wykonać poniższe procedury, otwórz rozwiązanie CRT, **CommerceRuntimeSamples.sln**, w obszarze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.PosnetSample** i zbuduj go.
2. W folderze **Extensions.DocumentProvider.PosnetSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji Microsoft Internet Information Services (IIS) witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzeń dla CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config** i jest w folderze bin\\ext w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę CRT w pliku konfiguracji rozszerzenia. Dodaj **source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample"**.
6. Uruchom ponownie usługę Retail.

    - **Retail Server:** uruchom ponownie witrynę usługi Retail z menedżera IIS.
    - **Broker klienta:** zakończ proces **dllhost.exe** w Menedżerze zadań, a następnie uruchom Modern POS.

#### <a name="hardware-station-extension-components"></a>Komponenty rozszerzenia Hardware Station

Komponenty rozszerzenia Hardware Station znajdują się w zestawie SDK modułu Retail. Aby wykonać poniższe procedury, otwórz rozwiązania Hardware Station (**HardwareStationSamples.sln**) w obszarze **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Znajdź projekt **Extension.PosnetThermalFVFiscalPrinterSample** i zbuduj go.
2. W folderze **Extension.PosnetThermalFVFiscalPrinterSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Skopiuj plik do wdrożonego komputera Hardware Station:

    - **Zdalna usługa Hardware Station:** skopiuj pliki do folderu **bin** w lokalizacji IIS witryny Hardware Station. Skopiuj biblioteki sterownika drukarki (**libposcmbth.dll**, **libcmbth\_serial.dll** oraz **cmbth\_pl.lng**).

4. Znajdź plik konfiguracji dla rozszerzeń Hardware Station. Plik nosi nazwę **HardwareStation.Extension.config**:

    - **Zdalna usługa Hardware Station:** plik znajduje się w lokalizacji IIS witryny Hardware Station.

5. Dodaj następującą sekcję do sekcji **kompozycja** pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Uruchom ponownie usługę Hardware Station:

    - **Zdalna usługa Hardware Station:** uruchom ponownie Hardware Station z Menedżera IIS.

### <a name="set-up-the-registration-process"></a>Konfigurowanie procesu rejestracji

Aby włączyć proces rejestracji, wykonaj następujące kroki do skonfigurowania Retail Headquarters. Aby uzyskać więcej informacji, zobacz [Konfigurowanie procesu rejestracji fiskalnej](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Wybierz kolejno **Handel detaliczny \> Konfigurowanie kanału \> Integracja fiskalna \> Łączniki fiskalne**. Zaimportuj konfigurację z **RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorConnectorPosnetThermalFVEJ.xml**.
2. Wybierz kolejno **Handel detaliczny \> Ustawienia kanału \> Integracja fiskalna \> Dostawcy dokumentów fiskalnych**. Zaimportuj konfigurację z **RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml**.
3. Wybierz kolejno **Handel detaliczny \> Konfigurowanie kanału \> Integracja fiskalna \> Profile techniczne łącznika**. Utwórz nowy profil i wybierz łącznik załadowany w poprzednim kroku. Zaktualizuj ustawienia połączenia, jeśli wymagana jest aktualizacja.
4. Wybierz kolejno **Handel detaliczny \> Konfigurowanie kanału \> Integracja fiskalna \> Profile funkcjonalności łącznika**. Utwórz nowy profil i wybierz łącznik i dostawcę dokumentów załadowane w poprzednich krokach. Zaktualizuj ustawienia mapowania danych, jeśli aktualizacja jest wymagana.
5. Wybierz kolejno **Handel detaliczny \> Konfigurowanie kanału \> Integracja fiskalna \> Grupa funkcjonalności łącznika**. Utwórz nową grupę i wybierz profil funkcji łącznika z poprzedniego kroku.
6. Wybierz kolejno **Handel detaliczny \> Konfigurowanie kanału \> Integracja fiskalna \> Proces rejestracji**. Utwórz nowy proces i wybierz grupę funkcji łącznika z poprzedniego kroku.
7. Wybierz kolejno **Handel detaliczny \> Ustawienia kanału punkt sprzedaży \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**. Otwórz profil funkcji, który jest połączony z magazynem, w którym należy aktywować proces rejestracji. Na skróconej karcie **Proces rejestracji fiskalnej** wybierz proces rejestracji, który został utworzony wcześniej.
8. Wybierz kolejno opcje **Handel detaliczny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu**. Otwórz profil sprzętu, który jest połączony z usługą Hardware Station, do której będzie połączona drukarka fiskalna. Na skróconej karcie **Fiskalne urządzenia peryferyjne** wybierz profil techniczny łącznika.
9. Otwórz harmonogram dystrybucji (**Handel detaliczny \> Składniki IT w handlu detalicznym \> Harmonogram dystrybucji**) i wybierz zadania **1070** i **1090** do przesyłania danych do bazy danych kanału.

### <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj następujące kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki sieci sprzedaży i aby stosować te pakiety w środowisku produkcyjnym.

1. Wykonaj kroki opisane w części [Włączanie rozszerzeń](#enable-extensions) w tym temacie.
2. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    - W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

3. Należy wprowadzić następujące zmiany w pliku konfiguracji dostosowań pakietu **BuildTools\\Customization.settings**:

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenie CRT w pakietach, które można wdrożyć.

        ``` xml 
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenie stacji sprzętu w pakietach, które można wdrożyć.

        ``` xml 
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

4. Uruchom wiersz polecenia MSBuild dla Visual Studio i uruchom **msbuild** w folderze Retail SDK, aby utworzyć pakiety, które można wdrożyć.
5. Zastosuj pakiety za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS) lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów rozwiązania Retail](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Celem rozszerzenia (dostawcy dokumentów fiskalnych) jest generowanie dokumentów specyficznych dla drukarki i obsługa odpowiedzi z drukarki fiskalnej.

Rozszerzenie środowiska uruchomieniowego Commerce to **Runtime.Extensions.DocumentProvider.PosnetSample**. To rozszerzenie generuje zestaw poleceń specyficznych dla drukarki, które są definiowane przez specyfikację POSNET 19-3678 w formacie JavaScript Object Notation (JSON).

Aby uzyskać więcej informacji o projektowaniu rozwiązań integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

#### <a name="request-handler"></a>Program obsługi żądań
    
Program obsługi żądań **DocumentProviderPosnetProtocol** jest punktem wejścia dla żądania generowania dokumentów z drukarki fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi powinna odpowiadać nazwie dostawcy dokumentów łącznika określonej w Retail Headquarters.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla drukarki, który powinien zostać zarejestrowany w drukarce fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie są obsługiwane następujące zdarzenia: sprzedaż, drukowanie raportu X i drukowanie końcowego raportu sprzedaży.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień dostawcy dokumentu z Retail Headquarters. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- Mapowanie stawek VAT
- Mapowanie typów metod płatności
- Typ płatności wpłaty

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Zastosowaniem rozszerzenia (łącznika fiskalnego) jest do komunikowanie się z drukarką fiskalną.

Rozszerzenie Hardware Station to **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. To rozszerzenie przesyła polecenia, które rozszerzenia środowiska uruchomieniowego Commerce generuje na drukarce fiskalnej, przez wywołanie funkcji POSNET sterownika dostarczonego przez producenta. Obsługuje również błędy urządzenia.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **FiscalPrinterHandler** jest punktem wejściowym dla obsługi żądania przez fiskalne urządzenie peryferyjne.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi powinna odpowiadać nazwie łącznika fiskalnego określonej w Retail Headquarters.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do drukarek i zwraca odpowiedzi z drukarki fiskalnej.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania stanu urządzenia.
- **InitializeFiscalDeviceRequest** — to żądanie jest używane do inicjowania drukarki.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień łącznika z Retail Headquarters. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Ciąg połączenia** — ten ciąg opisuje szczegóły połączenia do urządzenia w formacie obsługiwanym przez sterownik urządzenia. Aby uzyskać szczegółowe informacje, zobacz dokumentację sterownika POSNET.
- **Data i godzina synchronizacji** — to ustawienie określa, czy należy zsynchronizować datę i godzinę drukarki ze stacją połączoną Hardware Station
- **Limit czasu urządzenia** — ilość czasu, w milisekundach, przez który sterownik czeka na odpowiedź z urządzenia. Aby uzyskać szczegółowe informacje, zobacz dokumentację sterownika POSNET.
