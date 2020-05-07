---
title: Rozwiązywanie problemów z synchronizacją na żywo
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.
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
ms.openlocfilehash: d45b19c1e88e6a27bde4335d4a356f2173bdfcd3
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275424"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="bdd4a-103">Rozwiązywanie problemów z synchronizacją na żywo</span><span class="sxs-lookup"><span data-stu-id="bdd4a-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bdd4a-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="bdd4a-105">Ten temat zawiera informacje, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdd4a-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="bdd4a-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="bdd4a-108">Synchronizacja na żywo powoduje, że podczas tworzenia rekordu w aplikacji Finance and Operations jest zgłaszany błąd 403 Zabroniony</span><span class="sxs-lookup"><span data-stu-id="bdd4a-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="bdd4a-109">Może pojawić się następujący komunikat o błędzie podczas tworzenia zapisu w aplikacji Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="bdd4a-110">*\[{\\„błąd\\”:{\\„kod\\”:\\„0x 80072560\\”,\\„komunikat\\”:\\„użytkownik nie jest członkiem organizacji.\\”}}\], Serwer zdalny zwrócił błąd: (403) zabroniony”}}”.*</span><span class="sxs-lookup"><span data-stu-id="bdd4a-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="bdd4a-111">Aby rozwiązać ten problem, należy wykonać kroki opisane w [Wymagania systemowe i wymagania wstępne](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="bdd4a-112">Aby wykonać te kroki, użytkownicy aplikacji podwójnego odpisu, którzy utworzyli w Common Data Service, muszą mieć rolę administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="bdd4a-113">Domyślny zespół będący właścicielem musi mieć również rolę Administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="bdd4a-114">Synchronizacja na żywo dla jakiejkolwiek firmy powoduje, że podczas tworzenia zapisu w aplikacji Finance and Operations jest wciąż zgłaszany podobny błąd</span><span class="sxs-lookup"><span data-stu-id="bdd4a-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="bdd4a-115">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="bdd4a-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="bdd4a-116">Przy każdej próbie zapisania danych jednostki w aplikacji Finance and Operations może pojawić się komunikat o błędzie podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="bdd4a-117">*Nie można zapisać zmian w bazie danych. Jednostka pracy nie może zatwierdzić transakcji. Nie można zapisać danych do jednostki uoms. Zapis do UnitOfMeasureEntity nie powiódł się. Komunikatu o błędzie nie można zsynchronizować z jednostką uoms.*</span><span class="sxs-lookup"><span data-stu-id="bdd4a-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="bdd4a-118">Aby rozwiązać ten problem, należy upewnić się, że istnieją dane referencyjne wymagań wstępnych w aplikacji Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="bdd4a-119">Jeśli na przykład odbiorca należący do danej aplikacji Finance and Operations należy do konkretnej grupy odbiorców, należy upewnić się, że Grupa odbiorców istnieje w Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="bdd4a-120">Jeśli istnieją dane po obu stronach i potwierdzono, że ten błąd nie jest związany z danymi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="bdd4a-121">Zatrzymaj powiązaną jednostkę.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-121">Stop the related entity.</span></span>
2. <span data-ttu-id="bdd4a-122">Zaloguj się do aplikacji Finance and Operations i upewnij się, że w tabelach DualWriteProjectConfiguration i DualWriteProjectFieldConfiguration istnieją rekordy dla jednostki, której dotyczy niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="bdd4a-123">Oto przykład kwerendy, która wygląda tak jak w przypadku niepowodzenia jednostki **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="bdd4a-124">Jeśli istnieją rekordy dla jednostki, której dotyczy błąd, nawet po zatrzymaniu mapowania jednostki, usuń te rekordy, które są powiązane z niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="bdd4a-125">Należy zwrócić uwagę na kolumnę **projectname** w tabeli DualWriteProjectConfiguration i pobrać rekord w tabeli DualWriteProjectFieldConfiguration, używając nazwy projektu w celu usunięcia zapisu.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="bdd4a-126">Rozpocznij mapowanie jednostki.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-126">Start the entity mapping.</span></span> <span data-ttu-id="bdd4a-127">Sprawdź, czy dane są zsynchronizowane bez problemów.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="bdd4a-128">Obsługa błędów uprawnień do odczytu lub odczytu podczas tworzenia danych w aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bdd4a-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="bdd4a-129">Podczas tworzenia danych w aplikacji Finance and Operations może pojawić się komunikat o błędzie „Złe żądanie”, który przypomina poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Przykład komunikatu o błędzie złego żądania](media/error_record_id_source.png)

<span data-ttu-id="bdd4a-131">Aby rozwiązać ten problem, należy przypisać poprawną rolę zabezpieczeń zespołowi zamapowanej jednostki biznesowej usługi Dynamics 365 Customer Service lub Dynamics 365 Sales w celu włączenia brakującego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="bdd4a-132">W aplikacji Finance and Operations znajdź jednostkę biznesową, która jest zamapowana w zestawie połączenia integracji danych.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Mapowanie organizacji](media/mapped_business_unit.png)

2. <span data-ttu-id="bdd4a-134">Zaloguj się do środowiska w aplikacji na podstawie modelu w Dynamics 365, przejdź do **Ustawienia \> Zabezpieczenia** i znajdź zespół zamapowanej jednostki biznesowej.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Zespół zamapowanej jednostki biznesowej](media/setting_security_page.png)

3. <span data-ttu-id="bdd4a-136">Otwórz stronę zespołu do edycji, a następnie wybierz pozycję **Zarządzaj rolami**, aby otworzyć okno dialogowe **Zarządzanie rolami zespołu**.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Przycisk Zarządzaj rolami](media/manage_team_roles.png)

4. <span data-ttu-id="bdd4a-138">Przypisz rolę, która ma uprawnienie odczyt/zapis dla odpowiednich jednostek, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="bdd4a-139">Poprawianie problemów z synchronizacją w środowisku, w którym jest ostatnio zmienione środowisko Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bdd4a-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="bdd4a-140">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="bdd4a-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="bdd4a-141">Może pojawić się następujący komunikat o błędzie podczas tworzenia danych w aplikacji Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="bdd4a-142">*{„EntityName”: „CustCustomerV3Entity”, „executionStatus”: 2, „fieldResponses”:\[\], „recordResponses”:\[{„ErrorMessage”: „**nie można wygenerować ładunku dla jednostki CustCustomerV3Entity**”, „logDateTime”: „2019-08-27T 18:51:52.5843124Z”, „verboseError”: „Tworzenie ładunku nie powiodło się z powodu błędu nieprawidłowy identyfikator URI: identyfikator URI jest pusty”}\], „isErrorCountUpdated”: prawda}*</span><span class="sxs-lookup"><span data-stu-id="bdd4a-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="bdd4a-143">Oto, jak wygląda błąd w aplikacji opartej na modelu w Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="bdd4a-144">*Wystąpił nieoczekiwany błąd w kodzie ISV. (Błąd = ClientError) Nieoczekiwany wyjątek od wtyczki (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nie można przetworzyć konta jednostki — (Próba połączenia nie powiodła się, ponieważ połączona strona nie odpowiedziała prawidłowo po upływie określonego czasu lub ustanowienie połączenia nie powiodło się, ponieważ połączony host nie odpowiedział*</span><span class="sxs-lookup"><span data-stu-id="bdd4a-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="bdd4a-145">Ten błąd występuje, gdy środowisko Common Data Service jest niepoprawnie resetowane w trakcie próby utworzenia danych w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="bdd4a-146">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="bdd4a-147">Zaloguj się do maszyny wirtualnej (VM) Finance and Operations, otwórz program SQL Server Management Studio (SSMSE) i wyszukaj rekordy w tabeli DUALWRITEPROJECTCONFIGURATIONENTITY, gdzie **internalentityname** oznacza **Odbiorców v3** i **externalentityname** równą **konta**.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="bdd4a-148">Oto, co ma wyglądać kwerenda.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="bdd4a-149">Za pomocą nazwy projektu z wyników poprzedniej kwerendy uruchom następującą kwerendę.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="bdd4a-150">Upewnij się, że kolumna **externalenvironmentURL** ma poprawny Common Data Service lub adres URL aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="bdd4a-151">Usuń wszystkie zduplikowane rekordy, które wskazują na nieprawidłowy adres URL Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="bdd4a-152">Usuń odpowiednie rekordy z tabel DUALWRITEPROJECTFIELDCONFIGURATION i DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="bdd4a-153">Zatrzymaj mapowanie jednostki, a następnie uruchom je ponownie</span><span class="sxs-lookup"><span data-stu-id="bdd4a-153">Stop the entity mapping, and then restart it</span></span>
