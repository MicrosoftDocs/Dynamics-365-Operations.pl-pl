---
title: Uaktualnianie do modelu globalnej książki adresowej i strony
description: W tym temacie opisano sposób uaktualniania danych o dwóch zapisach do strony globalna książka adresowa modelu.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 76e64d483e833782733277a64d8dc37cbeba6130
ms.sourcegitcommit: 011468a6cffea8641bebc2922e0676d9f44b36fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2021
ms.locfileid: "5857377"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="830fc-103">Uaktualnianie do modelu globalnej książki adresowej i strony</span><span class="sxs-lookup"><span data-stu-id="830fc-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="830fc-104">[Szablon Azure Data Factory](https://aka.ms/dual-write-gab-adf) pomaga zaktualizować istniejące tabele danych **Konto**, **Kontakt** i **Dostawca** za pomocą podwójnego zapisu dla strony i moddelu globalnej książki adresowej.</span><span class="sxs-lookup"><span data-stu-id="830fc-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="830fc-105">Szablon uzgadnia dane z aplikacji Finance and Operations oraz aplikacji angażujących klientów.</span><span class="sxs-lookup"><span data-stu-id="830fc-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="830fc-106">Na zakończenie procesu zostaną utworzone i skojarzone pola **Strona** i **Kontakt** dla rekordów **Strony** z rekordami **Konto**, **Kontakt** i **Dostawca** w aplikacjach zaangażowania kllienta.</span><span class="sxs-lookup"><span data-stu-id="830fc-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="830fc-107">Zostanie wygenerowany plik csv (`FONewParty.csv`) w celu utworzenia nowych rekordów **Strona** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="830fc-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="830fc-108">Ten temat zawiera instrukcje dotyczące używania szablonu Data Factory i uaktualniania danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="830fc-109">Jeśli nie masz żadnych dostosowań, możesz użyć szablonu w takiej postaci, w jakiej jest.</span><span class="sxs-lookup"><span data-stu-id="830fc-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="830fc-110">Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon, korzystając z poniższych instrukcji.</span><span class="sxs-lookup"><span data-stu-id="830fc-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="830fc-111">Szablon pomaga uaktualnić tylko dane **Strony**.</span><span class="sxs-lookup"><span data-stu-id="830fc-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="830fc-112">W przyszłej wersji zostaną uwzględnione adresy pocztowe i elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="830fc-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="830fc-113">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="830fc-113">Prerequisites</span></span>

<span data-ttu-id="830fc-114">Te wymagania wstępne są wymagane:</span><span class="sxs-lookup"><span data-stu-id="830fc-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="830fc-115">Subskrypcja platformy Azure</span><span class="sxs-lookup"><span data-stu-id="830fc-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="830fc-116">Dostęp do szablonu</span><span class="sxs-lookup"><span data-stu-id="830fc-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="830fc-117">Jesteś istniejącym klientem podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="830fc-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="830fc-118">Przygotowanie do aktualizacji</span><span class="sxs-lookup"><span data-stu-id="830fc-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="830fc-119">**W pełni zsynchronizowane**: oba środowiska są w pełni zsynchronizowane dla **Konto (klient)**, **Kontakt** i **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="830fc-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="830fc-120">**Klucze integracji**: tabele **konto (Klient)**, **Kontakt** i **Dostawca** w aplikacjach do obsługi klienta są dostępne za pomocą kluczy integracji, które są gotowe do użytku.</span><span class="sxs-lookup"><span data-stu-id="830fc-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="830fc-121">Jeśli użytkownik dostosuje klucze integracji, należy dostosować szablon.</span><span class="sxs-lookup"><span data-stu-id="830fc-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="830fc-122">**Numer strony**: Wszystkie rekody **Konto (Klient)**, **Kontakt** i **Dostawca**, które zostaną zaktualizowane, mają numer **Strony**.</span><span class="sxs-lookup"><span data-stu-id="830fc-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="830fc-123">Rekordy bez numeru **Strony** zostaną zignorowane.</span><span class="sxs-lookup"><span data-stu-id="830fc-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="830fc-124">Aby uaktualnić te rekordy, dodaj do nich numer **Strony** przed rozpoczęciem procesu uaktualniania.</span><span class="sxs-lookup"><span data-stu-id="830fc-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="830fc-125">**Okres przestoju systemu**: Podczas procesu uaktualniania konieczne będzie przełączenie środowisk Finance and Operations oraz obsługi klienta do trybu offline.</span><span class="sxs-lookup"><span data-stu-id="830fc-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="830fc-126">**Migawka**: tworzenie migawki aplikacji Finance and Operations i aplikacji obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="830fc-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="830fc-127">W razie potrzeby użyj migawki, aby przywrócić poprzedni stan.</span><span class="sxs-lookup"><span data-stu-id="830fc-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="830fc-128">Wdrażanie</span><span class="sxs-lookup"><span data-stu-id="830fc-128">Deployment</span></span>

1. <span data-ttu-id="830fc-129">Pobierz szablon z witryny [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="830fc-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="830fc-130">Zaloguj się w [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="830fc-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="830fc-131">Wybierz [grupę zasobów](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="830fc-131">Create a [resource group](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="830fc-132">Utwórz [konto magazynu](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) w utworzonej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="830fc-132">Create a [storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="830fc-133">Utwórz [fabryke danych](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) w utworzonej powyżej grupie zasobów.</span><span class="sxs-lookup"><span data-stu-id="830fc-133">Create a [data factory](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="830fc-134">Otwórz fabrykę danych i wybierz kafelek **Twórz i Monitoruj**.</span><span class="sxs-lookup"><span data-stu-id="830fc-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="830fc-135">Na karcie **Zarządzaj** wybierz **Szablon ARM**.</span><span class="sxs-lookup"><span data-stu-id="830fc-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="830fc-136">Wybierz **Importuj szablon ARM**, aby zaimportować szablon **Strony**.</span><span class="sxs-lookup"><span data-stu-id="830fc-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="830fc-137">Importowanie szablonu do fabryki danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-137">Import the template into the data factory.</span></span> <span data-ttu-id="830fc-138">Wprowadź następujące wartości **Szczegółów projektu** i **Szczegółów wystąpienia**.</span><span class="sxs-lookup"><span data-stu-id="830fc-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="830fc-139">Pole</span><span class="sxs-lookup"><span data-stu-id="830fc-139">Field</span></span> | <span data-ttu-id="830fc-140">Wartość</span><span class="sxs-lookup"><span data-stu-id="830fc-140">Value</span></span>
    ---|---
    <span data-ttu-id="830fc-141">Subskrypcja</span><span class="sxs-lookup"><span data-stu-id="830fc-141">Subscription</span></span> | <span data-ttu-id="830fc-142">Subskrypcja platformy Azure</span><span class="sxs-lookup"><span data-stu-id="830fc-142">Azure subscription</span></span>
    <span data-ttu-id="830fc-143">Grupa zasobów</span><span class="sxs-lookup"><span data-stu-id="830fc-143">Resource group</span></span> | <span data-ttu-id="830fc-144">Podaj ten sam zasób, pod którym zostanie utworzone konto magazynu.</span><span class="sxs-lookup"><span data-stu-id="830fc-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="830fc-145">Region</span><span class="sxs-lookup"><span data-stu-id="830fc-145">Region</span></span> | <span data-ttu-id="830fc-146">Określ region.</span><span class="sxs-lookup"><span data-stu-id="830fc-146">Specify region.</span></span>
    <span data-ttu-id="830fc-147">Nazwa fabryki</span><span class="sxs-lookup"><span data-stu-id="830fc-147">Factory Name</span></span> | <span data-ttu-id="830fc-148">Określ nazwę fabryki.</span><span class="sxs-lookup"><span data-stu-id="830fc-148">Specify factory name.</span></span>
    <span data-ttu-id="830fc-149">FO Powiązanego klucza głównego Service_service</span><span class="sxs-lookup"><span data-stu-id="830fc-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="830fc-150">Określ klucz aplikacji.</span><span class="sxs-lookup"><span data-stu-id="830fc-150">Specify the application's key.</span></span>
    <span data-ttu-id="830fc-151">Ciąg Azure Blob Storage_connection</span><span class="sxs-lookup"><span data-stu-id="830fc-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="830fc-152">Parametry połączenia usługi Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="830fc-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="830fc-153">Hasło usługi powiązane z Dynamics Crm</span><span class="sxs-lookup"><span data-stu-id="830fc-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="830fc-154">Hasło do konta użytkownika określonego jako nazwa użytkownika.</span><span class="sxs-lookup"><span data-stu-id="830fc-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="830fc-155">FO Połączone Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="830fc-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="830fc-156">FO Połączone Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="830fc-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="830fc-157">Określ informacje o dzierżawcy (nazwę domeny lub identyfikator dzierżawy), pod którymi znajduje się aplikacja.</span><span class="sxs-lookup"><span data-stu-id="830fc-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="830fc-158">FO Połączone Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="830fc-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="830fc-159">FO Połączone Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="830fc-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="830fc-160">Określ identyfikator klienta aplikacji.</span><span class="sxs-lookup"><span data-stu-id="830fc-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="830fc-161">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="830fc-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="830fc-162">Nazwa użytkownika do połączenia z Dynamics.</span><span class="sxs-lookup"><span data-stu-id="830fc-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="830fc-163">Aby uzyskać więcej informacji, zobacz tematy [Ręcznie podwyższaj szablon usługi Resource Manager dla każdego środowiska](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Połączone właściwości usługi](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties) i [Skopiuj dane za pomocą usługi Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="830fc-163">For more information, see [Manually promote a Resource Manager template for each environment](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="830fc-164">Po wdrożeniu sprawdź poprawność zestawów danych, przepływu danych i połączonej usługi fabryki danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Zestawy danych, przepływ danych i połączona usługa](media/data-factory-validate.png)

11. <span data-ttu-id="830fc-166">Przejdź do **Zarządzaj**.</span><span class="sxs-lookup"><span data-stu-id="830fc-166">Navigate to **Manage**.</span></span> <span data-ttu-id="830fc-167">W obszarze **Połączenia** wybierz pozycję **Połączona usługa**.</span><span class="sxs-lookup"><span data-stu-id="830fc-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="830fc-168">Wybierz **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="830fc-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="830fc-169">W formularzu **Edycja połączonej usługi (Dynamics CRM)** wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="830fc-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="830fc-170">Pole</span><span class="sxs-lookup"><span data-stu-id="830fc-170">Field</span></span> | <span data-ttu-id="830fc-171">Wartość</span><span class="sxs-lookup"><span data-stu-id="830fc-171">Value</span></span>
    ---|---
    <span data-ttu-id="830fc-172">Imię i nazwisko</span><span class="sxs-lookup"><span data-stu-id="830fc-172">Name</span></span> | <span data-ttu-id="830fc-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="830fc-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="830fc-174">opis</span><span class="sxs-lookup"><span data-stu-id="830fc-174">Description</span></span> | <span data-ttu-id="830fc-175">Połączone usługi nawiązania połączenia z wystąpieniem CRM w celu pobrania danych jednostek</span><span class="sxs-lookup"><span data-stu-id="830fc-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="830fc-176">Połącz za pomocą środowiska uruchomieniowego integracji</span><span class="sxs-lookup"><span data-stu-id="830fc-176">Connect via integration runtime</span></span> | <span data-ttu-id="830fc-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="830fc-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="830fc-178">Typ wdrożenia</span><span class="sxs-lookup"><span data-stu-id="830fc-178">Deployment type</span></span> | <span data-ttu-id="830fc-179">Online</span><span class="sxs-lookup"><span data-stu-id="830fc-179">Online</span></span>
    <span data-ttu-id="830fc-180">URI usługi</span><span class="sxs-lookup"><span data-stu-id="830fc-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="830fc-181">Typ uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="830fc-181">Authentication type</span></span> | <span data-ttu-id="830fc-182">Office365</span><span class="sxs-lookup"><span data-stu-id="830fc-182">Office365</span></span>
    <span data-ttu-id="830fc-183">Nazwa użytkownika</span><span class="sxs-lookup"><span data-stu-id="830fc-183">User name</span></span> |
    <span data-ttu-id="830fc-184">Hasło lub klucz Azure</span><span class="sxs-lookup"><span data-stu-id="830fc-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="830fc-185">Hasło</span><span class="sxs-lookup"><span data-stu-id="830fc-185">Password</span></span>
    <span data-ttu-id="830fc-186">Hasło</span><span class="sxs-lookup"><span data-stu-id="830fc-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="830fc-187">Uruchom szablon.</span><span class="sxs-lookup"><span data-stu-id="830fc-187">Run the template</span></span>

1. <span data-ttu-id="830fc-188">Zatrzymaj korzystanie z podwójnego zapisu **Konto**, **Kontakt** i **Dostawca** za pomocą aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="830fc-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="830fc-189">Odbiorcy wersja 3 (konta)</span><span class="sxs-lookup"><span data-stu-id="830fc-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="830fc-190">Odbiorcy wersja 3(kontakty)</span><span class="sxs-lookup"><span data-stu-id="830fc-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="830fc-191">CDS Kontakty V2(kontakty)</span><span class="sxs-lookup"><span data-stu-id="830fc-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="830fc-192">CDS Kontakty V2(kontakty)</span><span class="sxs-lookup"><span data-stu-id="830fc-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="830fc-193">Dostawca wersja 2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="830fc-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="830fc-194">Upewnij się, że mapy zostały usunięte z tabeli `msdy_dualwriteruntimeconfig` w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="830fc-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="830fc-195">Zainstaluj [Rozwiązania z podwójnym zapisem i globalna książka adresowa](https://aka.ms/dual-write-gab) z AppSource.</span><span class="sxs-lookup"><span data-stu-id="830fc-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="830fc-196">W aplikacji Finance and Operations, jeśli poniższe tabele zawierają dane, uruchom dla nich **wstępną synchronizację**.</span><span class="sxs-lookup"><span data-stu-id="830fc-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="830fc-197">Zwroty grzecznościowe</span><span class="sxs-lookup"><span data-stu-id="830fc-197">Salutations</span></span>
    + <span data-ttu-id="830fc-198">Typy osób</span><span class="sxs-lookup"><span data-stu-id="830fc-198">Personal character types</span></span>
    + <span data-ttu-id="830fc-199">Formuła grzecznościowa</span><span class="sxs-lookup"><span data-stu-id="830fc-199">Complimentary closing</span></span>
    + <span data-ttu-id="830fc-200">Tytuły osoby kontaktowej</span><span class="sxs-lookup"><span data-stu-id="830fc-200">Contact person titles</span></span>
    + <span data-ttu-id="830fc-201">Role podejmujące decyzje</span><span class="sxs-lookup"><span data-stu-id="830fc-201">Decision making roles</span></span>
    + <span data-ttu-id="830fc-202">Poziomy lojalności</span><span class="sxs-lookup"><span data-stu-id="830fc-202">Loyalty levels</span></span>

5. <span data-ttu-id="830fc-203">W aplikacji obsługi klienta wyłącz poniższe kroki dodatku plug-in.</span><span class="sxs-lookup"><span data-stu-id="830fc-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="830fc-204">Aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-204">Account Update</span></span>
         + <span data-ttu-id="830fc-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="830fc-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="830fc-207">Aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-207">Contact Update</span></span>
         + <span data-ttu-id="830fc-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="830fc-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="830fc-210">msdyn_party aktualizacja</span><span class="sxs-lookup"><span data-stu-id="830fc-210">msdyn_party Update</span></span>
         + <span data-ttu-id="830fc-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party</span><span class="sxs-lookup"><span data-stu-id="830fc-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="830fc-212">msdyn_vendor aktualizacja</span><span class="sxs-lookup"><span data-stu-id="830fc-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="830fc-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="830fc-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="830fc-214">W aplikacji obsługi klienta wyłącz poniższe przepływy pracy:</span><span class="sxs-lookup"><span data-stu-id="830fc-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="830fc-215">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-216">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-217">Tworzenie dostawców typu osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="830fc-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="830fc-218">Tworzenie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="830fc-219">Aktualizowanie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-220">Aktualizowanie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="830fc-221">Aktualizowanie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="830fc-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="830fc-222">Aktualizowanie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="830fc-223">W fabryki danych uruchom szablon, wybierając pozycję **Wyzwól teraz**, tak jak pokazano na poniższym obrazie.</span><span class="sxs-lookup"><span data-stu-id="830fc-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="830fc-224">Ten proces może potrwać kilka godzin na podstawie objętości danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Wyzwalanie uruchomienia](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="830fc-226">Jeśli masz dostosowania dla **Konta**, **Kontaktu** i **Dostawcy**, musisz zmodyfikować szablon.</span><span class="sxs-lookup"><span data-stu-id="830fc-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="830fc-227">Zaimportuj nowe rekordy **Strony** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="830fc-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="830fc-228">Pobierz plik `FONewParty.csv` z magazynu obiektów blob Azure.</span><span class="sxs-lookup"><span data-stu-id="830fc-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="830fc-229">Ścieżka w `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="830fc-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="830fc-230">Skonwertuj plik `FONewParty.csv` na plik programu Excel i zaimportuj go do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="830fc-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="830fc-231">Jeśli import CSV działa dla Ciebie, możesz zaimportować plik CSV bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="830fc-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="830fc-232">Uruchomienie importowania może potrwać kilka godzin, w zależności od objętości danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="830fc-233">Aby uzyskać więcej informacji, zapoznaj się z [Omówieniem importowania i eksportowania danych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span><span class="sxs-lookup"><span data-stu-id="830fc-233">For more information, see [Data import and export jobs overview](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span></span>

    ![Importowanie rekordów strony Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="830fc-235">W aplikacjach angażujących klientów włącz następujące kroki wtyczki plug-in:</span><span class="sxs-lookup"><span data-stu-id="830fc-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="830fc-236">Aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-236">Account Update</span></span>
         + <span data-ttu-id="830fc-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="830fc-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aktualizacja konta</span><span class="sxs-lookup"><span data-stu-id="830fc-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="830fc-239">Aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-239">Contact Update</span></span>
         + <span data-ttu-id="830fc-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="830fc-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aktualizacja kontaktu</span><span class="sxs-lookup"><span data-stu-id="830fc-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="830fc-242">msdyn_party aktualizacja</span><span class="sxs-lookup"><span data-stu-id="830fc-242">msdyn_party Update</span></span>
         + <span data-ttu-id="830fc-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aktualizacja msdyn_party</span><span class="sxs-lookup"><span data-stu-id="830fc-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="830fc-244">msdyn_vendor aktualizacja</span><span class="sxs-lookup"><span data-stu-id="830fc-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="830fc-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aktualizacja msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="830fc-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="830fc-246">W aplikacjach do obsługi klienta aktywuj następujące przepływy pracy, jeśli zdezaktywowano je w poprzednich krokach:</span><span class="sxs-lookup"><span data-stu-id="830fc-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="830fc-247">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-248">Tworzenie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-249">Tworzenie dostawców typu osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="830fc-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="830fc-250">Tworzenie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="830fc-251">Aktualizowanie dostawców w tabeli kont</span><span class="sxs-lookup"><span data-stu-id="830fc-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="830fc-252">Aktualizowanie dostawców w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="830fc-253">Aktualizowanie dostawców typu Osoba w tabeli kontaktów</span><span class="sxs-lookup"><span data-stu-id="830fc-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="830fc-254">Aktualizowanie dostawców typu Osoba w tabeli dostawców</span><span class="sxs-lookup"><span data-stu-id="830fc-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="830fc-255">Uruchom mapy powiązane z **Stroną** zgodnie z instrukcjami w [Książka adresowa strony i globalna książka adresowa](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="830fc-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="830fc-256">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="830fc-256">Troubleshooting</span></span>

1. <span data-ttu-id="830fc-257">W przypadku niepowodzenia procesu należy ponownie uruchomić fabryki danych począwszy od nieudanych działań.</span><span class="sxs-lookup"><span data-stu-id="830fc-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="830fc-258">Niektóre pliki są generowane przez fabryki danych, których można używać do weryfikacji danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="830fc-259">Fabryki danych są uruchamiane na podstawie plików CSV, które są rozdzielane przecinkami.</span><span class="sxs-lookup"><span data-stu-id="830fc-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="830fc-260">Jeśli istnieje wartość pola z przecinkiem, może to wpływać na wyniki.</span><span class="sxs-lookup"><span data-stu-id="830fc-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="830fc-261">Należy usunąć przecinek.</span><span class="sxs-lookup"><span data-stu-id="830fc-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="830fc-262">Karta **Monitorowanie** zawiera informacje o wszystkich przetwarzanych krokach i danych.</span><span class="sxs-lookup"><span data-stu-id="830fc-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="830fc-263">Wybierz określony krok do debugowania.</span><span class="sxs-lookup"><span data-stu-id="830fc-263">Select a specific step to debug it.</span></span>

    ![Karta Monitorowanie](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="830fc-265">Dowiedz się więcej o szablonie</span><span class="sxs-lookup"><span data-stu-id="830fc-265">Learn more about the template</span></span>

<span data-ttu-id="830fc-266">Komentarze do szablonu można znaleźć w pliku [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="830fc-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>
