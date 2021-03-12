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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: a2f0e0cbf0f8710dc020a48506775fa28df9c2d2
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744644"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="3b19b-103">Rozwiązywanie problemów podczas synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="3b19b-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3b19b-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3b19b-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="3b19b-105">A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="3b19b-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b19b-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3b19b-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3b19b-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="3b19b-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="3b19b-108">Sprawdź, czy w aplikacji Finance and Operations nie występują błędy synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="3b19b-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="3b19b-109">Po włączeniu szablonów mapowania stan map powinien być **Uruchomione**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="3b19b-110">Jeśli stan jest **Nie uruchomione**, wystąpiły błędy podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="3b19b-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="3b19b-111">Aby wyświetlić błędy, wybierz kartę **Szczegóły wstępnej synchronizacji** na stronie **Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Błąd na karcie Szczegóły początkowej synchronizacji](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="3b19b-113">Nie można ukończyć synchronizacji początkowej: 400 złe żądanie</span><span class="sxs-lookup"><span data-stu-id="3b19b-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="3b19b-114">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="3b19b-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="3b19b-115">Podczas próby uruchomienia mapowania i wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="3b19b-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="3b19b-116">*(\[Złe żądanie\], Serwer zdalny zwrócił błąd: (400) złe żądanie.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="3b19b-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="3b19b-117">Oto przykład tabeli pełnego komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="3b19b-118">Jeśli ten błąd występuje zawsze i nie można ukończyć wstępnej synchronizacji, należy wykonać poniższe kroki w celu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="3b19b-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="3b19b-119">Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b19b-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="3b19b-120">Otwórz Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="3b19b-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="3b19b-121">Upewnij się, że w okienku **Usługi** jest uruchomiona usługa struktury eksportu danych Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3b19b-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="3b19b-122">Uruchom ją ponownie, jeśli została zatrzymana, ponieważ wymaga tego synchronizacja wstępna.</span><span class="sxs-lookup"><span data-stu-id="3b19b-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="3b19b-123">Błąd synchronizacji początkowej: 403 zabroniony</span><span class="sxs-lookup"><span data-stu-id="3b19b-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="3b19b-124">Podczas wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="3b19b-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="3b19b-125">*(\[Zabroniony\], serwer zdalny zwrócił błąd: (403) Zabroniony.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="3b19b-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="3b19b-126">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="3b19b-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="3b19b-127">Zaloguj się do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b19b-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="3b19b-128">Na stronie **aplikacje Azure Active Directory** usuń klienta **DtAppID**, a następnie dodaj go ponownie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Klient DtAppID na liście aplikacji Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="3b19b-130">Błędy odwołują się do siebie lub odwołują się cyklicznie podczas początkowej synchronizacji</span><span class="sxs-lookup"><span data-stu-id="3b19b-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="3b19b-131">Mogą pojawić się komunikaty o błędach, jeśli którekolwiek z mapowań zawierają odwołania do siebie lub odwołania cykliczne.</span><span class="sxs-lookup"><span data-stu-id="3b19b-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="3b19b-132">Błędy należą do następujących kategorii:</span><span class="sxs-lookup"><span data-stu-id="3b19b-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="3b19b-133">Błędy w mapowaniu tabeli dostawców V2-na-msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="3b19b-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="3b19b-134">Błędy w mapowaniu tabeli Klienci V3 do Kont</span><span class="sxs-lookup"><span data-stu-id="3b19b-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="3b19b-135">Rozwiązywanie błędów w mapowaniu tabeli dostawców V2-na-msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="3b19b-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="3b19b-136">Można napotkać następujące błędy wstępne synchronizacji w przypadku mapowania **Dostawców V2** do **msdyn\_vendors**, jeśli tabeli mają istniejące wiersze z wartościami w kolumnach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="3b19b-137">Błędy są spowodowane tym, że **InvoiceVendorAccountNumber** jest kolumną odwołującą się do siebie, a **PrimaryContactPersonId** jest odwołaniem cyklicznym w mapowaniu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3b19b-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="3b19b-138">Otrzymane komunikaty o błędach będą miały następujący format:</span><span class="sxs-lookup"><span data-stu-id="3b19b-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="3b19b-139">*Nie można rozpoznać identyfikatora GUID dla pola: \<field\>. Nie znaleziono wyszukiwania: \<value\>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="3b19b-140">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="3b19b-140">Here are some examples:</span></span>

- <span data-ttu-id="3b19b-141">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="3b19b-142">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Nie znaleziono wyszukiwania:  V24-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="3b19b-143">Jeśli istnieją wiersze w tabeli dostawcy mają wartości w kolumnach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.</span><span class="sxs-lookup"><span data-stu-id="3b19b-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="3b19b-144">W aplikacji Finance and Operations usuń kolumny **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z mapowania i zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="3b19b-145">Przejdź na stronę mapowanie podwójnego dostępu dla **Dostawcy V2 (msdyn\_vendors)** i wybierz kartę **Mapowanie tabeli**. W lewym filtrze wybierz pozycję **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="3b19b-146">W prawym filtrze wybierz opcję **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="3b19b-147">Wyszukaj **primarycontactperson**, aby odnaleźć kolumnę źródłową **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="3b19b-148">Wybierz opcję **Akcje**, a następnie wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Usuwanie kolumny PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="3b19b-150">Powtórz te kroki, aby usunąć kolumnę **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Usuwanie kolumny InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="3b19b-152">Zapisz zmiany w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="3b19b-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="3b19b-153">Wyłącz śledzenie zmian dla tabeli **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="3b19b-154">W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Tabele danych**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="3b19b-155">Wybierz tabelę **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="3b19b-156">W okienku akcji wybierz opcję **Opcje**, a następnie wybierz opcję **Śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Wybieranie opcji śledzenia zmian](media/selfref_options.png)

    4. <span data-ttu-id="3b19b-158">Wybierz **Wyłącz śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-158">Select **Disable Change Tracking**.</span></span>

        ![Wybór opcji Wyłącz śledzenie zmian](media/selfref_tracking.png)

3. <span data-ttu-id="3b19b-160">Uruchom synchronizację wstępną mapowania **Dostawców V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="3b19b-161">Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="3b19b-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="3b19b-162">Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="3b19b-163">Musisz zsynchronizować to odwzorowanie, jeśli chcesz zsynchronizować podstawową kolumnę kontaktu w tabeli dostawcy, ponieważ początkowa synchronizacja musi być również wykonana dla wierszy kontaktów.</span><span class="sxs-lookup"><span data-stu-id="3b19b-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="3b19b-164">Dodaj kolumny **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z powrotem do mapowania **Dostawcy v2 (msdyn\_vendors)** i zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="3b19b-165">Uruchom ponownie synchronizację wstępną mapowania **Dostawców V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="3b19b-166">Ponieważ śledzenie zmian jest wyłączone, wszystkie wiersze zostaną zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="3b19b-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="3b19b-167">Wyłącz ponownie śledzenie zmian dla tabeli **Dostawcy V2**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="3b19b-168">Rozwiąż błędy w mapowaniu tabeli Klienci V3-do-Kont</span><span class="sxs-lookup"><span data-stu-id="3b19b-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="3b19b-169">Można napotkać następujące błędy wstępne synchronizacji w przypadku mapowania **Klienci V3** do **Kont**, jeśli tabele mają istniejące wiersze z wartościami w kolumnach **ContactPersonID** i **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="3b19b-170">Te błędy są spowodowane tym, że **InvoiceAccount** jest kolumną odwołującą się do siebie, a **ContactPersonID** jest odwołaniem cyklicznym w mapowaniu dostawcy.</span><span class="sxs-lookup"><span data-stu-id="3b19b-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="3b19b-171">Otrzymane komunikaty o błędach będą miały następujący format:</span><span class="sxs-lookup"><span data-stu-id="3b19b-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="3b19b-172">*Nie można rozpoznać identyfikatora GUID dla pola: \<field\>. Nie znaleziono wyszukiwania: \<value\>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="3b19b-173">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="3b19b-173">Here are some examples:</span></span>

- <span data-ttu-id="3b19b-174">*Nie można rozpoznać identyfikatora GUID dla pola: primarycontactid.msdyn\_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="3b19b-175">*Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_billingaccount.accountnumber. Nie znaleziono wyszukiwania: 1206-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="3b19b-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="3b19b-176">Jeśli istnieją wiersze w tabeli klienta mają wartości w kolumnach **ContactPersonID** i **InvoiceAccount**, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.</span><span class="sxs-lookup"><span data-stu-id="3b19b-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="3b19b-177">Z tego podejścia można skorzystać w przypadku dowolnych gotowych tabel, takich jak **Konta** i **Kontakty**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="3b19b-178">W aplikacji Finance and Operations usuń kolumny **ContactPersonID** i **InvoiceAccount** z mapowania **Klienci V3 (konta)** i nstępnie zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="3b19b-179">Na stronie mapowanie podwójnego dostępu dla **Klienci V3 (konta)** i wybierz kartę **Mapowanie tabeli** . W lewym filtrze wybierz pozycję **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="3b19b-180">W prawym filtrze wybierz **Dataverse.Account**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="3b19b-181">Wyszukaj **contactperson**, aby odnaleźć kolumnę źródłową **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="3b19b-182">Wybierz opcję **Akcje**, a następnie wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Usuwanie kolumny ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="3b19b-184">Powtórz te kroki, aby usunąć kolumnę **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Usuwanie kolumny InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="3b19b-186">Zapisz zmiany w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="3b19b-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="3b19b-187">Wyłącz śledzenie zmian dla tabeli **Klienci V3**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="3b19b-188">W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Tabele danych**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="3b19b-189">Wybierz tabelę **Klient (wersja 3)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="3b19b-190">W okienku akcji wybierz opcję **Opcje**, a następnie wybierz opcję **Śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Wybieranie opcji śledzenia zmian](media/selfref_options.png)

    4. <span data-ttu-id="3b19b-192">Wybierz **Wyłącz śledzenie zmian**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-192">Select **Disable Change Tracking**.</span></span>

        ![Wybór opcji Wyłącz śledzenie zmian](media/selfref_tracking.png)

3. <span data-ttu-id="3b19b-194">Uruchom synchronizację początkową dla mapowania **Klienci V3 (Konta)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="3b19b-195">Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.</span><span class="sxs-lookup"><span data-stu-id="3b19b-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="3b19b-196">Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b19b-197">Istnieją dwa mapy o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-197">There are two maps that have the same name.</span></span> <span data-ttu-id="3b19b-198">Pamiętaj, aby wybrać mapę, która ma następujący opis na karcie **Szczegóły**: **Szablon 2Dual-write do synchronizacji między kontaktami dostawcy FO.CDS V2 i CDS. Wymaga nowego pakietu \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="3b19b-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="3b19b-199">Dodaj kolumny **InvoiceAccount** i **ContactPersonId** z powrotem do mapowania **Klienci V3 (Konta)** i nastepnie zapisz mapowanie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="3b19b-200">Teraz zarówno kolumna **InvoiceAccount**, jak i kolumna **ContactPersonId** są ponownie częścią trybu synchronizacji na żywo.</span><span class="sxs-lookup"><span data-stu-id="3b19b-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="3b19b-201">W następnym kroku wykonasz synchronizację początkową dla tych kolumn.</span><span class="sxs-lookup"><span data-stu-id="3b19b-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="3b19b-202">Uruchom ponownie synchronizację początkową dla mapowania **Klienci V3 (Konta)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="3b19b-203">Ponieważ śledzenie zmian jest wyłączone, dae dla **InvoiceAccount** i **ContactPersonId** będą zsynchronizowane z aplikacji Finance and Operations do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3b19b-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="3b19b-204">Aby synchronizować dane dla **InvoiceAccount** i **ContactPersonId** z Dataverse do aplikacji Finance and Operations, należy skorzystać z projektu integracji danych.</span><span class="sxs-lookup"><span data-stu-id="3b19b-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="3b19b-205">W Power Apps utwórz projekt integracji danych między tabelami **Sales.Account** i **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="3b19b-206">Kierunek danych musi być z Dataverse do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b19b-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="3b19b-207">Ponieważ **InvoiceAccount** jest nowym atrybutem w podwójnym zapisywaniu, można pominąć synchronizację początkową dla niego.</span><span class="sxs-lookup"><span data-stu-id="3b19b-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="3b19b-208">Aby uzyskać więcej informacji, zobacz [Integrowanie danych z Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="3b19b-208">For more information, see [Integrate data into Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="3b19b-209">Na poniższej ilustracji przedstawiono projekt, który aktualizuje **CustomerAccount** i **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Projekt integracji danych w celu zaktualizowania CustomerAccount i ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="3b19b-211">Dodaj kryteria firmy w polu filtruj po stronie Dataverse, aby w aplikacji Finance and Operations została zaktualizowana tylko liczba wierszy spełniających kryteria filtru.</span><span class="sxs-lookup"><span data-stu-id="3b19b-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="3b19b-212">Aby dodać filtr, kliknij przycisk filtru.</span><span class="sxs-lookup"><span data-stu-id="3b19b-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="3b19b-213">W oknie dialogowym **Edytuj kwerendę** można dodać kwerendę filtru, taką jak **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="3b19b-214">[UWAGA] Jeśli przycisk filtru nie istnieje, utwórz bilet pomocy technicznej, aby poprosić zespół integracji danych o umożliwienie obsługi filtru w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="3b19b-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="3b19b-215">Jeśli kwerenda filtru nie zostanie wprowadzona dla **\_msdyn\_company\_value**, wszystkie wiersze zostaną zsynchronizowane.</span><span class="sxs-lookup"><span data-stu-id="3b19b-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Dodawanie kwerendy filtru](media/cust_selfref7.png)

    <span data-ttu-id="3b19b-217">Początkowa synchronizacja wierszy jest teraz zakończona.</span><span class="sxs-lookup"><span data-stu-id="3b19b-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="3b19b-218">W aplikacji Finance and Operations wyłącz śledzenie zmian dla tabeli **Klienci (wersja 3)**.</span><span class="sxs-lookup"><span data-stu-id="3b19b-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>
