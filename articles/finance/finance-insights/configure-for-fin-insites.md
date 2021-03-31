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
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cf29e3c05f9fdcc685017a4c640ef32c40989c73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208564"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="dd28c-103">Konfiguracja korzystania z modułu Finance Insights (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="dd28c-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="dd28c-104">Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Microsoft Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="dd28c-105">W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="dd28c-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="dd28c-106">Wdrażanie Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="dd28c-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="dd28c-107">Aby wdrożyć środowiska, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="dd28c-108">W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="dd28c-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="dd28c-109">Środowisko wymaga wersji aplikacji 10.0.11/Platform Update 35 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="dd28c-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="dd28c-110">Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="dd28c-111">(Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="dd28c-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="dd28c-112">Jeśli są używane dane demonstracyjne firmy Contoso, potrzebne będą dodatkowe przykładowe dane, aby korzystać z funkcji prognoz płatności od odbiorców, prognoz przepływów pieniężnych oraz prognoz budżetu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="dd28c-113">Skonfiguruj usługę Dataverse</span><span class="sxs-lookup"><span data-stu-id="dd28c-113">Configure Dataverse</span></span>

<span data-ttu-id="dd28c-114">Można wykonać następującą procedurę ręcznego konfigurowania lub przyspieszyć proces konfigurowania, korzystając z dostarczonego skryptu programu Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd28c-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="dd28c-115">Po zakończeniu działania skryptu programu PowerShell program udostępnia wartości potrzebne do skonfigurowania modułu Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="dd28c-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="dd28c-116">Otwórz program PowerShell na komputerze, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="dd28c-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="dd28c-117">Może być potrzebny program PowerShell w wersji 5.</span><span class="sxs-lookup"><span data-stu-id="dd28c-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="dd28c-118">Opcja „Wypróbuj to" interfejsu wierszu polecenia Microsoft Azure może nie działać.</span><span class="sxs-lookup"><span data-stu-id="dd28c-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="dd28c-119">Procedura ręcznego konfigurowania</span><span class="sxs-lookup"><span data-stu-id="dd28c-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="dd28c-120">Otwórz the [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com/) i wykonaj następujące kroki, aby utworzyć nowe środowisko Dataverse w tym samym dzierżawcy Active Directory:</span><span class="sxs-lookup"><span data-stu-id="dd28c-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="dd28c-121">Otwórz stronę **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="dd28c-122">[![Strona Środowiska](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="dd28c-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="dd28c-123">Wybierz opcję **Nowe środowisko**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="dd28c-124">W polu **Typ** wybierz opcję **Piaskownica**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="dd28c-125">Ustaw wartość opcji **Utwórz bazę danych** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="dd28c-126">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-126">Select **Next**.</span></span>
    6. <span data-ttu-id="dd28c-127">Wybierz język i walutę organizacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="dd28c-128">Zaakceptuj wartości domyślne wszystkich pozostałych pól.</span><span class="sxs-lookup"><span data-stu-id="dd28c-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="dd28c-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-129">Select **Save**.</span></span>
    9. <span data-ttu-id="dd28c-130">Odśwież stronę **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="dd28c-131">Poczekaj, aż wartość pola **Stan** zostanie zaktualizowana na **Gotowe**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="dd28c-132">Zanotuj identyfikator organizacji Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="dd28c-133">Wybierz środowisko, a następnie wybierz **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="dd28c-134">Wybierz **Zasoby \> Wszystkie ustawienia starego typu**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="dd28c-135">Na górnym pasku nawigacyjnym wybierz opcję **Ustawienia**, a następnie wybierz opcję **Dostosowania**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="dd28c-136">Wybierz **Zasoby deweloperskie**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="dd28c-137">W polu **Identyfikator informacji referencyjnej wystąpienia** określ wartość identyfikatora organizacji Dataverse, który został zanotowany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="dd28c-137">Set the **Instance Reference Information ID** field to the Dataverse organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="dd28c-138">Zanotuj adres URL organizacji Dataverse z paska adresu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="dd28c-139">Może to być na przykład adres URL `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="dd28c-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="dd28c-140">Jeśli planowane jest użycie funkcji prognoz przepływów pieniężnych lub funkcji prognoz budżetu, należy wykonać następujące kroki w celu zaktualizowania limitu adnotacji dla organizacji na co najmniej 50 megabajtów (MB):</span><span class="sxs-lookup"><span data-stu-id="dd28c-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="dd28c-141">Otwórz portal [Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="dd28c-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="dd28c-142">Wybierz nowo utworzone środowisko, a następnie wybierz **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="dd28c-143">Wybierz **Ustawienia \> Konfiguracja poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="dd28c-144">Zmień wartość w polu **Maksymalny rozmiar pliku** na **51 200**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="dd28c-145">(Wartość jest wyrażona w kilobajtach \[KB\]).</span><span class="sxs-lookup"><span data-stu-id="dd28c-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="dd28c-146">Wybierz przycisk **OK**, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="dd28c-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="dd28c-147">Skrypt konfiguracji programu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd28c-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

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

## <a name="configure-the-azure-setup"></a><span data-ttu-id="dd28c-148">Konfigurowanie ustawień platformy Azure</span><span class="sxs-lookup"><span data-stu-id="dd28c-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="dd28c-149">Wprowadź Identyfikator katalogu Dataverse i identyfikator obiektu Azure AD użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dd28c-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="dd28c-150">Wprowadź identyfikator katalogu Dataverse:</span><span class="sxs-lookup"><span data-stu-id="dd28c-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="dd28c-151">Otwórz [portal Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="dd28c-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="dd28c-152">Zaloguj się przy użyciu identyfikatora użytkownika, który został użyty do utworzenia środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="dd28c-153">Przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="dd28c-154">Umożliwia skopiowanie wartości **Identyfikator dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="dd28c-155">Wprowadź identyfikator obiektu Azure Active Directory (Azure AD) użytkownika:</span><span class="sxs-lookup"><span data-stu-id="dd28c-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="dd28c-156">W [portalu Azure](https://portal.azure.com) przejdź do okna **Użytkownicy** i wyszukaj użytkownika na podstawie adresu e-mail.</span><span class="sxs-lookup"><span data-stu-id="dd28c-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="dd28c-157">Zaznacz nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="dd28c-157">Select the user's name.</span></span>
    3. <span data-ttu-id="dd28c-158">Skopiuj wartość **Identyfikator obiektu**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="dd28c-159">Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights</span><span class="sxs-lookup"><span data-stu-id="dd28c-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="dd28c-160">Korzystanie ze skryptu programu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd28c-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="dd28c-161">Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="dd28c-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="dd28c-162">Jeśli wolisz przeprowadzić ręczną konfigurację, pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="dd28c-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="dd28c-163">Wykonaj poniższe kroki, aby uruchomić skrypt programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd28c-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="dd28c-164">Opcja „Wypróbuj to" interfejsu wierszu polecenia Azure może nie działać, podobnie jak wykonywanie skryptu na komputerze.</span><span class="sxs-lookup"><span data-stu-id="dd28c-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="dd28c-165">Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="dd28c-166">Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd28c-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="dd28c-167">Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="dd28c-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="dd28c-168">W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure.</span><span class="sxs-lookup"><span data-stu-id="dd28c-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="dd28c-169">Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="dd28c-170">Wybierz opcję **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="dd28c-171">Jeśli zostanie wyświetlony odpowiedni monit, utwórz magazyn.</span><span class="sxs-lookup"><span data-stu-id="dd28c-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="dd28c-172">Następnie przekaż skrypt programu Windows PowerShell do sesji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="dd28c-173">Uruchom skrypt.</span><span class="sxs-lookup"><span data-stu-id="dd28c-173">Run the script.</span></span>
5. <span data-ttu-id="dd28c-174">Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="dd28c-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="dd28c-175">Korzystając z informacji z wyników skryptu, zainstaluj dodatek **Eksport do Data Lake** w LCS.</span><span class="sxs-lookup"><span data-stu-id="dd28c-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="dd28c-176">Za pomocą informacji z wyników skryptu można włączyć magazyn jednostek na stronie **Połączenia danych** w module Finance (**Administrowanie systemem \> Parametry systemu \> Połączenia danych**).</span><span class="sxs-lookup"><span data-stu-id="dd28c-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="dd28c-177">Konfiguracja ręczna</span><span class="sxs-lookup"><span data-stu-id="dd28c-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="dd28c-178">Dodawanie aplikacji do dzierżawcy Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd28c-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="dd28c-179">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="dd28c-180">Wybierz **Zarządzaj \> Aplikacje dla przedsiębiorstw**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="dd28c-181">Wyszukaj następujące aplikacje na podstawie identyfikatora aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="dd28c-182">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="dd28c-182">Application</span></span>                              | <span data-ttu-id="dd28c-183">Identyfikator aplikacji</span><span class="sxs-lookup"><span data-stu-id="dd28c-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="dd28c-184">Mikrousługi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="dd28c-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="dd28c-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="dd28c-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="dd28c-186">CDS mikrousług ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="dd28c-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="dd28c-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="dd28c-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="dd28c-188">Usługa autoryzacji AI Builder</span><span class="sxs-lookup"><span data-stu-id="dd28c-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="dd28c-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="dd28c-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="dd28c-190">Jeśli nie możesz znaleźć dowolnej z tych aplikacji, spróbuj wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="dd28c-191">Na komputerze lokalnym naciśnij menu **Start** i wyszukaj program **powershell**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="dd28c-192">Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) program **Windows PowerShell**, a następnie wybierz polecenie **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="dd28c-193">Uruchom następujące polecenie, aby zainstalować moduł **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="dd28c-194">Jeśli dostawca NuGet jest wymagany, aby kontynuować, wybierz opcję **Y**, aby go zainstalować.</span><span class="sxs-lookup"><span data-stu-id="dd28c-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="dd28c-195">Jeśli zostanie wyświetlony komunikat „Niezaufane repozytorium”, wybierz opcję **Y**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="dd28c-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="dd28c-196">Dla każdej aplikacji, która musi zostać dodana, należy uruchomić następujące polecenia, aby dodać aplikację do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd28c-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="dd28c-197">Po wyświetleniu monitu zaloguj się jako administrator Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd28c-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="dd28c-198">Tworzenie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="dd28c-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="dd28c-199">Należy się upewnić, że następujące zasoby są tworzone w tym samym wystąpieniu Azure AD, co środowisko Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="dd28c-200">Nie można użyć zasobów z innego wystąpienia Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd28c-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="dd28c-201">Tworzenie nowego konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="dd28c-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="dd28c-202">W [portalu Azure](https://portal.azure.com) utwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="dd28c-203">W oknie dialogowym **Utwórz konto magazynu** ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="dd28c-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="dd28c-204">**Lokalizacja** — umożliwia wybór centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="dd28c-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="dd28c-205">**Wydajność** — zaleca się, aby w wybrać opcję **Standardowa**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="dd28c-206">**Rodzaj konta** — musisz wybrać **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="dd28c-207">W oknie dialogowym **Opcje zaawansowane**, jako wartość opcji **Data Lake Storage Gen2** wybierz **Włącz** w obszarze funkcji **Hierarchiczne przestrzenie nazw**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="dd28c-208">Jeśli ta funkcja zostanie wyłączona, nie będzie można używać danych, które aplikacje Finance and Operations zapisują przy użyciu usług, takich jak przepływy danych Power BI.</span><span class="sxs-lookup"><span data-stu-id="dd28c-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="dd28c-209">Wybierz opcję **Przejrzyj i utwórz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-209">Select **Review and create**.</span></span> <span data-ttu-id="dd28c-210">Po zakończeniu wdrażania nowy zasób zostanie wyświetlony w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="dd28c-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="dd28c-211">Przejdź do utworzonego konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="dd28c-212">W menu po lewej stronie wybierz **Klucze dostępu**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="dd28c-213">Skopiuj i zapisz parametry połączenia **Klucza1** lub **Klucza2**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="dd28c-214">Skopiuj i zapisz nazwę konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="dd28c-215">Utwórz nowy magazyn kluczy:</span><span class="sxs-lookup"><span data-stu-id="dd28c-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="dd28c-216">W [portalu Azure](https://portal.azure.com) utwórz magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="dd28c-217">W oknie dialogowym **Utwórz magazyn kluczy**, w polu **Lokalizacja** wybierz centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="dd28c-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="dd28c-218">Po utworzeniu magazynu kluczy wybierz go z listy, a następnie wybierz opcję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="dd28c-219">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="dd28c-220">W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="dd28c-221">Wprowadź nazwę wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="dd28c-221">Enter a name for the secret.</span></span> <span data-ttu-id="dd28c-222">Zanotuj nazwę, ponieważ później będzie musiała zostać podana.</span><span class="sxs-lookup"><span data-stu-id="dd28c-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="dd28c-223">W polu **Wartość** wprowadź parametry połączenia uzyskane z konta magazynu w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="dd28c-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="dd28c-224">Wybierz opcję **Włączone**, a następnie opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="dd28c-225">Wpis tajny został utworzony i dodany do magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="dd28c-226">Przejdź do strony **Przegląd magazynu kluczy** i zanotuj nazwę DNS.</span><span class="sxs-lookup"><span data-stu-id="dd28c-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="dd28c-227">Utwórz i zarejestruj aplikację Azure AD:</span><span class="sxs-lookup"><span data-stu-id="dd28c-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="dd28c-228">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory** i wybierz opcję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="dd28c-229">Wybierz opcję **Nowa rejestracja aplikacji** i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="dd28c-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="dd28c-230">**Nazwa** — Wprowadź nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="dd28c-231">**Typ aplikacji** — wybierz **internetowy interfejs API**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="dd28c-232">**Ustawienia URI przekierowania** — wprowadź adres URL wystąpienia Dynamics 365, jak `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="dd28c-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="dd28c-233">Przejdź do właśnie utworzonej aplikacji, a następnie skopiuj i zapisz jej wartość **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="dd28c-234">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="dd28c-235">Przejdź do okna **Uprawnienia do interfejsu API** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dd28c-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="dd28c-236">Wybierz opcję **Dodaj uprawnienie**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="dd28c-237">Wybierz **Magazyn kluczy Azure**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="dd28c-238">Po wybraniu uprawnień delegowanych wybierz opcję **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="dd28c-239">Wybierz opcję **Dodaj uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="dd28c-240">W menu aplikacji wybierz pozycję **Certyfikaty i tajne wpisy**, a następnie wykonaj następujące kroki, aby utworzyć wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="dd28c-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="dd28c-241">Wybierz **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="dd28c-242">W polu **Opis klucza** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="dd28c-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="dd28c-243">Wybierz czas trwania, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="dd28c-244">Wpis tajny jest generowany w polu **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="dd28c-245">Skopiuj i zapisz wartość wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="dd28c-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="dd28c-246">Utwórz wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="dd28c-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="dd28c-247">Przejdź do utworzonego wcześniej magazynu kluczy i wybierz opcję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="dd28c-248">Z każdą nazwą wpisu tajnego w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dd28c-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="dd28c-249">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="dd28c-250">W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="dd28c-251">Utwórz nazwę i wartość wpisu tajnego z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd28c-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="dd28c-252">Wybierz opcję **Włączone**, a następnie opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="dd28c-253">Wpis tajny został utworzony i dodany do magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="dd28c-254">Nazwa wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="dd28c-254">Secret name</span></span>                       | <span data-ttu-id="dd28c-255">Wartość wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="dd28c-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="dd28c-256">app-id</span><span class="sxs-lookup"><span data-stu-id="dd28c-256">app-id</span></span>                            | <span data-ttu-id="dd28c-257">Identyfikator aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="dd28c-258">app-secret</span><span class="sxs-lookup"><span data-stu-id="dd28c-258">app-secret</span></span>                        | <span data-ttu-id="dd28c-259">Klucz tajny klienta, który został wcześniej zapisany</span><span class="sxs-lookup"><span data-stu-id="dd28c-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="dd28c-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="dd28c-260">storage-account-name</span></span>              | <span data-ttu-id="dd28c-261">Nazwa utworzonego wcześniej konta magazynu, na przykład **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="dd28c-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="dd28c-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="dd28c-262">storage-account-connection-string</span></span> | <span data-ttu-id="dd28c-263">Parametry połączenia skopiowane z strony **Klucze dostępu** konta magazynu</span><span class="sxs-lookup"><span data-stu-id="dd28c-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="dd28c-264">Autoryzuj aplikację, aby mogła uzyskać dostęp do magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="dd28c-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="dd28c-265">W [portalu Azure](https://portal.azure.com) otwórz utworzony wcześniej magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="dd28c-266">Wybierz zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-266">Select the access policies.</span></span>
    3. <span data-ttu-id="dd28c-267">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dd28c-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="dd28c-268">Wybierz pozycję **Dodaj zasady dostępu**, aby utworzyć zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="dd28c-269">W polu **Uprawnienia wpisu tajnego** wybierz uprawnienia z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd28c-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="dd28c-270">W polu **Wybierz główne** wyszukaj nazwę wyświetlaną aplikacji z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd28c-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="dd28c-271">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-271">Select **Select**.</span></span>
        5. <span data-ttu-id="dd28c-272">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-272">Select **Add**.</span></span>
        6. <span data-ttu-id="dd28c-273">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-273">Select **Save**.</span></span>

        | <span data-ttu-id="dd28c-274">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="dd28c-274">Application</span></span>                                              | <span data-ttu-id="dd28c-275">Uprawnienia</span><span class="sxs-lookup"><span data-stu-id="dd28c-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="dd28c-276">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-276">The display name of the new application that you created</span></span> | <span data-ttu-id="dd28c-277">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="dd28c-277">Get, List</span></span>   |
        | <span data-ttu-id="dd28c-278">**Mikrousługi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="dd28c-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="dd28c-279">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="dd28c-279">Get, List</span></span>   |

6. <span data-ttu-id="dd28c-280">Przypisz role, aby uzyskać dostęp do konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="dd28c-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="dd28c-281">W [portalu Azure](https://portal.azure.com) otwórz utworzone wcześniej konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="dd28c-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="dd28c-282">Wybierz pozycję **Kontrola dostępu (IAM)**, a następnie wybierz **Przypisania ról**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="dd28c-283">Wybierz **Dodaj, Dodaj przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="dd28c-284">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dd28c-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="dd28c-285">Wybierz rolę z następującej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd28c-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="dd28c-286">Pozostaw ustawienie pola **Przypisz dostęp do** jako **Użytkownik, grupa lub nazwa główna usługi Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="dd28c-287">W polu **Wybierz** wprowadź aplikację z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="dd28c-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="dd28c-288">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-288">Select **Save**.</span></span>

        | <span data-ttu-id="dd28c-289">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="dd28c-289">Application</span></span>                                              | <span data-ttu-id="dd28c-290">Rola</span><span class="sxs-lookup"><span data-stu-id="dd28c-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="dd28c-291">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-291">The display name of the new application that you created</span></span> | <span data-ttu-id="dd28c-292">Właściciel</span><span class="sxs-lookup"><span data-stu-id="dd28c-292">Owner</span></span>                       |
        | <span data-ttu-id="dd28c-293">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-293">The display name of the new application that you created</span></span> | <span data-ttu-id="dd28c-294">Osoba wpłacająca</span><span class="sxs-lookup"><span data-stu-id="dd28c-294">Contributor</span></span>                 |
        | <span data-ttu-id="dd28c-295">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-295">The display name of the new application that you created</span></span> | <span data-ttu-id="dd28c-296">Współautor konta magazynu</span><span class="sxs-lookup"><span data-stu-id="dd28c-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="dd28c-297">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="dd28c-297">The display name of the new application that you created</span></span> | <span data-ttu-id="dd28c-298">Właściciel danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="dd28c-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="dd28c-299">**Usługa autoryzacji AI Builder**</span><span class="sxs-lookup"><span data-stu-id="dd28c-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="dd28c-300">Czytelnik danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="dd28c-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="dd28c-301">Interfejs wiersza polecenia Azure</span><span class="sxs-lookup"><span data-stu-id="dd28c-301">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-entity-store"></a><span data-ttu-id="dd28c-302">Konfigurowanie magazynu jednostek</span><span class="sxs-lookup"><span data-stu-id="dd28c-302">Configure the entity store</span></span>

<span data-ttu-id="dd28c-303">Aby skonfigurować magazyn jednostek w środowisku Finance, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="dd28c-304">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu \> Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="dd28c-305">Zmień ustawienie opcji **Włącz integrację Data Lake** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="dd28c-306">Ustaw następujące pola magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="dd28c-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="dd28c-307">**Identyfikator aplikacji (klienta)** — wprowadź utworzony wcześniej identyfikator klienta aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="dd28c-308">**Wpis tajny aplikacji** — wprowadź wpis tajny zapisany dla utworzonej wcześniej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="dd28c-309">**Nazwa DNS** — nazwa systemu DNS (Domain Name System) znajduje się na stronie szczegółów aplikacji dla utworzonej wcześniej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="dd28c-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="dd28c-310">**Nazwa wpisu tajnego** — wprowadź **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="dd28c-311">Konfigurowanie data lake</span><span class="sxs-lookup"><span data-stu-id="dd28c-311">Configure the data lake</span></span>

<span data-ttu-id="dd28c-312">Aby dodać dodatek Azure Data Lake do środowiska, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="dd28c-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="dd28c-313">Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="dd28c-314">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="dd28c-315">Wybierz dodatek **Eksport do Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="dd28c-316">Wprowadź następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="dd28c-316">Enter the following values.</span></span>

    | <span data-ttu-id="dd28c-317">Wartość</span><span class="sxs-lookup"><span data-stu-id="dd28c-317">Value</span></span>                                                              | <span data-ttu-id="dd28c-318">opis</span><span class="sxs-lookup"><span data-stu-id="dd28c-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="dd28c-319">Identyfikator dzierżawcy subskrypcji Azure, w której znajduje się magazyn kluczy</span><span class="sxs-lookup"><span data-stu-id="dd28c-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="dd28c-320">Identyfikator dzierżawcy, w którym znajdują się konto magazynu, aplikacje i magazyny kluczy.</span><span class="sxs-lookup"><span data-stu-id="dd28c-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="dd28c-321">Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="dd28c-322">Podaj nazwę DNS usługi Key Vault</span><span class="sxs-lookup"><span data-stu-id="dd28c-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="dd28c-323">Nazwa DNS magazynu kluczy, np. `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="dd28c-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="dd28c-324">(Wartość ta pokrywa się z nazwą DNS używaną w magazynie jednostek).</span><span class="sxs-lookup"><span data-stu-id="dd28c-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="dd28c-325">Podaj wpis tajny zawierający nazwę konta magazynu</span><span class="sxs-lookup"><span data-stu-id="dd28c-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="dd28c-326">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="dd28c-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="dd28c-327">Nazwa wpisu tajnego identyfikatora aplikacji, który będzie używany w celu uzyskania dostępu do Data Lake</span><span class="sxs-lookup"><span data-stu-id="dd28c-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="dd28c-328">**app-id**</span><span class="sxs-lookup"><span data-stu-id="dd28c-328">**app-id**</span></span> |
    | <span data-ttu-id="dd28c-329">Nazwa wpisu tajnego do używania z identyfikatorem aplikacji</span><span class="sxs-lookup"><span data-stu-id="dd28c-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="dd28c-330">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="dd28c-330">**app-secret**</span></span> |

5. <span data-ttu-id="dd28c-331">Zaakceptuj warunki i wybierz opcję **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="dd28c-332">Dodatek zostanie zainstalowany w ciągu kilku minut.</span><span class="sxs-lookup"><span data-stu-id="dd28c-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="dd28c-333">Konfigurowanie AI Builder</span><span class="sxs-lookup"><span data-stu-id="dd28c-333">Configure AI Builder</span></span>

1. <span data-ttu-id="dd28c-334">Zaloguj się do LCS i otwórz stronę **Szczegóły środowiska**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="dd28c-335">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="dd28c-336">Powinny zostać wyświetlone dodatki, które są już zainstalowane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="dd28c-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="dd28c-337">Jeśli nie ma wśród nich dodatku **Eksport do Data Lake**, skonfiguruj ten dodatek.</span><span class="sxs-lookup"><span data-stu-id="dd28c-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="dd28c-338">Wybierz dodatek **Pobierz szczegółowe dane**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="dd28c-339">Na stronie szczegółów dodatku **Pobierz szczegółowe analizy** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="dd28c-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="dd28c-340">Wartość</span><span class="sxs-lookup"><span data-stu-id="dd28c-340">Value</span></span>                                                    | <span data-ttu-id="dd28c-341">opis</span><span class="sxs-lookup"><span data-stu-id="dd28c-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="dd28c-342">Adres URL organizacji CDS</span><span class="sxs-lookup"><span data-stu-id="dd28c-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="dd28c-343">Adres URL organizacji Dataverse wystąpienia Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-343">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="dd28c-344">Aby znaleźć tę wartość, otwórz [Portal Power Apps](https://make.powerapps.com), naciśnij przycisk **Ustawienia** (symbol narzędzia) w górnym prawym górnym rogu, wybierz opcję **Ustawienia zaawansowane** i skopiuj adres URL.</span><span class="sxs-lookup"><span data-stu-id="dd28c-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="dd28c-345">(Adres URL kończy się na „dynamics.com”).</span><span class="sxs-lookup"><span data-stu-id="dd28c-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="dd28c-346">Identyfikator organizacji CDS</span><span class="sxs-lookup"><span data-stu-id="dd28c-346">CDS Org ID</span></span>                                               | <span data-ttu-id="dd28c-347">Identyfikator środowiska wystąpienia Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-347">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="dd28c-348">Aby znaleźć tę wartość, otwórz [Portal Power Apps](https://make.powerapps.com), naciśnij przycisk **Ustawienia** (symbol narzędzia) w górnym prawym górnym rogu, wybierz opcję **Dostosowania \> Zasoby deweloperskie \> Informacje referencyjne wystąpienia** i skopiuj wartość **Identyfikator**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="dd28c-349">Identyfikator dzierżawcy CDS (identyfikator katalogu z AAD)</span><span class="sxs-lookup"><span data-stu-id="dd28c-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="dd28c-350">Identyfikator dzierżawcy wystąpienia Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-350">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="dd28c-351">Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="dd28c-352">Podaj identyfikator obiektu użytkownika, który ma rolę administratora systemu</span><span class="sxs-lookup"><span data-stu-id="dd28c-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="dd28c-353">Identyfikator obiektu użytkownika Azure AD w programie Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-353">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="dd28c-354">Ten użytkownik musi być administratorem wystąpienia Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dd28c-354">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="dd28c-355">Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź **Azure Active Directory \> Użytkownicy**, wybierz użytkownika, a następnie w sekcji **Tożsamość** skopiuj wartość **Identyfikator obiektu**.</span><span class="sxs-lookup"><span data-stu-id="dd28c-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="dd28c-356">Czy to jest domyślne środowisko CDS dla dzierżawcy?</span><span class="sxs-lookup"><span data-stu-id="dd28c-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="dd28c-357">To pole wyboru należy zaznaczyć, jeśli wystąpienie Dataverse było pierwszym wystąpieniem produkcyjnym, które zostało utworzone.</span><span class="sxs-lookup"><span data-stu-id="dd28c-357">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="dd28c-358">Jeśli wystąpienie Dataverse zostało utworzone ręcznie, należy wyczyścić to pole wyboru.</span><span class="sxs-lookup"><span data-stu-id="dd28c-358">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="dd28c-359">Opinie i pomoc techniczna</span><span class="sxs-lookup"><span data-stu-id="dd28c-359">Feedback and support</span></span>

<span data-ttu-id="dd28c-360">Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="dd28c-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="dd28c-361">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="dd28c-361">Privacy notice</span></span>

<span data-ttu-id="dd28c-362">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="dd28c-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]