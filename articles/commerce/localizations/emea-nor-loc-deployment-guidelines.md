---
ms.openlocfilehash: b17bd56f9f3e4def341658626915adbd7f5aada6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281546"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Przewodniki wdrażania kas fiskalnych w Norwegii (starsze)
---

tytuł: Przewodniki wdrażania kas fiskalnych w Norwegii (starsze) [!include [banner](../includes/banner.md)]
opis: Ten artykuł stanowi podręcznik wdrażania, który pokazuje sposób włączenia lokalizacji Microsoft Dynamics 365 Commerce dla Norwegii.

autor: EvgenyPopovMBS Ten artykuł stanowi podręcznik wdrażania, który pokazuje sposób włączenia lokalizacji Microsoft Dynamics 365 Commerce dla Norwegii. Lokalizacja składa się z kilku rozszerzeń składników rozwiązania Commerce. Te rozszerzenia umożliwiają wykonywanie takich akcji, jak drukowanie niestandardowych pól na paragonach, rejestrowanie dodatkowych zdarzeń inspekcji, transakcji sprzedaży i transakcji płatności w programie punkt sprzedaży (POS), cyfrowe podpisywanie transakcji sprzedaży i drukowanie raportów X i Z w formatach lokalnych. Aby uzyskać więcej informacji o lokalizacji dla Norwegii, zobacz temat [Funkcje kas fiskalnych dla Norwegii](./emea-nor-cash-registers.md).
ms.data: 2021-12-20

ms.topic: article Ten przykład jest częścią zestawu Retail software development kit (SDK). Aby uzyskać informacje dotyczące zestawu SDK, zobacz [Omówienie zestawu Retail software development kit (SDK)](../dev-itpro/retail-sdk/retail-sdk-overview.md).
informacje: użytkownik aplikacji, deweloper, IT Pro

ms.reviewer: v-chgriffin Ten przykład składa się z rozszerzeń kolekcji Commerce runtime (CRT), usługi Retail Server i punktu sprzedaży. Aby uruchomić ten przykład, musisz zmodyfikować i skompilować projekty kolekcji CRT, usługi Retail Server i punktów sprzedaży. Zalecamy, aby w celu wprowadzenia zmian opisanych w tym artykule używać niezmodyfikowanego zestawu Retail SDK. Zalecamy również korzystanie z systemu kontroli źródła, takiego jak usługa Microsoft Visual Studio Online (VOS), w sytuacji, gdy nie zmieniono jeszcze żadnego pliku.
ms.search.region: globalny

ms.author: josaw
> [!NOTE]
ms.search.validFrom: 2018-02-28 W usługach Commerce 10.0.8 i powyższych program Retail Server jest znany jako Commerce Scale Unit. Artykuł dotyczy wielu poprzednich wersji aplikacji, a więc program *Retail Server* jest stosowany w całej tej części.
>
---
> Niektóre kroki procedury opisane w tej części różnią się w zależności od wersji aplikacji Commerce, która jest w użyciu. Aby uzyskać więcej informacji, zobacz [Nowości i zmiany w rozwiązaniu Dynamics 365 Retail](../get-started/whats-new.md).


6. Zaktualizuj plik konfiguracji usługi Retail Server. W pliku **RetailSDK\\Packages\\RetailServer\\Code\\web.config** dodaj poniższe wiersze do sekcji **extensionComposition**.
### <a name="using-certificate-profiles-in-commerce-channels"></a>Korzystanie z profilów certyfikatów w kanałach Commerce


    ``` xml
W wersjach Commerce 10.0.15 i nowszych można używać [zdefiniowanych przez użytkownika profilów certyfikatów sklepów detalicznych](./certificate-profiles-for-retail-stores.md), która obsługuje tryb offline, gdy nie są dostępne centrale Key Vault lub Commerce. Ta funkcja rozszerza funkcję [Zarządzanie kanałami sprzedaży detalicznej](../dev-itpro/manage-secrets.md).
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />

    ```
Aby użyć tej funkcjonalności w rozszerzeniu CRT, należy wykonać następujące kroki.


7. Uruchom **msbulid** dla całego zestawu Retail SDK, aby utworzyć pakiety do wdrożenia.
1. Utwórz nowy projekt rozszerzenia CRT (typ projektu biblioteki klasy C#). Użyj przykładowych szablonów z zestawu Retail software development kit (SDK) (RetailSDK\SampleExtensions\CommerceRuntime).
8. Zastosuj pakiety za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS) lub ręcznie. Aby uzyskać więcej informacji, zobacz [Tworzenie wdrażalnych pakietów](../dev-itpro/retail-sdk/retail-sdk-packaging.md).


2. Dodaj procedurę obsługi niestandardowej dla funkcji CertificateSignatureServiceRequest w projekcie SequentialSignatureRegister.
### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Włączanie podpisu cyfrowego w trybie offline dla aplikacji Modern POS


3. Aby odczytać tajne wywołanie, `GetUserDefinedSecretCertificateServiceRequest` należy użyć konstruktora z parametrem profileId. Spowoduje to uruchomienie funkcji pracy z ustawieniami z profilów certyfikatu. Zgodnie z ustawieniami certyfikat zostanie pobrany z magazynu Azure Key Vault lub magazynu komputera lokalnego.
Aby włączyć podpis cyfrowy w trybie offline dla aplikacji Modern POS, po uaktywnieniu aplikacji Modern POS na nowym urządzeniu należy wykonać następujące kroki.


    ```csharp
1. Sign in to POS.
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
2. On the **Database connection status** page, make sure that the offline database is fully synchronized. When the value of the **Pending downloads** field is **0** (zero), the database is fully synchronized.
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);
3. Sign out of POS.

4. Wait a while for the offline database to be fully synchronized.
    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
5. Sign in to POS.
    ```
6. Na stronie **Stan połączenia z bazą danych** upewnij się, że baza danych w trybie offline jest w pełni zsynchronizowana. Gdy wartość pola **Oczekujące transakcje w bazie danych offline** wynosi **0** (zero), baza danych jest w pełni zsynchronizowana.

7. Uruchom ponownie Modern POS.
4. Po pobraniu certyfikatu kontynuuj podpisywanie danych.



5. Skompilowanie projektu rozszerzenia CRT.
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

6. Skopiuj bibliotekę klas wyjściowych i wklej ją do ...\RetailServer\webroot\bin\Ext do testowania ręcznego.

7. W pliku CommerceRuntime.Ext.config zaktualizuj sekcję kompozycji rozszerzenia, tak aby zawierała informacje o bibliotece niestandardowej.

## <a name="development-environment"></a>Środowiska programistyczne

Zrealizuj poniższą procedurę, aby skonfigurować środowisko projektowe, co umożliwi testowanie i rozszerzanie przykładu.

### <a name="the-crt-extension-components"></a>Komponenty rozszerzenia CRT

Składniki rozszerzenia kolekcji CRT znajdują się w przykładach kolekcji CRT. Aby wykonać poniższe procedury, otwórz rozwiązanie CRT, **CommerceRuntimeSamples.sln**, w obszarze **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>Składnik ReceiptsNorway

1. Znajdź projekt **Runtime.Extensions.ReceiptsNorway** i skompiluj go.
2. Znajdź w folderze **Extensions.ReceiptsNorway\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.ReceiptsNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji Microsoft Internet Information Services (IIS) witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salespaymenttransext-component"></a>Składnik SalesPaymentTransExt

1. Znajdź projekt **Runtime.Extensions.SalesPaymentTransExt** i skompiluj go.
2. Znajdź w folderze **Extensions.SalesPaymentTransExt\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="xzreportsnorway-component"></a>Składnik XZReportsNorway

1. Znajdź projekt **Runtime.Extensions.XZReportsNorway** i skompiluj go.
2. Znajdź w folderze **Extensions.XZReportsNorway\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.XZReportsNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

# <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>Przykładowy składnik RegisterAuditEvent

1. Znajdź projekt **Runtime.Extensions.RegisterAuditEventSample** i skompiluj go.
2. Znajdź w folderze **Extensions.RegisterAuditEventSample\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignature-sample-component"></a>Składnik przykładowy SalesTransactionSignature

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SalesTransactionSignatureSample\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

# <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>Przykładowy składnik RegisterAuditEvent

1. Znajdź projekt **Runtime.Extensions.RegisterAuditEventSample** i skompiluj go.
2. Znajdź w folderze **Extensions.RegisterAuditEventSample\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignature-sample-component"></a>Składnik przykładowy SalesTransactionSignature

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SalesTransactionSignatureSample\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignaturesamplemessages-component"></a>Składnik SalesTransactionSignatureSample.Messages

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureSample.Messages**.
2. W folderze **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>Przykładowy składnik RegisterAuditEvent

1. Znajdź projekt **Runtime.Extensions.RegisterAuditEventSample** i skompiluj go.
2. Znajdź w folderze **Extensions.RegisterAuditEventSample\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignature-sample-component"></a>Składnik przykładowy SalesTransactionSignature

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SalesTransactionSignatureSample\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregistercontracts-component"></a>Składnik SequentialSignatureRegister.Contracts

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. W folderze **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

# <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>Przykładowy składnik RegisterAuditEvent

1. Znajdź projekt **Runtime.Extensions.RegisterAuditEventSample** i skompiluj go.
2. Znajdź w folderze **Extensions.RegisterAuditEventSample\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregister-component"></a>Składnik SequentialSignatureRegister

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SequentialSignatureRegister\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignaturenorway-component"></a>Składnik SalesTransactionSignatureNorway

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. W folderze **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregistercontracts-component"></a>Składnik SequentialSignatureRegister.Contracts

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. W folderze **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

#### <a name="salespaymenttransextnorway-component"></a>Składnik SalesPaymentTransExtNorway

1. Znajdź projekt **Runtime.Extensions.SalesPaymentTransExtNorway** i skompiluj go.
2. Znajdź w folderze **Extensions.SalesPaymentTransExtNorway\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

# <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>Składnik RegisterAuditEventNorway

1. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

2. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregister-component"></a>Składnik SequentialSignatureRegister

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SequentialSignatureRegister\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignaturenorway-component"></a>Składnik SalesTransactionSignatureNorway

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. W folderze **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregistercontracts-component"></a>Składnik SequentialSignatureRegister.Contracts

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. W folderze **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

#### <a name="salespaymenttransextnorway-component"></a>Składnik SalesPaymentTransExtNorway

1. Znajdź projekt **Runtime.Extensions.SalesPaymentTransExtNorway** i skompiluj go.
2. Znajdź w folderze **Extensions.SalesPaymentTransExtNorway\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

# <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>Składnik RegisterAuditEventNorway

1. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

2. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregister-component"></a>Składnik SequentialSignatureRegister

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister**.
2. Zmodyfikuj plik **App.config**, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży.
3. Skompiluj projekt.
4. W folderze **Extension.SequentialSignatureRegister\\bin\\Debug** znajdź następujące pliki:

    - Plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Plik konfiguracji **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Skopiuj pliki do folderu rozszerzenia CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

6. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

7. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="salestransactionsignaturenorway-component"></a>Składnik SalesTransactionSignatureNorway

1. Znajdź projekt **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. W folderze **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

#### <a name="sequentialsignatureregistercontracts-component"></a>Składnik SequentialSignatureRegister.Contracts

1. Znajdź projekt **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. W folderze **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

#### <a name="salespaymenttransextnorway-component"></a>Składnik SalesPaymentTransExtNorway

1. Znajdź projekt **Runtime.Extensions.SalesPaymentTransExtNorway** i skompiluj go.
2. Znajdź w folderze **Extensions.SalesPaymentTransExtNorway\\bin\\Debug** plik zestawu **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń kolekcji CRT:

    - **Retail Server:** skopiuj zestaw do folderu **\\bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** skopiuj zestaw do folderu **\\ext** w lokalizacji brokera lokalnego klienta CRT.

4. Znajdź plik konfiguracji rozszerzenia dla kolekcji CRT:

    - **Retail Server:** plik nosi nazwę **commerceruntime.ext.config**, znajduje się w folderze **bin\\ext** w lokalizacji IIS witryny Retail Server.
    - **Lokalne wystąpienie CRT na Modern POS:** plik nosi nazwę **CommerceRuntime.MPOSOffline.Ext.config** i znajduje się w lokalizacji brokera lokalnego klienta CRT.

5. Zarejestruj zmianę kolekcji CRT w pliku konfiguracji rozszerzenia.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Nie należy** edytować plików commerceruntime.config i CommerceRuntime.MPOSOffline.config. Pliki te nie są przeznaczone do żadnych dostosowań.

---

### <a name="the-retail-server-extension-components"></a>Składniki rozszerzenia usługi Retail Server

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Składnik przykładowy SalesTransactionSignature Retail Server

1. W folderze **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample** znajdź projekt **RetailServer.Extensions.SalesTransactionSignatureSample** i skompiluj go.
2. W folderze **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** znajdź plik zestawu **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Skopiuj plik zestawu do folderu rozszerzeń usługi Retail Server.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    Ten folder jest folderem **\\bin** w lokalizacji witryny IIS usługi Retail Server.

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    Ten folder jest folderem **\\bin** w lokalizacji witryny IIS usługi Retail Server.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Ten folder jest folderem **\\bin\\ext** w lokalizacji witryny IIS usługi Retail Server.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    Ten folder jest folderem **\\bin\\ext** w lokalizacji witryny IIS usługi Retail Server.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    Ten folder jest folderem **\\bin\\ext** w lokalizacji witryny IIS usługi Retail Server.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    Ten folder jest folderem **\\bin\\ext** w lokalizacji witryny IIS usługi Retail Server.

    ---

4. Znajdź plik konfiguracji usługi Retail Server. Plik nosi nazwę **web.config**, i znajduje się w folderze źródłowym w lokalizacji IIS witryny Retail Server.
5. Zarejestruj rozszerzenia usługi Retail Server w sekcji **extensionComposition** pliku konfiguracji.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Zarejestruj zależności rozszerzeń usługi Retail Server.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4/)

    1. Znajdź w folderze **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** następujące pliki:

        - Plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - Plik konfiguracji **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Skopiuj pliki do folderu **\\bin** w lokalizacji witryny IIS usługi Retail Server.
    3. Zarejestruj zmianę CRT w pliku konfiguracji rozszerzenia dla CRT. Plik nosi nazwę **commerceruntime.ext.config**, i znajduje się w folderze **bin** w lokalizacji IIS witryny Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later/)

    1. W folderze **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
    2. Skopiuj plik do folderu **\\bin** w lokalizacji witryny IIS usługi Retail Server.
    3. Zarejestruj zmianę CRT w pliku konfiguracji rozszerzenia dla CRT. Plik nosi nazwę **commerceruntime.ext.config**, i znajduje się w folderze **bin** w lokalizacji IIS witryny Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Nie są wymagane żadne działania.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    > [!NOTE]
    > Nie są wymagane żadne działania.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    > [!NOTE]
    > Nie są wymagane żadne działania.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    > [!NOTE]
    > Nie są wymagane żadne działania.

    ---

### <a name="the-modern-pos-extension-components"></a>Komponenty rozszerzenia Modern POS

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implementowanie kodu serwera proxy dla trybu offline

Ta część odpowiada kontrolerowi usługi Retail Server, ale rozszerza element lokalny CRT, który jest używany, gdy klient nie jest połączony.

1. W pliku **customization.settings** zmień sekcję **@(RetailServerLibraryPathForProxyGeneration)**, tak aby na serwerze proxy był używany nowy zestaw usługi.
2. Implementowanie następujących metod interfejsu w klasie **StoreOperationsManager**. Dla pierwszej iteracji dodaj następujący kod:

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    ---

3. Aby ponownie wygenerować kod serwera proxy, skompiluj folder **Proxy** z wiersza polecenia, używając polecenia **msbuild /t:Rebuild**.
4. Rozwiąż zależności projektu **Proxies.RetailProxy**:

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    Otwórz **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, dodaj projekt **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** do rozwiązania i dodaj odwołanie do projektu **RetailProxy**, aby odwołać się do **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    Otwórz **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, dodaj projekt **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** do rozwiązania i dodaj odwołanie do projektu **RetailProxy**, aby odwołać się do **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    ---

5. Dostosuj następujące metody interfejsu w klasie **StoreOperationsManager**:

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    > [!NOTE]
    > Ten krok nie ma zastosowania do tej wersji.

    ---

6. Zaktualizuj plik **dllhost.exe.config**, aby broker klienta załadował nowy zestaw RetailProxy.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Składnik rozszerzenia serwera proxy Retail (Retail 7.3.1 lub nowsza wersja)

Tę procedurę należy wykonać tylko w przypadku korzystania z programu Retail 7.3.1 i nowszej wersji.

1. W folderze **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample** znajdź projekt **RetailServer.Extensions.SalesTransactionSignatureSample** i skompiluj go.
2. W folderze **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug** znajdź plik zestawu **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Skopiuj plik zestawu do katalogu **\\ext** w lokalizacji brokera lokalnego klienta CRT.
4. Zarejestruj zmianę serwera proxy Retail w pliku konfiguracji rozszerzenia. Plik nosi nazwę **RetailProxy.MPOSOffline.ext.config**, i znajduje się w lokalizacji brokera lokalnego klienta CRT.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Komponenty rozszerzenia nowoczesnego POS

1. Otwórz rozwiązanie w **RetailSdk\\POS\\ModernPOS.sln**, upewnij się, że można je skompilować bez błędów. Ponadto upewnij się, że program Modern POS od firmy Microsoft Visual Studio można uruchomić za pomocą polecenia **Uruchom**.

    > [!NOTE]
    > Nie można dostosowywać Modern POS. Należy włączyć funkcję Kontroli konta użytkownika (UAC) i w razie potrzeby odinstalować uprzednio zainstalowane wersje programu Modern POS.

2. Uwzględnij poniższe istniejące foldery kodu źródłowego w projekcie **Pos.Extensions**.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Włącz skompilowanie rozszerzeń w pliku **tsconfig.json**, usuwając poniższe foldery z listy wykluczeń.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Włącz możliwość ładowania rozszerzeń przez dodanie następujących wierszy do pliku **extensions.json** w odpowiednim miejscu.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Aby uzyskać więcej informacji oraz przykładów, które pokazują sposób dołączania folderów kodu źródłowego i włączania ładowania rozszerzeń, zobacz instrukcje w pliku readme.md w projekcie **Pos.Extensions**.

5. Skompiluj ponownie rozwiązanie.
6. Uruchom program Modern POS w debugerze i sprawdź funkcjonalność.

### <a name="cloud-pos-extension-components"></a>Komponenty rozszerzenia Cloud POS

1. Otwórz rozwiązanie w **RetailSdk\\POS\\CloudPOS.sln**, upewnij się, że można je skompilować bez błędów.
2. Uwzględnij poniższe istniejące foldery kodu źródłowego w projekcie **Pos.Extensions**.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Włącz skompilowanie rozszerzeń w pliku **tsconfig.json**, usuwając poniższe foldery z listy wykluczeń.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Włącz możliwość ładowania rozszerzeń przez dodanie następujących wierszy do pliku **extensions.json** w odpowiednim miejscu.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Aby uzyskać więcej informacji oraz przykładów, które pokazują sposób dołączania folderów kodu źródłowego i włączania ładowania rozszerzeń, zobacz instrukcje w pliku readme.md w projekcie **Pos.Extensions**.

5. Skompiluj ponownie rozwiązanie.
6. Uruchom rozwiązanie, używając polecenia **Uruchom** i wykonaj kroki opisane w podręczniku zestawu Retail SDK.
7. Przetestuj funkcję.

### <a name="set-up-required-parameters-in-headquarters"></a>Konfigurowanie wymaganych parametrów w centrali

Aby uzyskać więcej informacji, patrz [Funkcjonalność kas fiskalnych dla Norwegii](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Środowisko produkcyjne

Wykonaj następujące kroki, aby utworzyć możliwe do wdrożenia pakiety, które zawierają składniki Commerce i aby stosować te pakiety w środowisku produkcyjnym.

1. Wykonaj kroki opisane w sekcji [Składniki rozszerzenia aplikacji Cloud POS](#cloud-pos-extension-components) lub [Składniki rozszerzenia aplikacji Modern POS](#modern-pos-extension-components) znajdujące się wcześniej w tym artykule.
2. Wprowadź następujące zmiany w pliku konfiguracji pakietu w folderze **RetailSdk\\aktywów**:

    1. W plikach konfiguracji **commerceruntime.ext.config** i **CommerceRuntime.MPOSOffline.Ext.config** dodaj następujące wiersze w sekcji **kompozycji**:

        # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Włącz dostosowanie serwera Proxy Commerce:

        # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

        W pliku konfiguracji **dllhost.exe.config** dodaj poniższe wiersze do podsekcji **appSettings** sekcji **konfiguracji**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

        W pliku konfiguracji **dllhost.exe.config** dodaj poniższe wiersze do podsekcji **appSettings** sekcji **konfiguracji**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        W pliku konfiguracji **RetailProxy.MPOSOffline.ext.config** dodaj następujące wiersze w sekcji **kompozycji**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

        W pliku konfiguracji **RetailProxy.MPOSOffline.ext.config** dodaj następujące wiersze w sekcji **kompozycji**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

        W pliku konfiguracji **RetailProxy.MPOSOffline.ext.config** dodaj następujące wiersze w sekcji **kompozycji**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

        W pliku konfiguracji **RetailProxy.MPOSOffline.ext.config** dodaj następujące wiersze w sekcji **kompozycji**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Należy wprowadzić następujące zmiany w pliku konfiguracji dostosowań pakietu **Customization.settings**:

    1. Włącz dostosowanie serwera proxy Retail.

        # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

        Dodaj następujące wiersze do sekcji **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

        Dodaj następujące wiersze do sekcji **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie serwera proxy Retail w pakietach do wdrożenia:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

        Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie serwera proxy Retail w pakietach do wdrożenia:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

        Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie serwera proxy Retail w pakietach do wdrożenia:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

        Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie serwera proxy Retail w pakietach do wdrożenia:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie CRT w pakietach do wdrożenia:

        # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Dodaj poniższe wiersze do sekcji **ItemGroup**, aby dołączyć rozszerzenie usługi Retail Server w pakietach do wdrożenia:

        # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Zmodyfikuj następujące pliki, aby uwzględnić pliki zasobów dla Norwegii w wdrażalnych pakietach:
    - Pakiety\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Pakiety\RetailServer\Sdk.RetailServerSetup.proj
  
  - Dla pliku **Sdk.ModernPos.Shared.csproj** 
    - Dodaj wiersz do sekcji **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > Zamiast <File_name> należy określić nazwę pliku zasobu. To samo dotyczy innych przykładów podanych poniżej.
 
    - Dodaj wiersz do sekcji **Nazwa celu="CopyPackageFiles”**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - Dla pliku **Sdk.RetailServerSetup.proj** 
    - Dodaj wiersz do sekcji **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Dodaj wiersz do sekcji **Nazwa celu="CopyPackageFiles”**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Zmodyfikuj plik konfiguracji certyfikatu, określając odcisk palca, lokalizację sklepu oraz nazwę sklepu dla certyfikatu, który ma być używany do podpisywania transakcji sprzedaży. Skopiuj plik konfiguracji do folderu **Odniesienia**.

    # <a name="application-update-4"></a>[Aktualizacja aplikacji 4](#tab/app-update-4)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, i znajduje się w lokalizacji **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[Aktualizacja aplikacji 5 i nowszej wersji](#tab/app-update-5-and-later)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, i znajduje się w lokalizacji **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, i znajduje się w lokalizacji **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Wersja 7.3.2 Retail i nowsze](#tab/retail-7-3-2)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, i znajduje się w lokalizacji **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Wersja 7.3.5 Retail i nowsze](#tab/retail-7-3-5)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, i znajduje się w lokalizacji **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Wersja 8.1.1 Retail i nowsze](#tab/retail-8-1-1)

    Plik nosi nazwę **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, i znajduje się w lokalizacji **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---
