---
title: Konfiguracja korzystania z modułu Finance Insights (wersja zapoznawcza)
description: W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.
author: ShivamPandey-msft
ms.date: 11/25/2020
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
ms.openlocfilehash: 60e4d69157d7b73bd9e47310adae320687230080
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941233"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="b3843-103">Konfiguracja korzystania z modułu Finance Insights (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="b3843-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b3843-104">Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Microsoft Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="b3843-105">W tym temacie objaśniono kroki konfiguracyjne, które umożliwią systemowi korzystanie z funkcji dostępnych w module Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="b3843-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="b3843-106">Wdrażanie Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="b3843-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="b3843-107">Aby wdrożyć środowiska, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b3843-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="b3843-108">W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b3843-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="b3843-109">Środowisko wymaga wersji aplikacji 10.0.11/Platform Update 35 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="b3843-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="b3843-110">Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="b3843-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="b3843-111">(Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="b3843-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="b3843-112">Jeśli są używane dane demonstracyjne firmy Contoso, potrzebne będą dodatkowe przykładowe dane, aby korzystać z funkcji prognoz płatności od odbiorców, prognoz przepływów pieniężnych oraz prognoz budżetu.</span><span class="sxs-lookup"><span data-stu-id="b3843-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="b3843-113">Skonfiguruj usługę Dataverse</span><span class="sxs-lookup"><span data-stu-id="b3843-113">Configure Dataverse</span></span>

<span data-ttu-id="b3843-114">Wykonaj następujące kroki, aby skonfigurować Dataverse for Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="b3843-114">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="b3843-115">Otwórz stronę środowiska w u usługach LCS i sprawdź, czy sekcja **Integracja Power Platform** jest już skonfigurowana.</span><span class="sxs-lookup"><span data-stu-id="b3843-115">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="b3843-116">Jeśli jest już skonfigurowana, na liście powinna znajdować się nazwa środowiska Dataverse połączona ze środowiskiem Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b3843-116">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="b3843-117">Skopiuj nazwę środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b3843-117">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="b3843-118">Jeśli nie jest skonfigurowana, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="b3843-118">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="b3843-119">Wybierz przycisk **Ustawienia** w sekcji Integracja Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b3843-119">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="b3843-120">Skonfigurowanie środowiska może potrwać do godziny.</span><span class="sxs-lookup"><span data-stu-id="b3843-120">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="b3843-121">Gdy środowisko Dataverse zostanie poprawnie skonfigurowane, na liście powinna zostać wyświetlona nazwa środowiska Dataverse połączona ze środowiskiem Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b3843-121">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="b3843-122">Skopiuj nazwę środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b3843-122">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="b3843-123">Po skonfigurowaniu środowiska **NIE należy** wybierać przycisku Łącze do usługi **CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="b3843-123">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="b3843-124">Nie jest to potrzebne w przypadku aplikacji Finance Insights i pozbawiłoby możliwości wykonywania wymaganych dodatków środowiska w usługach LCS.</span><span class="sxs-lookup"><span data-stu-id="b3843-124">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="b3843-125">Otwórz the [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com/) i wykonaj następujące kroki, aby utworzyć nowe środowisko Dataverse w tym samym dzierżawcy Active Directory:</span><span class="sxs-lookup"><span data-stu-id="b3843-125">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="b3843-126">Otwórz stronę **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="b3843-126">Open the **Environments** page.</span></span>

        <span data-ttu-id="b3843-127">[![Strona Środowiska](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="b3843-127">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="b3843-128">Wybierz środowisko Dataverse utworzone powyżej,, a następnie wybierz opcję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="b3843-128">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="b3843-129">Wybierz **Zasoby \> Wszystkie ustawienia starego typu**.</span><span class="sxs-lookup"><span data-stu-id="b3843-129">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="b3843-130">Na górnym pasku nawigacyjnym wybierz opcję **Ustawienia**, a następnie wybierz opcję **Dostosowania**.</span><span class="sxs-lookup"><span data-stu-id="b3843-130">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="b3843-131">Wybierz **Zasoby deweloperskie**.</span><span class="sxs-lookup"><span data-stu-id="b3843-131">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="b3843-132">Umożliwia skopiowanie wartości **Identyfikator organizacji Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="b3843-132">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="b3843-133">Zanotuj adres URL organizacji Dataverse z paska adresu przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="b3843-133">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="b3843-134">Może to być na przykład adres URL `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="b3843-134">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="b3843-135">Jeśli planowane jest użycie funkcji prognoz przepływów pieniężnych lub funkcji prognoz budżetu, należy wykonać następujące kroki w celu zaktualizowania limitu adnotacji dla organizacji na co najmniej 50 megabajtów (MB):</span><span class="sxs-lookup"><span data-stu-id="b3843-135">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="b3843-136">Otwórz portal [Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="b3843-136">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="b3843-137">Wybierz nowo utworzone środowisko, a następnie wybierz **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="b3843-137">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="b3843-138">Wybierz **Ustawienia \> Konfiguracja poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="b3843-138">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="b3843-139">Zmień wartość w polu **Maksymalny rozmiar pliku** na **51 200**.</span><span class="sxs-lookup"><span data-stu-id="b3843-139">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="b3843-140">(Wartość jest wyrażona w kilobajtach \[KB\]).</span><span class="sxs-lookup"><span data-stu-id="b3843-140">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="b3843-141">Wybierz przycisk **OK**, aby zapisać zmiany.</span><span class="sxs-lookup"><span data-stu-id="b3843-141">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="b3843-142">Konfigurowanie ustawień platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b3843-142">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="b3843-143">Wprowadź Identyfikator katalogu Dataverse i identyfikator obiektu Azure AD użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b3843-143">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="b3843-144">Wprowadź identyfikator katalogu Dataverse:</span><span class="sxs-lookup"><span data-stu-id="b3843-144">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="b3843-145">Otwórz [portal Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b3843-145">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="b3843-146">Zaloguj się przy użyciu identyfikatora użytkownika, który został użyty do utworzenia środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b3843-146">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="b3843-147">Przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b3843-147">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="b3843-148">Umożliwia skopiowanie wartości **Identyfikator dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3843-148">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="b3843-149">Wprowadź identyfikator obiektu Azure Active Directory (Azure AD) użytkownika:</span><span class="sxs-lookup"><span data-stu-id="b3843-149">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="b3843-150">W [portalu Azure](https://portal.azure.com) przejdź do okna **Użytkownicy** i wyszukaj użytkownika na podstawie adresu e-mail.</span><span class="sxs-lookup"><span data-stu-id="b3843-150">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="b3843-151">Zaznacz nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b3843-151">Select the user's name.</span></span>
    3. <span data-ttu-id="b3843-152">Skopiuj wartość **Identyfikator obiektu**.</span><span class="sxs-lookup"><span data-stu-id="b3843-152">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="b3843-153">Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights</span><span class="sxs-lookup"><span data-stu-id="b3843-153">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="b3843-154">Korzystanie ze skryptu programu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3843-154">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="b3843-155">Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="b3843-155">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="b3843-156">Jeśli wolisz przeprowadzić ręczną konfigurację, pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="b3843-156">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="b3843-157">Wykonaj poniższe kroki, aby uruchomić skrypt programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3843-157">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="b3843-158">Opcja „Wypróbuj to" interfejsu wierszu polecenia Azure może nie działać, podobnie jak wykonywanie skryptu na komputerze.</span><span class="sxs-lookup"><span data-stu-id="b3843-158">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="b3843-159">Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b3843-159">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="b3843-160">Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3843-160">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="b3843-161">Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="b3843-161">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="b3843-162">W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure.</span><span class="sxs-lookup"><span data-stu-id="b3843-162">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="b3843-163">Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="b3843-163">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="b3843-164">Wybierz opcję **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b3843-164">Select **PowerShell**.</span></span>
3. <span data-ttu-id="b3843-165">Jeśli zostanie wyświetlony odpowiedni monit, utwórz magazyn.</span><span class="sxs-lookup"><span data-stu-id="b3843-165">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="b3843-166">Przejdź do karty **Azure CLI** i wybierz polecenie **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-166">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="b3843-167">Otwórz notatnik i wklej skrypt programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3843-167">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="b3843-168">Zapisz plik jako ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="b3843-168">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="b3843-169">Przekaż skrypt programu Windows PowerShell do sesji, używając opcji menu do przekazania w Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="b3843-169">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="b3843-170">Uruchom skrypt .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="b3843-170">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="b3843-171">Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="b3843-171">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="b3843-172">Korzystając z informacji z wyników skryptu, zainstaluj dodatek **Eksport do Data Lake** w LCS.</span><span class="sxs-lookup"><span data-stu-id="b3843-172">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="b3843-173">Za pomocą informacji z wyników skryptu można włączyć magazyn jednostek na stronie **Połączenia danych** w module Finance (**Administrowanie systemem \> Parametry systemu \> Połączenia danych**).</span><span class="sxs-lookup"><span data-stu-id="b3843-173">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="b3843-174">Konfiguracja ręczna</span><span class="sxs-lookup"><span data-stu-id="b3843-174">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="b3843-175">Dodawanie aplikacji do dzierżawcy Azure AD</span><span class="sxs-lookup"><span data-stu-id="b3843-175">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="b3843-176">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b3843-176">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="b3843-177">Wybierz **Zarządzaj \> Aplikacje dla przedsiębiorstw**.</span><span class="sxs-lookup"><span data-stu-id="b3843-177">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="b3843-178">Wyszukaj następujące aplikacje na podstawie identyfikatora aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-178">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="b3843-179">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="b3843-179">Application</span></span>                              | <span data-ttu-id="b3843-180">Identyfikator aplikacji</span><span class="sxs-lookup"><span data-stu-id="b3843-180">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="b3843-181">Mikrousługi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="b3843-181">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="b3843-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="b3843-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="b3843-183">CDS mikrousług ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="b3843-183">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="b3843-184">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="b3843-184">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="b3843-185">Usługa autoryzacji AI Builder</span><span class="sxs-lookup"><span data-stu-id="b3843-185">AI Builder Authorization Service</span></span>         | <span data-ttu-id="b3843-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="b3843-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="b3843-187">Jeśli nie możesz znaleźć dowolnej z tych aplikacji, spróbuj wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="b3843-187">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="b3843-188">Na komputerze lokalnym naciśnij menu **Start** i wyszukaj program **powershell**.</span><span class="sxs-lookup"><span data-stu-id="b3843-188">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="b3843-189">Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) program **Windows PowerShell**, a następnie wybierz polecenie **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="b3843-189">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="b3843-190">Uruchom następujące polecenie, aby zainstalować moduł **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="b3843-190">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="b3843-191">Jeśli dostawca NuGet jest wymagany, aby kontynuować, wybierz opcję **Y**, aby go zainstalować.</span><span class="sxs-lookup"><span data-stu-id="b3843-191">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="b3843-192">Jeśli zostanie wyświetlony komunikat „Niezaufane repozytorium”, wybierz opcję **Y**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="b3843-192">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="b3843-193">Dla każdej aplikacji, która musi zostać dodana, należy uruchomić następujące polecenia, aby dodać aplikację do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3843-193">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="b3843-194">Po wyświetleniu monitu zaloguj się jako administrator Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3843-194">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="b3843-195">Tworzenie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b3843-195">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="b3843-196">Należy się upewnić, że następujące zasoby są tworzone w tym samym wystąpieniu Azure AD, co środowisko Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b3843-196">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="b3843-197">Nie można użyć zasobów z innego wystąpienia Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3843-197">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="b3843-198">Tworzenie nowego konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="b3843-198">Create a new storage account:</span></span>

    1. <span data-ttu-id="b3843-199">W [portalu Azure](https://portal.azure.com) utwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="b3843-199">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="b3843-200">W oknie dialogowym **Utwórz konto magazynu** ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="b3843-200">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="b3843-201">**Lokalizacja** — umożliwia wybór centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="b3843-201">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="b3843-202">**Wydajność** — zaleca się, aby w wybrać opcję **Standardowa**.</span><span class="sxs-lookup"><span data-stu-id="b3843-202">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="b3843-203">**Rodzaj konta** — musisz wybrać **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="b3843-203">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="b3843-204">W oknie dialogowym **Opcje zaawansowane**, jako wartość opcji **Data Lake Storage Gen2** wybierz **Włącz** w obszarze funkcji **Hierarchiczne przestrzenie nazw**.</span><span class="sxs-lookup"><span data-stu-id="b3843-204">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="b3843-205">Jeśli ta funkcja zostanie wyłączona, nie będzie można używać danych, które aplikacje Finance and Operations zapisują przy użyciu usług, takich jak przepływy danych Power BI.</span><span class="sxs-lookup"><span data-stu-id="b3843-205">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="b3843-206">Wybierz opcję **Przejrzyj i utwórz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-206">Select **Review and create**.</span></span> <span data-ttu-id="b3843-207">Po zakończeniu wdrażania nowy zasób zostanie wyświetlony w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="b3843-207">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="b3843-208">Przejdź do utworzonego konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="b3843-208">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="b3843-209">W menu po lewej stronie wybierz **Klucze dostępu**.</span><span class="sxs-lookup"><span data-stu-id="b3843-209">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="b3843-210">Skopiuj i zapisz parametry połączenia **Klucza1** lub **Klucza2**.</span><span class="sxs-lookup"><span data-stu-id="b3843-210">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="b3843-211">Skopiuj i zapisz nazwę konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="b3843-211">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="b3843-212">Utwórz nowy magazyn kluczy:</span><span class="sxs-lookup"><span data-stu-id="b3843-212">Create a new key vault:</span></span>

    1. <span data-ttu-id="b3843-213">W [portalu Azure](https://portal.azure.com) utwórz magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-213">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="b3843-214">W oknie dialogowym **Utwórz magazyn kluczy**, w polu **Lokalizacja** wybierz centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="b3843-214">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="b3843-215">Po utworzeniu magazynu kluczy wybierz go z listy, a następnie wybierz opcję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="b3843-215">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="b3843-216">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-216">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="b3843-217">W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="b3843-217">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="b3843-218">Wprowadź nazwę wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="b3843-218">Enter a name for the secret.</span></span> <span data-ttu-id="b3843-219">Zanotuj nazwę, ponieważ później będzie musiała zostać podana.</span><span class="sxs-lookup"><span data-stu-id="b3843-219">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="b3843-220">W polu **Wartość** wprowadź parametry połączenia uzyskane z konta magazynu w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="b3843-220">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="b3843-221">Wybierz opcję **Włączone**, a następnie opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-221">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="b3843-222">Wpis tajny został utworzony i dodany do magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-222">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="b3843-223">Przejdź do strony **Przegląd magazynu kluczy** i zanotuj nazwę DNS.</span><span class="sxs-lookup"><span data-stu-id="b3843-223">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="b3843-224">Utwórz i zarejestruj aplikację Azure AD:</span><span class="sxs-lookup"><span data-stu-id="b3843-224">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="b3843-225">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory** i wybierz opcję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="b3843-225">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="b3843-226">Wybierz opcję **Nowa rejestracja aplikacji** i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="b3843-226">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="b3843-227">**Nazwa** — Wprowadź nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-227">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="b3843-228">**Typ aplikacji** — wybierz **internetowy interfejs API**.</span><span class="sxs-lookup"><span data-stu-id="b3843-228">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="b3843-229">**Ustawienia URI przekierowania** — wprowadź adres URL wystąpienia Dynamics 365, jak `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="b3843-229">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="b3843-230">Przejdź do właśnie utworzonej aplikacji, a następnie skopiuj i zapisz jej wartość **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="b3843-230">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="b3843-231">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-231">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="b3843-232">Przejdź do okna **Uprawnienia do interfejsu API** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b3843-232">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="b3843-233">Wybierz opcję **Dodaj uprawnienie**.</span><span class="sxs-lookup"><span data-stu-id="b3843-233">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="b3843-234">Wybierz **Magazyn kluczy Azure**.</span><span class="sxs-lookup"><span data-stu-id="b3843-234">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="b3843-235">Po wybraniu uprawnień delegowanych wybierz opcję **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="b3843-235">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="b3843-236">Wybierz opcję **Dodaj uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="b3843-236">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="b3843-237">W menu aplikacji wybierz pozycję **Certyfikaty i tajne wpisy**, a następnie wykonaj następujące kroki, aby utworzyć wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="b3843-237">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="b3843-238">Wybierz **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="b3843-238">Select **New client secret**.</span></span>
        2. <span data-ttu-id="b3843-239">W polu **Opis klucza** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="b3843-239">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="b3843-240">Wybierz czas trwania, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-240">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="b3843-241">Wpis tajny jest generowany w polu **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="b3843-241">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="b3843-242">Skopiuj i zapisz wartość wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="b3843-242">Copy and save the secret value.</span></span>

4. <span data-ttu-id="b3843-243">Utwórz wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="b3843-243">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="b3843-244">Przejdź do utworzonego wcześniej magazynu kluczy i wybierz opcję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="b3843-244">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="b3843-245">Z każdą nazwą wpisu tajnego w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b3843-245">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="b3843-246">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-246">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="b3843-247">W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="b3843-247">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="b3843-248">Utwórz nazwę i wartość wpisu tajnego z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b3843-248">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="b3843-249">Wybierz opcję **Włączone**, a następnie opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-249">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="b3843-250">Wpis tajny został utworzony i dodany do magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-250">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="b3843-251">Nazwa wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="b3843-251">Secret name</span></span>                       | <span data-ttu-id="b3843-252">Wartość wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="b3843-252">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="b3843-253">app-id</span><span class="sxs-lookup"><span data-stu-id="b3843-253">app-id</span></span>                            | <span data-ttu-id="b3843-254">Identyfikator aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-254">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="b3843-255">app-secret</span><span class="sxs-lookup"><span data-stu-id="b3843-255">app-secret</span></span>                        | <span data-ttu-id="b3843-256">Klucz tajny klienta, który został wcześniej zapisany</span><span class="sxs-lookup"><span data-stu-id="b3843-256">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="b3843-257">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="b3843-257">storage-account-name</span></span>              | <span data-ttu-id="b3843-258">Nazwa utworzonego wcześniej konta magazynu, na przykład **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="b3843-258">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="b3843-259">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="b3843-259">storage-account-connection-string</span></span> | <span data-ttu-id="b3843-260">Parametry połączenia skopiowane z strony **Klucze dostępu** konta magazynu</span><span class="sxs-lookup"><span data-stu-id="b3843-260">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="b3843-261">Autoryzuj aplikację, aby mogła uzyskać dostęp do magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="b3843-261">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="b3843-262">W [portalu Azure](https://portal.azure.com) otwórz utworzony wcześniej magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-262">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="b3843-263">Wybierz zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="b3843-263">Select the access policies.</span></span>
    3. <span data-ttu-id="b3843-264">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b3843-264">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="b3843-265">Wybierz pozycję **Dodaj zasady dostępu**, aby utworzyć zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="b3843-265">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="b3843-266">W polu **Uprawnienia wpisu tajnego** wybierz uprawnienia z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b3843-266">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="b3843-267">W polu **Wybierz główne** wyszukaj nazwę wyświetlaną aplikacji z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b3843-267">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="b3843-268">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-268">Select **Select**.</span></span>
        5. <span data-ttu-id="b3843-269">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-269">Select **Add**.</span></span>
        6. <span data-ttu-id="b3843-270">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-270">Select **Save**.</span></span>

        | <span data-ttu-id="b3843-271">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="b3843-271">Application</span></span>                                              | <span data-ttu-id="b3843-272">Uprawnienia</span><span class="sxs-lookup"><span data-stu-id="b3843-272">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="b3843-273">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-273">The display name of the new application that you created</span></span> | <span data-ttu-id="b3843-274">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="b3843-274">Get, List</span></span>   |
        | <span data-ttu-id="b3843-275">**Mikrousługi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="b3843-275">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="b3843-276">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="b3843-276">Get, List</span></span>   |

6. <span data-ttu-id="b3843-277">Przypisz role, aby uzyskać dostęp do konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="b3843-277">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="b3843-278">W [portalu Azure](https://portal.azure.com) otwórz utworzone wcześniej konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="b3843-278">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="b3843-279">Wybierz pozycję **Kontrola dostępu (IAM)**, a następnie wybierz **Przypisania ról**.</span><span class="sxs-lookup"><span data-stu-id="b3843-279">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="b3843-280">Wybierz **Dodaj, Dodaj przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="b3843-280">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="b3843-281">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b3843-281">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="b3843-282">Wybierz rolę z następującej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b3843-282">Select the role from the following table.</span></span>
        2. <span data-ttu-id="b3843-283">Pozostaw ustawienie pola **Przypisz dostęp do** jako **Użytkownik, grupa lub nazwa główna usługi Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b3843-283">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="b3843-284">W polu **Wybierz** wprowadź aplikację z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b3843-284">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="b3843-285">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3843-285">Select **Save**.</span></span>

        | <span data-ttu-id="b3843-286">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="b3843-286">Application</span></span>                                              | <span data-ttu-id="b3843-287">Rola</span><span class="sxs-lookup"><span data-stu-id="b3843-287">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="b3843-288">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-288">The display name of the new application that you created</span></span> | <span data-ttu-id="b3843-289">Właściciel</span><span class="sxs-lookup"><span data-stu-id="b3843-289">Owner</span></span>                       |
        | <span data-ttu-id="b3843-290">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-290">The display name of the new application that you created</span></span> | <span data-ttu-id="b3843-291">Osoba wpłacająca</span><span class="sxs-lookup"><span data-stu-id="b3843-291">Contributor</span></span>                 |
        | <span data-ttu-id="b3843-292">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-292">The display name of the new application that you created</span></span> | <span data-ttu-id="b3843-293">Współautor konta magazynu</span><span class="sxs-lookup"><span data-stu-id="b3843-293">Storage Account Contributor</span></span> |
        | <span data-ttu-id="b3843-294">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="b3843-294">The display name of the new application that you created</span></span> | <span data-ttu-id="b3843-295">Właściciel danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="b3843-295">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="b3843-296">**Usługa autoryzacji AI Builder**</span><span class="sxs-lookup"><span data-stu-id="b3843-296">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="b3843-297">Czytelnik danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="b3843-297">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="b3843-298">Interfejs wiersza polecenia Azure</span><span class="sxs-lookup"><span data-stu-id="b3843-298">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="b3843-299">Konfigurowanie data lake</span><span class="sxs-lookup"><span data-stu-id="b3843-299">Configure the data lake</span></span>

<span data-ttu-id="b3843-300">Aby dodać dodatek Azure Data Lake do środowiska, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b3843-300">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="b3843-301">Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="b3843-301">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="b3843-302">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="b3843-302">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="b3843-303">Wybierz dodatek **Eksport do Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="b3843-303">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="b3843-304">Wprowadź następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="b3843-304">Enter the following values.</span></span>

    | <span data-ttu-id="b3843-305">Wartość</span><span class="sxs-lookup"><span data-stu-id="b3843-305">Value</span></span>                                                              | <span data-ttu-id="b3843-306">opis</span><span class="sxs-lookup"><span data-stu-id="b3843-306">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="b3843-307">Identyfikator dzierżawcy subskrypcji Azure, w której znajduje się magazyn kluczy</span><span class="sxs-lookup"><span data-stu-id="b3843-307">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="b3843-308">Identyfikator dzierżawcy, w którym znajdują się konto magazynu, aplikacje i magazyny kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3843-308">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="b3843-309">Aby znaleźć tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3843-309">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="b3843-310">Podaj nazwę DNS usługi Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3843-310">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="b3843-311">Nazwa DNS magazynu kluczy, np. `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="b3843-311">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="b3843-312">(Wartość ta pokrywa się z nazwą DNS używaną w magazynie jednostek).</span><span class="sxs-lookup"><span data-stu-id="b3843-312">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="b3843-313">Podaj wpis tajny zawierający nazwę konta magazynu</span><span class="sxs-lookup"><span data-stu-id="b3843-313">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="b3843-314">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="b3843-314">**storage-account-name**</span></span> |
    | <span data-ttu-id="b3843-315">Nazwa wpisu tajnego identyfikatora aplikacji, który będzie używany w celu uzyskania dostępu do Data Lake</span><span class="sxs-lookup"><span data-stu-id="b3843-315">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="b3843-316">**app-id**</span><span class="sxs-lookup"><span data-stu-id="b3843-316">**app-id**</span></span> |
    | <span data-ttu-id="b3843-317">Nazwa wpisu tajnego do używania z identyfikatorem aplikacji</span><span class="sxs-lookup"><span data-stu-id="b3843-317">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="b3843-318">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="b3843-318">**app-secret**</span></span> |

5. <span data-ttu-id="b3843-319">Zaakceptuj warunki i wybierz opcję **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="b3843-319">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="b3843-320">Dodatek zostanie zainstalowany w ciągu kilku minut.</span><span class="sxs-lookup"><span data-stu-id="b3843-320">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="b3843-321">Konfigurowanie AI Builder</span><span class="sxs-lookup"><span data-stu-id="b3843-321">Configure AI Builder</span></span>

1. <span data-ttu-id="b3843-322">Zaloguj się do LCS i otwórz stronę **Szczegóły środowiska**.</span><span class="sxs-lookup"><span data-stu-id="b3843-322">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="b3843-323">Przewiń w dół do sekcji **Dodatki środowiska**.</span><span class="sxs-lookup"><span data-stu-id="b3843-323">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="b3843-324">Powinny zostać wyświetlone dodatki, które są już zainstalowane w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="b3843-324">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="b3843-325">Jeśli nie ma wśród nich dodatku **Eksport do Data Lake**, skonfiguruj ten dodatek.</span><span class="sxs-lookup"><span data-stu-id="b3843-325">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="b3843-326">Wybierz dodatek **Pobierz szczegółowe dane**.</span><span class="sxs-lookup"><span data-stu-id="b3843-326">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="b3843-327">Na stronie szczegółów dodatku **Pobierz szczegółowe analizy** wprowadź następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="b3843-327">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="b3843-328">Wartość</span><span class="sxs-lookup"><span data-stu-id="b3843-328">Value</span></span>                                                    | <span data-ttu-id="b3843-329">opis</span><span class="sxs-lookup"><span data-stu-id="b3843-329">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="b3843-330">Adres URL organizacji CDS</span><span class="sxs-lookup"><span data-stu-id="b3843-330">CDS Organization URL</span></span>                                     | <span data-ttu-id="b3843-331">Adres URL organizacji Dataverse skopiowany z góry.</span><span class="sxs-lookup"><span data-stu-id="b3843-331">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="b3843-332">Identyfikator organizacji CDS</span><span class="sxs-lookup"><span data-stu-id="b3843-332">CDS Org ID</span></span>                                               | <span data-ttu-id="b3843-333">Identyfikator organizacji Dataverse skopiowany z góry.</span><span class="sxs-lookup"><span data-stu-id="b3843-333">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="b3843-334">Włącz opcję **Czy to jest domyślne środowisko CDS dla dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3843-334">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="b3843-335">Konfigurowanie magazynu jednostek</span><span class="sxs-lookup"><span data-stu-id="b3843-335">Configure the entity store</span></span>

<span data-ttu-id="b3843-336">Aby skonfigurować magazyn jednostek w środowisku Finance, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b3843-336">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="b3843-337">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu \> Połączenia danych**.</span><span class="sxs-lookup"><span data-stu-id="b3843-337">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="b3843-338">Ustaw następujące pola magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="b3843-338">Set the following key vault fields:</span></span>

    - <span data-ttu-id="b3843-339">**Identyfikator aplikacji (klienta)** — wprowadź utworzony wcześniej identyfikator klienta aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-339">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="b3843-340">**Wpis tajny aplikacji** — wprowadź wpis tajny zapisany dla utworzonej wcześniej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-340">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="b3843-341">**Nazwa DNS** — nazwa systemu DNS (Domain Name System) znajduje się na stronie szczegółów aplikacji dla utworzonej wcześniej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3843-341">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="b3843-342">**Nazwa wpisu tajnego** — wprowadź **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="b3843-342">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="b3843-343">Włącz opcję **Włącz integrację danych w usłudze Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="b3843-343">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="b3843-344">Naciśnij łącze **Testuj Azure Key Vault** i sprawdź, czy nie ma żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="b3843-344">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="b3843-345">Naciśnij łącze **Testuj magazyn usługi Azure** i sprawdź, czy nie ma żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="b3843-345">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="b3843-346">Opinie i pomoc techniczna</span><span class="sxs-lookup"><span data-stu-id="b3843-346">Feedback and support</span></span>

<span data-ttu-id="b3843-347">Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b3843-347">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="b3843-348">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="b3843-348">Privacy notice</span></span>

<span data-ttu-id="b3843-349">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="b3843-349">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
