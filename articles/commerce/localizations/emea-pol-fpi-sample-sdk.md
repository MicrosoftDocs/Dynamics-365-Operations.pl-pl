---
title: Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski (starsza wersja)
description: Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski z poziomu Retail Software Development Kit (SDK) rozwiązania Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 178301e6d8e5f87376ed893e4bf5f966260cad62
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336722"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski (starsza wersja)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Należy postępować zgodnie z wytycznymi z tego artykułu, tylko jeśli używasz wersji Microsoft Dynamics 365 Commerce 10.0.28 lub wcześniejszej. Od wersji Commerce 10.0.19 przykład integracji drukarki fiskalnej dla Polski jest dostępny w zestawie SDK do Commerce. Aby uzyskać więcej informacji, zajrzyj do [Konfiguracja składników kanału](./emea-pol-fpi-sample.md#configure-channel-components).

Ten artykuł zawiera wskazówki dotyczące wdrażania przykładu integracji drukarki fiskalnej dla Polski z poziomu zestawu Software Development Kit (SDK) do Retail Dynamics 365 Commerce na maszynie wirtualnej dewelopera w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji dotyczących tego przykładu integracji fiskalnej, zobacz [Przykład integracji drukarki fiskalnej dla Polski](emea-pol-fpi-sample.md). 

Przykład integracji fiskalnej dla Polski jest częścią zestawu Retail SDK. Aby uzyskać informacje dotyczące instalowania i używania zestawu SDK, zobacz [Omówienie zestawu Retail SDK (Software Development Kit)](../dev-itpro/retail-sdk/retail-sdk-overview.md). Ten przykład składa się z rozszerzeń kolekcji Commerce Runtime (CRT) i stacji sprzętowej. Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT i stacji sprzętowej. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym artykule używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Azure DevOps, w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.

## <a name="development-environment"></a>Środowiska programistyczne

Wykonaj poniższe kroki, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

### <a name="commerce-runtime-extension-components"></a>Komponentu rozszerzenia środowiska uruchomieniowego Commerce

Komponenty rozszerzenia CRT znajdują się w zestawie Retail SDK. Aby wykonać poniższe procedury, otwórz rozwiązanie **CommerceRuntimeSamples.sln** w folderze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Znajdź projekt **Runtime.Extensions.DocumentProvider.PosnetSample** i zbuduj go.
2. W folderze **Extensions.DocumentProvider.PosnetSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzenia CRT:

    - **Commerce Scale Unit:** skopiuj plik do folderu **\\bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w Internetowych usługach informacyjnych (IIS).
    - **Lokalna kolekcja CRT w aplikacji Modern POS:** skopiuj plik do folderu **\\ext** w lokalizacji brokera klienta lokalnej kolekcji CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Commerce Scale Unit:** plik nosi nazwę **commerceruntime.ext.config** i znajduje się w folderze **bin\\ext** w lokalizacji witryny rozwiązania Commerce Scale Unit w usługach IIS.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Uruchom ponownie usługę Commerce:

    - **Commerce Scale Unit:** Uruchom ponownie oddział usługi Commerce Service w Menedżerze IIS.
    - **Broker klienta:** zakończ proces **dllhost.exe** w Menedżerze zadań, a następnie uruchom Modern POS.

### <a name="hardware-station-extension-components"></a>Komponenty rozszerzenia Hardware Station

Komponenty rozszerzenia Hardware Station znajdują się w zestawie SDK modułu Retail. Aby wykonać poniższe procedury, otwórz rozwiązania **HardwareStationSamples.sln** w folderze **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Znajdź projekt **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** i skompiluj go.
2. W folderze **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Skopiuj plik zestawu do wdrożonego komputera Hardware Station:

    - **Zdalna usługa Hardware Station:** skopiuj plik do folderu **bin** w lokalizacji IIS witryny Hardware Station. Skopiuj biblioteki sterownika drukarki (**libposcmbth.dll**, **libcmbth\_serial.dll** oraz **cmbth\_pl.lng**).

4. Znajdź plik konfiguracji dla rozszerzeń Hardware Station. Plik nosi nazwę **HardwareStation.Extension.config**:

    - **Zdalna usługa Hardware Station:** plik znajduje się w lokalizacji IIS witryny Hardware Station.

5. Dodaj poniższy wiersz do sekcji **composition** pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Uruchom ponownie usługę Hardware Station:

    - **Zdalna usługa Hardware Station:** uruchom ponownie Hardware Station z Menedżera IIS.

## <a name="production-environment"></a>Środowisko produkcyjne

Wykonanie poprzedniej procedury spowodowało włączenie rozszerzeń, które są składnikami przykładu integracji usługi rejestracji fiskalnej. Oprócz tego musisz wykonać te kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki rozwiązania Commerce, oraz zastosować te pakiety w środowisku produkcyjnym.

1. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    - W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - W pliku konfiguracji **HardwareStation.Extension.config** dodaj następujący wiersz w sekcji **kompozycja**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Wprowadź poniższe zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings** w folderze **BuildTools**:

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenie CRT w pakietach, które można wdrożyć.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Dodaj poniższy wiersz, aby dołączyć rozszerzenie stacji sprzętu w pakietach, które można wdrożyć.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Uruchom wiersz polecenia MSBuild dla Visual Studio i uruchom **msbuild** w folderze Retail SDK, aby utworzyć pakiety, które można wdrożyć.
1. Zastosuj pakiety za pośrednictwem usługi LCS lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Projekt rozszerzenia

Przykład integracji drukarki fiskalnej dla Polski jest oparty na [funkcjonalności integracji fiskalnej](fiscal-integration-for-retail-channel.md). Aby uzyskać więcej informacji dotyczących projektu rozwiązania integracji fiskalnej, zobacz [Omówienie projektu przykładu integracji fiskalnej](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Projekt rozszerzenia środowiska uruchomieniowego Commerce

Celem rozszerzenia (dostawcy dokumentów fiskalnych) jest generowanie dokumentów specyficznych dla drukarki i obsługa odpowiedzi z drukarki fiskalnej.

Rozszerzenie kolekcji CRT to **Runtime.Extensions.DocumentProvider.PosnetSample**. To rozszerzenie generuje zestaw poleceń specyficznych dla drukarki, które są definiowane przez specyfikację POSNET 19-3678 w formacie JavaScript Object Notation (JSON).

Aby uzyskać więcej informacji o projektowaniu rozwiązań integracji fiskalnej, zobacz [Proces rejestracji fiskalnej i przykładowe integracje fiskalne dla urządzeń i usług fiskalnych](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **DocumentProviderPosnetProtocol** jest punktem wejścia dla żądania generowania dokumentów z drukarki fiskalnej.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą dostawcy dokumentów łącznika określoną w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **GetFiscalDocumentDocumentProviderRequest** – to żądanie zawiera informacje dotyczące dokumentu, który ma być generowany. Zwraca dokument specyficzny dla drukarki, który powinien zostać zarejestrowany w drukarce fiskalnej.
- **GetSupportedRegistrableEventsDocumentProviderRequest** — to zapytanie zwraca listę zdarzeń do subskrybowania. Obecnie są obsługiwane następujące zdarzenia: sprzedaż, drukowanie raportu X i drukowanie końcowego raportu sprzedaży.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień dostawcy dokumentu z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- Mapowanie stawek VAT
- Mapowanie typów metod płatności
- Typ płatności wpłaty

### <a name="hardware-station-extension-design"></a>Projekt rozszerzenia Hardware Station

Zastosowaniem rozszerzenia (łącznika fiskalnego) jest do komunikowanie się z drukarką fiskalną.

Rozszerzenie Hardware Station to **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. To rozszerzenie przesyła polecenia, które rozszerzenie CRT generuje na drukarce fiskalnej, przez wywołanie funkcji POSNET sterownika dostarczonego przez producenta. Obsługuje również błędy urządzenia.

#### <a name="request-handler"></a>Program obsługi żądań

Program obsługi żądań **FiscalPrinterHandler** jest punktem wejściowym dla obsługi żądania przez fiskalne urządzenie peryferyjne.

Program obsługi jest dziedziczony z interfejsu **INamedRequestHandler**. Metoda **HandlerName** odpowiada za zwrócenie nazwa programu obsługi. Nazwa programu obsługi musi być zgodna z nazwą łącznika fiskalnego określonego w centrali rozwiązania Commerce.

Łącznik obsługuje następujące żądania:

- **SubmitDocumentFiscalDeviceRequest** — to żądanie wysyła dokumenty do drukarek i zwraca odpowiedzi z drukarki fiskalnej.
- **IsReadyFiscalDeviceRequest** — to żądanie służy do sprawdzania stanu urządzenia.
- **InitializeFiscalDeviceRequest** — to żądanie jest używane do inicjowania drukarki.

#### <a name="configuration"></a>Konfiguracja

Plik konfiguracyjny znajduje się w folderze **Konfiguracja** projektu rozszerzenia. Ten plik służy do obsługi konfiguracji ustawień łącznika z centrali Commerce. Format pliku jest zgodny z wymaganiami konfiguracji integracji fiskalnej. Dodano następujące ustawienia:

- **Ciąg połączenia** – ciąg opisuje szczegóły połączenia z urządzeniem w formacie obsługiwanym przez sterownik urządzenia. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją sterownika POSNET.
- **Data i godzina synchronizacji** – wartość określająca, czy należy zsynchronizować datę i godzinę drukarki ze stacją połączoną Hardware Station.
- **Limit czasu urządzenia** — ilość czasu, w milisekundach, przez który sterownik czeka na odpowiedź z urządzenia. Aby uzyskać więcej informacji, zapoznaj się z dokumentacją sterownika POSNET.
