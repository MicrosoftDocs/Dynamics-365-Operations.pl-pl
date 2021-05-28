---
title: '`Dodatek Widoczność magazynu'
description: W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017013"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="6f69a-103">Dodatek Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6f69a-104">Dodatek Widoczność magazynu jest niezależną i wysoko skalowalną mikrodostępną usługą, która umożliwia śledzenie dostępnych zapasów w czasie rzeczywistym, udostępniając w ten sposób globalny widok widoczności zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="6f69a-105">Wszystkie informacje dotyczące dostępnych zapasów są eksportowane do usługi w czasie rzeczywistym przez integrację SQL niskiego poziomu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="6f69a-106">System zewnętrzny uzyskuje dostęp do usługi za pośrednictwem interfejsów API RESTful w celu uzyskania informacji o dostępnych zapasach w danym zbiorze wymiarów, pobierając w ten sposób listę dostępnych stanowisk.</span><span class="sxs-lookup"><span data-stu-id="6f69a-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="6f69a-107">Widoczność zapasów to mikrousługa wbudowana w systemie Microsoft Dataverse, co oznacza, że można ją rozszerzyć przez budowanie Power Apps i stosowanie dostosowanych funkcji Power BI w celu spełnienia wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="6f69a-108">Możliwe jest również uaktualnienie indeksu do kwerend magazynowych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="6f69a-109">Widoczność zapasów zapewnia opcje konfiguracji, które umożliwiają integrację z wieloma systemami innych firm.</span><span class="sxs-lookup"><span data-stu-id="6f69a-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="6f69a-110">Obsługuje on standardowy rozmiar magazynu, możliwe do dostosowania rozszerzenia i standardowe, konfigurowalne obliczone ilości.</span><span class="sxs-lookup"><span data-stu-id="6f69a-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="6f69a-111">W tym temacie opisano sposób instalowania i konfigurowania dodatku widoczność magazynu dla systemu Dynamics 365 Supply Chain Management oraz używania jego interfejsu programowania aplikacji (API).</span><span class="sxs-lookup"><span data-stu-id="6f69a-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="6f69a-112">Instalowanie dodatku Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="6f69a-113">Musisz zainstalować dodatek Widoczność magazynu, korzystając z Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6f69a-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6f69a-114">LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f69a-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="6f69a-115">Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="6f69a-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="6f69a-116">Wymagania wstępne dodatku Widoczność zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="6f69a-117">Aby można było zainstalować dodatek Widoczność magazynu, trzeba:</span><span class="sxs-lookup"><span data-stu-id="6f69a-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="6f69a-118">Uzyskać projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.</span><span class="sxs-lookup"><span data-stu-id="6f69a-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="6f69a-119">Upewnij się, że zostały spełnione wymagania wstępne dotyczące konfigurowania dodatków dostępnych w [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6f69a-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="6f69a-120">Widoczność zapasów nie wymaga podwójnego łączenia.</span><span class="sxs-lookup"><span data-stu-id="6f69a-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="6f69a-121">Skontaktuj się z zespołem widoczności pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) aby uzyskać następujące trzy wymagane pliki:</span><span class="sxs-lookup"><span data-stu-id="6f69a-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="6f69a-122">`Inventory Visibility Integration.zip` (jeśli uruchomiona wersja Supply Chain Management jest wcześniejsza niż 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="6f69a-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="6f69a-123">Alternatywnie, skontaktuj się z zespołem ds. Widoczności zapasów pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com), aby uzyskać package deployer.</span><span class="sxs-lookup"><span data-stu-id="6f69a-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="6f69a-124">Te pakiety mogą być używane przez oficjalne narzędzie package deployer.</span><span class="sxs-lookup"><span data-stu-id="6f69a-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="6f69a-125">`InventoryServiceApplication.PackageDeployer.zip` (ten pakiet zawiera wszystkie zmiany w pakiecie `InventoryServiceBase` oraz dodatkowe składniki aplikacji interfejsu użytkownika)</span><span class="sxs-lookup"><span data-stu-id="6f69a-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="6f69a-126">Postępuj zgodnie z instrukcjami podanymi w narzędziu [Przewodnik Szybki start: Rejestrowanie aplikacji na platformie tożsamości firmy Microsoft](/azure/active-directory/develop/quickstart-register-app), aby zarejestrować aplikację i dodać tajny kod klienta do usługi AAD w subskrypcji platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="6f69a-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="6f69a-127">Rejestrowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="6f69a-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="6f69a-128">Dodaj klucz tajny klienta</span><span class="sxs-lookup"><span data-stu-id="6f69a-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="6f69a-129">W poniższych krokach zostaną użyte **Identyfikator aplikacji(Klient)**, **Tajny klucz klienta** i **Identyfikator dzierżawy**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="6f69a-130">Obecnie obsługiwanymi krajami i regionami są Kanada, Stany Zjednoczone i Unia Europejska (UE).</span><span class="sxs-lookup"><span data-stu-id="6f69a-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="6f69a-131">Jeśli masz pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="6f69a-132">Ustaw Dataverse</span><span class="sxs-lookup"><span data-stu-id="6f69a-132">Set up Dataverse</span></span>

<span data-ttu-id="6f69a-133">Aby używać Dataverse z widocznością zapasów, należy najpierw przygotować wymagania wstępne, a następnie zdecydować, czy należy skonfigurować Dataverse za pomocą narzędzia package deployer, czy też ręcznie zaimportować rozwiązania (nie trzeba ich obu).</span><span class="sxs-lookup"><span data-stu-id="6f69a-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="6f69a-134">Następnie zainstaluj dodatek Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="6f69a-135">W poniższych podrozdziałach opisano, jak wykonać każde z tych zadań.</span><span class="sxs-lookup"><span data-stu-id="6f69a-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="6f69a-136">Przygotowywanie wymagań wstępnych Dataverse</span><span class="sxs-lookup"><span data-stu-id="6f69a-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="6f69a-137">Przed rozpoczęciem konfigurowanie dodaj do dzierżawy zasadę Dataverse, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6f69a-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="6f69a-138">Zainstaluj moduł Azure AD PowerShell w wersji 2 zgodnie z opisem w [Zainstaluj Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="6f69a-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="6f69a-139">Uruchom następujące polecenie PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f69a-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="6f69a-140">Skonfiguruj Dataverse za pomocą narzędzia package deployer</span><span class="sxs-lookup"><span data-stu-id="6f69a-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="6f69a-141">Jeśli preferujesz skonfigurowanie za pomocą narzędzia package deployer Dataverse, użyj poniższych procedur.</span><span class="sxs-lookup"><span data-stu-id="6f69a-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="6f69a-142">Zobacz następną sekcję, aby uzyskać szczegółowe informacje o ręcznym importowaniu rozwiązań (nie obu).</span><span class="sxs-lookup"><span data-stu-id="6f69a-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="6f69a-143">Zainstaluj narzędzia deweloperskie zgodnie z opisem w tece [Pobieranie narzędzi z NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="6f69a-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="6f69a-144">W zależności od wymagań firmy wybierz `InventoryServiceBase` lub `InventoryServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="6f69a-145">Importowanie rozwiązań:</span><span class="sxs-lookup"><span data-stu-id="6f69a-145">Import the solutions:</span></span>
    1. <span data-ttu-id="6f69a-146">Dla pakietu `InventoryServiceBase`:</span><span class="sxs-lookup"><span data-stu-id="6f69a-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="6f69a-147">Rozpakuj `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="6f69a-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="6f69a-148">Znajdź pliki `InventoryServiceBase`, `[Content_Types].xml`, `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` i `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="6f69a-149">Skopiuj każdy z tych folderów i plików do katalogu `.\Tools\PackageDeployment`, który został utworzony podczas instalowania narzędzi dewelopera.</span><span class="sxs-lookup"><span data-stu-id="6f69a-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="6f69a-150">Dla pakietu `InventoryServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="6f69a-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="6f69a-151">Rozpakuj `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="6f69a-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="6f69a-152">Znajdź pliki `InventoryServiceApplication`, `[Content_Types].xml`, `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` i `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="6f69a-153">Skopiuj każdy z tych folderów i plików do katalogu `.\Tools\PackageDeployment`, który został utworzony podczas instalowania narzędzi dewelopera.</span><span class="sxs-lookup"><span data-stu-id="6f69a-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="6f69a-154">Wykonaj `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="6f69a-155">Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby zaimportować rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="6f69a-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="6f69a-156">Przypisz role zabezpieczeń użytkownikowi aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6f69a-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="6f69a-157">Otwórz adres URL środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6f69a-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="6f69a-158">Przejdź do opcji **Zaawansowane ustawianie \> System \> Bezpieczeństwo \> Użytkownicy** i znajdź użytkownika o nazwie **# InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="6f69a-159">Wybierz pozycję **Przypisz rolę**, a następnie pozycję **Administrator systemu**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="6f69a-160">Jeśli istnieje rola o nazwie **Użytkownik Common Data Service** również ją zaznacz.</span><span class="sxs-lookup"><span data-stu-id="6f69a-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="6f69a-161">Skonfiguruj Dataverse ręcznie, importując rozwiązania</span><span class="sxs-lookup"><span data-stu-id="6f69a-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="6f69a-162">Jeśli preferujesz skonfigurowanie za pomocą narzędzia wdrażania pakietu Dataverse, importuj ręcznie rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="6f69a-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="6f69a-163">Zobacz poprzednią sekcję, aby uzyskać szczegółowe informacje dotyczące używania zamiast tego narzędzia package deployer (nie używaj obu).</span><span class="sxs-lookup"><span data-stu-id="6f69a-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="6f69a-164">Utwórz użytkownika aplikacji dla Widoczność magazynu w Dataverse:</span><span class="sxs-lookup"><span data-stu-id="6f69a-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="6f69a-165">Otwórz adres URL środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6f69a-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="6f69a-166">Przejdź do **Ustawienia zaawansowane \> System \> Zabezpieczenia \> Użytkownicy** i utwórz użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6f69a-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="6f69a-167">Użyj menu Widok, aby zmienić widok strony na **Użytkowników aplikacji**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="6f69a-168">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-168">Select **New**.</span></span> <span data-ttu-id="6f69a-169">Ustaw Identyfikator aplikacji na *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="6f69a-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="6f69a-170">(Identyfikator obiektu zostanie automatycznie załadowany po zapisaniu zmian) Możesz dostosować nazwę.</span><span class="sxs-lookup"><span data-stu-id="6f69a-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="6f69a-171">Na przykład można zmienić go na *Widoczność magazynu*.</span><span class="sxs-lookup"><span data-stu-id="6f69a-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="6f69a-172">Po zakończeniu wybierz przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="6f69a-173">Wybierz pozycję **Przypisz rolę**, a następnie pozycję **Administrator systemu**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="6f69a-174">Jeśli istnieje rola o nazwie **Użytkownik Common Data Service** również ją zaznacz.</span><span class="sxs-lookup"><span data-stu-id="6f69a-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="6f69a-175">Aby uzyskać więcej informacji, zobacz [Utwórz użytkownika aplikacji](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="6f69a-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="6f69a-176">Jeśli domyślnym językem używanym przez Dataverse nie jest **angielski**:</span><span class="sxs-lookup"><span data-stu-id="6f69a-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="6f69a-177">Przejdź do **Ustawienia zaawansowane \> Administracja \> Języki**,</span><span class="sxs-lookup"><span data-stu-id="6f69a-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="6f69a-178">Wybierz **Język angielski (LanguageCode=1033)** i wybierz opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="6f69a-179">Importuj plik `Inventory Visibility Dataverse Solution.zip`, który zawiera jednostki powiązane z konfiguracją Dataverse i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="6f69a-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="6f69a-180">Przejdź do strony **Rozwiązania**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="6f69a-181">Wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-181">Select **Import**.</span></span>

1. <span data-ttu-id="6f69a-182">Importuj przepływ wyzwalacza uaktualnienia konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="6f69a-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="6f69a-183">Przechodzenie do strony Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="6f69a-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="6f69a-184">Upewnij się, że istnieje połączenie o nazwie *Dataverse (starsze)*.</span><span class="sxs-lookup"><span data-stu-id="6f69a-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="6f69a-185">(Jeśli nie istnieje, utwórz go)</span><span class="sxs-lookup"><span data-stu-id="6f69a-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="6f69a-186">Importuj plik `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="6f69a-187">Po zaimportowaniu wyzwalacz pojawi się w obszarze **Moje przepływy**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="6f69a-188">Inicjuj następujące cztery zmienne na podstawie informacji o środowisku:</span><span class="sxs-lookup"><span data-stu-id="6f69a-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="6f69a-189">Identyfikator dzierżawy systemu Azure</span><span class="sxs-lookup"><span data-stu-id="6f69a-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="6f69a-190">Identyfikator klienta aplikacji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="6f69a-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="6f69a-191">Wpis tajny klienta aplikacji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="6f69a-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="6f69a-192">Punkt końcowy Widoczności zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="6f69a-193">Aby uzyskać więcej informacji o tej zmiennej, zobacz sekcję [Konfiguracja integracji widoczności zapasów](#setup-inventory-visibility-integration) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="6f69a-194">![Wyzwalacz konfiguracji](media/configuration-trigger.png "Wyzwalacz konfiguracji")</span><span class="sxs-lookup"><span data-stu-id="6f69a-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="6f69a-195">Wybierz opcję **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="6f69a-196">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="6f69a-196">Install the add-in</span></span>

<span data-ttu-id="6f69a-197">Aby zainstalować dodatek Widoczność magazynu, trzeba:</span><span class="sxs-lookup"><span data-stu-id="6f69a-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="6f69a-198">Zalogować się do portalu [Microsoft LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="6f69a-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="6f69a-199">Na stronie głównej wybierz projekt, w którym jest wdrożone środowisko.</span><span class="sxs-lookup"><span data-stu-id="6f69a-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="6f69a-200">Na stronie projektu wybierz środowisko, w którym chcesz zainstalować dodatek.</span><span class="sxs-lookup"><span data-stu-id="6f69a-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="6f69a-201">Na stronie środowisko przewiń w dół do momentu, w sekcji **Dodatki środowiska**, w sekcji **Integracji Power Platform**, gdzie możesz znaleźć nazwę środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6f69a-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="6f69a-202">W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="6f69a-203">![Strona środowiska w LCS](media/inventory-visibility-environment.png "Strona środowiska w LCS")</span><span class="sxs-lookup"><span data-stu-id="6f69a-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="6f69a-204">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="6f69a-205">Zostanie otwarta lista dostępnych dodatków.</span><span class="sxs-lookup"><span data-stu-id="6f69a-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="6f69a-206">Z listy menu wybierz opcję **Widoczność magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="6f69a-207">Wprowadź wartości dla następujących pól środowiska:</span><span class="sxs-lookup"><span data-stu-id="6f69a-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="6f69a-208">**Identyfikator aplikacji AAD (klienta)**</span><span class="sxs-lookup"><span data-stu-id="6f69a-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="6f69a-209">**Identyfikator AAD dzierżawy**</span><span class="sxs-lookup"><span data-stu-id="6f69a-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="6f69a-210">![Strona konfiguracji dodatku](media/inventory-visibility-setup.png "Strona konfiguracji dodatku")</span><span class="sxs-lookup"><span data-stu-id="6f69a-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="6f69a-211">Zaakceptuj regulamin, zaznaczając pole wyboru **Regulamin**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="6f69a-212">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-212">Select **Install**.</span></span> <span data-ttu-id="6f69a-213">Stan dodatku będzie widoczny jako **Instalowany**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="6f69a-214">Po zakończeniu operacji odśwież stronę, aby zobaczyć zmianę stanu na **Zainstalowane**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="6f69a-215">Odinstalowywanie dodatku</span><span class="sxs-lookup"><span data-stu-id="6f69a-215">Uninstall the add-in</span></span>

<span data-ttu-id="6f69a-216">Aby odinstalować dodatek, wybierz opcję **Odinstaluj**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="6f69a-217">Po odświeżeniu LCS dodatek Widoczności magazynu zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="6f69a-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="6f69a-218">Proces dezinstalacji usuwa rejestrację dodatku, a także rozpoczyna zadanie czyszczenia wszystkich danych biznesowych przechowywanych w usłudze.</span><span class="sxs-lookup"><span data-stu-id="6f69a-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="6f69a-219">Zużycie danych o dostępnych zapasach z Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6f69a-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="6f69a-220">Wdróż pakiet integracyjny Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="6f69a-221">Jeśli korzystasz z rozwiązania Supply Chain Management w wersji 10.0.17 lub starszej, skontaktuj się z pokładowym zespołem pomocy technicznej ds. Widoczności zapasów pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com), aby uzyskać paczkę z plikami.</span><span class="sxs-lookup"><span data-stu-id="6f69a-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="6f69a-222">Następnie wdróż pakiet w LCS.</span><span class="sxs-lookup"><span data-stu-id="6f69a-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="6f69a-223">Jeśli podczas wdrażania wystąpi błąd niezgodności wersji, należy ręcznie zaimportować projekt X ++ do środowiska programistycznego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="6f69a-224">Następnie utwórz pakiet do wdrożenia w swoim środowisku programistycznym i wdróż go w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="6f69a-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="6f69a-225">Kod jest dołączony do programu Supply Chain Management w wersji 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="6f69a-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="6f69a-226">Jeśli używasz tej lub nowszej wersji, wdrożenie nie jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="6f69a-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="6f69a-227">Upewnij się, że poniższe funkcje są włączone w środowisku Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f69a-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="6f69a-228">(Domyślnie są włączone).</span><span class="sxs-lookup"><span data-stu-id="6f69a-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="6f69a-229">Opis funkcji</span><span class="sxs-lookup"><span data-stu-id="6f69a-229">Feature description</span></span> | <span data-ttu-id="6f69a-230">Wersja kodu</span><span class="sxs-lookup"><span data-stu-id="6f69a-230">Code version</span></span> | <span data-ttu-id="6f69a-231">Przełącz klasę</span><span class="sxs-lookup"><span data-stu-id="6f69a-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="6f69a-232">Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSum</span><span class="sxs-lookup"><span data-stu-id="6f69a-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="6f69a-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="6f69a-233">10.0.11</span></span> | <span data-ttu-id="6f69a-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="6f69a-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="6f69a-235">Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="6f69a-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="6f69a-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="6f69a-236">10.0.12</span></span> | <span data-ttu-id="6f69a-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="6f69a-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="6f69a-238">Konfiguracja integracji Widoczności zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="6f69a-239">W Supply Chain Management otwórz obszar roboczy **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i włącz funkcję **Integracja widoczności magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6f69a-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="6f69a-240">Przejdź do witryny **Zarządzanie zapasami \> Konfiguracja \> Parametry integracji widoczności magazynu**, i wprowadź adres URL środowiska, w którym jest uruchamiana widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="6f69a-241">Znajdź region systemu Azure środowiska usługi LCS, a następnie wprowadź adres URL.</span><span class="sxs-lookup"><span data-stu-id="6f69a-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="6f69a-242">Adres URL ma następujący formularz:</span><span class="sxs-lookup"><span data-stu-id="6f69a-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="6f69a-243">Na przykład, jeśli znajdujesz się w Europie, Twoje środowisko będzie mieć jeden z następujących adresów URL:</span><span class="sxs-lookup"><span data-stu-id="6f69a-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="6f69a-244">Obecnie dostępne są następujące regiony.</span><span class="sxs-lookup"><span data-stu-id="6f69a-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="6f69a-245">Region systemu Azure</span><span class="sxs-lookup"><span data-stu-id="6f69a-245">Azure region</span></span> | <span data-ttu-id="6f69a-246">Krótka nazwa regionu</span><span class="sxs-lookup"><span data-stu-id="6f69a-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="6f69a-247">Australia Wschodnia</span><span class="sxs-lookup"><span data-stu-id="6f69a-247">Australia east</span></span> | <span data-ttu-id="6f69a-248">eau</span><span class="sxs-lookup"><span data-stu-id="6f69a-248">eau</span></span> |
    | <span data-ttu-id="6f69a-249">Australia Południowo-Wschodnia</span><span class="sxs-lookup"><span data-stu-id="6f69a-249">Australia southeast</span></span> | <span data-ttu-id="6f69a-250">seau</span><span class="sxs-lookup"><span data-stu-id="6f69a-250">seau</span></span> |
    | <span data-ttu-id="6f69a-251">Kanada środkowa</span><span class="sxs-lookup"><span data-stu-id="6f69a-251">Canada central</span></span> | <span data-ttu-id="6f69a-252">cca</span><span class="sxs-lookup"><span data-stu-id="6f69a-252">cca</span></span> |
    | <span data-ttu-id="6f69a-253">Kanada wschodnia</span><span class="sxs-lookup"><span data-stu-id="6f69a-253">Canada east</span></span> | <span data-ttu-id="6f69a-254">eca</span><span class="sxs-lookup"><span data-stu-id="6f69a-254">eca</span></span> |
    | <span data-ttu-id="6f69a-255">Europa Północna</span><span class="sxs-lookup"><span data-stu-id="6f69a-255">North Europe</span></span> | <span data-ttu-id="6f69a-256">neu</span><span class="sxs-lookup"><span data-stu-id="6f69a-256">neu</span></span> |
    | <span data-ttu-id="6f69a-257">Europa Zachodnia</span><span class="sxs-lookup"><span data-stu-id="6f69a-257">West Europe</span></span> | <span data-ttu-id="6f69a-258">weu</span><span class="sxs-lookup"><span data-stu-id="6f69a-258">weu</span></span> |
    | <span data-ttu-id="6f69a-259">Wschodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6f69a-259">East US</span></span> | <span data-ttu-id="6f69a-260">eus</span><span class="sxs-lookup"><span data-stu-id="6f69a-260">eus</span></span> |
    | <span data-ttu-id="6f69a-261">Zachodnie stany USA</span><span class="sxs-lookup"><span data-stu-id="6f69a-261">West US</span></span> | <span data-ttu-id="6f69a-262">wus</span><span class="sxs-lookup"><span data-stu-id="6f69a-262">wus</span></span> |

1. <span data-ttu-id="6f69a-263">Przejdź do **Zarządzanie zapasami \> Okresowe \> Integracja widoczności magazynu** i włącz zadanie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="6f69a-264">Wszystkie zdarzenia zmiany zapasów z Supply Chain Management zostaną teraz zaksięgowane w widoczności magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="6f69a-265">Dodatek Widoczność magazynu w API publicznym</span><span class="sxs-lookup"><span data-stu-id="6f69a-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="6f69a-266">Publiczny interfejs API REST w dodatku Widoczność magazynu przedstawia kilka konkretnych punktów końcowych integracji.</span><span class="sxs-lookup"><span data-stu-id="6f69a-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="6f69a-267">Obsługuje on trzy główne typy interakcji:</span><span class="sxs-lookup"><span data-stu-id="6f69a-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="6f69a-268">Księgowanie dostępnych zmian zapasów w dodatku z systemu zewnętrznego</span><span class="sxs-lookup"><span data-stu-id="6f69a-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="6f69a-269">Badanie bieżących ilości dostępnych zapasów z systemu zewnętrznego</span><span class="sxs-lookup"><span data-stu-id="6f69a-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="6f69a-270">Automatyczna synchronizacja z dostępnymi zapasami Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6f69a-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="6f69a-271">Synchronizacja automatyczna nie jest częścią publicznego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6f69a-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="6f69a-272">Jest natomiast obsługiwane w tle środowisk, w których jest włączony dodatek Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="6f69a-273">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="6f69a-273">Authentication</span></span>

<span data-ttu-id="6f69a-274">Token zabezpieczeń platformy służy do wywołania dodatku Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="6f69a-275">Dlatego należy wygenerować *token Azure Active Directory (Azure AD)* przy użyciu aplikacji Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6f69a-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="6f69a-276">Następnie należy użyć tokenu Azure AD, aby uzyskać *token dostępu* z usługi zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="6f69a-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="6f69a-277">Aby uzyskać token usługi zabezpieczeń, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6f69a-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="6f69a-278">Zaloguj się do witryny Azure i użyj go, aby znaleźć parametry `clientId` i `clientSecret` dla aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f69a-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="6f69a-279">Pobiera token usługi Azure Active Directory (`aadToken`), przesyłając żądanie HTTP z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="6f69a-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="6f69a-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="6f69a-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="6f69a-281">**Metoda** - `GET`</span><span class="sxs-lookup"><span data-stu-id="6f69a-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="6f69a-282">**Treść (dane formularza)**:</span><span class="sxs-lookup"><span data-stu-id="6f69a-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="6f69a-283">klucz</span><span class="sxs-lookup"><span data-stu-id="6f69a-283">key</span></span> | <span data-ttu-id="6f69a-284">wartość</span><span class="sxs-lookup"><span data-stu-id="6f69a-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="6f69a-285">client_id</span><span class="sxs-lookup"><span data-stu-id="6f69a-285">client_id</span></span> | <span data-ttu-id="6f69a-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="6f69a-286">${aadAppId}</span></span> |
        | <span data-ttu-id="6f69a-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="6f69a-287">client_secret</span></span> | <span data-ttu-id="6f69a-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="6f69a-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="6f69a-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="6f69a-289">grant_type</span></span> | <span data-ttu-id="6f69a-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="6f69a-290">client_credentials</span></span> |
        | <span data-ttu-id="6f69a-291">resource</span><span class="sxs-lookup"><span data-stu-id="6f69a-291">resource</span></span> | <span data-ttu-id="6f69a-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="6f69a-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="6f69a-293">Otrzymasz w odpowiedzi token `aadToken`, który przypomina poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="6f69a-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="6f69a-294">Formułuj żądanie JSON przypominające:</span><span class="sxs-lookup"><span data-stu-id="6f69a-294">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="6f69a-295">Gdzie:</span><span class="sxs-lookup"><span data-stu-id="6f69a-295">Where:</span></span>
    - <span data-ttu-id="6f69a-296">Wartość `client_assertion` musi być tokenem `aadToken` otrzymanym w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="6f69a-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="6f69a-297">Wartość `context` musi być identyfikatorem środowiska, w którym ma zostać wdrożony dodatek.</span><span class="sxs-lookup"><span data-stu-id="6f69a-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="6f69a-298">Ustaw wszystkie inne wartości, tak jak pokazano w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="6f69a-299">Prześlij żądanie HTTP z następującymi właściwościami:</span><span class="sxs-lookup"><span data-stu-id="6f69a-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="6f69a-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="6f69a-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="6f69a-301">**Metoda** - `POST`</span><span class="sxs-lookup"><span data-stu-id="6f69a-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="6f69a-302">**Nagłówek HTTP** — uwzględnij wersję interfejsu API (klucz to `Api-Version`, wartość to `1.0`)</span><span class="sxs-lookup"><span data-stu-id="6f69a-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="6f69a-303">**Treść** — umożliwia dołączenie żądania JSON utworzonego w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="6f69a-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="6f69a-304">Otrzymasz `access_token` w odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="6f69a-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="6f69a-305">Do wywołania interfejsu API Widoczność magazynu potrzebny jest token elementu nośnego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="6f69a-306">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="6f69a-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="6f69a-307">Przykładowe żądanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-307">Sample Request</span></span>

<span data-ttu-id="6f69a-308">W celach informacyjnych, oto przykładowe żądanie http, możesz użyć dowolnego narzędzia lub języka kodowania, aby wysłać to żądanie, na przykład ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="6f69a-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="6f69a-309">Skonfiguruj interfejs API funkcji Widoczność magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="6f69a-310">Przed rozpoczęciem korzystania z usługi należy wykonać konfiguracje opisane w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="6f69a-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="6f69a-311">Konfiguracja może się różnić w zależności od szczegółów środowiska.</span><span class="sxs-lookup"><span data-stu-id="6f69a-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="6f69a-312">Obejmuje ono głównie cztery części:</span><span class="sxs-lookup"><span data-stu-id="6f69a-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="6f69a-313">Partycjonowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="6f69a-314">Konfiguracje wymiarów</span><span class="sxs-lookup"><span data-stu-id="6f69a-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="6f69a-315">Indeksowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="6f69a-316">Miara niestandardowa</span><span class="sxs-lookup"><span data-stu-id="6f69a-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="6f69a-317">Partycjonowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-317">Partitioning</span></span>

<span data-ttu-id="6f69a-318">Partycjonowanie może znacząco wpłynąć na wydajność interfejsu API funkcji Widoczność magazynu.</span><span class="sxs-lookup"><span data-stu-id="6f69a-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="6f69a-319">Dobrym pomysłem jest zdefiniowanie schematu, który umożliwi obsługę małych grup danych, a jednocześnie pozwala na uzyskanie istotnych kwerend dotyczących danych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="6f69a-320">`organizationId` (`dataAreaId` w Supply Chain Management) zawsze jest częścią partycjonowania, a domyślnie Widoczność magazynu jest ustawiana jako partycja według wymiarów jako *Oddział + Lokalizacja*.</span><span class="sxs-lookup"><span data-stu-id="6f69a-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="6f69a-321">Oznacza to, że usługa musi być zawsze kwerendą o wymiarach zdefiniowane w filtrach.</span><span class="sxs-lookup"><span data-stu-id="6f69a-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="6f69a-322">*Oddział* i *Lokalizacja* to dwa ogólne wymiary domyślne w obszarze Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="6f69a-323">W Supply Chain Management te wymiary są nazywane *Oddziałem* (`InventSiteId`) i *Magazynem* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="6f69a-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="6f69a-324">Konfiguracje wymiarów</span><span class="sxs-lookup"><span data-stu-id="6f69a-324">Dimension configurations</span></span>

<span data-ttu-id="6f69a-325">Widoczność magazynu będzie zawierać listę ogólnych wymiarów, które umożliwiają integrację z systemem z wieloma źródłami.</span><span class="sxs-lookup"><span data-stu-id="6f69a-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="6f69a-326">W poniższej tabeli wymieniono wymiary magazynowe, które będą domyślnymi nazwami wymiarów widocznymi w obszarze Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="6f69a-327">Typ wymiaru</span><span class="sxs-lookup"><span data-stu-id="6f69a-327">Dimension type</span></span> | <span data-ttu-id="6f69a-328">Nazwa wymiaru</span><span class="sxs-lookup"><span data-stu-id="6f69a-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="6f69a-329">Produkt</span><span class="sxs-lookup"><span data-stu-id="6f69a-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="6f69a-330">Produkt</span><span class="sxs-lookup"><span data-stu-id="6f69a-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="6f69a-331">Produkt</span><span class="sxs-lookup"><span data-stu-id="6f69a-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="6f69a-332">Produkt</span><span class="sxs-lookup"><span data-stu-id="6f69a-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="6f69a-333">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="6f69a-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="6f69a-334">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="6f69a-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="6f69a-335">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="6f69a-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="6f69a-336">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="6f69a-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="6f69a-337">Stan zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="6f69a-338">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="6f69a-339">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="6f69a-340">Właściwe dla magazynu</span><span class="sxs-lookup"><span data-stu-id="6f69a-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="6f69a-341">Typ wymiaru wymieniony w poprzedniej tabeli służy tylko do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="6f69a-342">Nie trzeba definiować typu wymiaru w funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="6f69a-343">Jeśli wymiar niestandardowy istnieje i musi przepływać do wartości domyślnej w przypadku zużycia przez Widoczność zapasów, można skonfigurować **niestandardową** nazwę wymiaru w funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="6f69a-344">Widoczność zapasów w systemie zewnętrznym za pośrednictwem interfejsów API RESTful, które umożliwiają uzyskiwanie dostępnych informacji na temat danego zestawu wymiarów do zbadania.</span><span class="sxs-lookup"><span data-stu-id="6f69a-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="6f69a-345">W przypadku integracji funkcja Widoczność zapasów umożliwia skonfigurowanie *źródła danych kanału zewnętrznego* i wymiaru źródłowego do *Wymiarów docelowych* w ramach funkcji Widoczność zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="6f69a-346">Wymiar docelowy powinien mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="6f69a-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="6f69a-347">Wymiary domyślne w funkcji Widoczność zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="6f69a-348">Wymiary niestandardowe</span><span class="sxs-lookup"><span data-stu-id="6f69a-348">Custom dimensions</span></span>

<span data-ttu-id="6f69a-349">Celem konfiguracji wymiarów jest ujednolicenie integracji wielosystemowej dla kwerendy dotyczącej wymiarów i zdarzenia księgowania z wymiarami.</span><span class="sxs-lookup"><span data-stu-id="6f69a-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="6f69a-350">Indeksowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-350">Indexing</span></span>

<span data-ttu-id="6f69a-351">W większości momentów zapytanie o dostępne zapasy nie będzie zwracane tylko na najwyższym poziomie „suma”, ale wyniki zagregowane mogą być wyświetlane na podstawie wymiarów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="6f69a-352">Widoczność zapasów zapewnia elastyczność, umożliwiając konfigurowanie indeksów opartych na wymiarze lub kombinacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="6f69a-353">Obecnie można konfigurować indeksy tylko do maks. pięć.</span><span class="sxs-lookup"><span data-stu-id="6f69a-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="6f69a-354">Należy dokładnie rozważyć, którą kombinację wymiarów należy zastosować przed implementacją, aby zagwarantować, że będzie ona zgodna z potrzebami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="6f69a-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="6f69a-355">Na przykład, jeśli chcesz zbadać produkty w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6f69a-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="6f69a-356">Umożliwia wykonanie kwerendy dotyczącej zagregowanych dostępnych zapasów towaru, korzystając z wymiarów *Kolor* i *Rozmiar*.</span><span class="sxs-lookup"><span data-stu-id="6f69a-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="6f69a-357">W niektórych przypadkach użytkownik chce jedynie wykonać kwerendę dotyczącą produktu łącznie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="6f69a-358">Dwa indeksy powinny mieć zdefiniowane następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="6f69a-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="6f69a-359">Pusty nawias będzie agregował na podstawie identyfikatora produktu w partycji.</span><span class="sxs-lookup"><span data-stu-id="6f69a-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="6f69a-360">Indeksowanie określa sposób grupowania wyników na podstawie ustawienia kwerendy `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="6f69a-361">W takim przypadku, jeśli nie zostaną zdefiniowane żadne wartości `groupBy`, sumy będą pobierane według `productid`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="6f69a-362">W przeciwnym razie, jeśli zostanie zdefiniowana `groupBy` jako `groupBy=ColorId&groupBy=SizeId`, zostanie otrzymanych wiele wierszy na podstawie różnych kombinacji koloru i rozmiaru w systemie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="6f69a-363">Kryteria kwerendy można umieścić w treści żądania.</span><span class="sxs-lookup"><span data-stu-id="6f69a-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="6f69a-364">Oto przykładowe zapytanie dotyczące produktu z kombinacją koloru i rozmiaru.</span><span class="sxs-lookup"><span data-stu-id="6f69a-364">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

<span data-ttu-id="6f69a-365">W przypadku pola `filters` tylko `ProductId` aktualnie obsługuje wiele wartości.</span><span class="sxs-lookup"><span data-stu-id="6f69a-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="6f69a-366">Jeśli `ProductId` to pusta tablica, zapytanie będzie dotyczyło wszystkich produktów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="6f69a-367">Miara niestandardowa</span><span class="sxs-lookup"><span data-stu-id="6f69a-367">Custom measurement</span></span>

<span data-ttu-id="6f69a-368">Domyślne ilości miar są połączone z Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f69a-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="6f69a-369">Jednakże może być wymagane, aby ilość składała się z kombinacji domyślnych miar.</span><span class="sxs-lookup"><span data-stu-id="6f69a-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="6f69a-370">W tym celu można skonfigurować niestandardowe ilości, które zostaną dodane do danych wyjściowych zapytań dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="6f69a-371">Funkcja umożliwia po prostu zdefiniowanie zestawu miar, które będą dodawane, i/lub zestawu miar, które zostaną odjęte od miary niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="6f69a-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="6f69a-372">Na przykład przy użyciu poniższego warunku kwerendy można skonfigurować niestandardową ilość miary jako `MyCustomAvailableforReservation`, która będzie zużywana przez system zużycia.</span><span class="sxs-lookup"><span data-stu-id="6f69a-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="6f69a-373">System zużycia</span><span class="sxs-lookup"><span data-stu-id="6f69a-373">Consumption system</span></span> | <span data-ttu-id="6f69a-374">Obliczone miary</span><span class="sxs-lookup"><span data-stu-id="6f69a-374">Calculated measurers</span></span> | <span data-ttu-id="6f69a-375">Źródło danych</span><span class="sxs-lookup"><span data-stu-id="6f69a-375">Data source</span></span> | <span data-ttu-id="6f69a-376">Modyfikator</span><span class="sxs-lookup"><span data-stu-id="6f69a-376">Modifier</span></span> | <span data-ttu-id="6f69a-377">Typ obliczania modyfikatora</span><span class="sxs-lookup"><span data-stu-id="6f69a-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="6f69a-378">Dodanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="6f69a-379">Dodanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="6f69a-380">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="6f69a-381">Dodanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="6f69a-382">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="6f69a-383">Dodanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="6f69a-384">Dodanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="6f69a-385">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="6f69a-386">Odejmowanie</span><span class="sxs-lookup"><span data-stu-id="6f69a-386">Subtraction</span></span> |

<span data-ttu-id="6f69a-387">Dzięki temu kwerenda dotycząca niestandardowej ilości miary zwróci następujące dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="6f69a-388">Dane wyjściowe `MyCustomAvailableforReservation` są oparte na ustawieniu obliczania w niestandardowych pomiarach jako:</span><span class="sxs-lookup"><span data-stu-id="6f69a-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="6f69a-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="6f69a-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="6f69a-390">Księgowanie zmian dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-390">Posting on-hand changes</span></span>

<span data-ttu-id="6f69a-391">Dokładny adres URL, na który zostanie ogłoszone zdarzenie, zależy od regionu geograficznego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="6f69a-392">Przyjmie on postać:</span><span class="sxs-lookup"><span data-stu-id="6f69a-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="6f69a-393">Po uwierzytelnieniu ten adres URL może być używany wraz z HTTP `POST` w celu wysyłania do usługi zdarzeń zmiany dostępnych zapasów.</span><span class="sxs-lookup"><span data-stu-id="6f69a-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="6f69a-394">Specjalny nagłówek jest używany do komunikowania się z usługami Dynamics 365 Services za pośrednictwem żądań HTTP, oznaczający identyfikator środowiska Supply Chain Management, z którym są połączone dane.</span><span class="sxs-lookup"><span data-stu-id="6f69a-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="6f69a-395">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="6f69a-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="6f69a-396">Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 1</span><span class="sxs-lookup"><span data-stu-id="6f69a-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="6f69a-397">W tym przykładzie przedstawiono scenariusz, w którym zostanie ustawiona konfiguracja wymiaru w programie Power Apps.</span><span class="sxs-lookup"><span data-stu-id="6f69a-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="6f69a-398">Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:</span><span class="sxs-lookup"><span data-stu-id="6f69a-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="6f69a-399">Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary.</span><span class="sxs-lookup"><span data-stu-id="6f69a-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="6f69a-400">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="6f69a-401">Wysyłanie zapytania o zmiany dostępnych zapasów — przykład 2</span><span class="sxs-lookup"><span data-stu-id="6f69a-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="6f69a-402">W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="6f69a-403">Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null, jest puste lub zawiera białe znaki.</span><span class="sxs-lookup"><span data-stu-id="6f69a-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="6f69a-404">Edytowanie pól właściwości dokumentów JSON</span><span class="sxs-lookup"><span data-stu-id="6f69a-404">JSON document field properties</span></span>

<span data-ttu-id="6f69a-405">Pola z dostarczonych wcześniej przykładów zapytania JSON mają właściwości wymienione w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="6f69a-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="6f69a-406">Identyfikator pola</span><span class="sxs-lookup"><span data-stu-id="6f69a-406">Field ID</span></span> | <span data-ttu-id="6f69a-407">opis</span><span class="sxs-lookup"><span data-stu-id="6f69a-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="6f69a-408">Unikatowy identyfikator określonego zdarzenia zmiany.</span><span class="sxs-lookup"><span data-stu-id="6f69a-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="6f69a-409">Ten identyfikator służy do zapewnienia, że jeśli komunikacja z usługą nie powiedzie się w trakcie księgowania, ponowne przesłanie zdarzenia nie spowoduje, że zdarzenie to jest zliczane dwukrotnie w systemie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="6f69a-410">Identyfikator organizacji połączonej ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="6f69a-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="6f69a-411">Ta opcja jest mapowana na dane organizacji Supply Chain Management lub identyfikatory obszaru danych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="6f69a-412">Identyfikator zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="6f69a-413">Ilość, o którą należy zmienić dostępne zapasy.</span><span class="sxs-lookup"><span data-stu-id="6f69a-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="6f69a-414">Jeśli na przykład do półki dodano 10 nowych bajgli, ta wartość byłaby równa 10.</span><span class="sxs-lookup"><span data-stu-id="6f69a-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="6f69a-415">Jeśli 3 bajgle zostały usunięte z półki lub sprzedane, ta wartość wynosi-3.</span><span class="sxs-lookup"><span data-stu-id="6f69a-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="6f69a-416">Źródło danych wymiarów używanych w zdarzeniu zmiany księgowania i kwerendzie.</span><span class="sxs-lookup"><span data-stu-id="6f69a-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="6f69a-417">W przypadku określenia źródła danych można wykorzystać niestandardowe wymiary z określonego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="6f69a-418">W przypadku konfiguracji wymiarów widoczność zapasów może mapować niestandardowe wymiary do ogólnych wymiarów domyślnych.</span><span class="sxs-lookup"><span data-stu-id="6f69a-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="6f69a-419">Jeśli `dimensionDataSource` nie określiło wartości, w kwerendach można stosować tylko ogólne wymiary domyślne.</span><span class="sxs-lookup"><span data-stu-id="6f69a-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="6f69a-420">Dynamiczny zbiór par klucz-wartość.</span><span class="sxs-lookup"><span data-stu-id="6f69a-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="6f69a-421">Zostaną one zmapowane na niektóre wymiary w module Supply Chain Management, ale można również dodać niestandardowe wymiary (np *źródło*), które mogą oznaczać, że zdarzenie pochodzi z Supply Chain Management lub z systemu zewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="6f69a-422">Badanie bieżących dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="6f69a-422">Querying current on-hand</span></span>

<span data-ttu-id="6f69a-423">Punkt końcowy badania bieżących dostępnych zapasów będzie miał podobny adres URL:</span><span class="sxs-lookup"><span data-stu-id="6f69a-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="6f69a-424">Zostanie zbadany za pomocą metody HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="6f69a-425">Bieżąca kwerenda dostępnych zapasów — przykład 1</span><span class="sxs-lookup"><span data-stu-id="6f69a-425">Current on-hand query example 1</span></span>

<span data-ttu-id="6f69a-426">W tym przykładzie przedstawiono scenariusz, w którym została zakończona konfiguracja wymiaru w programie Power Apps.</span><span class="sxs-lookup"><span data-stu-id="6f69a-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="6f69a-427">Aby skonfigurować mapowanie wymiaru w programie, należy skorzystać z następującej kwerendy Power Apps:</span><span class="sxs-lookup"><span data-stu-id="6f69a-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="6f69a-428">Teraz można określić `dimensionDataSource` i zastosować w kwerendach niestandardowe wymiary.</span><span class="sxs-lookup"><span data-stu-id="6f69a-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="6f69a-429">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="6f69a-430">Istnieje możliwość określenia wartości `DimensionDataSource` w polu `filters` i określenia wymiarów niestandardowych w polach `filters` i `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="6f69a-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="6f69a-431">System automatycznie przekonwertuje niestandardowe wymiary na wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="6f69a-432">Bieżąca kwerenda dostępnych zapasów — przykład 2</span><span class="sxs-lookup"><span data-stu-id="6f69a-432">Current on-hand query example 2</span></span>

<span data-ttu-id="6f69a-433">W tym przykładzie przedstawiono scenariusz, w którym nie skonfigurowano żadnych mapowań konfiguracji wymiarów w systemie Power Apps, więc Księgowanie powinno również mieć wymiary podstawowe.</span><span class="sxs-lookup"><span data-stu-id="6f69a-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="6f69a-434">Wszystkie wymiary muszą być wymiarami podstawowymi, jeśli pole `dimensionDataSource` ma wartość null w `filters`, jest puste lub zawiera białe znaki.</span><span class="sxs-lookup"><span data-stu-id="6f69a-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="6f69a-435">Przykładowy wynik zwrotu</span><span class="sxs-lookup"><span data-stu-id="6f69a-435">Example return result</span></span>

<span data-ttu-id="6f69a-436">Kwerendy przedstawione w poprzednich przykładach mogą zwracać wynik podobny do tego.</span><span class="sxs-lookup"><span data-stu-id="6f69a-436">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="6f69a-437">Należy zwrócić uwagę, że pola ilości są ustrukturyzowane i w postaci słownika miar i skojarzonych z nimi wartości.</span><span class="sxs-lookup"><span data-stu-id="6f69a-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
