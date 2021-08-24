---
title: Konfiguracja korzystania z modułu Finance Insights (przed wersją 10.0.19)
description: W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights (przed wersją 10.0.19).
author: ShivamPandey-msft
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 77d51302ee38c843a1988d9a65537015edb9b5159ed1e9f657a04b5e0fe72cea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764341"
---
# <a name="configuration-for-finance-insights-for-private-preview-preview---before-version-10019"></a>Konfiguracja dla Finance Insights w ramach prywatnej wersji zapoznawczej (podglądowej) — przed wersją 10.0.19

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Poniższe procedury konfigurowania rozwiązania Finance Insights są prawidłowe w przypadku wersji rozwiązania Microsoft Dynamics 365 Finance przed wersją 10.0.19. Aby skonfigurować Finance Insights w wersji 10.0.20 i późniejszych, patrz [Konfiguracja Finance Insights (wersja zapoznawcza)— wersje do 10.0.20 i nowsze](configure-for-fin-insites-PubPrvw.md).

Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Microsoft Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji. W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.

## <a name="deploy-dynamics-365-finance"></a>Wdrażanie Dynamics 365 Finance

Aby wdrożyć środowiska, wykonaj następujące kroki.

1. W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Dynamics 365 Finance. Środowisko wymaga wersji aplikacji 10.0.11/Platform Update 35 lub nowszego.
2. Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy. (Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Jeśli konfigurujesz Finance Insights w środowisku piaskownicy, być może będziesz musiał skopiować dane produkcyjne do tego środowiska, aby prognozy zadziałały. Model prognozy używa wielu lat danych do tworzenia prognoz. Dane demonstracyjne Contoso nie zawierają wystarczającej ilości danych historycznych do szkolenia modelu prognozy. 

## <a name="configure-dataverse"></a>Skonfiguruj usługę Dataverse

Wykonaj następujące kroki, aby skonfigurować Dataverse for Finance Insights.

1. Otwórz stronę środowiska w u usługach LCS i sprawdź, czy sekcja **Integracja Power Platform** jest już skonfigurowana.
    1. Jeśli jest już skonfigurowana, na liście powinna znajdować się nazwa środowiska Dataverse połączona ze środowiskiem Dynamics 365 Finance. Skopiuj nazwę środowiska Dataverse.
    2. Jeśli nie jest skonfigurowana, należy wykonać następujące czynności:
        1. Wybierz przycisk **Ustawienia** w sekcji Integracja Power Platform. Skonfigurowanie środowiska może potrwać do godziny.
        2. Gdy środowisko Dataverse zostanie poprawnie skonfigurowane, na liście powinna zostać wyświetlona nazwa środowiska Dataverse połączona ze środowiskiem Dynamics 365 Finance. Skopiuj nazwę środowiska Dataverse.
> [!NOTE]
> Po skonfigurowaniu środowiska **NIE należy** wybierać przycisku Łącze do usługi **CDS for Apps**. Nie jest to potrzebne w przypadku aplikacji Finance Insights i pozbawiłoby możliwości wykonywania wymaganych dodatków środowiska w usługach LCS.

2. Otwórz the [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com/) i wykonaj następujące kroki, aby utworzyć nowe środowisko Dataverse w tym samym dzierżawcy Active Directory:

    1. Otwórz stronę **Środowiska**.

        [![Strona Środowiska.](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Wybierz środowisko Dataverse utworzone powyżej,, a następnie wybierz opcję **Ustawienia**.
    3. Wybierz **Zasoby \> Wszystkie ustawienia starego typu**.
    4. Na górnym pasku nawigacyjnym wybierz opcję **Ustawienia**, a następnie wybierz opcję **Dostosowania**.
    5. Wybierz **Zasoby deweloperskie**.
    6. Umożliwia skopiowanie wartości **Identyfikator organizacji Dataverse**.
    7. Zanotuj adres URL organizacji Dataverse z paska adresu przeglądarki. Może to być na przykład adres URL `https://org42b2b3d3.crm.dynamics.com`.

3. Jeśli planowane jest użycie funkcji prognoz przepływów pieniężnych lub funkcji prognoz budżetu, należy wykonać następujące kroki w celu zaktualizowania limitu adnotacji dla organizacji na co najmniej 50 megabajtów (MB):

    1. Otwórz portal [Power Apps](https://make.powerapps.com).
    2. Wybierz nowo utworzone środowisko, a następnie wybierz **Ustawienia zaawansowane**.
    3. Wybierz **Ustawienia \> Konfiguracja poczty e-mail**.
    4. Zmień wartość w polu **Maksymalny rozmiar pliku** na **51 200**. (Wartość jest wyrażona w kilobajtach \[KB\]).
    5. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="configure-the-azure-setup"></a>Konfigurowanie ustawień platformy Azure

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Wprowadź Identyfikator katalogu Dataverse i identyfikator obiektu Azure AD użytkownika.

1. Wprowadź identyfikator katalogu Dataverse:

    1. Otwórz [portal Azure](https://portal.azure.com).
    2. Zaloguj się przy użyciu identyfikatora użytkownika, który został użyty do utworzenia środowiska Dataverse.
    3. Przejdź do **Azure Active Directory**.
    4. Umożliwia skopiowanie wartości **Identyfikator dzierżawcy**.

2. Wprowadź identyfikator obiektu Azure Active Directory (Azure AD) użytkownika:

    1. W [portalu Azure](https://portal.azure.com) przejdź do okna **Użytkownicy** i wyszukaj użytkownika na podstawie adresu e-mail.
    2. Zaznacz nazwę użytkownika.
    3. Skopiuj wartość **Identyfikator obiektu**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Korzystanie ze skryptu programu Windows PowerShell](#tab/use-a-powershell-script)

Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Jeśli wolisz przeprowadzić ręczną konfigurację, pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).

> [!NOTE]
> Wykonaj poniższe kroki, aby uruchomić skrypt programu PowerShell. Opcja „Wypróbuj to" interfejsu wierszu polecenia Azure może nie działać, podobnie jak wykonywanie skryptu na komputerze.

Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki. Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD. Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure. Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.
2. Wybierz opcję **PowerShell**.
3. Jeśli zostanie wyświetlony odpowiedni monit, utwórz magazyn.
4. Przejdź do karty **Azure CLI** i wybierz polecenie **Kopiuj**.  
5. Otwórz notatnik i wklej skrypt programu PowerShell. Zapisz plik jako ConfigureDataLake.ps1.
6. Przekaż skrypt programu Windows PowerShell do sesji, używając opcji menu do przekazania w Cloud Shell.
7. Uruchom skrypt .\ConfigureDataLake.ps1.
8. Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.
9. Korzystając z informacji z wyników skryptu, zainstaluj dodatek **Eksport do Data Lake** w LCS.
10. Za pomocą informacji z wyników skryptu można włączyć magazyn jednostek na stronie **Połączenia danych** w module Finance (**Administrowanie systemem \> Parametry systemu \> Połączenia danych**).

### <a name="manual-setup"></a>Konfiguracja ręczna

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Dodawanie aplikacji do dzierżawcy Azure AD

1. W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory**.
2. Wybierz **Zarządzaj \> Aplikacje dla przedsiębiorstw**.
3. Wyszukaj następujące aplikacje na podstawie identyfikatora aplikacji.

    | Zgłoszenie                              | Identyfikator aplikacji                               |
    |------------------------------------------|--------------------------------------|
    | Mikrousługi ERP Microsoft Dynamics     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS mikrousług ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Usługa autoryzacji AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Jeśli nie możesz znaleźć dowolnej z tych aplikacji, spróbuj wykonać poniższe kroki.

1. Na komputerze lokalnym naciśnij menu **Start** i wyszukaj program **powershell**.
2. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) program **Windows PowerShell**, a następnie wybierz polecenie **Uruchom jako administrator**.
3. Uruchom następujące polecenie, aby zainstalować moduł **AzureAD**.

    `Install-Module -Name AzureAD`

4. Jeśli dostawca NuGet jest wymagany, aby kontynuować, wybierz opcję **Y**, aby go zainstalować.
5. Jeśli zostanie wyświetlony komunikat „Niezaufane repozytorium”, wybierz opcję **Y**, aby kontynuować.
6. Dla każdej aplikacji, która musi zostać dodana, należy uruchomić następujące polecenia, aby dodać aplikację do Azure AD. Po wyświetleniu monitu zaloguj się jako administrator Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Tworzenie zasobów platformy Azure

> [!NOTE]
> Należy się upewnić, że następujące zasoby są tworzone w tym samym wystąpieniu Azure AD, co środowisko Dataverse. Nie można użyć zasobów z innego wystąpienia Azure AD.

1. Tworzenie nowego konta magazynu:

    1. W [portalu Azure](https://portal.azure.com) utwórz konto magazynu.
    2. W oknie dialogowym **Utwórz konto magazynu** ustaw następujące pola:

        - **Lokalizacja** — umożliwia wybór centrum danych, w którym znajduje się dane środowisko.
        - **Wydajność** — zaleca się, aby w wybrać opcję **Standardowa**.
        - **Rodzaj konta** — musisz wybrać **StorageV2**.

    3. W oknie dialogowym **Opcje zaawansowane**, jako wartość opcji **Data Lake Storage Gen2** wybierz **Włącz** w obszarze funkcji **Hierarchiczne przestrzenie nazw**. Jeśli ta funkcja zostanie wyłączona, nie będzie można używać danych, które aplikacje Finance and Operations zapisują przy użyciu usług, takich jak przepływy danych Power BI.
    4. Wybierz opcję **Przejrzyj i utwórz**. Po zakończeniu wdrażania nowy zasób zostanie wyświetlony w portalu Azure.
    5. Przejdź do utworzonego konta magazynu.
    6. W menu po lewej stronie wybierz **Klucze dostępu**.
    7. Skopiuj i zapisz parametry połączenia **Klucza1** lub **Klucza2**.
    8. Skopiuj i zapisz nazwę konta magazynu.

2. Utwórz nowy magazyn kluczy:

    1. W [portalu Azure](https://portal.azure.com) utwórz magazyn kluczy.
    2. W oknie dialogowym **Utwórz magazyn kluczy**, w polu **Lokalizacja** wybierz centrum danych, w którym znajduje się dane środowisko.
    3. Po utworzeniu magazynu kluczy wybierz go z listy, a następnie wybierz opcję **Wpisy tajne**.
    4. Wybierz pozycję **Generuj/importuj**.
    5. W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
    6. Wprowadź nazwę wpisu tajnego. Zanotuj nazwę, ponieważ później będzie musiała zostać podana.
    7. W polu **Wartość** wprowadź parametry połączenia uzyskane z konta magazynu w poprzedniej procedurze.
    8. Wybierz opcję **Włączone**, a następnie opcję **Utwórz**. Wpis tajny został utworzony i dodany do magazynu kluczy.
    9. Przejdź do strony **Przegląd magazynu kluczy** i zanotuj nazwę DNS.

3. Utwórz i zarejestruj aplikację Azure AD:

    1. W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory** i wybierz opcję **Rejestracje aplikacji**.
    2. Wybierz opcję **Nowa rejestracja aplikacji** i ustaw następujące pola:

        - **Nazwa** — Wprowadź nazwę aplikacji.
        - **Typ aplikacji** — wybierz **internetowy interfejs API**.
        - **Ustawienia URI przekierowania** — wprowadź adres URL wystąpienia Dynamics 365, jak `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Przejdź do właśnie utworzonej aplikacji, a następnie skopiuj i zapisz jej wartość **Identyfikator aplikacji (klienta)**. Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.
    4. Przejdź do okna **Uprawnienia do interfejsu API** i wykonaj następujące kroki:

        1. Wybierz opcję **Dodaj uprawnienie**.
        2. Wybierz **Magazyn kluczy Azure**.
        3. Po wybraniu uprawnień delegowanych wybierz opcję **user\_impersonation**.
        4. Wybierz opcję **Dodaj uprawnienia**.

    5. W menu aplikacji wybierz pozycję **Certyfikaty i tajne wpisy**, a następnie wykonaj następujące kroki, aby utworzyć wpisy tajne magazynu kluczy:

        1. Wybierz **Nowy klucz tajny klienta**.
        2. W polu **Opis klucza** wprowadź nazwę.
        3. Wybierz czas trwania, a następnie wybierz **Dodaj**. Wpis tajny jest generowany w polu **Wartość**.
        4. Skopiuj i zapisz wartość wpisu tajnego.

4. Utwórz wpisy tajne magazynu kluczy:

    1. Przejdź do utworzonego wcześniej magazynu kluczy i wybierz opcję **Wpisy tajne**.
    2. Z każdą nazwą wpisu tajnego w poniższej tabeli wykonaj następujące kroki:

        1. Wybierz pozycję **Generuj/importuj**.
        2. W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
        3. Utwórz nazwę i wartość wpisu tajnego z poniższej tabeli.
        4. Wybierz opcję **Włączone**, a następnie opcję **Utwórz**. Wpis tajny został utworzony i dodany do magazynu kluczy.

        | Nazwa wpisu tajnego                       | Wartość wpisu tajnego                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | app-id                            | Identyfikator aplikacji, która została utworzona wcześniej                                      |
        | app-secret                        | Klucz tajny klienta, który został wcześniej zapisany                                                    |
        | storage-account-name              | Nazwa utworzonego wcześniej konta magazynu, na przykład **storageaccount1**       |
        | storage-account-connection-string | Parametry połączenia skopiowane z strony **Klucze dostępu** konta magazynu |

5. Autoryzuj aplikację, aby mogła uzyskać dostęp do magazynu kluczy:

    1. W [portalu Azure](https://portal.azure.com) otwórz utworzony wcześniej magazyn kluczy.
    2. Wybierz zasady dostępu.
    3. Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:

        1. Wybierz pozycję **Dodaj zasady dostępu**, aby utworzyć zasady dostępu.
        2. W polu **Uprawnienia wpisu tajnego** wybierz uprawnienia z poniższej tabeli.
        3. W polu **Wybierz główne** wyszukaj nazwę wyświetlaną aplikacji z poniższej tabeli.
        4. Wybierz pozycję **Wybierz**.
        5. Wybierz opcję **Dodaj**.
        6. Wybierz opcję **Zapisz**.

        | Zgłoszenie                                              | Uprawnienia |
        |----------------------------------------------------------|-------------|
        | Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej | Pobieranie, Tworzenie listy   |
        | **Mikrousługi ERP Microsoft Dynamics**                 | Pobieranie, Tworzenie listy   |

6. Przypisz role, aby uzyskać dostęp do konta magazynu:

    1. W [portalu Azure](https://portal.azure.com) otwórz utworzone wcześniej konto magazynu.
    2. Wybierz pozycję **Kontrola dostępu (IAM)**, a następnie wybierz **Przypisania ról**.
    3. Wybierz **Dodaj, Dodaj przypisanie roli**.
    4. Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:

        1. Wybierz rolę z następującej tabeli.
        2. Pozostaw ustawienie pola **Przypisz dostęp do** jako **Użytkownik, grupa lub nazwa główna usługi Azure AD**.
        3. W polu **Wybierz** wprowadź aplikację z poniższej tabeli.
        4. Wybierz opcję **Zapisz**.

        | Zgłoszenie                                              | Rola                        |
        |----------------------------------------------------------|-----------------------------|
        | Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej | Właściciel                       |
        | Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej | Osoba wpłacająca                 |
        | Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej | Współautor konta magazynu |
        | Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej | Właściciel danych obiektów blob magazynu     |
        | **Usługa autoryzacji AI Builder**                     | Czytelnik danych obiektów blob magazynu    |

# <a name="azure-cli"></a>[Interfejs wiersza polecenia Azure](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}

```
---



## <a name="configure-the-data-lake"></a>Konfigurowanie data lake

Aby dodać dodatek Azure Data Lake do środowiska, należy wykonać następujące kroki.

1. Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.
2. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. Wybierz dodatek **Eksport do Data Lake**.
4. Wprowadź następujące wartości.

    | Wartość                                                              | opis |
    |--------------------------------------------------------------------|-------------|
    | Identyfikator dzierżawcy subskrypcji Azure, w której znajduje się magazyn kluczy | Identyfikator dzierżawcy, w którym znajdują się konto magazynu, aplikacje i magazyny kluczy. Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**. |
    | Podaj nazwę DNS usługi Key Vault                             | Nazwa DNS magazynu kluczy, np. `https://customkeyvault.vault.azure.net/`. (Wartość ta pokrywa się z nazwą DNS używaną w magazynie jednostek). |
    | Podaj wpis tajny zawierający nazwę konta magazynu   | **storage-account-name** |
    | Nazwa wpisu tajnego identyfikatora aplikacji, który będzie używany w celu uzyskania dostępu do Data Lake          | **app-id** |
    | Nazwa wpisu tajnego do używania z identyfikatorem aplikacji                                 | **app-secret** |

5. Zaakceptuj warunki i wybierz opcję **Zainstaluj**.

Dodatek zostanie zainstalowany w ciągu kilku minut.

## <a name="configure-ai-builder"></a>Konfigurowanie AI Builder

1. Zaloguj się do LCS i otwórz stronę **Szczegóły środowiska**.
2. Przewiń w dół do sekcji **Dodatki środowiska**. Powinny zostać wyświetlone dodatki, które są już zainstalowane w tym środowisku. Jeśli nie ma wśród nich dodatku **Eksport do Data Lake**, skonfiguruj ten dodatek.
3. Wybierz dodatek **Pobierz szczegółowe dane**.
4. Na stronie szczegółów dodatku **Pobierz szczegółowe analizy** wprowadź następujące informacje.

    | Wartość                                                    | opis |
    |----------------------------------------------------------|-------------|
    | Adres URL organizacji CDS                                     | Adres URL organizacji Dataverse skopiowany z góry. |
    | Identyfikator organizacji CDS                                               | Identyfikator organizacji Dataverse skopiowany z góry. |
5. Włącz opcję **Czy to jest domyślne środowisko CDS dla dzierżawcy**.

Instalacja dodatku może potrwać kilka minut.
    
## <a name="configure-the-entity-store"></a>Konfigurowanie magazynu jednostek

Aby skonfigurować magazyn jednostek w środowisku Finance, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu \> Połączenia danych**.
2. Ustaw następujące pola magazynu kluczy:

    - **Identyfikator aplikacji (klienta)** — wprowadź utworzony wcześniej identyfikator klienta aplikacji.
    - **Wpis tajny aplikacji** — wprowadź wpis tajny zapisany dla utworzonej wcześniej aplikacji.
    - **Nazwa DNS** — nazwa systemu DNS (Domain Name System) znajduje się na stronie szczegółów aplikacji dla utworzonej wcześniej aplikacji.
    - **Nazwa wpisu tajnego** — wprowadź **storage-account-connection-string**.
3. Włącz opcję **Włącz integrację danych w usłudze Data Lake**.
4. Naciśnij łącze **Testuj Azure Key Vault** i sprawdź, czy nie ma żadnych błędów.
5. Naciśnij łącze **Testuj magazyn usługi Azure** i sprawdź, czy nie ma żadnych błędów.

## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com).

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
