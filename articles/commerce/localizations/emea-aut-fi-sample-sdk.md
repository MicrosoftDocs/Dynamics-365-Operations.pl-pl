---
title: Wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Austrii (starsza wersja)
description: Ten temat zawiera wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Austrii z poziomu zestawu Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce Retail.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 6238b67a35a303a03c51bbd261dd24d1b2acf041
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077122"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-austria-legacy"></a>Wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Austrii (starsza wersja)

[!include [banner](../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Austrii z poziomu zestawu Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji dotyczących tego przykładu integracji fiskalnej, zobacz [Przykład integracji usługi rejestracji fiskalnej dla Austrii](emea-aut-fi-sample.md). 

Przykład integracji fiskalnej dla Austrii jest częścią zestawu Retail SDK. Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK, zobacz [Omówienie zestawu Retail SDK (Software Development Kit)](../dev-itpro/retail-sdk/retail-sdk-overview.md). Przykład integracji fiskalnej składa się z rozszerzeń kolekcji Commerce Runtime (CRT), stacji sprzętowej i punktu sprzedaży. Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT, stacji sprzętowej i punktu sprzedaży. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym temacie używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Azure DevOps, w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.

## <a name="development-environment"></a>Środowiska programistyczne

Wykonaj poniższe kroki, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

### <a name="enable-commerce-runtime-extensions"></a>Włączanie rozszerzeń kolekcji Commerce Runtime

Składniki rozszerzenia kolekcji CRT znajdują się w przykładach kolekcji CRT. Aby wykonać poniższe procedury, otwórz rozwiązanie **CommerceRuntimeSamples.sln** w folderze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>Składnik DocumentProvider.EFRSample

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.EFRSample** i skompiluj go.
2. W folderze **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w Internetowych usługach informacyjnych (IIS).
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>Składnik DocumentProvider.DataModelEFR

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.DataModelEFR** i skompiluj go.
2. W folderze **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Plik konfiguracji rozszerzenia

1. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

2. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
    ```

### <a name="enable-hardware-station-extensions"></a>Włączanie rozszerzeń stacji sprzętowej

Składniki rozszerzenia stacji sprzętowej wchodzą w skład przykładów stacji sprzętowej. Aby wykonać poniższe procedury, otwórz rozwiązania **HardwareStationSamples.sln** w folderze **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="efrsample-component"></a>Składnik EFRSample

1. Znajdź projekt **HardwareStation.Extension.EFRSample** i skompiluj go.
2. W folderze **Extension.EFRSample\\bin\\Debug** znajdź następujące pliki zestawów:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Skopiuj pliki zestawów do folderu rozszerzeń stacji sprzętowej:

    - **Udostępniona stacja sprzętowa:** skopiuj pliki do folderu **bin** w lokalizacji witryny stacji sprzętowej w usługach IIS.
    - **Dedykowana stacja sprzętowa w aplikacji Modern POS:** skopiuj pliki do lokalizacji brokera klienta aplikacji Modern POS.

4. Znajdź plik konfiguracji rozszerzenia dla rozszerzeń stacji sprzętowej. Ten plik nosi nazwę **HardwareStation.Extension.config**.

    - **Udostępniona stacja sprzętowa:** plik znajduje się w lokalizacji witryny stacji sprzętowej w usługach IIS.
    - **Dedykowana stacja sprzętowa w aplikacji Modern POS:** plik znajduje się w lokalizacji brokera klienta aplikacji Modern POS.

5. Dodaj poniższy wiersz do sekcji **composition** pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Włączanie składników rozszerzenia Modern POS

1. Otwórz rozwiązanie **ModernPOS.sln** w **RetailSdk\\POS**, i upewnij się, że można je skompilować bez błędów. Ponadto upewnij się, że program Modern POS firmy Visual Studio można uruchomić za pomocą polecenia **Uruchom**.

    > [!NOTE]
    > Nie można dostosowywać Modern POS. Należy włączyć funkcję Kontroli konta użytkownika (UAC) i w razie potrzeby odinstalować uprzednio zainstalowane wersje programu Modern POS.

2. Włącz możliwość ładowania rozszerzeń przez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Aby uzyskać więcej informacji oraz przykładów, które pokazują sposób dołączania folderów kodu źródłowego i włączania ładowania rozszerzeń, zobacz instrukcje w pliku readme.md w projekcie **Pos.Extensions**.

3. Skompiluj ponownie rozwiązanie.
4. Uruchom program Modern POS w debugerze i sprawdź funkcjonalność.

### <a name="enable-cloud-pos-extension-components"></a>Włączanie składników rozszerzenia Cloud POS

1. Otwórz rozwiązanie **CloudPOS.sln** w **RetailSdk\\POS**, i upewnij się, że można je skompilować bez błędów.
2. Włącz możliwość ładowania rozszerzeń przez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Aby uzyskać więcej informacji oraz przykładów, które pokazują sposób dołączania folderów kodu źródłowego i włączania ładowania rozszerzeń, zobacz instrukcje w pliku readme.md w projekcie **Pos.Extensions**.

3. Skompiluj ponownie rozwiązanie.
4. Uruchom rozwiązanie, używając polecenia **Uruchom** i wykonaj kroki opisane w podręczniku zestawu Retail SDK.

## <a name="production-environment"></a>Środowisko produkcyjne

Wykonanie poprzedniej procedury powoduje włączenie rozszerzeń, które są składnikami przykładu integracji usługi rejestracji fiskalnej. Oprócz tego musisz wykonać te kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki rozwiązania Commerce, oraz zastosować te pakiety w środowisku produkcyjnym.

1. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    - W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujące wiersze w sekcji **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
        ```

    - W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

2. Wprowadź poniższe zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings** w folderze **BuildTools**:

    - Dodaj poniższe wiersze, aby dołączyć rozszerzenia kolekcji CRT w pakietach, które można wdrożyć.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenie stacji sprzętu w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Uruchom wiersz polecenia MSBuild dla Visual Studio i uruchom **msbuild** w folderze Retail SDK, aby utworzyć pakiety, które można wdrożyć.
4. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Wykonaj wszystkie wymagane zadania konfiguracyjne opisane w artykule [Konfigurowanie rozwiązania Commerce dla Austrii](emea-aut-fi-sample.md#set-up-commerce-for-austria).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji usługi rejestracji fiskalnej dla Austrii jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md). Aby uzyskać więcej informacji dotyczących projektu rozwiązania integracji fiskalnej, zobacz [Omówienie projektu przykładu integracji fiskalnej](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Rozszerzenie (dostawca dokumentów fiskalnych) służy do generowania dokumentów specyficznych dla usługi oraz obsługi odpowiedzi z usługi rejestracji fiskalnej.

Rozszerzenie kolekcji CRT to **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Program obsługi żądań

Istnieją dwa programy obsługi żądań dla dostawców dokumentów:

- **DocumentProviderEFRFiscalAUT** — ten program obsługi służy do generowania dokumentów fiskalnych dla usługi rejestracji fiskalnej.
- **DocumentProviderEFRNonFiscalAUT** — ten program obsługi służy do generowania dokumentów niefiskalnych dla usługi rejestracji fiskalnej.

Te programy obsługi są dziedziczone z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetNonFiscalDocumentDocumentProviderRequest** — to żądanie zawiera informacje dotyczące dokumentu niefiskalnego, który ma zostać wygenerowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Aktualnie obsługiwane są następujące zdarzenia: sprzedaż, drukowanie częściowego raportu sprzedaży, drukowanie końcowego raportu sprzedaży, wpłaty na konta odbiorców, wpłaty za zamówienia odbiorców, zdarzenia inspekcji i transakcji niezwiązane ze sprzedażą.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** — to żądanie zwraca odpowiedź z usługi rejestracji fiskalnej. Ta odpowiedź jest serializowana do postaci ciągu, dzięki czemu można ją zapisać.

#### <a name="configuration"></a>Konfiguracja

Pliki konfiguracji znajdują się w folderze **Konfiguracja** projektu rozszerzenia:

- **DocumentProviderFiscalEFRSampleAustria** — do obsługi dokumentów fiskalnych.
- **DocumentProviderNonFiscalEFRSampleAustria** — do obsługi dokumentów niefiskalnych.

Te pliki umożliwiają skonfigurowanie ustawień dostawcy dokumentów z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienie:

- Mapowanie stawek VAT

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Rozszerzenie (łącznik fiskalny) służy do komunikacji z usługą rejestracji fiskalnej.

Rozszerzenie stacji sprzętowej to **HardwareStation.Extension.EFRSample**. Używa ono protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do usługi rejestracji fiskalnej. Obsługuje również odpowiedzi odbierane z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EFRHandler** jest punktem wejściowym obsługi żądań kierowanych do usługi rejestracji fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do usługi rejestracji fiskalnej i zwraca odpowiedź z tej usługi.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania kondycji usługi rejestracji fiskalnej.
- **InitializeFiscalDeviceRequest** — to żądanie służy do inicjowania usługi rejestracji fiskalnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — ilość czasu (w milisekundach), przez który sterownik będzie czekał na odpowiedź z usługi rejestracji fiskalnej.
