---
title: Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch (starsza wersja)
description: Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch z poziomu zestawu Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce Retail.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 9e951c1a1ee5c967d2bd67941ff3d19c62b59ba6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279547"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch (starsza wersja)

[!include[banner](../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Włoch z poziomu zestawu Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce Retail na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji dotyczących tego przykładu integracji fiskalnej, zobacz [Przykład integracji drukarki fiskalnej dla Włoch](emea-ita-fpi-sample.md). 

Przykład integracji fiskalnej dla Włoch jest częścią zestawu Retail SDK. Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK, zobacz [Omówienie zestawu Retail SDK (Software Development Kit)](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ten przykład składa się z rozszerzeń kolekcji Commerce Runtime (CRT) i stacji sprzętowej. Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT i stacji sprzętowej. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym artykule używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Azure DevOps, w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.

## <a name="development-environment"></a>Środowiska programistyczne

Wykonaj poniższe kroki, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

### <a name="commerce-runtime-extension-components"></a>Komponentu rozszerzenia środowiska uruchomieniowego Commerce

Komponenty rozszerzenia CRT znajdują się w zestawie Retail SDK. Aby wykonać poniższe procedury, otwórz rozwiązanie **CommerceRuntimeSamples.sln** w folderze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** i skompiluj go.
2. W folderze **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w Internetowych usługach informacyjnych (IIS).
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. Uruchom ponownie rozwiązanie Commerce Scale Unit:

    - **Commerce Scale Unit:** uruchom ponownie witrynę rozwiązania Commerce Scale Unit w Menedżerze usług IIS.
    - **Broker klienta:** zakończ proces **dllhost.exe** w Menedżerze zadań, a następnie uruchom Modern POS.

### <a name="hardware-station-extension-components"></a>Komponenty rozszerzenia Hardware Station

Komponenty rozszerzenia Hardware Station znajdują się w zestawie SDK modułu Retail. Aby wykonać poniższe procedury, otwórz rozwiązania **HardwareStationSamples.sln** w folderze **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Znajdź projekt **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** i skompiluj go.
2. W folderze **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Skopiuj plik zestawu do wdrożonego komputera Hardware Station:

    - **Zdalna usługa Hardware Station:** skopiuj plik do folderu **bin** w lokalizacji IIS witryny Hardware Station.
    - **Lokalna stacja sprzętowa:** skopiuj plik do lokalizacji brokera klienta programu Modern POS.

4. Znajdź plik konfiguracji dla rozszerzeń Hardware Station. Plik nosi nazwę **HardwareStation.Extension.config**:

    - **Zdalna usługa Hardware Station:** plik znajduje się w lokalizacji IIS witryny Hardware Station.
    - **Lokalna stacja sprzętowa:** plik znajduje się w lokalizacji brokera klienta aplikację Modern POS.

5. Dodaj następującą sekcję do sekcji **composition** w pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Uruchom ponownie usługę Hardware Station:

    - **Zdalna usługa Hardware Station:** uruchom ponownie Hardware Station z Menedżera IIS.
    - **Lokalna stacja sprzętowa:** zakończ proces **dllhost.exe** w Menedżerze zadań, a następnie uruchom ponownie aplikację Modern POS.

## <a name="production-environment"></a>Środowisko produkcyjne

Aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki rozwiązania Commerce, i zastosować te pakiety w środowisku produkcyjnym, wykonaj poniższe kroki.

1. Wykonaj kroki opisane w sekcji [Środowisko projektowe](#development-environment) wcześniej w tym artykule.
2. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    1. W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    1. W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Wprowadź poniższe zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings** w folderze **BuildTools**:

    1. Dodaj poniższy wiersz, aby dołączyć rozszerzenie CRT w pakietach, które można wdrożyć.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    1. Dodaj poniższy wiersz, aby dołączyć rozszerzenie stacji sprzętu w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Wprowadź następujące zmiany w pliku **Sdk.ModernPos.Shared.csproj** w folderze **Packages\_SharedPackagingProjectComponents**, aby uwzględnić pliki zasobów dla Włoch w pakietach do wdrożenia:

    1. Dodaj sekcję **ItemGroup** zawierającą węzły, które wskazują na pliki zasobów dla żądanych tłumaczeń. Upewnij się, że określono poprawne obszary nazw i przykładowe nazwy. Poniższy przykład dodaje węzły zasobów dla lokalizacji **it** i **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. W sekcji **Nazwa celu=CopyPackageFiles** dodaj jeden wiersz dla każdej lokalizacji lokalnej, tak jak pokazano w poniższym przykładzie.

        ```xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it-CH" SkipUnchangedFiles="true" />
        ```

5. Wprowadź następujące zmiany w pliku **Sdk.RetailServerSetup.proj** w folderze **Packages\_SharedPackagingProjectComponents**, aby uwzględnić pliki zasobów dla Włoch w pakietach do wdrożenia:

    1. Dodaj sekcję **ItemGroup** zawierającą węzły, które wskazują na pliki zasobów dla żądanych tłumaczeń. Upewnij się, że określono poprawne obszary nazw i przykładowe nazwy. Poniższy przykład dodaje węzły zasobów dla lokalizacji **it** i **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. W sekcji **Nazwa celu=CopyPackageFiles** dodaj jeden wiersz dla każdej lokalizacji lokalnej, tak jak pokazano w poniższym przykładzie.

        ``` xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it-CH" SkipUnchangedFiles="true" />
        ```

6. Uruchom narzędzie Wiersz polecenia programu MSBuild dla programu Visual Studio, a następnie uruchom polecenie **msbuild** w folderze zestawu Retail SDK, aby utworzyć pakiety, które można wdrożyć.
7. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Celem rozszerzenia (dostawcy dokumentów fiskalnych) jest generowanie dokumentów specyficznych dla drukarki i obsługa odpowiedzi z drukarki fiskalnej.

Rozszerzenie kolekcji CRT to **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Aby uzyskać więcej informacji o projektowaniu rozwiązań integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń i usług fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **DocumentProviderEpsonFP90III** jest punktem wejścia dla żądania generowania dokumentów z drukarki fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla drukarki, który powinien zostać zarejestrowany w drukarce fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie są obsługiwane następujące zdarzenia: sprzedaż, drukowanie raportu X i drukowanie końcowego raportu sprzedaży.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień dostawcy dokumentu z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- Mapowanie kodów VAT
- Mapowanie stawek VAT
- Mapowanie typów metod płatności
- Typ kodu kreskowego dla numeru paragonu
- Typ płatności wpłaty

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Zastosowaniem rozszerzenia (łącznika fiskalnego) jest do komunikowanie się z drukarką fiskalną.

Rozszerzenie stacji sprzętowej to **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. To rozszerzenie używa protokołu HTTP w celu przesyłania dokumentów generowanych przez rozszerzenie kolekcji CRT do drukarki fiskalnej. Obsługuje również odpowiedzi odbierane z drukarki fiskalnej.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **EpsonFP90IIISample** jest punktem wejściowym obsługi żądań kierowanych do fiskalnego urządzenia peryferyjnego.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do drukarek i zwraca odpowiedzi z drukarki fiskalnej.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania stanu urządzenia.
- **InitializeFiscalDeviceRequest** — to żądanie jest używane do inicjowania drukarki.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień łącznika z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Adres punktu końcowego** — adres URL drukarki.
- **Data i godzina synchronizacji** – wartość określająca, czy należy zsynchronizować datę i godzinę drukarki ze stacją połączoną Hardware Station.
