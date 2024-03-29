---
title: Wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Niemiec (starsza wersja)
description: Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji fiskalnej dla Niemiec z poziomu zestawu Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce Retail.
author: EvgenyPopovMBS
ms.date: 08/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7315b6bb145ccdc5631a558af88de55660ebf877
ms.sourcegitcommit: 0feb5d0b06e04f99903069ff2801577be86b8555
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2022
ms.locfileid: "9313863"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-germany-legacy"></a>Wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Niemiec (starsza wersja)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Musisz postępować zgodnie z wytycznymi z tego artykułu, tylko jeśli używasz wersji Microsoft Dynamics 365 Commerce 10.0.28 lub wcześniejszej. Od wersji Commerce 10.0.29 przykładowa integracja usługi rejestracji obrachunkowej dla Niemiec jest dostępna w zestawie SDK do Commerce w wersji 10.0.29. Aby uzyskać więcej informacji, zajrzyj do [Konfiguracja składników kanału](./emea-deu-fi-sample.md#configure-channel-components).

Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji usługi rejestracji fiskalnej dla Niemiec z poziomu zestawu Software Development Kit (SDK) rozwiązania Dynamics 365 Commerce Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji dotyczących tego przykładu integracji fiskalnej, zobacz [Przykład integracji usługi rejestracji fiskalnej dla Niemiec](emea-deu-fi-sample.md). 

Przykład integracji fiskalnej dla Niemiec jest częścią zestawu Retail SDK. Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK, zobacz [Omówienie zestawu Retail SDK (Software Development Kit)](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ten przykład składa się z rozszerzeń kolekcji Commerce Runtime (CRT) i stacji sprzętowej. Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT i stacji sprzętowej. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym artykule używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Azure DevOps, w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.

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
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Włącz rozszerzenia złącza fiskalnego

Rozszerzenia programu Fiscal Connector można włączać w stacji [sprzętowej](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) lub kasie [punktu sprzedaży](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

#### <a name="enable-hardware-station-extensions"></a>Włączanie rozszerzeń stacji sprzętowej

Składniki rozszerzenia stacji sprzętowej wchodzą w skład przykładów stacji sprzętowej. Aby wykonać poniższe procedury, otwórz rozwiązania **HardwareStationSamples.sln** w folderze **RetailSdk\\SampleExtensions\\HardwareStation**.

##### <a name="efrsample-component"></a>Składnik EFRSample

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

#### <a name="enable-pos-extensions"></a>Włączanie rozszerzeń punktu sprzedaży

Próbka rozszerzenia punktu sprzedaży znajduje się w folderze **src\\FiscalIntegration\\PosFiscalConnectorSample** w [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) repozytorium.

Aby użyć przykładowego rozszerzenia punktu sprzedaży w starszym pakiecie SDK, wykonaj następujące kroki.

1. Skopiuj folder **Pos.Extension** do folderu **Rozszerzenia** programu POS starszego zestawu SDK (na przykład`C:\RetailSDK\src\POS\Extensions`).
1. Zmień nazwę kopii folderu **Pos.Extension** **PosFiscalConnector**.
1. Usuń następujące foldery i pliki z folderu **PosFiscalConnector**:

    - pojemnik
    - DataService
    - devDependencies
    - Biblioteki
    - Obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Otwórz rozwiązanie **CloudPos.sln** lub **ModernPos.sln**.
1. W projekcie **Pos.Extensions** uwzględnij folder **PosFiscalConnector**.
1. Otwórz plik **extensions.json** i dodaj rozszerzenie **PosFiscalConnector**.
1. Zbuduj SDK.

### <a name="production-environment"></a>Środowisko produkcyjne

Wykonanie poprzedniej procedury spowodowało włączenie rozszerzeń, które są składnikami przykładu integracji usługi rejestracji fiskalnej. Oprócz tego musisz wykonać te kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki rozwiązania Commerce, oraz zastosować te pakiety w środowisku produkcyjnym.

1. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    - W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujące wiersze w sekcji **composition**.

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

    - W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujące wiersze w sekcji **composition**.

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

    - Dodaj poniższe wiersze, aby uwzględnić rozszerzenia stacji sprzętowej w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Uruchom wiersz polecenia MSBuild dla Visual Studio i uruchom **msbuild** w folderze Retail SDK, aby utworzyć pakiety, które można wdrożyć.
4. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Wykonaj wszystkie wymagane zadania konfiguracyjne opisane w artykule [Konfigurowanie rozwiązania Commerce dla Niemiec](emea-deu-fi-sample.md#set-up-commerce-for-germany).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji usługi rejestracji fiskalnej dla Niemiec jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md). Aby uzyskać więcej informacji dotyczących projektu rozwiązania integracji fiskalnej, zobacz [Omówienie projektu przykładu integracji fiskalnej](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Rozszerzenie (dostawca dokumentów fiskalnych) służy do generowania dokumentów specyficznych dla usługi oraz obsługi odpowiedzi z usługi rejestracji fiskalnej.

Rozszerzenie kolekcji CRT to **Runtime.Extensions.DocumentProvider.EFRSample**. Aby uzyskać więcej informacji dotyczących projektu rozwiązania integracji fiskalnej, zobacz [Omówienie integracji fiskalnej dla kanałów rozwiązania Commerce](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Program obsługi żądań

Istnieje jeden program obsługi żądań dla dostawcy dokumentów o nazwie **DocumentProviderEFRFiscalDEU**. Ten program obsługi służy do generowania dokumentów fiskalnych dla usługi rejestracji fiskalnej. Jest on dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla usługi, który ma zostać zarejestrowany w usłudze rejestracji fiskalnej.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** — to żądanie zwraca odpowiedź wraz z rozszerzonymi danymi.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracji **DocumentProviderFiscalEFRSampleGermany** znajduje się w folderze **Configuration** projektu rozszerzenia. Ten plik umożliwia skonfigurowanie ustawień dostawcy dokumentów z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

Dodano następujące ustawienia:

- **Mapowanie stawek podatku VAT** — mapowanie wartości procentowych podatku skonfigurowanych dla kodów podatków na wartości atrybutu **TaxG** (grupa podatków) w żądaniach wysyłanych do usługi fiskalnej.
- **Grupa podatków dla kart upominkowych i wpłat** — wartość atrybutu **TaxG** w żądaniach wysyłanych do usługi fiskalnej ustalana na podstawie operacji, które dotyczą kart upominkowych lub wpłat.
- **Mapowanie typów metod płatności** — mapowanie metod płatności na wartości atrybutu **PayG** (grupa płatności) w żądaniach wysyłanych do usługi fiskalnej.
- **Grupa podatków dla zwolnienia z podatku VAT** — wartość atrybutu **TaxG** w żądaniach wysyłanych do usługi fiskalnej ustalana na podstawie operacji objętych zwolnieniem ze zobowiązań podatkowych.
- **Uwzględnij dane odbiorcy** — jeśli ten parametr jest włączony, żądania kierowane do usługi fiskalnej będą zawierać informacje dotyczące odbiorcy, takie jak nazwy i adresy, w sytuacjach, gdy odbiorca zostanie dodany do transakcji.

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Rozszerzenie (łącznik fiskalny) służy do komunikacji z usługą rejestracji fiskalnej.

Rozszerzenie stacji sprzętowej to **HardwareStation.Extension.EFRSample**. Używa ono protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do usługi rejestracji fiskalnej. Obsługuje również odpowiedzi odbierane z usługi rejestracji fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EFRHandler** jest punktem wejściowym obsługi żądań kierowanych do usługi rejestracji fiskalnej. Ten program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do usługi rejestracji fiskalnej i zwraca odpowiedź z tej usługi.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania kondycji usługi rejestracji fiskalnej.
- **InitializeFiscalDeviceRequest** — to żądanie służy do inicjowania usługi rejestracji fiskalnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej.

Dodano następujące ustawienia:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — ilość czasu (w milisekundach), przez który sterownik będzie czekał na odpowiedź z usługi rejestracji fiskalnej.
- **Pokaż powiadomienia rejestracji fiskalnej** — jeśli ten parametr będzie włączony, powiadomienia z usługi fiskalnej będą wyświetlane w punkcie sprzedaży jako komunikaty użytkownika.

### <a name="pos-fiscal-connector-extension-design"></a>Projekt przedłużenia złącza fiskalnego POS

Rozszerzenie konektor fiskalny POS służy do komunikacji z usługą rejestracji fiskalnej z POS. Używa protokołu HTTPS do komunikacji.

#### <a name="fiscal-connector-factory"></a>Fabryka łącznika fiskalnego

Fabryka łącznika fiskalnego mapuje nazwę łącznika na implementację łącznika fiskalnego i znajduje się w pliku **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. Nazwa łącznika powinna być zgodna z nazwą łącznika fiskalnego określoną w centrali handlowej.

#### <a name="efr-fiscal-connector"></a>Łącznik fiskalny EFR

Łącznik obrachunkowy CSV znajduje się w pliku **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Implementuje on interfejs **IFiscalConnector** obsługujący następujące żądania:

- **FiscalRegisterSubmitDocumentClientRequest** — to żądanie wysyła dokumenty do usługi rejestracji fiskalnej i zwraca odpowiedź z tej usługi.
- **FiscalRegisterIsReadyClientRequest** — to żądanie służy do sprawdzania kondycji usługi rejestracji fiskalnej.
- **FiscalRegisterInitializeClientRequest** — to żądanie służy do inicjowania usługi rejestracji fiskalnej.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** w [Rozwiązania Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) repozytorium. Ten plik umożliwia skonfigurowanie ustawień łącznika fiskalnego z poziomu centrali rozwiązania Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Adres punktu końcowego** — adres URL usługi rejestracji fiskalnej.
- **Limit czasu** — Czas w milisekundach, przez który łącznik będzie czekał na odpowiedź z usługi rejestracji fiskalnej.
