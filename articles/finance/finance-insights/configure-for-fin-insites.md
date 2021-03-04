---
title: Konfiguracja korzystania z modułu Finance Insights (wersja zapoznawcza)
description: W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 38cdeb9110691e594b4b90fc5bc79e369c9f4707
ms.sourcegitcommit: 1cfd6e0c808341b0f5bafbde7d04b0255b27352f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664097"
---
# <a name="configuration-for-finance-insights-preview"></a>Konfiguracja korzystania z modułu Finance Insights (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Common Data Service, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji. W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.

## <a name="deploy-dynamics-365-finance"></a>Wdrażanie Dynamics 365 Finance

Aby wdrożyć środowiska, wykonaj następujące kroki.

1. W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Dynamics 365 Finance. Środowisko wymaga wersji aplikacji 10.0.11/Platform Update 35 lub nowszego.
2. Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy. (Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Jeśli są używane dane demonstracyjne firmy Contoso, potrzebne będą dodatkowe przykładowe dane, aby korzystać z funkcji prognoz płatności od odbiorców, prognoz przepływów pieniężnych oraz prognoz budżetu. 

## <a name="configure-common-data-service"></a>Skonfiguruj usługę Common Data Service

Można wykonać następującą procedurę ręcznego konfigurowania lub przyspieszyć proces konfigurowania, korzystając z dostarczonego skryptu programu Windows PowerShell. Po zakończeniu działania skryptu programu PowerShell program udostępnia wartości potrzebne do skonfigurowania modułu Finance Insights. 

> [!NOTE]
> Otwórz program PowerShell na komputerze, aby uruchomić skrypt. Może być potrzebny program PowerShell w wersji 5. Opcja „Wypróbuj to" interfejsu wierszu polecenia Microsoft Azure może nie działać.

# <a name="manual-configuration-steps"></a>[Procedura ręcznego konfigurowania](#tab/configuration-steps)

1. Otwórz the [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com/) i wykonaj następujące kroki, aby utworzyć nowe środowisko Common Data Service w tym samym dzierżawcy Active Directory:

    1. Otwórz stronę **Środowiska**.

        [![Strona Środowiska](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Wybierz opcję **Nowe środowisko**.
    3. W polu **Typ** wybierz opcję **Piaskownica**.
    4. Ustaw wartość opcji **Utwórz bazę danych** na **Tak**.
    5. Wybierz pozycję **Następny**.
    6. Wybierz język i walutę organizacji.
    7. Zaakceptuj wartości domyślne wszystkich pozostałych pól.
    8. Wybierz opcję **Zapisz**.
    9. Odśwież stronę **Środowiska**.
    10. Poczekaj, aż wartość pola **Stan** zostanie zaktualizowana na **Gotowe**.
    11. Zanotuj identyfikator organizacji Common Data Service.
    12. Wybierz środowisko, a następnie wybierz **Ustawienia**.
    13. Wybierz **Zasoby \> Wszystkie ustawienia starego typu**.
    14. Na górnym pasku nawigacyjnym wybierz opcję **Ustawienia**, a następnie wybierz opcję **Dostosowania**.
    15. Wybierz **Zasoby deweloperskie**.
    16. W polu **Identyfikator informacji referencyjnej wystąpienia** określ wartość identyfikatora organizacji Common Data Service, który został zanotowany wcześniej.
    17. Zanotuj adres URL organizacji Common Data Service z paska adresu przeglądarki. Może to być na przykład adres URL `https://org42b2b3d3.crm.dynamics.com`.

2. Jeśli planowane jest użycie funkcji prognoz przepływów pieniężnych lub funkcji prognoz budżetu, należy wykonać następujące kroki w celu zaktualizowania limitu adnotacji dla organizacji na co najmniej 50 megabajtów (MB):

    1. Otwórz portal [Power Apps](https://make.powerapps.com).
    2. Wybierz nowo utworzone środowisko, a następnie wybierz **Ustawienia zaawansowane**.
    3. Wybierz **Ustawienia \> Konfiguracja poczty e-mail**.
    4. Zmień wartość w polu **Maksymalny rozmiar pliku** na **51 200**. (Wartość jest wyrażona w kilobajtach \[KB\]).
    5. Wybierz przycisk **OK**, aby zapisać zmiany.

# <a name="windows-powershell-configuration-script"></a>[Skrypt konfiguracji programu Windows PowerShell](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a>Konfigurowanie ustawień platformy Azure

### <a name="enter-the-common-data-service-directory-id-and-the-users-azure-ad-object-id"></a>Wprowadź Identyfikator katalogu Common Data Service i identyfikator obiektu Azure AD użytkownika.

1. Wprowadź identyfikator katalogu Common Data Service:

    1. Otwórz [portal Azure](https://portal.azure.com).
    2. Zaloguj się przy użyciu identyfikatora użytkownika, który został użyty do utworzenia środowiska Common Data Service.
    3. Przejdź do **Azure Active Directory**.
    4. Umożliwia skopiowanie wartości **Identyfikator dzierżawcy**.

2. Wprowadź identyfikator obiektu Azure Active Directory (Azure AD) użytkownika:

    1. W [portalu Azure](https://portal.azure.com) przejdź do okna **Użytkownicy** i wyszukaj użytkownika na podstawie adresu e-mail.
    2. Zaznacz nazwę użytkownika.
    3. Skopiuj wartość **Identyfikator obiektu**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Korzystanie ze skryptu programu Windows PowerShell](#tab/use-a-powershell-script)

Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake). Jeśli wolisz przeprowadzić ręczną konfigurację, pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).

> [!NOTE]
> Wykonaj poniższe kroki, aby uruchomić skrypt programu PowerShell. Opcja „Wypróbuj to" interfejsu wierszu polecenia Azure może nie działać, podobnie jak wykonywanie skryptu na komputerze.

Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki. Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD. Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure. Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.
2. Wybierz opcję **PowerShell**.
3. Jeśli zostanie wyświetlony odpowiedni monit, utwórz magazyn. Następnie przekaż skrypt programu Windows PowerShell do sesji.
4. Uruchom skrypt.
5. Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.
6. Korzystając z informacji z wyników skryptu, zainstaluj dodatek **Eksport do Data Lake** w LCS.
7. Za pomocą informacji z wyników skryptu można włączyć magazyn jednostek na stronie **Połączenia danych** w module Finance (**Administrowanie systemem \> Parametry systemu \> Połączenia danych**).

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
> Należy się upewnić, że następujące zasoby są tworzone w tym samym wystąpieniu Azure AD, co środowisko Common Data Service. Nie można użyć zasobów z innego wystąpienia Azure AD.

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
    $defaultSecretExpiryInYear = 1

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

    $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (blank for default)")
    if ($subscriptionId.Trim() -ne '') {
        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }

    $resourceGroupName = (Read-Host -Prompt "Enter the Azure Resource Group name: (blank for 'FinanceDataLake')")
    if ($null -eq $resourceGroupName -or $resourceGroupName.Trim() -eq '') {
        $resourceGroupName = 'FinanceDataLake'
    }
    $resourceGroup = Get-AzResourceGroup -Name $resourceGroupName -ErrorAction SilentlyContinue

    if (-not ($resourceGroup)) {
        $resourceLocation = ''
        $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
        while ($resourceLocation.Trim() -eq '' -or (-not ($resourceLocation -in $azResourceLocations))) {
            $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
            if ($resourceLocation -eq 'help') {
                $azResourceLocations
                $resourceLocation = ''
            }
        }
        $resourceGroup = New-AzResourceGroup -Name $resourceGroupName -Location $resourceLocation
    }
    else {
        $resourceLocation = $resourceGroup.Location
    }

    $clientAppName = (Read-Host -Prompt "Enter the name of the application registration: (blank for 'Finance Data Lake Application')")
    if ($clientAppName.Trim() -eq '') {
        $clientAppName = 'Finance Data Lake Application'
    }

    Write-Output '================================================================================='

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    $MicrosoftDynamicsERPMicroservicesAppObjectId = $service.ObjectId

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesCDSAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Format-Table -AutoSize
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    $aibuilderAuthorizationServiceObjectId = $service.ObjectId

    Write-Output '================================================================================='

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $clientAppName + "'")
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

        $clientApp = New-AzureADApplication -DisplayName $clientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($clientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $clientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($defaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    $deployment = New-AzResourceGroupDeployment -ResourceGroupName $resourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId

    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $resourceGroupName)
    }

    Write-Output '================================================================================='

    $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
    Write-Output "Values for LCS Data Lake Add-In:"
    Write-Output ("  Tenant ID:                         " + $subscriptionContext.Context.Subscription.TenantId)
    Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
    Write-Output "  Storage account secret name:       storage-account-name"
    Write-Output "  Application ID secret name:        app-id"
    Write-Output "  Application Secret secret name:    app-secret"
    Write-Warning "Copy this information for the LCS Add-in as it is not saved. Azure Cloud Shell will eventually time out and close."

    Write-Output '================================================================================='
    Write-Output "Values for System parameters > Data connections:"
    Write-Output ("  Application ID:                    " + $clientAppId)
    Write-Output ("  Application Secret:                " + $ClientAppSecret)
    Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
    Write-Output "  Secret name:                       storage-account-connection-string"
    Write-Warning "Copy this information for the System parameters as it is not saved. Azure Cloud Shell will eventually time out and close."
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
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message
  Write-Warning $_.Exception.StackTrace
  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}

```
---

## <a name="configure-the-entity-store"></a>Konfigurowanie magazynu jednostek

Aby skonfigurować magazyn jednostek w środowisku Finance, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu \> Połączenia danych**.
2. Zmień ustawienie opcji **Włącz integrację Data Lake** na **Tak**.
3. Ustaw następujące pola magazynu kluczy:

    - **Identyfikator aplikacji (klienta)** — wprowadź utworzony wcześniej identyfikator klienta aplikacji.
    - **Wpis tajny aplikacji** — wprowadź wpis tajny zapisany dla utworzonej wcześniej aplikacji.
    - **Nazwa DNS** — nazwa systemu DNS (Domain Name System) znajduje się na stronie szczegółów aplikacji dla utworzonej wcześniej aplikacji.
    - **Nazwa wpisu tajnego** — wprowadź **storage-account-connection-string**.

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
    | Adres URL organizacji CDS                                     | Adres URL organizacji Common Data Service wystąpienia Common Data Service. Aby znaleźć tę wartość, otwórz [Portal Power Apps](https://make.powerapps.com), naciśnij przycisk **Ustawienia** (symbol narzędzia) w górnym prawym górnym rogu, wybierz opcję **Ustawienia zaawansowane** i skopiuj adres URL. (Adres URL kończy się na „dynamics.com”). |
    | Identyfikator organizacji CDS                                               | Identyfikator środowiska wystąpienia Common Data Service. Aby znaleźć tę wartość, otwórz [Portal Power Apps](https://make.powerapps.com), naciśnij przycisk **Ustawienia** (symbol narzędzia) w górnym prawym górnym rogu, wybierz opcję **Dostosowania \> Zasoby deweloperskie \> Informacje referencyjne wystąpienia** i skopiuj wartość **Identyfikator**. |
    | Identyfikator dzierżawcy CDS (identyfikator katalogu z AAD)               | Identyfikator dzierżawcy wystąpienia Common Data Service. Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**. |
    | Podaj identyfikator obiektu użytkownika, który ma rolę administratora systemu | Identyfikator obiektu użytkownika Azure AD w programie Common Data Service. Ten użytkownik musi być administratorem wystąpienia Common Data Service. Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź **Azure Active Directory \> Użytkownicy**, wybierz użytkownika, a następnie w sekcji **Tożsamość** skopiuj wartość **Identyfikator obiektu**. |
    | Czy to jest domyślne środowisko CDS dla dzierżawcy?      | To pole wyboru należy zaznaczyć, jeśli wystąpienie Common Data Service było pierwszym wystąpieniem produkcyjnym, które zostało utworzone. Jeśli wystąpienie Common Data Service zostało utworzone ręcznie, należy wyczyścić to pole wyboru. |

## <a name="feedback-and-support"></a>Opinie i pomoc techniczna

Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com).

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]