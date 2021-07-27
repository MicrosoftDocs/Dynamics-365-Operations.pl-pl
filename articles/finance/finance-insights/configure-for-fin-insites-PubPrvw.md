---
title: Konfiguracja dla Finance Insights w ramach publicznej wersji zapoznawczej (podglądowej) — wersja 10.0.20 i późniejsze
description: W tym temacie wyjaśniono, jak skonfigurować system, aby korzystał z możliwości dostępnych w programie Finance Insights dla publicznego podglądu w wersji 10.0.20 i nowszych.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: eeb3061f215666d0aeb32094b5d04a9ae6e618f2
ms.sourcegitcommit: f6050b444e636ba662c00d0443c94a99f8ea0b0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309672"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a>Konfiguracja dla Finance Insights w ramach publicznej wersji zapoznawczej (podglądowej) — wersja 10.0.20 i późniejsze

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji. W tym temacie wyjaśniono, jak skonfigurować Dynamics 365 Finance w wersji 10.0.20, aby system korzystał z możliwości dostępnych w programie Finance Insights dla publicznego podglądu w wersji 10.0.20 i nowszych.

> [!NOTE]
> Kroki konfiguracyjne opisane w tym temacie dotyczą tylko wersji Finance 10.0.20 i nowszych. Aby skonfigurować Finance Insights w wersji 10.0.19 i wcześniejszych, patrz [Konfiguracja Finance Insights — wersje do 10.0.19](configure-for-fin-insites.md).

## <a name="deploy-finance"></a>Wdrażanie Finance

Wykonaj poniższe kroki, aby wdrożyć środowiska.

1. W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Finance. Środowisko wymaga wersji aplikacji 10.0.20 Finance and Operations lub nowszej.
2. Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy. (Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Jeśli konfigurujesz Finance Insights w środowisku piaskownicy, być może będziesz musiał skopiować dane produkcyjne do tego środowiska, aby prognozy zadziałały. Model prognozy używa wielu lat danych do tworzenia prognoz. Dane demonstracyjne Contoso nie zawierają wystarczającej ilości danych historycznych do szkolenia modelu prognozy. 

## <a name="configure-dataverse"></a>Skonfiguruj usługę Dataverse

Wykonaj następujące kroki, aby skonfigurować Dataverse for Finance Insights.

1. W LCS otwórz stronę środowiska i sprawdź, czy sekcja **Integracja Power Platform** jest już skonfigurowana.

    - Jeśli jest już skonfigurowana, na liście powinna znajdować się nazwa środowiska Finance połączona ze środowiskiem Dataverse.
    - Jeśli nie jest jeszcze skonfigurowana, należy wykonać następujące czynności:

        1. Wybierz przycisk **Integracja Power Platform**, a następnie wybierz **Konfiguracja**. Konfiguracja środowiska może potrwać do godziny.
        2. Gdy środowisko Dataverse zostanie poprawnie skonfigurowane, na liście powinna zostać wyświetlona nazwa środowiska Dataverse połączona ze środowiskiem Finance.

        > [!NOTE]
        > Po zakończeniu konfigurowania środowiska **nie** należy wybierać opcji **Łącze do CDS**. Ten przycisk nie jest wymagany w przypadku Finance Insights. Jeśli ją wybierzesz, nie będziesz mógł skonfigurować wymaganych dodatków środowiskowych w LCS.

## <a name="configure-azure"></a>Konfiguruj system Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Korzystanie ze skryptu programu Windows PowerShell](#tab/use-a-powershell-script)

Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Jeśli wolisz przeprowadzić ręczną konfigurację, zamiast tego pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).

> [!NOTE]
> Użyj następującej procedury, aby uruchomić skrypt Windows PowerShell. Konfiguracja może nie zadziałać, jeśli użyjesz opcji **Wypróbuj** w Azure CLI lub jeśli uruchomisz skrypt na swoim komputerze.

Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki. Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD. Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure.
2. Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.
3. Wybierz opcję **PowerShell**.
4. Utwórz pamięć masową, jeśli zostanie wyświetlony monit o jej utworzenie.
5. Przejdź do karty **Azure CLI** i wybierz polecenie **Kopiuj**.
6. W Notatniku otwórz nowy plik i wklej do niego skrypt Windows PowerShell.
7. Zapisz plik jako **ConfigureDataLake.ps1**.
8. Przekaż skrypt programu Windows PowerShell do sesji, używając opcji menu do przekazania w Cloud Shell.
9. Uruchom skrypt **.\ConfigureDataLake.ps1**.
10. Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.
11. Korzystając z informacji z wyników skryptu, zainstaluj dodatek Eksport do Data Lake w LCS.

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

1. Tworzenie konta magazynu:

    1. W [portalu Azure](https://portal.azure.com) utwórz konto magazynu.
    2. W oknie dialogowym **Utwórz konto magazynu** ustaw następujące pola:

        - **Lokalizacja** — umożliwia wybór centrum danych, w którym znajduje się dane środowisko.
        - **Wydajność** — zaleca się, aby w wybrać opcję **Standardowa**.
        - **Rodzaj konta** — musisz wybrać **StorageV2**.

    3. W oknie dialogowym **Opcje zaawansowane**, jako wartość opcji **Data Lake Storage Gen2** wybierz **Włącz** w obszarze funkcji **Hierarchiczne przestrzenie nazw**. Jeśli ta funkcja nie zostanie wyłączona, nie będzie można używać danych, które aplikacje Finance and Operations zapisują przy użyciu usług, takich jak przepływy danych Power BI.
    4. Wybierz opcję **Przejrzyj i utwórz**. Po zakończeniu wdrażania nowy zasób zostanie wyświetlony w portalu Azure.
    5. Przejdź do utworzonego konta magazynu.
    6. W menu po lewej stronie wybierz **Klucze dostępu**.
    7. Skopiuj i zapisz nazwę konta magazynu. Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.

2. Tworzenie magazynu kluczy:

    1. W [portalu Azure](https://portal.azure.com) utwórz magazyn kluczy.
    2. W oknie dialogowym **Utwórz magazyn kluczy**, w polu **Lokalizacja** wybierz centrum danych, w którym znajduje się dane środowisko.
    3. Po utworzeniu klucza należy przejść do pola **Przegląd magazynu kluczy**, skopiować i zapisać nazwę DNS. Tę wartość trzeba będzie wprowadzić później podczas konfigurowania dodatku Data Lake.

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
        4. Skopiuj i zapisz wartość wpisu tajnego klienta. Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.

4. Utwórz wpisy tajne magazynu kluczy:

    1. Przejdź do utworzonego wcześniej magazynu kluczy i wybierz opcję **Wpisy tajne**.
    2. Z każdą nazwą wpisu tajnego w poniższej tabeli wykonaj następujące kroki:

        1. Wybierz pozycję **Generuj/importuj**.
        2. W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
        3. Utwórz nazwę i wartość wpisu tajnego z poniższej tabeli.
        4. Wybierz opcję **Włączone**, a następnie opcję **Utwórz**. Wpis tajny został utworzony i dodany do magazynu kluczy.

        | Nazwa wpisu tajnego                       | Wartość wpisu tajnego                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | Identyfikator aplikacji, która została utworzona wcześniej.                                      |
        | app-secret                        | Klucz tajny klienta, który został wcześniej zapisany.                                                    |
        | storage-account-name              | Nazwa utworzonego wcześniej konta magazynu, na przykład **storageaccount1**.       |

5. Autoryzuj aplikację, aby mogła uzyskać dostęp do magazynu kluczy:

    1. W [portalu Azure](https://portal.azure.com) otwórz utworzony wcześniej magazyn kluczy.
    2. Wybierz zasady dostępu.
    3. Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:

        1. Wybierz pozycję **Dodaj zasady dostępu**, aby utworzyć zasady dostępu.
        2. W polu **Uprawnienia wpisu tajnego** wybierz uprawnienia z tabeli.
        3. W polu **Wybierz główne** wyszukaj nazwę wyświetlaną aplikacji z tabeli.
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

        1. Wybierz rolę z tabeli.
        2. Pozostaw ustawienie pola **Przypisz dostęp do** jako **Użytkownik, grupa lub nazwa główna usługi Azure AD**.
        3. W polu **Wybierz** wprowadź aplikację z tabeli.
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

## <a name="configure-the-export-to-data-lake-add-in"></a>Konfigurowanie eksportu do dodatku Data Lake

Wykonaj poniższe kroki, aby użyć LCS do dodania dodatku Eksport do Data Lake do środowiska.

1. Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.
2. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. Wybierz dodatek **Eksport do Data Lake**.
4. Wprowadź następujące wartości.

    | Wartość                                                              | opis |
    |--------------------------------------------------------------------|-------------|
    | Identyfikator dzierżawcy subskrypcji Azure, w której znajduje się magazyn kluczy | Identyfikator dzierżawcy, w którym znajdują się konto magazynu, aplikacje i magazyny kluczy. Aby uzyskać tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**. |
    | Podaj nazwę DNS usługi Key Vault                             | Nazwa DNS magazynu kluczy, np. `https://customkeyvault.vault.azure.net/`. |
    | Podaj wpis tajny zawierający nazwę konta magazynu   | **storage-account-name** |
    | Nazwa wpisu tajnego identyfikatora aplikacji, który będzie używany w celu uzyskania dostępu do Data Lake          | **app-id** |
    | Nazwa aplikacji tajnej dla wpisu tajnego klienta                                  | **app-secret** |

5. Zaakceptuj warunki i wybierz opcję **Zainstaluj**.

Dodatek zostanie zainstalowany w ciągu kilku minut.

## <a name="configure-the-finance-insights-add-in"></a>Konfigurowanie dodatku Finance Insights

> [!NOTE]
> Jeśli wcześniej został zainstalowany dodatek Get insights, odinstaluj go przed zakończeniem następującej procedury.

Aby zainstalować dodatek Finanse Insights, należy wykonać następujące kroki.

1. Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.
2. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
3. Konfigurowanie dodatku **Finance Insights**.
4. Zaakceptuj warunki i wybierz opcję **Zainstaluj**.

Instalacja dodatku może potrwać kilka minut.

## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Finance Insights (wersja zapoznawcza)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
