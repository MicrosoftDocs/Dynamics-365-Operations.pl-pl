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
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222619"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="0d398-103">Konfiguracja dla Finance Insights w ramach publicznej wersji zapoznawczej (podglądowej) — wersja 10.0.20 i późniejsze</span><span class="sxs-lookup"><span data-stu-id="0d398-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0d398-104">Finance Insights łączy funkcje firmy Microsoft Dynamics 365 Finance z Dataverse, Azure i AI Builder w celu zapewnienia wydajnego narzędzia prognozowania dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="0d398-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="0d398-105">W tym temacie wyjaśniono, jak skonfigurować Dynamics 365 Finance w wersji 10.0.20, aby system korzystał z możliwości dostępnych w programie Finance Insights dla publicznego podglądu w wersji 10.0.20 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="0d398-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="0d398-106">Kroki konfiguracyjne opisane w tym temacie dotyczą tylko wersji Finance 10.0.20 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="0d398-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="0d398-107">Aby skonfigurować Finance Insights w wersji 10.0.19 i wcześniejszych, patrz [Konfiguracja Finance Insights — wersje do 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="0d398-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="0d398-108">Wdrażanie Finance</span><span class="sxs-lookup"><span data-stu-id="0d398-108">Deploy Finance</span></span>

<span data-ttu-id="0d398-109">Wykonaj poniższe kroki, aby wdrożyć środowiska.</span><span class="sxs-lookup"><span data-stu-id="0d398-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="0d398-110">W Microsoft Dynamics Lifecycle Services (LCS) utwórz lub zaktualizuj środowisko Finance.</span><span class="sxs-lookup"><span data-stu-id="0d398-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="0d398-111">Środowisko wymaga wersji aplikacji 10.0.20 Finance and Operations lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="0d398-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="0d398-112">Środowisko musi być środowiskiem o wysokiej dostępności (HA) w piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="0d398-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="0d398-113">(Środowisko tego typu jest również nazywane środowiskiem warstwy 2) Aby uzyskać więcej informacji, zobacz [Planowanie środowiska](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="0d398-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="0d398-114">Jeśli konfigurujesz Finance Insights w środowisku piaskownicy, być może będziesz musiał skopiować dane produkcyjne do tego środowiska, aby prognozy zadziałały.</span><span class="sxs-lookup"><span data-stu-id="0d398-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="0d398-115">Model prognozy używa wielu lat danych do tworzenia prognoz.</span><span class="sxs-lookup"><span data-stu-id="0d398-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="0d398-116">Dane demonstracyjne Contoso nie zawierają wystarczającej ilości danych historycznych do szkolenia modelu prognozy.</span><span class="sxs-lookup"><span data-stu-id="0d398-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="0d398-117">Skonfiguruj usługę Dataverse</span><span class="sxs-lookup"><span data-stu-id="0d398-117">Configure Dataverse</span></span>

<span data-ttu-id="0d398-118">Wykonaj następujące kroki, aby skonfigurować Dataverse for Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="0d398-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="0d398-119">W LCS otwórz stronę środowiska i sprawdź, czy sekcja **Integracja Power Platform** jest już skonfigurowana.</span><span class="sxs-lookup"><span data-stu-id="0d398-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="0d398-120">Jeśli jest już skonfigurowana, na liście powinna znajdować się nazwa środowiska Finance połączona ze środowiskiem Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0d398-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="0d398-121">Jeśli nie jest jeszcze skonfigurowana, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="0d398-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="0d398-122">Wybierz przycisk **Integracja Power Platform**, a następnie wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="0d398-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="0d398-123">Konfiguracja środowiska może potrwać do godziny.</span><span class="sxs-lookup"><span data-stu-id="0d398-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="0d398-124">Gdy środowisko Dataverse zostanie poprawnie skonfigurowane, na liście powinna zostać wyświetlona nazwa środowiska Dataverse połączona ze środowiskiem Finance.</span><span class="sxs-lookup"><span data-stu-id="0d398-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0d398-125">Po zakończeniu konfigurowania środowiska **nie** należy wybierać opcji **Łącze do CDS**.</span><span class="sxs-lookup"><span data-stu-id="0d398-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="0d398-126">Ten przycisk nie jest wymagany w przypadku Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="0d398-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="0d398-127">Jeśli ją wybierzesz, nie będziesz mógł skonfigurować wymaganych dodatków środowiskowych w LCS.</span><span class="sxs-lookup"><span data-stu-id="0d398-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="0d398-128">Konfiguruj system Azure</span><span class="sxs-lookup"><span data-stu-id="0d398-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="0d398-129">Korzystanie z Azure Cloud Shell w celu konfigurowania zasobów Data Lake modułu Finance Insights</span><span class="sxs-lookup"><span data-stu-id="0d398-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="0d398-130">Korzystanie ze skryptu programu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d398-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="0d398-131">Został przygotowany skrypt programu Windows PowerShell ułatwiający skonfigurowanie zasobów Azure opisanych w sekcji [Konfigurowanie eksportu do Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0d398-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="0d398-132">Jeśli wolisz przeprowadzić ręczną konfigurację, zamiast tego pomiń tę procedurę i przejdź do procedury w sekcji [Konfiguracja ręczna](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="0d398-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="0d398-133">Użyj następującej procedury, aby uruchomić skrypt Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d398-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="0d398-134">Konfiguracja może nie zadziałać, jeśli użyjesz opcji **Wypróbuj** w Azure CLI lub jeśli uruchomisz skrypt na swoim komputerze.</span><span class="sxs-lookup"><span data-stu-id="0d398-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="0d398-135">Aby skonfigurować platformę Azure przy użyciu skryptu programu Windows PowerShell, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0d398-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="0d398-136">Użytkownik musi mieć uprawnienia do tworzenia grupy zasobów Azure, zasobów Azure i aplikacji Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d398-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="0d398-137">Aby uzyskać informacje dotyczące wymaganych uprawnień, zobacz [Sprawdzanie uprawnień Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="0d398-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="0d398-138">W [portalu Azure](https://portal.azure.com) przejdź do docelowej subskrypcji Azure.</span><span class="sxs-lookup"><span data-stu-id="0d398-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="0d398-139">Naciśnij przycisk **Cloud Shell** na prawo od pola **wyszukiwania**.</span><span class="sxs-lookup"><span data-stu-id="0d398-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="0d398-140">Wybierz opcję **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0d398-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="0d398-141">Utwórz pamięć masową, jeśli zostanie wyświetlony monit o jej utworzenie.</span><span class="sxs-lookup"><span data-stu-id="0d398-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="0d398-142">Przejdź do karty **Azure CLI** i wybierz polecenie **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="0d398-143">W Notatniku otwórz nowy plik i wklej do niego skrypt Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d398-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="0d398-144">Zapisz plik jako **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="0d398-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="0d398-145">Przekaż skrypt programu Windows PowerShell do sesji, używając opcji menu do przekazania w Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="0d398-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="0d398-146">Uruchom skrypt **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="0d398-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="0d398-147">Postępuj zgodnie z instrukcjami, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="0d398-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="0d398-148">Korzystając z informacji z wyników skryptu, zainstaluj dodatek Eksport do Data Lake w LCS.</span><span class="sxs-lookup"><span data-stu-id="0d398-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="0d398-149">Konfiguracja ręczna</span><span class="sxs-lookup"><span data-stu-id="0d398-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="0d398-150">Dodawanie aplikacji do dzierżawcy Azure AD</span><span class="sxs-lookup"><span data-stu-id="0d398-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="0d398-151">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0d398-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="0d398-152">Wybierz **Zarządzaj \> Aplikacje dla przedsiębiorstw**.</span><span class="sxs-lookup"><span data-stu-id="0d398-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="0d398-153">Wyszukaj następujące aplikacje na podstawie identyfikatora aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0d398-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="0d398-154">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="0d398-154">Application</span></span>                              | <span data-ttu-id="0d398-155">Identyfikator aplikacji</span><span class="sxs-lookup"><span data-stu-id="0d398-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="0d398-156">Mikrousługi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="0d398-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="0d398-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="0d398-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="0d398-158">CDS mikrousług ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="0d398-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="0d398-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="0d398-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="0d398-160">Usługa autoryzacji AI Builder</span><span class="sxs-lookup"><span data-stu-id="0d398-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="0d398-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="0d398-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="0d398-162">Jeśli nie możesz znaleźć dowolnej z tych aplikacji, spróbuj wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="0d398-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="0d398-163">Na komputerze lokalnym naciśnij menu **Start** i wyszukaj program **powershell**.</span><span class="sxs-lookup"><span data-stu-id="0d398-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="0d398-164">Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) program **Windows PowerShell**, a następnie wybierz polecenie **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="0d398-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="0d398-165">Uruchom następujące polecenie, aby zainstalować moduł **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="0d398-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="0d398-166">Jeśli dostawca NuGet jest wymagany, aby kontynuować, wybierz opcję **Y**, aby go zainstalować.</span><span class="sxs-lookup"><span data-stu-id="0d398-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="0d398-167">Jeśli zostanie wyświetlony komunikat „Niezaufane repozytorium”, wybierz opcję **Y**, aby kontynuować.</span><span class="sxs-lookup"><span data-stu-id="0d398-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="0d398-168">Dla każdej aplikacji, która musi zostać dodana, należy uruchomić następujące polecenia, aby dodać aplikację do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d398-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="0d398-169">Po wyświetleniu monitu zaloguj się jako administrator Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d398-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="0d398-170">Tworzenie zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="0d398-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="0d398-171">Należy się upewnić, że następujące zasoby są tworzone w tym samym wystąpieniu Azure AD, co środowisko Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0d398-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="0d398-172">Nie można użyć zasobów z innego wystąpienia Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d398-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="0d398-173">Tworzenie konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="0d398-173">Create a storage account:</span></span>

    1. <span data-ttu-id="0d398-174">W [portalu Azure](https://portal.azure.com) utwórz konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="0d398-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="0d398-175">W oknie dialogowym **Utwórz konto magazynu** ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="0d398-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="0d398-176">**Lokalizacja** — umożliwia wybór centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="0d398-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="0d398-177">**Wydajność** — zaleca się, aby w wybrać opcję **Standardowa**.</span><span class="sxs-lookup"><span data-stu-id="0d398-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="0d398-178">**Rodzaj konta** — musisz wybrać **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="0d398-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="0d398-179">W oknie dialogowym **Opcje zaawansowane**, jako wartość opcji **Data Lake Storage Gen2** wybierz **Włącz** w obszarze funkcji **Hierarchiczne przestrzenie nazw**.</span><span class="sxs-lookup"><span data-stu-id="0d398-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="0d398-180">Jeśli ta funkcja nie zostanie wyłączona, nie będzie można używać danych, które aplikacje Finance and Operations zapisują przy użyciu usług, takich jak przepływy danych Power BI.</span><span class="sxs-lookup"><span data-stu-id="0d398-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="0d398-181">Wybierz opcję **Przejrzyj i utwórz**.</span><span class="sxs-lookup"><span data-stu-id="0d398-181">Select **Review and create**.</span></span> <span data-ttu-id="0d398-182">Po zakończeniu wdrażania nowy zasób zostanie wyświetlony w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="0d398-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="0d398-183">Przejdź do utworzonego konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="0d398-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="0d398-184">W menu po lewej stronie wybierz **Klucze dostępu**.</span><span class="sxs-lookup"><span data-stu-id="0d398-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="0d398-185">Skopiuj i zapisz nazwę konta magazynu.</span><span class="sxs-lookup"><span data-stu-id="0d398-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="0d398-186">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="0d398-187">Tworzenie magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="0d398-187">Create a key vault:</span></span>

    1. <span data-ttu-id="0d398-188">W [portalu Azure](https://portal.azure.com) utwórz magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="0d398-189">W oknie dialogowym **Utwórz magazyn kluczy**, w polu **Lokalizacja** wybierz centrum danych, w którym znajduje się dane środowisko.</span><span class="sxs-lookup"><span data-stu-id="0d398-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="0d398-190">Po utworzeniu klucza należy przejść do pola **Przegląd magazynu kluczy**, skopiować i zapisać nazwę DNS.</span><span class="sxs-lookup"><span data-stu-id="0d398-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="0d398-191">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania dodatku Data Lake.</span><span class="sxs-lookup"><span data-stu-id="0d398-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="0d398-192">Utwórz i zarejestruj aplikację Azure AD:</span><span class="sxs-lookup"><span data-stu-id="0d398-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="0d398-193">W [portalu Azure](https://portal.azure.com) przejdź do **Azure Active Directory** i wybierz opcję **Rejestracje aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="0d398-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="0d398-194">Wybierz opcję **Nowa rejestracja aplikacji** i ustaw następujące pola:</span><span class="sxs-lookup"><span data-stu-id="0d398-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="0d398-195">**Nazwa** — Wprowadź nazwę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0d398-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="0d398-196">**Typ aplikacji** — wybierz **internetowy interfejs API**.</span><span class="sxs-lookup"><span data-stu-id="0d398-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="0d398-197">**Ustawienia URI przekierowania** — wprowadź adres URL wystąpienia Dynamics 365, jak `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="0d398-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="0d398-198">Przejdź do właśnie utworzonej aplikacji, a następnie skopiuj i zapisz jej wartość **Identyfikator aplikacji (klienta)**.</span><span class="sxs-lookup"><span data-stu-id="0d398-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="0d398-199">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="0d398-200">Przejdź do okna **Uprawnienia do interfejsu API** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0d398-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="0d398-201">Wybierz opcję **Dodaj uprawnienie**.</span><span class="sxs-lookup"><span data-stu-id="0d398-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="0d398-202">Wybierz **Magazyn kluczy Azure**.</span><span class="sxs-lookup"><span data-stu-id="0d398-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="0d398-203">Po wybraniu uprawnień delegowanych wybierz opcję **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="0d398-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="0d398-204">Wybierz opcję **Dodaj uprawnienia**.</span><span class="sxs-lookup"><span data-stu-id="0d398-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="0d398-205">W menu aplikacji wybierz pozycję **Certyfikaty i tajne wpisy**, a następnie wykonaj następujące kroki, aby utworzyć wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="0d398-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="0d398-206">Wybierz **Nowy klucz tajny klienta**.</span><span class="sxs-lookup"><span data-stu-id="0d398-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="0d398-207">W polu **Opis klucza** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="0d398-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="0d398-208">Wybierz czas trwania, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="0d398-209">Wpis tajny jest generowany w polu **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="0d398-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="0d398-210">Skopiuj i zapisz wartość wpisu tajnego klienta.</span><span class="sxs-lookup"><span data-stu-id="0d398-210">Copy and save the client secret value.</span></span> <span data-ttu-id="0d398-211">Tę wartość trzeba będzie wprowadzić później podczas konfigurowania magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="0d398-212">Utwórz wpisy tajne magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="0d398-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="0d398-213">Przejdź do utworzonego wcześniej magazynu kluczy i wybierz opcję **Wpisy tajne**.</span><span class="sxs-lookup"><span data-stu-id="0d398-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="0d398-214">Z każdą nazwą wpisu tajnego w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0d398-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0d398-215">Wybierz pozycję **Generuj/importuj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="0d398-216">W oknie dialogowym **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.</span><span class="sxs-lookup"><span data-stu-id="0d398-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="0d398-217">Utwórz nazwę i wartość wpisu tajnego z poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="0d398-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="0d398-218">Wybierz opcję **Włączone**, a następnie opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="0d398-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="0d398-219">Wpis tajny został utworzony i dodany do magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="0d398-220">Nazwa wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="0d398-220">Secret name</span></span>                       | <span data-ttu-id="0d398-221">Wartość wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="0d398-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="0d398-222">app-id</span><span class="sxs-lookup"><span data-stu-id="0d398-222">app-id</span></span>                            | <span data-ttu-id="0d398-223">Identyfikator aplikacji, która została utworzona wcześniej.</span><span class="sxs-lookup"><span data-stu-id="0d398-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="0d398-224">app-secret</span><span class="sxs-lookup"><span data-stu-id="0d398-224">app-secret</span></span>                        | <span data-ttu-id="0d398-225">Klucz tajny klienta, który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="0d398-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="0d398-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="0d398-226">storage-account-name</span></span>              | <span data-ttu-id="0d398-227">Nazwa utworzonego wcześniej konta magazynu, na przykład **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="0d398-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="0d398-228">Autoryzuj aplikację, aby mogła uzyskać dostęp do magazynu kluczy:</span><span class="sxs-lookup"><span data-stu-id="0d398-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="0d398-229">W [portalu Azure](https://portal.azure.com) otwórz utworzony wcześniej magazyn kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="0d398-230">Wybierz zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="0d398-230">Select the access policies.</span></span>
    3. <span data-ttu-id="0d398-231">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0d398-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0d398-232">Wybierz pozycję **Dodaj zasady dostępu**, aby utworzyć zasady dostępu.</span><span class="sxs-lookup"><span data-stu-id="0d398-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="0d398-233">W polu **Uprawnienia wpisu tajnego** wybierz uprawnienia z tabeli.</span><span class="sxs-lookup"><span data-stu-id="0d398-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="0d398-234">W polu **Wybierz główne** wyszukaj nazwę wyświetlaną aplikacji z tabeli.</span><span class="sxs-lookup"><span data-stu-id="0d398-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="0d398-235">Wybierz pozycję **Wybierz**.</span><span class="sxs-lookup"><span data-stu-id="0d398-235">Select **Select**.</span></span>
        5. <span data-ttu-id="0d398-236">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-236">Select **Add**.</span></span>
        6. <span data-ttu-id="0d398-237">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0d398-237">Select **Save**.</span></span>

        | <span data-ttu-id="0d398-238">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="0d398-238">Application</span></span>                                              | <span data-ttu-id="0d398-239">Uprawnienia</span><span class="sxs-lookup"><span data-stu-id="0d398-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="0d398-240">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="0d398-240">The display name of the new application that you created</span></span> | <span data-ttu-id="0d398-241">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="0d398-241">Get, List</span></span>   |
        | <span data-ttu-id="0d398-242">**Mikrousługi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="0d398-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="0d398-243">Pobieranie, Tworzenie listy</span><span class="sxs-lookup"><span data-stu-id="0d398-243">Get, List</span></span>   |

6. <span data-ttu-id="0d398-244">Przypisz role, aby uzyskać dostęp do konta magazynu:</span><span class="sxs-lookup"><span data-stu-id="0d398-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="0d398-245">W [portalu Azure](https://portal.azure.com) otwórz utworzone wcześniej konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="0d398-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="0d398-246">Wybierz pozycję **Kontrola dostępu (IAM)**, a następnie wybierz **Przypisania ról**.</span><span class="sxs-lookup"><span data-stu-id="0d398-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="0d398-247">Wybierz **Dodaj, Dodaj przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="0d398-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="0d398-248">Z każdą aplikacją w poniższej tabeli wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0d398-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="0d398-249">Wybierz rolę z tabeli.</span><span class="sxs-lookup"><span data-stu-id="0d398-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="0d398-250">Pozostaw ustawienie pola **Przypisz dostęp do** jako **Użytkownik, grupa lub nazwa główna usługi Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="0d398-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="0d398-251">W polu **Wybierz** wprowadź aplikację z tabeli.</span><span class="sxs-lookup"><span data-stu-id="0d398-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="0d398-252">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0d398-252">Select **Save**.</span></span>

        | <span data-ttu-id="0d398-253">Zgłoszenie</span><span class="sxs-lookup"><span data-stu-id="0d398-253">Application</span></span>                                              | <span data-ttu-id="0d398-254">Rola</span><span class="sxs-lookup"><span data-stu-id="0d398-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="0d398-255">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="0d398-255">The display name of the new application that you created</span></span> | <span data-ttu-id="0d398-256">Właściciel</span><span class="sxs-lookup"><span data-stu-id="0d398-256">Owner</span></span>                       |
        | <span data-ttu-id="0d398-257">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="0d398-257">The display name of the new application that you created</span></span> | <span data-ttu-id="0d398-258">Osoba wpłacająca</span><span class="sxs-lookup"><span data-stu-id="0d398-258">Contributor</span></span>                 |
        | <span data-ttu-id="0d398-259">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="0d398-259">The display name of the new application that you created</span></span> | <span data-ttu-id="0d398-260">Współautor konta magazynu</span><span class="sxs-lookup"><span data-stu-id="0d398-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="0d398-261">Nazwa wyświetlana nowej aplikacji, która została utworzona wcześniej</span><span class="sxs-lookup"><span data-stu-id="0d398-261">The display name of the new application that you created</span></span> | <span data-ttu-id="0d398-262">Właściciel danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="0d398-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="0d398-263">**Usługa autoryzacji AI Builder**</span><span class="sxs-lookup"><span data-stu-id="0d398-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="0d398-264">Czytelnik danych obiektów blob magazynu</span><span class="sxs-lookup"><span data-stu-id="0d398-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="0d398-265">Interfejs wiersza polecenia Azure</span><span class="sxs-lookup"><span data-stu-id="0d398-265">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="0d398-266">Konfigurowanie eksportu do dodatku Data Lake</span><span class="sxs-lookup"><span data-stu-id="0d398-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="0d398-267">Wykonaj poniższe kroki, aby użyć LCS do dodania dodatku Eksport do Data Lake do środowiska.</span><span class="sxs-lookup"><span data-stu-id="0d398-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="0d398-268">Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="0d398-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="0d398-269">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="0d398-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="0d398-270">Wybierz dodatek **Eksport do Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="0d398-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="0d398-271">Wprowadź następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="0d398-271">Enter the following values.</span></span>

    | <span data-ttu-id="0d398-272">Wartość</span><span class="sxs-lookup"><span data-stu-id="0d398-272">Value</span></span>                                                              | <span data-ttu-id="0d398-273">opis</span><span class="sxs-lookup"><span data-stu-id="0d398-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="0d398-274">Identyfikator dzierżawcy subskrypcji Azure, w której znajduje się magazyn kluczy</span><span class="sxs-lookup"><span data-stu-id="0d398-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="0d398-275">Identyfikator dzierżawcy, w którym znajdują się konto magazynu, aplikacje i magazyny kluczy.</span><span class="sxs-lookup"><span data-stu-id="0d398-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="0d398-276">Aby uzyskać tę wartość, otwórz [portal Azure](https://portal.azure.com), przejdź do **Azure Active Directory** i skopiuj wartość **Identyfikatora dzierżawcy**.</span><span class="sxs-lookup"><span data-stu-id="0d398-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="0d398-277">Podaj nazwę DNS usługi Key Vault</span><span class="sxs-lookup"><span data-stu-id="0d398-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="0d398-278">Nazwa DNS magazynu kluczy, np. `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="0d398-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="0d398-279">Podaj wpis tajny zawierający nazwę konta magazynu</span><span class="sxs-lookup"><span data-stu-id="0d398-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="0d398-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="0d398-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="0d398-281">Nazwa wpisu tajnego identyfikatora aplikacji, który będzie używany w celu uzyskania dostępu do Data Lake</span><span class="sxs-lookup"><span data-stu-id="0d398-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="0d398-282">**app-id**</span><span class="sxs-lookup"><span data-stu-id="0d398-282">**app-id**</span></span> |
    | <span data-ttu-id="0d398-283">Nazwa aplikacji tajnej dla wpisu tajnego klienta</span><span class="sxs-lookup"><span data-stu-id="0d398-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="0d398-284">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="0d398-284">**app-secret**</span></span> |

5. <span data-ttu-id="0d398-285">Zaakceptuj warunki i wybierz opcję **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="0d398-286">Dodatek zostanie zainstalowany w ciągu kilku minut.</span><span class="sxs-lookup"><span data-stu-id="0d398-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="0d398-287">Konfigurowanie dodatku Finance Insights</span><span class="sxs-lookup"><span data-stu-id="0d398-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="0d398-288">Jeśli wcześniej został zainstalowany dodatek Get insights, odinstaluj go przed zakończeniem następującej procedury.</span><span class="sxs-lookup"><span data-stu-id="0d398-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="0d398-289">Aby zainstalować dodatek Finanse Insights, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="0d398-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="0d398-290">Zaloguj się do LCS, a następnie w obszarze nazwy środowiska po prawej stronie strony wybierz opcję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="0d398-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="0d398-291">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="0d398-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="0d398-292">Konfigurowanie dodatku **Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="0d398-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="0d398-293">Zaakceptuj warunki i wybierz opcję **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="0d398-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="0d398-294">Opinie i pomoc techniczna</span><span class="sxs-lookup"><span data-stu-id="0d398-294">Feedback and support</span></span>

<span data-ttu-id="0d398-295">Jeśli chcesz przekazać opinie lub potrzebujesz pomocy technicznej, wyślij e-mail do [Finance Insights (wersja zapoznawcza)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0d398-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
