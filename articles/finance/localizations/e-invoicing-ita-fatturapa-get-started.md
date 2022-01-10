---
title: Konfigurowanie bezpośredniej integracji funkcji Włoska faktura FatturaPA z usługą SDI
description: Ten temat zawiera informacje ułatwiające rozpoczynanie pracy z fakturowaniem elektronicznym dla Włoch i skonfigurowanie bezpośredniej integracji funkcji Włoska faktura FatturaPA z systemem Exchange (usługa SDI).
author: abaryshnikov
ms.date: 12/14/2021
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 0ccc9f04e42e748b4531622a1c90559d4ca17196
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2021
ms.locfileid: "7922454"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Konfigurowanie bezpośredniej integracji funkcji Włoska faktura FatturaPA z usługą SDI

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Faktury elektroniczne dla Włoch może obecnie nie obsługiwać wszystkich funkcji dostępnych dla faktur elektronicznych w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z funkcją Fakturowanie elektroniczne dla Włoch w rozwiązaniach Finance i Supply Chain Management. Ten artykuł przeprowadzi Cię przez kolejne kroki konfiguracji, które są zależne od kraju/regionu, w usługach Regulatory Configuration Services (RCS). Te kroki uzupełniają kroki opisane w artykule [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem kroków opisanych w tym temacie musisz spełnić następujące wymagania wstępne:

- Wykonaj kroki opisane w artykule [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md).
- Zaimportuj funkcję fakturowania elektronicznego **Włoska faktura FatturaPA** do usług RCS z repozytorium globalnego. Aby uzyskać więcej informacji, zobacz sekcję [Importowanie funkcji fakturowania elektronicznego z dostawcy konfiguracji firmy Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) we wspomnianym wcześniej temacie „Rozpoczynanie pracy z fakturowaniem elektronicznym”.
- Dodaj linki z wymaganych certyfikatów do środowiska usług. Wymagane certyfikaty to certyfikat podpisu cyfrowego, certyfikat urzędu certyfikacji (CA) i certyfikat klientów. Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie wpisu tajnego certyfikatu cyfrowego](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) w temacie „Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami”.

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja funkcji fakturowania elektronicznego Włoska FatturaPA (IT)

Przed wdrożeniem konfiguracji aplikacji w połączonej aplikacji Finance lub Supply Chain Management wykonaj poniższe procedury.

Ta sekcja stanowi uzupełnienie sekcji [Specyficzna dla kraju konfiguracja aplikacji](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) w temacie „Rozpoczynanie pracy z fakturowaniem elektronicznym”.

### <a name="create-a-new-feature"></a>Tworzenie nowej funkcji

1. Zaloguj się w RCS.
2. W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** oznacz dostawcę konfiguracji swojej firmy jako aktywnego.
3. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
4. Na stronie **Funkcje fakturowania elektronicznego** wybierz kolejno pozycje **Dodaj** \> **Na podstawie istniejącej funkcji**.
5. W obszarze **Dostawca konfiguracji firmy Microsoft** wybierz pozycję **Włoska faktura FatturaPA (IT)** jako funkcję podstawową, wprowadź nazwę, a następnie wybierz pozycję **Utwórz funkcję**.

### <a name="set-up-application-specific-parameters"></a>Konfigurowanie parametrów specyficznych dla aplikacji

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz funkcję do edycji.
2. Na karcie **Wersje** sprawdź, czy jest wybrana **Wersja robocza**.
3. Na karcie **Konfiguracje** wybierz konfigurację, a następnie wybierz pozycję **Parametry specyficzne dla aplikacji**.
4. Upewnij się, że w sekcji **Wyszukiwania** jest zaznaczone wyszukiwanie **Lista podkategorii opłat zwrotnych Natura**.
5. W sekcji **Warunki** wybierz pozycję **Dodaj**.
6. Dodaj określone warunki dla każdej podkategorii zdefiniowanej w systemie, a następnie zapisz zmiany.

    > [!NOTE]
    > W kolumnie **Nazwa** możesz wybrać wartość symbolu zastępczego **\*Pusta\*** lub **\*Niepusta\*** zamiast określonej wartości.

### <a name="configure-a-processing-pipeline-for-export"></a>Konfigurowanie potoku przetwarzania na potrzeby eksportu

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz funkcję do edycji.
2. Na karcie **Ustawienia** wybierz pozycję **Faktury sprzedaży**, a następnie wybierz pozycję **Edytuj**.
3. W sekcji **Potok przetwarzania** przejdź przez akcje i ustaw wszystkie wymagane pola:

    - Dla akcji **Podpisz dokument** w polu **Nazwa certyfikatu** określ wartość Certyfikat podpisu cyfrowego.
    - Dla akcji **Prześlij** ustaw wartości pól **Adres URL** i **Certyfikaty**. Wartość pola **Certyfikaty** to łańcuch certyfikatów, z których pierwszy to certyfikat głównego urzędu certyfikacji (caentrate.cer), a drugi to certyfikat klientów.

4. Wybierz pozycję **Weryfikuj**, aby upewnić się, że wszystkie wymagane pola zostały ustawione.
5. Zapisz zmiany i zamknij stronę.
6. Na karcie **Ustawienia** wybierz pozycję **Faktury projektu**, a następnie wybierz pozycję **Edytuj**.
7. Powtórz kroki od 3 do 5 w odniesieniu do faktur projektu.

### <a name="configure-the-processing-pipeline-for-import"></a>Konfigurowanie potoku przetwarzania na potrzeby importu

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz funkcję do edycji.
2. Na karcie **Ustawienia** wybierz pozycję **Importuj faktury**, a następnie wybierz pozycję **Edytuj**.
3. W sekcji **Kanał danych** na karcie **Parametry** w polu **Kanał danych** wprowadź wartość typu ciąg.
4. Na karcie **Reguły stosowania** ustaw pola konfiguracji. Możesz użyć domyślnej klauzuli **Kanał**, przekazując wartość ustawioną w polu **Kanał danych** w poprzednim kroku do pola **Wartość**.

    ![Konfigurowanie reguł stosowania.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Wybierz pozycję **Weryfikuj**, aby upewnić się, że wszystkie wymagane pola zostały ustawione.

### <a name="deploy-the-feature"></a>Wdrażanie funkcji

1. Zakończ tworzenie funkcji, opublikuj ją i wdróż ją w środowisku usług. Aby uzyskać więcej informacji, zobacz sekcję [Wdrażanie funkcji fakturowania elektronicznego w środowisku usług](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) we wspomnianym wcześniej temacie „Rozpoczynanie pracy z fakturowaniem elektronicznym”.
2. Wdróż funkcję w połączonej aplikacji. Aby uzyskać więcej informacji, zobacz sekcję [Wdrażanie funkcji fakturowania elektronicznego w połączonej aplikacji](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) we wspomnianym wcześniej temacie „Rozpoczynanie pracy z fakturowaniem elektronicznym”.

### <a name="set-up-finance"></a>Konfigurowanie rozwiązania Finance

1. Zaloguj się do swojego środowiska rozwiązania Finance.
2. W module **Powiązane odnośniki**, w obszarze roboczym **Dostawcy konfiguracji** wybierz kafelek **Microsoft**.
3. Wybierz kolejno pozycje **Repozytoria** \> **Globalne** \> **Otwórz**.
4. Wybierz i zaimportuj konfiguracje **Model kontekstu faktury dla odbiorcy** i **Import faktury od dostawcy (IT)**.
5. Przejdź do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**.
6. Na karcie **Funkcje** znajdź i zaznacz funkcję **Włoska faktura elektroniczna**, a następnie zaznacz pole wyboru **Włącz**.
7. Na karcie **Dokument elektroniczny** upewnij się, że wartości pól **Arkusz faktur dla odbiorcy** i **Faktura projektu** są ustawione zgodnie z informacjami podanymi w temacie [Konfigurowanie ustawień aplikacji](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Konfigurowanie importu faktur od dostawców 

1. W rozwiązaniu Finance w obszarze roboczym **Raportowanie elektroniczne** w sekcji **Dostawcy konfiguracji** oznacz dostawcę konfiguracji swojej firmy jako aktywnego.
2. Wybierz **Raportowanie konfiguracji**.
3. Wybierz pozycję **Model kontekstu faktury dla odbiorcy**, a następnie wybierz pozycję **Utwórz konfigurację**.
4. Wybierz pozycję **Utwórz pochodne z nazwy: Kontekst faktury dla odbiorcy, Microsoft**, aby utworzyć konfigurację pochodną.
5. W obszarze **Wersja robocza** wybierz pozycję **Projektant**.
6. W drzewie **Model danych** wybierz pozycję **Mapuj model na źródło danych**.
7. W drzewie **Definicje** wybierz pozycję **DataChannel**, a następnie wybierz pozycję **Projektant**.
8. W drzewie **Źródła danych** rozwiń kontener **\$Context\_Channel**.
9. W polu **Wartość** wybierz pozycję **Edytuj**. 
10. Wprowadź nazwę kanału danych. Nazwa może zawierać maksymalnie 10 znaków. Musi być ona zgodna z wartością parametru **Kanał danych** kanału danych dla funkcji fakturowania elektronicznego w usługach RCS.
11. Zapisz zmiany, a następnie wybierz kolejno pozycje **Konfiguracje raportowania** \> **Zakończ wersję konfiguracji**.
12. Na karcie **Kanały zewnętrzne** w sekcji **Kanały** wybierz pozycję **Dodaj**.
13. W polu **Kanał** wprowadź wartość **\$Kanał kontekstu**.
14. Wprowadź wartości w polach **Opis** i **Firma**.
15. W polu **Kontekst dokumentu** wybierz nową konfigurację, będącą konfiguracją pochodną konfiguracji **Model kontekstu faktury dla odbiorcy**. Opis mapowania powinien brzmieć **Kontekst kanału danych**.
16. Na karcie **Źródła importu** wybierz pozycję **Dodaj**, a następnie ustaw następujące wartości:

    - **Nazwa:** OutputFile
    - **Nazwa jednostki danych:** nagłówek faktury od dostawcy (**jednostka danych:** VendorInvoiceHeaderEntity)
    - **Mapowanie modelu:** import faktur od dostawców (IT)

> [!NOTE]
> Jeśli importujesz faktury od dostawców z różnych źródeł, możesz utworzyć kilka kanałów zewnętrznych oraz kilka konfiguracji pochodnych mających różne wartości **\$Kanał kontekstu**. Na przykład możesz importować faktury od dostawców dla różnych osób prawnych.

## <a name="proxy-server-setup"></a>Ustawienia serwera proxy

Ta sekcja zawiera informacje ułatwiające instalowanie i konfigurowanie usługi serwera proxy służącej do obsługi komunikacji między systemem Exchange (usługa SDI) a usługą fakturowania elektronicznego.

### <a name="create-an-app-registration"></a>Tworzenie rejestracji aplikacji

1. Użyj poniższego skryptu programu Windows PowerShell, aby utworzyć certyfikat z podpisem własnym na potrzeby uwierzytelniania usługa-usługa (S2S).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Zapisz plik PFX certyfikatu w magazynie kluczy, a następnie usuń jego kopię lokalną.
3. Zaloguj się do portalu [Azure Portal](https://portal.azure.com) jako administrator.
4. Utwórz rejestrację aplikacji dla usługi serwera proxy usługi SDI.

    1. Przejdź do obszaru **Rejestracje aplikacji**, utwórz rejestrację, a następnie ustaw dla niej następujące wartości:

        - **Nazwa:** Klient serwera proxy usługi SDI
        - **Obsługiwane typy kont:** tylko konta w tym katalogu organizacyjnym (jedna dzierżawa)

    2. Wybierz pozycję **Zarejestruj**, a następnie wybierz właśnie utworzoną rejestrację aplikacji.
    3. Przejdź do obszaru **Uprawnienia interfejsów API** i wybierz pozycję **Udziel zgody administratora**.
    4. Przejdź do obszaru **Certyfikaty i wpisy tajne**, wybierz pozycję **Przekaż certyfikat**, a następnie przekaż plik CER certyfikatu, który będzie używany na potrzeby uwierzytelniania S2S.
    5. Przejdź do obszaru **Aplikacja dla przedsiębiorstwa** i wybierz utworzoną przez siebie aplikację.
    6. Zapisz wartości **Identyfikator aplikacji** (identyfikator klienta) i **Identyfikator obiektu** dotyczące aplikacji.
    7. Zespół usługi fakturowania musi udzielić aplikacji dostępu do usługi. Wyślij wartości następujących parametrów na adres <D365EInvoiceSupport@microsoft.com>:

        - Identyfikator dzierżawy AAD
        - Identyfikator środowiska usługi LCS
        - Identyfikator aplikacji
        - Identyfikator obiektu

5. W usługach RCS dodaj aplikację do listy aplikacji dostępnych w środowisku usług.

    1. Wybierz kolejno pozycje **Funkcje globalizacji** \> **Środowiska** \> **Fakturowanie elektroniczne** \> **Środowiska usług** i wybierz swoje środowisko.
    2. W sekcji **Aplikacje** dodaj wiersz do siatki, a następnie wprowadź nazwę i identyfikator obiektu aplikacji.

        ![Dodawanie aplikacji do środowiska usług.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Wybierz pozycję **Zapisz**, a następnie pozycję **Opublikuj**.

### <a name="create-an-azure-virtual-machine"></a>Tworzenie maszyny wirtualnej platformy Azure

1. W portalu [Azure Portal](https://portal.azure.com) wybierz pozycję **Maszyny wirtualne** i wybierz pozycję **Utwórz nową**.
2. Na karcie **Ustawienia podstawowe** wybierz subskrypcję i grupę zasobów. Te wartości muszą określać subskrypcję i grupę zasobów, w której znajduje się magazyn kluczy oraz magazyn obiektów blob.
3. Wybierz region. Ta wartość musi określać region, w którym jest wdrożone Twoje środowisko rozwiązania Finance.
4. Dodaj nazwę użytkownika i hasło administratora, a następnie zapisz je w magazynie kluczy.
5. W polu **Wybierz porty wejściowe** wybierz wartości **HTTPS (443)** i **RPD (3389)**.

    > [!NOTE]
    > Zalecamy wyłączenie portu **RDP (3389)** podczas przenoszenia systemu do środowiska produkcyjnego. Możesz włączyć go ponownie, jeśli w celu rozwiązania problemów trzeba będzie nawiązać połączenie z maszyną wirtualną.

    ![Ustawianie pól na karcie Ustawienia podstawowe w celu utworzenia maszyny wirtualnej platformy Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. Na karcie **Dyski** na skróconej karcie **Zaawansowane** zaznacz pole wyboru **Użyj dysków zarządzanych**. Pozostaw wyczyszczone pole wyboru **Efemeryczny dysk systemu operacyjnego**.

    ![Ustawianie pól na karcie Dyski w celu utworzenia maszyny wirtualnej platformy Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. Na karcie **Sieć** w polu **Publiczny adres IP** wybierz pozycję **Utwórz nowy**.

    ![Ustawianie pól na karcie Sieć w celu utworzenia maszyny wirtualnej platformy Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. W oknie dialogowym **Tworzenie publicznego adresu IP** w grupie pól **Jednostka SKU** wybierz opcję **Standardowa**. W grupie pól **Przypisanie** wybierz opcję **Statyczne**.

    ![Tworzenie publicznego adresu IP.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. Na karcie **Zarządzanie** wyczyść pole wyboru **Automatyczne zamykanie**, aby wyłączyć automatyczne zamykanie.
10. Ustaw w polu **Aktualizacje systemu operacyjnego gościa** wartość **Ręczne**, a następnie ustaw inne zasady.
11. Przejrzyj ustawienia i utwórz maszynę wirtualną.
12. Na nowej maszynie wirtualnej wybierz kolejno pozycje **Tożsamość** \> **Przypisana przez system**, a następnie ustaw dla opcji **Stan** wartość **Włączona**.
13. Udziel maszynie wirtualnej dostępu do magazynu kluczy.

    1. W magazynie kluczy wybierz kolejno pozycje **Kontrola dostępu (zarządzanie dostępem i tożsamościami)** \> **Przypisania ról**.
    2. Wybierz pozycję **Dodaj przypisanie roli**, a następnie ustaw wymienione poniżej pola:

        1. W polu **Rola** określ wartość **Użytkownik wpisów tajnych w magazynie kluczy**.
        2. W polu **Przypisz dostęp do** określ wartość **Maszyna wirtualna**.
        3. W polu **Subskrypcja** określ swoją subskrypcję.
        4. W polu **Wybierz** określ swoją maszynę wirtualną.

    3. Przejdź do obszaru **Zasady dostępu**.
    4. Wybierz pozycję **Dodaj zasady dostępu**, a następnie ustaw wymienione poniżej pola:

        1. W polu **Wybrany podmiot zabezpieczeń** wybierz swoją maszynę wirtualną.
        2. W sekcji **Certifikat** wybierz uprawnienia **Tworzenie listy** i **Pobieranie**.

14. W portalu [Azure Portal](https://portal.azure.com) przejdź do obszaru **Publiczne adresy IP** i wybierz adres IP utworzony na maszynie wirtualnej.
15. Przejdź do obszaru **Konfiguracja** i ustaw nazwę systemu nazw domen (DNS).

### <a name="prepare-the-proxy-service-environment"></a>Przygotowywanie środowiska usługi serwera proxy

Wykonaj te kroki na komputerze, na którym jest hostowana usługa serwera proxy.

1. Nawiąż połączenie z maszyną wirtualną, używając funkcji Podłączenie pulpitu zdalnego.
2. Otwórz przystawkę Certyfikat komputera lokalnego. Aby uzyskać więcej informacji, zobacz [Jak wyświetlać certyfikaty za pomocą przystawki programu MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Zaimportuj certyfikat **caentrate.cer** dla środowiska produkcyjnego oraz certyfikat **CAEntratetest.cer** dla środowiska testowego do [magazynu Zaufane główne urzędy certyfikacji](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** to certyfikat głównego urzędu certyfikacji dostarczony przez ten urząd).
4. W Panelu sterowania otwórz aplet **Włącz lub wyłącz funkcje systemu Windows** albo wybierz kolejno pozycje **Menedżer serwera** \> **Dodaj role i funkcje** dla systemu operacyjnego serwera i włącz funkcje Internetowych usług informacyjnych (IIS):

    - Narzędzia zarządzania siecią Web
        - Konsola zarządzania usługami IIS
    - Usługi WWW
        - Funkcje projektowania aplikacji
            - .NET Extensibility 4.7 (lub 4.8)
            - ASP
            - ASP.NET 4.7 (lub 4.8)
            - Interfejs CGI
            - Rozszerzenia ISAPI
            - Filtry ISAPI
        - Wspólne funkcje HTTP
            - Dokument domyślny
            - Przeglądanie katalogów
            - Błędy HTTP
            - Zawartość statyczna
        - Kondycja i diagnostyka
            - Rejestrowanie HTTP
            - Śledzenie
        - Funkcje wydajności
            - Kompresja zawartości statycznej
        - Zabezpieczenia
            - Filtrowanie żądań

    ![Włączanie funkcji usług IIS.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Konfigurowanie usługi serwera proxy usługi SDI w usługach IIS

1. W usłudze Microsoft Dynamics Lifecycle Services (LCS) przejdź do biblioteki udostępnionych elementów zawartości i wybierz wartość **Pakiet danych** jako typ elementu zawartości.
2. Znajdź element **Serwer proxy usługi SDI usługi fakturowania elektronicznego** i pobierz go na maszynę wirtualną.
3. Skonfiguruj usługę.

    1. Rozpakuj pobrany folder archiwum **Serwer proxy usługi SDI usługi fakturowania elektronicznego**.
    2. W folderze **src\\FattureService** otwórz plik **appsettings.json** i ustaw następujące parametry:

        - **KeyVaultUri** — określ adresu magazynu kluczy, w którym jest przechowywany certyfikat klienta dla usługi fakturowania.
        - **TenantId** — określ unikatowy identyfikator globalny (GUID) dzierżawy odbiorcy.
        - **EnvironmentId** — określ identyfikator środowiska usługi LCS.
        - **ClientId** — określ identyfikator aplikacji dla rejestracji aplikacji usług pośrednich w dzierżawie odbiorcy.
        - **ClientCertificateName** — określ nazwę certyfikatu S2S w magazynie kluczy.
        - **SecurityServiceClientOptions.Endpoint** — określ adres URL usługi zabezpieczeń.
        - **SecurityServiceClientOptions.Resource** — określ zakres, dla którego ma być uzyskiwany token.
        - **InvoicingServiceClientOptions.Endpoint** — określ punkt końcowy usługi fakturowania. Ta wartość musi wskazywać punkt końcowy używany na potrzeby usług RCS i rozwiązania Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** — określ nazwę środowiska usług. Ta wartość musi być nazwą Twojego środowiska rozwiązania Finance.
        - **NotificationsFolder** — określ folder, w którym mają być zapisywanie pliki powiadomień przychodzących.

    3. W pliku **web.config** znajdź poniższy wiersz i dodaj odcisk palca certyfikatu serwera proxy.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Podczas przenoszenia systemu do wersji produkcyjnej możesz zmienić niektóre wartości w pliku web.config, aby zmniejszyć ilość zbieranych informacji dziennika i oszczędzać miejsce na dysku. W węźle **\<system.diagnostics\>\<source\>** zmień wartość elementu **switchValue** na **Critical,Error**. Aby uzyskać więcej informacji, zobacz [Podgląd danych śledzenia usług firm Microsoft](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Otwórz Menedżera usług IIS. W drzewie po lewej stronie pozostań w węźle głównym. Po prawej stronie wybierz pozycję **Certyfikaty serwera**.

    ![Wybieranie certyfikatów usług w Menedżerze usług IIS.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Otwórz menu i wybierz polecenie **Importuj**.
6. W oknie dialogowym **Importowanie certyfikatu** w polu **Plik certyfikatu (.pfx)** określ ścieżkę pliku PFX dla certyfikatu serwera proxy.

    ![Określanie pliku certyfikatu usługi serwera proxy.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) pozycję **Witryny**, a następnie wybierz pozycję **Dodaj witrynę internetową**.
8. W oknie dialogowym **Dodawanie witryny internetowej** w polu **Nazwa witryny** wprowadź nazwę witryny.
9. W polu **Ścieżka fizyczna** wskaż folder **src\\FattureService**.
10. W polu **Typ powiązania** wybierz wartość **https**.
11. W polu **Nazwa hosta** określ nazwę hosta.
12. W polach **Adres IP** i **Port** pozostaw wartości domyślne.
13. Upewnij się, że pole wyboru **Wymagaj oznaczania nazwy serwera** jest wyczyszczone, ponieważ usługa SDI nie obsługuje tej technologii.
14. W polu **Certyfikat protokołu SSL** wybierz zaimportowany certyfikat serwera proxy.
15. W polu **Pula aplikacji** określ pulę dla witryny i zanotuj jej nazwę (na przykład **SdiAppPool**).

    ![Dodawanie witryny internetowej.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Po zakończeniu tworzenia witryny internetowej otwórz menu **Ustawienia protokołu SSL**.

    ![Otwieranie menu Ustawienia protokołu SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Zaznacz pole wyboru **Wymagaj protokołu SSL**, a następnie w grupie pól **Certyfikaty klienta** wybierz opcję **Wymagaj**.

    ![Konfigurowanie ustawień protokółu SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Otwórz stronę **Przeglądanie katalogów** i wybierz pozycję **Włącz**.
19. W dowolnej przeglądarce internetowej przejdź na stronę **serverDNS/TrasmissioneFatture.svc**. Musi zostać wyświetlona standardowa strona dotycząca usługi.

    ![Sprawdzanie usługi w przeglądarce.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Utwórz następujące foldery, aby przechowywać dzienniki i pliki:

    - **C:\\Dzienniki\\** — w tym folderze będą przechowywanie pliki dzienników. Te pliki można przeglądać za pomocą narzędzia [Podgląd danych śledzenia usług firmy Microsoft](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\Pliki\\** — w tym folderze będą przechowywane wszystkie pliki odpowiedzi.

21. W Eksploratorze plików udziel kontom **USŁUGA SIECIOWA** i **IIS AppPool\\SdiAppPool** (lub **IIS AppPool\\DefaultAppPool**, jeśli używasz puli domyślnej) dostępu do folderów **Dzienniki** i **Pliki**.

    1. Zaznacz jeden z folderów i przytrzymaj go (lub kliknij prawym przyciskiem myszy), a następnie wybierz pozycję **Właściwości**.
    2. W oknie dialogowym **Właściwości** na karcie **Zabezpieczenia** wybierz pozycję **Edytuj**.
    3. Dodaj użytkowników, jeśli nie znajdują się na liście.
    4. Powtórz kroki od 1 do 3 dla drugiego folderu.

    ![Dodawanie uprawnień dla użytkowników usługi.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Klauzula prywatności 

Włączenie funkcji **Włoska faktura elektroniczna** może wymagać wysyłania ograniczonej ilości danych. Te dane obejmują identyfikator podatkowy organizacji. Administrator może włączyć i wyłączyć funkcję Włoska faktura elektroniczna. Aby wyłączyć tę funkcję, wykonaj wymienione poniżej kroki.

1. Przejdź do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**.
2. Na karcie **Funkcje** zaznacz wiersze zawierające funkcję **Włoska faktura elektroniczna**, a następnie wybierz pozycję **Wyłącz teraz**.

Dane importowane z tych systemów zewnętrznych do tej usługi online, która wchodzi w skład usługi Dynamics 365, podlegają naszemu [oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcją „Uwagi dotyczące prywatności” w dokumentacji funkcji specyficznej dla kraju/regionu.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
