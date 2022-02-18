---
title: Wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji (starsza wersja).
description: Ten temat zawiera wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji z poziomu zestawu Retail SDK.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: b8d60f32d986dec6bb26d78ebdfe8cee3a6b688a
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077045"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji (starsza wersja).

[!include [banner](../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące wdrażania przykładu integracji jednostki kontrolnej dla Szwecji z poziomu zestawu Retail software development kit (SDK) na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji dotyczących tego przykładu integracji fiskalnej, zobacz [Przykład integracji jednostki kontrolnej dla Szwecji](emea-swe-fi-sample.md). 

Przykład integracji fiskalnej dla Szwecji jest częścią zestawu Retail SDK. Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK, zobacz [Omówienie zestawu Retail SDK (Software Development Kit)](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ten przykład składa się z rozszerzeń kolekcji Commerce Runtime (CRT), stacji sprzętowej i punktu sprzedaży (POS). Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT, stacji sprzętowej i punktu sprzedaży. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym temacie używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Azure DevOps, w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.

## <a name="development-environment"></a>Środowiska programistyczne

Wykonaj poniższe kroki, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

### <a name="enable-crt-extensions"></a>Włączanie rozszerzeń CRT

Składniki rozszerzenia kolekcji CRT znajdują się w przykładach kolekcji CRT. Aby wykonać poniższe procedury, otwórz rozwiązanie **CommerceRuntimeSamples.sln** w folderze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>Składnik DocumentProvider.CleanCashSample

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.CleanCashSample** i skompiluj go.
2. W folderze **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w Internetowych usługach informacyjnych (IIS).
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Plik konfiguracji rozszerzenia

1. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

2. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Włączanie rozszerzeń stacji sprzętowej

Składniki rozszerzenia stacji sprzętowej wchodzą w skład przykładów stacji sprzętowej. Aby wykonać poniższe procedury, otwórz rozwiązania **HardwareStationSamples.sln** w folderze **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>Składnik CleanCash

1. Znajdź projekt **HardwareStation.Extension.CleanCashSample** i skompiluj go.
2. W folderze **Extension.CleanCashSample\\bin\\Debug** znajdź zestaw plików **Contoso.Commerce.HardwareStation.CleanCashSample.dll** i **Interop.CleanCash\_1\_1.dll**.
3. Skopiuj pliki zestawów do folderu rozszerzeń stacji sprzętowej:

    - **Udostępniona stacja sprzętowa:** skopiuj pliki do folderu **bin** w lokalizacji witryny stacji sprzętowej w usługach IIS.
    - **Dedykowana stacja sprzętowa w aplikacji Modern POS:** skopiuj pliki do lokalizacji brokera klienta aplikacji Modern POS.

4. Znajdź plik konfiguracji rozszerzenia dla rozszerzeń stacji sprzętowej. Ten plik nosi nazwę **HardwareStation.Extension.config**.

    - **Udostępniona stacja sprzętowa:** plik znajduje się w lokalizacji witryny stacji sprzętowej w IIS.
    - **Dedykowana stacja sprzętowa w aplikacji Modern POS:** plik znajduje się w lokalizacji brokera klienta aplikacji Modern POS.

5. Dodaj poniższy wiersz do sekcji **composition** pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Włączanie składników rozszerzenia Modern POS

1. Otwórz rozwiązanie **ModernPOS.sln** w **RetailSdk\\POS**, i upewnij się, że można je skompilować bez błędów. Ponadto upewnij się, że program Modern POS firmy Visual Studio można uruchomić za pomocą polecenia **Uruchom**.

    > [!NOTE]
    > Nie można dostosowywać Modern POS. Należy włączyć funkcję Kontroli konta użytkownika (UAC) i w razie potrzeby odinstalować uprzednio zainstalowane wersje programu Modern POS.

2. Włącz możliwość ładowania rozszerzeń poprzez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
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
2. Włącz możliwość ładowania rozszerzeń poprzez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Aby uzyskać więcej informacji oraz przykładów, które pokazują sposób dołączania folderów kodu źródłowego i włączania ładowania rozszerzeń, zobacz instrukcje w pliku readme.md w projekcie **Pos.Extensions**.

3. Skompiluj ponownie rozwiązanie.
4. Uruchom rozwiązanie, używając polecenia **Uruchom** i wykonaj kroki opisane w podręczniku zestawu Retail SDK.

## <a name="production-environment"></a>Środowisko produkcyjne

Wykonanie poprzedniej procedury powoduje włączenie rozszerzeń, które są składnikami przykładu integracji jednostki kontrolnej. Oprócz tego musisz wykonać te kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki rozwiązania Commerce, oraz zastosować te pakiety w środowisku produkcyjnym.

1. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    - W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujące wiersze w sekcji **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Wprowadź poniższe zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings** w folderze **BuildTools**:

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenia CRT w pakietach, które można wdrożyć.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Dodaj poniższe wiersze, aby dołączyć rozszerzenie stacji sprzętu w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Włącz rozszerzenie programu POS, dodając następujące wiersze w pliku **extensions.json** w folderze **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Uruchom wiersz polecenia MSBuild dla Visual Studio i uruchom **msbuild** w folderze Retail SDK, aby utworzyć pakiety, które można wdrożyć.
5. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Wykonaj wszystkie wymagane zadania konfiguracyjne opisane w artykule [Konfigurowanie integracji z jednostką kontrolną](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Projekt rozszerzeń

### <a name="crt-extension-design"></a>Projekt rozszerzenia kolekcji CRT

Celem rozszerzenia, czyli dostawcy dokumentów fiskalnych, jest generowanie dokumentów specyficznych dla usługi i obsługa odpowiedzi z jednostki kontrolnej.

Rozszerzenie kolekcji CRT to **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Aby uzyskać więcej informacji o projektowaniu rozwiązań integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń i usług fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Program obsługi żądań

Istnieje jeden program obsługi żądań dla dostawcy dokumentów o nazwie **DocumentProviderCleanCash**. Ten program obsługi służy do generowania dokumentów fiskalnych dla jednostki kontrolnej.

Ten program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który powinien zostać zarejestrowany w jednostce kontrolnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie obsługiwane są zdarzenia sprzedaży i zdarzenia inspekcji.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji **DocumentProviderFiscalCleanCashSample** znajduje się w folderze **Configuration** projektu rozszerzenia. Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- Mapowanie kodów VAT

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Celem rozszerzenia, czyli łącznika fiskalnego, jest komunikowanie się z jednostką kontrolną.

Rozszerzenie Hardware Station to **HardwareStation.Extension.CleanCashSample**. Używa ono protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do jednostki kontrolnej. Obsługuje również odpowiedzi odbierane z jednostki kontrolnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **CleanCashHandler** jest punktem wejściowym obsługi żądań kierowanych do jednostki kontrolnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** – to żądanie wysyła dokumenty do jednostki kontrolnej i otrzymuje z niej odpowiedź.
- **IsReadyFiscalDeviceRequest** – to żądanie służy do sprawdzania stanu jednostki kontrolnej.
- **InitializeFiscalDeviceRequest** – to żądanie jest stosowane do inicjowania jednostki kontrolnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Ciąg połączeń** – ustawienia połączenia jednostki kontrolnej.
- **Limit czasu** – ilość czasu w milisekundach, przez który sterownik czeka na odpowiedź z jednostki kontrolnej.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrowanie z wcześniejszej przykładowej integracji

Jeśli do integracji z programem POS jest już używana wcześniejsza [próbka, z jednostkami kontrolnymi dla Szwecji](retail-sdk-control-unit-sample.md), może być konieczne przeprowadzenie migracji z tej wersji do bieżącej. Aby w przyszłości wprowadzić zmiany i otrzymać terminowe aktualizacje funkcji dla Szwecji, konieczne może być uaktualnienie, wprowadzanie pomocniczego kodu i korekt konfiguracji w wbudowanych rozszerzeniach oraz odbudowa rozwiązań. W utworzonej logice rozszerzeń nie są wymagane żadne główne zmiany. Wcześniejsza przykładowa integracja i dostosowania będą nadal działać, jeśli nie zostaną wprowadzone żadne zmiany ze strony użytkownika. W związku z tym można zaplanować, przygotować i wykonać pobieranie dla swojego środowiska.

### <a name="migration-process"></a>Proces migracji

Migracja ze starszego przykładu integracji do bieżącego przykładu integracji jednostek kontrolnych powinna opierać się na koncepcji aktualizacji stopniowej. Innymi słowy, wszystkie składniki centrali Commerce i Commerce Scale Unit powinny być już zaktualizowane przed rozpoczęciem aktualizacji programu POS i składników stacji sprzętowej.

Aby zapobiec sytuacji, w której zdarzenie lub transakcja są podpisane dwukrotnie (to jest podpisane zarówno przez wcześniejsze rozszerzenie, jak i bieżące rozszerzenie), lub jeśli nie można podpisać zdarzenia lub transakcji z powodu brakującej konfiguracji, zaleca się wyłączenie wszystkich urządzeń z programu POS i Hardware station, które korzystają z poprzedniej próbki , a następnie aktualizuj je jednocześnie. Tę jednoczesną aktualizację można wykonać na przykład dla sklepu po sklepie, aktualizując profil funkcji sklepu oraz profil sprzętu stacji sprzętowej.

Proces migracji powinien składać się z następujących kroków.

1. Aktualizowanie składników centrali Commerce.
1. Aktualizuj składniki Commerce Scale Unit i włącz rozszerzenia bieżącego przykładu.
1. Upewnij się, że wszystkie transakcje w trybie offline są synchronizowane z urządzeniami MPOS z włączoną obsługą trybu offline.
1. Wyłącz wszystkie urządzenia, w których są podłączone składniki wcześniejszej próbki.
1. Wykonaj wszystkie wymagane zadania konfiguracyjne opisane w artykule [Konfigurowanie integracji z jednostką kontrolną](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Zaktualizuj składniki programu POS i Hardware station, wyłącz rozszerzenia, które są częściami wcześniejszego przykładu, i włącz rozszerzenia bieżącego przykładu.

    > [!NOTE]
    > W zależności od typu środowiska można znaleźć bardziej techniczne szczegóły dotyczące procesu migracji w sekcji [środowiska developmentowego](#migration-in-a-development-environment) lub w sekcji [środowiska produkcyjnego](#migration-in-a-production-environment) tego tematu.

### <a name="migration-in-a-development-environment"></a>Migracja środowiska projektowego

#### <a name="update-crt"></a>Aktualizacja CRT

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.CleanCashSample** i skompiluj go.
2. W folderze **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **CommerceRuntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalny CRT w Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config**, i znajduje się w folderze **bin\\ext** w lokalizacji brokera klienta lokalnego CRT.

    > [!WARNING]
    > **Nie należy** edytować plików CommerceRuntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

5. Znajdź i usuń wcześniejsze rozszerzenie CRT z pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Nie wykonaj tego kroku, dopóki nie zaktualizujesz wszystkich urządzeń w urządzenia POS, które działają z tą wersją CRT.

6. Zarejestruj bieżący przykład rozszerzenia CRT w pliku konfiguracji rozszerzeń, dodając następujące wiersze.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Aktualizacja stacji sprzętowej

1. Znajdź projekt **HardwareStation.Extension.CleanCashSample** i skompiluj go.
2. W folderze **Extension.CleanCashSample\\bin\\Debug** znajdź zestaw plików **Contoso.Commerce.HardwareStation.CleanCashSample.dll** i **Interop.CleanCash\_1\_1.dll**.
3. Skopiuj pliki zestawów do folderu rozszerzeń stacji sprzętowej:

    - **Udostępniona stacja sprzętowa:** skopiuj pliki do folderu **bin** w lokalizacji witryny stacji sprzętowej w usługach IIS.
    - **Dedykowana stacja sprzętowa w aplikacji Modern POS:** skopiuj pliki do lokalizacji brokera klienta aplikacji Modern POS.

4. Znajdź plik konfiguracji rozszerzenia dla rozszerzenia **HardwareStation.Extension.config**:

    - **Zdalna usługa Hardware Station:** plik znajduje się w lokalizacji IIS witryny Hardware Station.
    - **Lokalna stacja sprzętowa w aplikacji Modern POS:** plik znajduje się w lokalizacji brokera klienta aplikacji Modern POS.

    > [!WARNING]
    > **Nie należy** edytować plików CommerceRuntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

5. Znajdź i usuń wcześniejsze rozszerzenie stacji sprzętowej z pliku konfiguracji rozszerzenia.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 i wcześniejsza wersja](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Wersja 7.3.1 Retail i nowsze](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Wersja 10.0 Retail i nowsze](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Dodaj poniższy wiersz do sekcji **composition** pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Aktualizacja Modern POS

1. Otwórz rozwiązanie **CloudPOS.sln** w **RetailSdk\\POS**.
2. Wyłącz wcześniejsze rozszerzenie programu POS, usuwając poniższe wiersze z pliku **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Włącz aktualny przykład rozszerzenia POS przez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Aktualizacja Cloud POS

1. Otwórz rozwiązanie **ModernPOS.sln** w **RetailSdk\\POS**.
2. Wyłącz wcześniejsze rozszerzenie programu POS, usuwając poniższe wiersze z pliku **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Włącz aktualny przykład rozszerzenia POS przez dodanie następujących wierszy do pliku **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migracja środowiska produkcyjnego

#### <a name="update-crt"></a>Aktualizacja CRT

1. Usuń wcześniejsze rozszerzenie CRT z plików konfiguracji **CommerceRuntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** w folderze **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Nie wykonaj tego kroku, dopóki nie zaktualizujesz wszystkich urządzeń w urządzenia POS, które działają z tą wersją CRT.

2. Włącz aktualny przykład rozszerzeń CRT, dokonując poniższych zmian w plikach konfiguracji **CommerceRuntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** w folderze **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. W pliku konfiguracji dostosowania pakietu **Customization.settings** w folderze **BuildTools** dodaj poniższy wiersz, aby uwzględnić bieżące przykładowe rozszerzenie CRT we wdrażanych pakietach.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Aktualizacja stacji sprzętowej

1. Usuń wcześniejsze rozszerzenie stacji sprzętowej, modyfikując plik konfiguracji **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 i wcześniejsza wersja](#tab/retail-7-3)

    Usuń następującą sekcję z plików konfiguracji **HardwareStation.Shared.config** i **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Wersja 7.3.1 Retail i nowsze](#tab/retail-7-3-1)

    Usuń następującą sekcję z pliku konfiguracji **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Wersja 10.0 Retail i nowsze](#tab/retail-10-0)

    Usuń następującą sekcję z pliku konfiguracji **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Włącz bieżący przykład rozszerzenia stacji sprzętowej, dodając następujący wiersz do sekcji **composition** w pliku konfiguracji **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Wprowadź poniższe zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings** w folderze **BuildTools**:

    - Usuń poniższy wiersz, aby wyłączyć wcześniejsze rozszerzenie stacji sprzętowej w pakietach, które można wdrożyć.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Dodaj poniższe wiersze, aby dołączyć bieżące rozszerzenie stacji sprzętowej w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Aktualizacja Modern POS

1. Otwórz rozwiązanie **CloudPOS.sln** w **RetailSdk\\POS**.
2. Wyłącz wcześniejsze rozszerzenie POS:

    - W pliku **tsconfig.json** dodaj folder **FiscalRegisterSample** do listy wykluczania.
    - Usuń poniższe wiersze z pliku **extensions.json** w folderze **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Włącz bieżące rozszerzenie programu POS, dodając następujące wiersze w pliku **extensions.json** w folderze **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Aktualizacja Cloud POS

1. Otwórz rozwiązanie **ModernPOS.sln** w **RetailSdk\\POS**.
2. Wyłącz wcześniejsze rozszerzenie POS:

    - W pliku **tsconfig.json** dodaj folder **FiscalRegisterSample** do listy wykluczania.
    - Usuń poniższe wiersze z pliku **extensions.json** w folderze **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Włącz bieżące rozszerzenie programu POS, dodając następujące wiersze w pliku **extensions.json** w folderze **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Tworzenie pakietów możliwych do wdrożenia

Uruchom **msbulid** dla całego zestawu Retail SDK, aby utworzyć pakiety do wdrożenia. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Pakiety Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
