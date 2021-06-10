---
title: Uaktualnianie do modelu globalnej książki adresowej i strony
description: W tym temacie opisano sposób uaktualniania danych o dwóch zapisach do strony globalna książka adresowa modelu.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112680"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="2ef8b-103">Uaktualnianie do modelu globalnej książki adresowej i strony</span><span class="sxs-lookup"><span data-stu-id="2ef8b-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2ef8b-104">[Szablon Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) pomaga zaktualizować istniejące tabele danych **Konto**, **Kontakt** i **Dostawca** za pomocą podwójnego zapisu dla strony i modelu globalnej książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="2ef8b-105">Szablon uzgadnia dane z aplikacji Finance and Operations oraz aplikacji angażujących klientów.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="2ef8b-106">Na zakończenie procesu zostaną utworzone i skojarzone pola **Strona** i **Kontakt** dla rekordów **Strony** z rekordami **Konto**, **Kontakt** i **Dostawca** w aplikacjach zaangażowania kllienta.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="2ef8b-107">Zostanie wygenerowany plik csv (`FONewParty.csv`) w celu utworzenia nowych rekordów **Strona** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="2ef8b-108">Ten temat zawiera instrukcje dotyczące używania szablonu Data Factory i uaktualniania danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="2ef8b-109">Jeśli nie masz żadnych dostosowań, możesz użyć szablonu w takiej postaci, w jakiej jest.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="2ef8b-110">Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon, korzystając z poniższych instrukcji.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef8b-111">Szablon uaktualnia tylko dane **Strony**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="2ef8b-112">W przyszłej wersji zostaną uwzględnione adresy pocztowe i elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ef8b-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2ef8b-113">Prerequisites</span></span>

<span data-ttu-id="2ef8b-114">Do uaktualnienia do modelu imprez i globalnej książki adresowej wymagane są następujące warunki wstępne:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="2ef8b-115">Subskrypcja platformy Azure</span><span class="sxs-lookup"><span data-stu-id="2ef8b-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="2ef8b-116">Dostęp do szablonu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="2ef8b-117">Musisz być istniejącym klientem podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="2ef8b-118">Przygotowanie do aktualizacji</span><span class="sxs-lookup"><span data-stu-id="2ef8b-118">Prepare for the upgrade</span></span>
<span data-ttu-id="2ef8b-119">Aby przygotować się do aktualizacji, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="2ef8b-120">**W pełni zsynchronizowane**: oba środowiska są w pełni zsynchronizowane dla **Konto (klient)**, **Kontakt** i **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="2ef8b-121">**Klucze integracji**: tabele **konto (Klient)**, **Kontakt** i **Dostawca** w aplikacjach do obsługi klienta są dostępne za pomocą kluczy integracji, które są gotowe do użytku.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="2ef8b-122">Jeśli użytkownik dostosuje klucze integracji, należy dostosować szablon.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="2ef8b-123">**Numer strony**: Wszystkie rekody **Konto (Klient)**, **Kontakt** i **Dostawca**, które zostaną zaktualizowane, mają numer **Strony**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="2ef8b-124">Rekordy bez numeru **Strony** zostaną zignorowane.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="2ef8b-125">Aby uaktualnić te rekordy, dodaj do nich numer **Strony** przed rozpoczęciem procesu uaktualniania.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="2ef8b-126">**Okres przestoju systemu**: Podczas procesu uaktualniania konieczne będzie przełączenie środowisk Finance and Operations oraz obsługi klienta do trybu offline.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="2ef8b-127">**Migawka**: tworzenie migawki aplikacji Finance and Operations i aplikacji obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="2ef8b-128">W razie potrzeby użyj migawki, aby przywrócić poprzedni stan.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="2ef8b-129">Wdrażanie</span><span class="sxs-lookup"><span data-stu-id="2ef8b-129">Deployment</span></span>

1. <span data-ttu-id="2ef8b-130">Pobierz szablon z witryny [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="2ef8b-131">Zaloguj się w [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="2ef8b-132">Wybierz [grupę zasobów](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="2ef8b-133">Utwórz [konto magazynu](/azure/storage/common/storage-account-create?tabs=azure-portal) w utworzonej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="2ef8b-134">Utwórz [fabryke danych](/azure/data-factory/quickstart-create-data-factory-portal) w utworzonej powyżej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="2ef8b-135">Otwórz fabrykę danych i wybierz kafelek **Twórz i Monitoruj**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="2ef8b-136">Na karcie **Zarządzaj** wybierz **Szablon ARM**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="2ef8b-137">Wybierz **Importuj szablon ARM**, aby zaimportować szablon **Strony**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="2ef8b-138">Importowanie szablonu do fabryki danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-138">Import the template into the data factory.</span></span> <span data-ttu-id="2ef8b-139">Wprowadź następujące wartości **Szczegółów projektu** i **Szczegółów wystąpienia**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="2ef8b-140">Pole</span><span class="sxs-lookup"><span data-stu-id="2ef8b-140">Field</span></span> | <span data-ttu-id="2ef8b-141">Wartość</span><span class="sxs-lookup"><span data-stu-id="2ef8b-141">Value</span></span>
    ---|---
    <span data-ttu-id="2ef8b-142">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="2ef8b-142">Subscription</span></span> | <span data-ttu-id="2ef8b-143">Subskrypcja platformy Azure</span><span class="sxs-lookup"><span data-stu-id="2ef8b-143">Azure subscription</span></span>
    <span data-ttu-id="2ef8b-144">Grupa zasobów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-144">Resource group</span></span> | <span data-ttu-id="2ef8b-145">Podaj ten sam zasób, pod którym zostanie utworzone konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="2ef8b-146">Region</span><span class="sxs-lookup"><span data-stu-id="2ef8b-146">Region</span></span> | <span data-ttu-id="2ef8b-147">Określ region.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-147">Specify region.</span></span>
    <span data-ttu-id="2ef8b-148">Nazwa fabryki</span><span class="sxs-lookup"><span data-stu-id="2ef8b-148">Factory Name</span></span> | <span data-ttu-id="2ef8b-149">Określ nazwę fabryki.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-149">Specify factory name.</span></span>
    <span data-ttu-id="2ef8b-150">FO Powiązanego klucza głównego Service_service</span><span class="sxs-lookup"><span data-stu-id="2ef8b-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="2ef8b-151">Określ klucz aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-151">Specify the application's key.</span></span>
    <span data-ttu-id="2ef8b-152">Ciąg Azure Blob Storage_connection</span><span class="sxs-lookup"><span data-stu-id="2ef8b-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="2ef8b-153">Parametry połączenia usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="2ef8b-154">Hasło usługi powiązane z Dynamics Crm</span><span class="sxs-lookup"><span data-stu-id="2ef8b-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="2ef8b-155">Hasło do konta użytkownika określonego jako nazwa użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="2ef8b-156">FO Połączone Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="2ef8b-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="2ef8b-157">FO Połączone Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="2ef8b-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="2ef8b-158">Określ informacje o dzierżawcy (nazwę domeny lub identyfikator dzierżawy), pod którymi znajduje się aplikacja.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="2ef8b-159">FO Połączone Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="2ef8b-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="2ef8b-160">FO Połączone Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="2ef8b-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="2ef8b-161">Określ identyfikator klienta aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="2ef8b-162">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="2ef8b-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="2ef8b-163">Nazwa użytkownika do połączenia z Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="2ef8b-164">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="2ef8b-165">Ręczne promowanie szablonu Resource Manager dla każdego środowiska</span><span class="sxs-lookup"><span data-stu-id="2ef8b-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="2ef8b-166">Połączone właściwości usługi</span><span class="sxs-lookup"><span data-stu-id="2ef8b-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="2ef8b-167">Kopiowanie danych przy użyciu Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="2ef8b-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="2ef8b-168">Po wdrożeniu sprawdź poprawność zestawów danych, przepływu danych i połączonej usługi fabryki danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Zestawy danych, przepływ danych i połączona usługa](media/data-factory-validate.png)

11. <span data-ttu-id="2ef8b-170">Przejdź do **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-170">Navigate to **Manage**.</span></span> <span data-ttu-id="2ef8b-171">W obszarze **Połączenia** wybierz pozycję **Połączona usługa**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="2ef8b-172">Wybierz **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="2ef8b-173">W formularzu **Edycja połączonej usługi (Dynamics CRM)** wprowadź następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="2ef8b-174">Pole</span><span class="sxs-lookup"><span data-stu-id="2ef8b-174">Field</span></span> | <span data-ttu-id="2ef8b-175">Wartość</span><span class="sxs-lookup"><span data-stu-id="2ef8b-175">Value</span></span>
    ---|---
    <span data-ttu-id="2ef8b-176">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="2ef8b-176">Name</span></span> | <span data-ttu-id="2ef8b-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="2ef8b-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="2ef8b-178">opis</span><span class="sxs-lookup"><span data-stu-id="2ef8b-178">Description</span></span> | <span data-ttu-id="2ef8b-179">Połączone usługi nawiązania połączenia z wystąpieniem CRM w celu pobrania danych jednostek</span><span class="sxs-lookup"><span data-stu-id="2ef8b-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="2ef8b-180">Połącz za pomocą środowiska uruchomieniowego integracji</span><span class="sxs-lookup"><span data-stu-id="2ef8b-180">Connect via integration runtime</span></span> | <span data-ttu-id="2ef8b-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="2ef8b-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="2ef8b-182">Typ wdrożenia</span><span class="sxs-lookup"><span data-stu-id="2ef8b-182">Deployment type</span></span> | <span data-ttu-id="2ef8b-183">Online</span><span class="sxs-lookup"><span data-stu-id="2ef8b-183">Online</span></span>
    <span data-ttu-id="2ef8b-184">URI usługi</span><span class="sxs-lookup"><span data-stu-id="2ef8b-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="2ef8b-185">Typ uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="2ef8b-185">Authentication type</span></span> | <span data-ttu-id="2ef8b-186">Office365</span><span class="sxs-lookup"><span data-stu-id="2ef8b-186">Office365</span></span>
    <span data-ttu-id="2ef8b-187">Nazwa użytkownika</span><span class="sxs-lookup"><span data-stu-id="2ef8b-187">User name</span></span> |
    <span data-ttu-id="2ef8b-188">Hasło lub klucz Azure</span><span class="sxs-lookup"><span data-stu-id="2ef8b-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="2ef8b-189">Hasło</span><span class="sxs-lookup"><span data-stu-id="2ef8b-189">Password</span></span>
    <span data-ttu-id="2ef8b-190">Hasło</span><span class="sxs-lookup"><span data-stu-id="2ef8b-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="2ef8b-191">Uruchom szablon.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-191">Run the template</span></span>

1. <span data-ttu-id="2ef8b-192">Zatrzymaj korzystanie z mapowania podwójnego zapisu **Konto**, **Kontakt** i **Dostawca** za pomocą aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="2ef8b-193">Odbiorcy wersja 3 (konta)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="2ef8b-194">Odbiorcy wersja 3(kontakty)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="2ef8b-195">CDS Kontakty V2(kontakty)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="2ef8b-196">CDS Kontakty V2(kontakty)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="2ef8b-197">Dostawca wersja 2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="2ef8b-198">Upewnij się, że mapy zostały usunięte z tabeli `msdy_dualwriteruntimeconfig` w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="2ef8b-199">Zainstaluj [Rozwiązania z podwójnym zapisem i globalna książka adresowa](https://aka.ms/dual-write-gab) z AppSource.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="2ef8b-200">W aplikacji Finance and Operations, jeśli poniższe tabele zawierają dane, uruchom dla nich **wstępną synchronizację**.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="2ef8b-201">Zwroty grzecznościowe</span><span class="sxs-lookup"><span data-stu-id="2ef8b-201">Salutations</span></span>
    + <span data-ttu-id="2ef8b-202">Typy osób</span><span class="sxs-lookup"><span data-stu-id="2ef8b-202">Personal character types</span></span>
    + <span data-ttu-id="2ef8b-203">Formuła grzecznościowa</span><span class="sxs-lookup"><span data-stu-id="2ef8b-203">Complimentary closing</span></span>
    + <span data-ttu-id="2ef8b-204">Tytuły osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="2ef8b-204">Contact person titles</span></span>
    + <span data-ttu-id="2ef8b-205">Role podejmujące decyzje</span><span class="sxs-lookup"><span data-stu-id="2ef8b-205">Decision making roles</span></span>
    + <span data-ttu-id="2ef8b-206">Poziomy lojalności</span><span class="sxs-lookup"><span data-stu-id="2ef8b-206">Loyalty levels</span></span>

5. <span data-ttu-id="2ef8b-207">W aplikacji obsługi klienta wyłącz poniższe kroki dodatku plug-in.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="2ef8b-208">Aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-208">Account Update</span></span>
         + <span data-ttu-id="2ef8b-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="2ef8b-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="2ef8b-211">Aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-211">Contact Update</span></span>
         + <span data-ttu-id="2ef8b-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="2ef8b-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="2ef8b-214">msdyn_party aktualizacja</span><span class="sxs-lookup"><span data-stu-id="2ef8b-214">msdyn_party Update</span></span>
         + <span data-ttu-id="2ef8b-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party</span><span class="sxs-lookup"><span data-stu-id="2ef8b-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="2ef8b-216">msdyn_vendor aktualizacja</span><span class="sxs-lookup"><span data-stu-id="2ef8b-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="2ef8b-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="2ef8b-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="2ef8b-218">W aplikacji obsługi klienta wyłącz poniższe przepływy pracy:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="2ef8b-219">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-220">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-221">Tworzenie dostawców typu osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="2ef8b-222">Tworzenie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="2ef8b-223">Aktualizowanie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-224">Aktualizowanie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="2ef8b-225">Aktualizowanie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="2ef8b-226">Aktualizowanie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="2ef8b-227">W fabryki danych uruchom szablon, wybierając pozycję **Wyzwól teraz**, tak jak pokazano na poniższym obrazie.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="2ef8b-228">Ten proces może potrwać kilka godzin na podstawie objętości danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Wyzwalanie uruchomienia](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="2ef8b-230">Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="2ef8b-231">Zaimportuj nowe rekordy **Strony** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="2ef8b-232">Pobierz plik `FONewParty.csv` z magazynu obiektów blob Azure.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="2ef8b-233">Ścieżka w `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="2ef8b-234">Skonwertuj plik `FONewParty.csv` na plik programu Excel i zaimportuj go do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="2ef8b-235">Jeśli import CSV działa dla Ciebie, możesz zaimportować plik CSV bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="2ef8b-236">Uruchomienie importowania może potrwać kilka godzin, w zależności od objętości danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="2ef8b-237">Aby uzyskać więcej informacji, zapoznaj się z [Omówieniem importowania i eksportowania danych](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importowanie rekordów strony Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="2ef8b-239">W aplikacjach angażujących klientów włącz następujące kroki wtyczki plug-in:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="2ef8b-240">Aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-240">Account Update</span></span>
         + <span data-ttu-id="2ef8b-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="2ef8b-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="2ef8b-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="2ef8b-243">Aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-243">Contact Update</span></span>
         + <span data-ttu-id="2ef8b-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="2ef8b-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="2ef8b-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="2ef8b-246">msdyn_party aktualizacja</span><span class="sxs-lookup"><span data-stu-id="2ef8b-246">msdyn_party Update</span></span>
         + <span data-ttu-id="2ef8b-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party</span><span class="sxs-lookup"><span data-stu-id="2ef8b-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="2ef8b-248">msdyn_vendor aktualizacja</span><span class="sxs-lookup"><span data-stu-id="2ef8b-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="2ef8b-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="2ef8b-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="2ef8b-250">W aplikacjach do obsługi klienta aktywuj następujące przepływy pracy, jeśli zdezaktywowano je w poprzednich krokach:</span><span class="sxs-lookup"><span data-stu-id="2ef8b-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="2ef8b-251">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-252">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-253">Tworzenie dostawców typu osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="2ef8b-254">Tworzenie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="2ef8b-255">Aktualizowanie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="2ef8b-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="2ef8b-256">Aktualizowanie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="2ef8b-257">Aktualizowanie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="2ef8b-258">Aktualizowanie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="2ef8b-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="2ef8b-259">Uruchom mapy powiązane z **Stroną** zgodnie z instrukcjami w [Książka adresowa strony i globalna książka adresowa](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2ef8b-260">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="2ef8b-260">Troubleshooting</span></span>

1. <span data-ttu-id="2ef8b-261">W przypadku niepowodzenia procesu należy ponownie uruchomić fabryki danych począwszy od nieudanych działań.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="2ef8b-262">Niektóre pliki są generowane przez fabryki danych, których można używać do weryfikacji danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="2ef8b-263">Fabryki danych są uruchamiane na podstawie plików CSV, które są rozdzielane przecinkami.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="2ef8b-264">Jeśli istnieje wartość pola z przecinkiem, może to wpływać na wyniki.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="2ef8b-265">Należy usunąć przecinek.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="2ef8b-266">Karta **Monitorowanie** zawiera informacje o wszystkich przetwarzanych krokach i danych.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="2ef8b-267">Wybierz określony krok do debugowania.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-267">Select a specific step to debug it.</span></span>

    ![Karta Monitorowanie](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="2ef8b-269">Dowiedz się więcej o szablonie</span><span class="sxs-lookup"><span data-stu-id="2ef8b-269">Learn more about the template</span></span>

<span data-ttu-id="2ef8b-270">Dodatkowe informacje dotyczące tego szablonu można znaleźć w sekcji [Pliku Readme —Komentarze do Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="2ef8b-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
