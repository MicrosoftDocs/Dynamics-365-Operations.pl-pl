---
title: Rozwiązywanie problemów podczas synchronizacji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410088"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="6f9d0-103">Rozwiązywanie problemów podczas synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="6f9d0-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6f9d0-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6f9d0-105">A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f9d0-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6f9d0-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6f9d0-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="6f9d0-108">Sprawdź, czy w aplikacji Finance and Operations nie występują błędy synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="6f9d0-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="6f9d0-109">Po włączeniu szablonów mapowania stan map powinien być **Uruchomione**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="6f9d0-110">Jeśli stan jest **Nie uruchomione**, wystąpiły błędy podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="6f9d0-111">Aby wyświetlić błędy, wybierz kartę **Szczegóły wstępnej synchronizacji** na stronie **Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Karta Szczegóły wstępnej synchronizacji](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="6f9d0-113">Nie można ukończyć synchronizacji początkowej: 400 złe żądanie</span><span class="sxs-lookup"><span data-stu-id="6f9d0-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="6f9d0-114">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="6f9d0-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="6f9d0-115">Podczas próby uruchomienia mapowania i wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="6f9d0-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="6f9d0-116">*Serwer zdalny zwrócił błąd: (400) złe żądanie.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="6f9d0-117">Oto przykład tabeli pełnego komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="6f9d0-118">Jeśli ten błąd występuje zawsze i nie można ukończyć wstępnej synchronizacji, należy wykonać poniższe kroki w celu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="6f9d0-119">Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="6f9d0-120">Otwórz Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="6f9d0-121">Upewnij się, że w okienku **Usługi** jest uruchomiona usługa struktury eksportu danych Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="6f9d0-122">Uruchom ją ponownie, jeśli została zatrzymana, ponieważ wymaga tego synchronizacja wstępna.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="6f9d0-123">Błąd synchronizacji początkowej: 403 zabroniony</span><span class="sxs-lookup"><span data-stu-id="6f9d0-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="6f9d0-124">Podczas wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="6f9d0-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="6f9d0-125">*(\[Zabroniony\], serwer zdalny zwrócił błąd: (403) Zabroniony.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="6f9d0-126">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="6f9d0-127">Zaloguj się do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="6f9d0-128">Na stronie **aplikacje Azure Active Directory** usuń klienta **DtAppID**, a następnie dodaj go ponownie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista aplikacji Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="6f9d0-130">Błędy odwołują się do siebie lub odwołują się cyklicznie podczas początkowej synchronizacji</span><span class="sxs-lookup"><span data-stu-id="6f9d0-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="6f9d0-131">Mogą pojawić się komunikaty o błędach, jeśli którekolwiek z mapowań zawierają odwołania do siebie lub odwołania cykliczne.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="6f9d0-132">Błędy należą do następujących kategorii:</span><span class="sxs-lookup"><span data-stu-id="6f9d0-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="6f9d0-133">Dostawcy (wersja 2) do mapowania jednostki msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="6f9d0-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="6f9d0-134">Mapowanie jednostki Dostawcy (wersja 3) do Kont</span><span class="sxs-lookup"><span data-stu-id="6f9d0-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="6f9d0-135">Rozwiąż błąd w dostawcy V2 na mapowanie encji msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="6f9d0-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="6f9d0-136">Można uruchomić następujące błędy wstępne synchronizacji w przypadku mapowania **Dostawców V2** do **msdyn_vendors**, jeśli jednostki mają istniejące rekordy z wartościami w polach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="6f9d0-137">Jest to spowodowane tym, że **InvoiceVendorAccountNumber** jest polem odwołującym się do siebie, a **PrimaryContactPersonId** jest odwołaniem cyklicznym w mapowaniu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6f9d0-138">*Nie można rozpoznać identyfikatora GUID dla pola: <field>. Nie znaleziono wyszukiwania: <value>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne :https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="6f9d0-139">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="6f9d0-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="6f9d0-140">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn_vendorprimarycontactperson. msdyn_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="6f9d0-141">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. Nie znaleziono wyszukiwania: V24-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="6f9d0-142">Jeśli istnieją rekordy z wartościami w tych polach jednostki dostawcy, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="6f9d0-143">W aplikacji Finance and Operations usuń pola **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z mapowania i zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="6f9d0-144">Przejdź na stronę mapowanie podwójnego dostępu dla **Dostawcy V2 (msdyn_vendors)** i wybierz kartę **Mapowanie jednostek**. W lewym filtrze wybierz pozycję **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="6f9d0-145">W prawym filtrze wybierz opcję **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="6f9d0-146">Wyszukaj **primarycontactperson**, aby odnaleźć pole źródłowe **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="6f9d0-147">Kliknij przycisk **Akcje** i wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![odwołanie własne lub cykliczne 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="6f9d0-149">Powtórz tę czynność, aby usunąć pole **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![odwołanie własne lub cykliczne 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="6f9d0-151">Zapisz zmiany mapowania.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="6f9d0-152">Wyłącz śledzenie zmian dla jednostki **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="6f9d0-153">Przejdź do **Zarządzanie danymi \> Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="6f9d0-154">Wybierz jednostkę **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="6f9d0-155">Kliknij opcję **Opcje** na pasku menu, a następnie **Zmień śledzenie**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![odwołanie własne lub cykliczne 5](media/selfref_options.png)
    
    4. <span data-ttu-id="6f9d0-157">Kliknij **Wyłącz śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-157">Click **Disable Change Tracking**.</span></span>
    
        ![odwołanie własne lub cykliczne 6](media/selfref_tracking.png)

3. <span data-ttu-id="6f9d0-159">Uruchom synchronizację wstępną mapowania **Dostawców V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="6f9d0-160">Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="6f9d0-161">Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6f9d0-162">Należy zsynchronizować to mapowanie, jeśli ma zostać zsynchronizowane główne pole kontaktu w jednostce dostawcy, ponieważ rekordy kontaktów muszą być zsynchronizowane jako wstępne.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="6f9d0-163">Dodaj pola **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z powrotem do mapowania **Dostawcy v2 (msdyn_vendors)** i zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="6f9d0-164">Uruchom ponowanie synchronizację wstępną mapowania **Dostawców V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="6f9d0-165">Wszystkie rekordy zostaną zsynchronizowane, ponieważ śledzenie zmian jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="6f9d0-166">Włącz śledzenie zmian dla jednostki **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="6f9d0-167">Rozwiąż błąd w mapowaniu jednostki Klienci V3 do Kont</span><span class="sxs-lookup"><span data-stu-id="6f9d0-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="6f9d0-168">Można uruchomić następujące błędy wstępne synchronizacji w przypadku mapowania **Klienci V3** do **Kont**, jeśli jednostki mają istniejące rekordy z wartościami w polach **ContactPersonID** i **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="6f9d0-169">Jest to spowodowane tym, że **InvoiceAccount** jest polem odwołującym się do siebie, a **ContactPersonID** jest odwołaniem cyklicznym w mapowaniu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6f9d0-170">*Nie można rozpoznać identyfikatora GUID dla pola: <field>. Nie znaleziono wyszukiwania: <value>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne :https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="6f9d0-171">*Nie można rozpoznać identyfikatora GUID dla pola: primarycontactid.msdyn_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="6f9d0-172">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn_billingaccount.accountnumber. Nie znaleziono wyszukiwania: 1206-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="6f9d0-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="6f9d0-173">Jeśli istnieją rekordy z wartościami w tych polach jednostki klienta, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="6f9d0-174">Z tego podejścia można skorzystać w przypadku dowolnych z pudełkych jednostek, takich jak konta i kontakty.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="6f9d0-175">W aplikacji Finance and Operations usuń pola **ContactPersonID** i **InvoiceAccount** z mapowania **Klienci V3 (konta)** i zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="6f9d0-176">Przejdź na stronę mapowanie podwójnego dostępu dla **Klienci V3 (konta)** i wybierz kartę **Mapowanie jednostek** . W lewym filtrze wybierz pozycję **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="6f9d0-177">W prawym filtrze wybierz **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="6f9d0-178">Wyszukaj **contactperson**, aby odnaleźć pole źródłowe **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="6f9d0-179">Kliknij przycisk **Akcje** i wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![odwołanie własne lub cykliczne 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="6f9d0-181">Powtórz tę czynność, aby usunąć pole **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![odwołanie własne lub cykliczne](media/cust_selfref4.png)
    
    5. <span data-ttu-id="6f9d0-183">Zapisz zmiany mapowania.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="6f9d0-184">Wyłącz śledzenie zmian dla jednostki **Klienci V3**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="6f9d0-185">Przejdź do **Zarządzanie danymi \> Jednostki danych**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="6f9d0-186">Wybierz jednostkę **Klienci V3**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="6f9d0-187">Kliknij opcję **Opcje** na pasku menu, a następnie **Zmień śledzenie**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![odwołanie własne lub cykliczne 5](media/selfref_options.png)
    
    4. <span data-ttu-id="6f9d0-189">Kliknij **Wyłącz śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-189">Click **Disable Change Tracking**.</span></span>
    
        ![odwołanie własne lub cykliczne 6](media/selfref_tracking.png)

3. <span data-ttu-id="6f9d0-191">Uruchom synchronizację początkową dla mapowania **Klienci V3 (Konta)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6f9d0-192">Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="6f9d0-193">Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6f9d0-194">Istnieją 2 mapy o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="6f9d0-195">Wybierz ten z opisem **Szablon podwójnego zapisu do synchronizacji między kontaktami dostawcy FO.CDS V2 do CDS.Contacts. Wymaga nowego pakietu \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="6f9d0-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="6f9d0-196">na karcie **Szczegóły** mapu.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="6f9d0-197">Dodaj pola **InvoiceAccount** i **ContactPersonId** z powrotem do mapowania **Klienci V3 (Konta)** i zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="6f9d0-198">Teraz zarówno pole **InvoiceAccount**, jak i pole **ContactPersonId** są ponownie częścią trybu synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="6f9d0-199">W następnym kroku przeprowadź synchronizację początkową tych pól.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="6f9d0-200">Uruchom znowu synchronizację początkową dla mapowania **Klienci V3 (Konta)**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6f9d0-201">Ponieważ śledzenie zmian jest wyłączone, uruchomienie synchronizacji spowoduje zsynchronizowanie danych dla **InvoiceAccount** i **ContactPersonId** z aplikacji Finance and Operations do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="6f9d0-202">Aby synchronizować dane dla **InvoiceAccount** i **ContactPersonId** z Common Data Service do Finance and Operations, należy skorzystać z projektu integracji danych.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="6f9d0-203">W Power Apps utwórz projekt integracji danych między jednostkami **Sales.Account** i **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="6f9d0-204">Kierunek danych musi być z Common Data Service do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="6f9d0-205">Ponieważ **InvoiceAccount** jest nowym atrybutem w podwójnym zapisywaniu, celowe może być pominięcie synchronizacji początkowej dla tego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="6f9d0-206">Aby uzyskać więcej informacji, zobacz [Integrowanie danych z Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="6f9d0-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="6f9d0-207">Na poniższym obrazie przedstawiono projekt, który aktualizuje **CustomerAccount** i **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![odwołanie własne lub cykliczne](media/cust_selfref6.png)

    2. <span data-ttu-id="6f9d0-209">Dodaj kryteria firmy w polu filtruj po stronie Common Data Service, ponieważ w aplikacji Finance and Operations zostanie zaktualizowana tylko liczba rekordów spełniających kryteria filtru.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="6f9d0-210">Aby dodać filtr, kliknij ikonę filtr.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="6f9d0-211">W oknie dialogowym **Edytuj** kwerendę można dodać kwerendę filtru, taką jak **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="6f9d0-212">Jeśli ikona filtru nie istnieje, utwórz bilet pomocy technicznej, aby poprosić zespół integracji danych o umożliwienie obsługi filtru w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="6f9d0-213">Jeśli kwerenda filtru nie zostanie wprowadzona dla **_msdyn_company_value**, wszystkie rekordy zostaną zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![odwołanie własne lub cykliczne](media/cust_selfref7.png)

        <span data-ttu-id="6f9d0-215">Spowoduje to ukończenie początkowej synchronizacji rekordów.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="6f9d0-216">Wyłącz śledzenie zmian dla jednostki **Klienci V3** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f9d0-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

