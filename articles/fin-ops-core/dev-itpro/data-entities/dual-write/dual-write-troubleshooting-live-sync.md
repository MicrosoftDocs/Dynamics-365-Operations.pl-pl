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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 59c8bd80b167cdfaa7a65e469f4dc7ebf8f50844
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744620"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="f8b72-103">Rozwiązywanie problemów z synchronizacją na żywo</span><span class="sxs-lookup"><span data-stu-id="f8b72-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="f8b72-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f8b72-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="f8b72-105">Ten temat zawiera informacje, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.</span><span class="sxs-lookup"><span data-stu-id="f8b72-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8b72-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f8b72-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="f8b72-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="f8b72-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="f8b72-108">Synchronizacja na żywo powoduje, że podczas tworzenia wiersza w aplikacji Finance and Operations jest zgłaszany błąd 403 Zabroniony</span><span class="sxs-lookup"><span data-stu-id="f8b72-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="f8b72-109">Może pojawić się następujący komunikat o błędzie podczas tworzenia wiersza w aplikacji Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="f8b72-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="f8b72-110">*\[{\\„błąd\\”:{\\„kod\\”:\\„0x 80072560\\”,\\„komunikat\\”:\\„użytkownik nie jest członkiem organizacji.\\”}}\], Serwer zdalny zwrócił błąd: (403) zabroniony”}}”.*</span><span class="sxs-lookup"><span data-stu-id="f8b72-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="f8b72-111">Aby rozwiązać ten problem, należy wykonać kroki opisane w [Wymagania systemowe i wymagania wstępne](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f8b72-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="f8b72-112">Aby wykonać te kroki, użytkownicy aplikacji podwójnego odpisu, którzy utworzyli w Dataverse, muszą mieć rolę administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="f8b72-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="f8b72-113">Domyślny zespół będący właścicielem musi mieć również rolę Administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="f8b72-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="f8b72-114">Synchronizacja na żywo dla jakiejkolwiek tabeli powoduje, że podczas tworzenia wiersza w aplikacji Finance and Operations jest wciąż zgłaszany podobny błąd</span><span class="sxs-lookup"><span data-stu-id="f8b72-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="f8b72-115">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="f8b72-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f8b72-116">Przy każdej próbie zapisania danych tabeli w aplikacji Finance and Operations może pojawić się komunikat o błędzie podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="f8b72-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="f8b72-117">*Nie można zapisać zmian w bazie danych. Jednostka pracy nie może zatwierdzić transakcji. Nie można zapisać danych do jednostki uoms. Zapis do UnitOfMeasureEntity nie powiódł się. Komunikatu o błędzie nie można zsynchronizować z jednostką uoms.*</span><span class="sxs-lookup"><span data-stu-id="f8b72-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="f8b72-118">Aby rozwiązać ten problem, należy upewnić się, że istnieją dane referencyjne wymagań wstępnych w aplikacji Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f8b72-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="f8b72-119">Jeśli na przykład odbiorca należący do danej aplikacji Finance and Operations należy do konkretnej grupy odbiorców, należy upewnić się, że Grupa odbiorców istnieje w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f8b72-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="f8b72-120">Jeśli istnieją dane po obu stronach i potwierdzono, że ten błąd nie jest związany z danymi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f8b72-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="f8b72-121">Zatrzymaj powiązaną tabelę.</span><span class="sxs-lookup"><span data-stu-id="f8b72-121">Stop the related table.</span></span>
2. <span data-ttu-id="f8b72-122">Zaloguj się do aplikacji Finance and Operations i upewnij się, że w tabelach DualWriteProjectConfiguration i DualWriteProjectFieldConfiguration istnieją wiersze dla tabeli, której dotyczy niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="f8b72-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="f8b72-123">Oto przykład zapytania, które wygląda tak jak w przypadku niepowodzenia tabeli **Klienci**.</span><span class="sxs-lookup"><span data-stu-id="f8b72-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="f8b72-124">Jeśli istnieją wiersze dla tabeli, której dotyczy błąd, nawet po zatrzymaniu mapowania tabeli, usuń te wiersze, które są powiązane z niepowodzeniem dla tabeli.</span><span class="sxs-lookup"><span data-stu-id="f8b72-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="f8b72-125">Należy zwrócić uwagę na kolumnę **projectname** w tabeli DualWriteProjectConfiguration i pobrać wiersz w tabeli DualWriteProjectFieldConfiguration, używając nazwy projektu w celu usunięcia wiersza.</span><span class="sxs-lookup"><span data-stu-id="f8b72-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="f8b72-126">Rozpocznij mapowanie tabeli.</span><span class="sxs-lookup"><span data-stu-id="f8b72-126">Start the table mapping.</span></span> <span data-ttu-id="f8b72-127">Sprawdź, czy dane są zsynchronizowane bez problemów.</span><span class="sxs-lookup"><span data-stu-id="f8b72-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="f8b72-128">Obsługa błędów uprawnień do odczytu lub odczytu podczas tworzenia danych w aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f8b72-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="f8b72-129">Podczas tworzenia danych w aplikacji Finance and Operations może pojawić się komunikat o błędzie „Złe żądanie”, który przypomina poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="f8b72-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Przykład komunikatu o błędzie złego żądania](media/error_record_id_source.png)

<span data-ttu-id="f8b72-131">Aby rozwiązać ten problem, należy przypisać poprawną rolę zabezpieczeń zespołowi zamapowanej jednostki biznesowej usługi Dynamics 365 Customer Service lub Dynamics 365 Sales w celu włączenia brakującego uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="f8b72-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="f8b72-132">W aplikacji Finance and Operations znajdź jednostkę biznesową, która jest zamapowana w zestawie połączenia integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f8b72-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Mapowanie organizacji](media/mapped_business_unit.png)

2. <span data-ttu-id="f8b72-134">Zaloguj się do środowiska w aplikacji na podstawie modelu w Dynamics 365, przejdź do **Ustawienia \> Zabezpieczenia** i znajdź zespół zamapowanej jednostki biznesowej.</span><span class="sxs-lookup"><span data-stu-id="f8b72-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Zespół zamapowanej jednostki biznesowej](media/setting_security_page.png)

3. <span data-ttu-id="f8b72-136">Otwórz stronę zespołu do edycji, a następnie wybierz pozycję **Zarządzaj rolami**, aby otworzyć okno dialogowe **Zarządzanie rolami zespołu**.</span><span class="sxs-lookup"><span data-stu-id="f8b72-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Przycisk Zarządzaj rolami](media/manage_team_roles.png)

4. <span data-ttu-id="f8b72-138">Przypisz rolę, która ma uprawnienie odczyt/zapis dla odpowiednich tabel, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8b72-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="f8b72-139">Poprawianie problemów z synchronizacją w środowisku, w którym jest ostatnio zmienione środowisko Dataverse</span><span class="sxs-lookup"><span data-stu-id="f8b72-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="f8b72-140">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="f8b72-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f8b72-141">Może pojawić się następujący komunikat o błędzie podczas tworzenia danych w aplikacji Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="f8b72-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="f8b72-142">*{„EntityName”: „CustCustomerV3Entity”, „executionStatus”: 2, „fieldResponses”:\[\], „recordResponses”:\[{„ErrorMessage”: „**nie można wygenerować ładunku dla jednostki CustCustomerV3Entity**”, „logDateTime”: „2019-08-27T 18:51:52.5843124Z”, „verboseError”: „Tworzenie ładunku nie powiodło się z powodu błędu nieprawidłowy identyfikator URI: identyfikator URI jest pusty”}\], „isErrorCountUpdated”: prawda}*</span><span class="sxs-lookup"><span data-stu-id="f8b72-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="f8b72-143">Oto, jak wygląda błąd w aplikacji opartej na modelu w Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="f8b72-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="f8b72-144">*Wystąpił nieoczekiwany błąd w kodzie ISV. (Błąd = ClientError) Nieoczekiwany wyjątek od wtyczki (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nie można przetworzyć konta jednostki — (Próba połączenia nie powiodła się, ponieważ połączona strona nie odpowiedziała prawidłowo po upływie określonego czasu lub ustanowienie połączenia nie powiodło się, ponieważ połączony host nie odpowiedział*</span><span class="sxs-lookup"><span data-stu-id="f8b72-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="f8b72-145">Ten błąd występuje, gdy środowisko Dataverse jest niepoprawnie resetowane w trakcie próby utworzenia danych w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f8b72-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="f8b72-146">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="f8b72-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="f8b72-147">Zaloguj się do maszyny wirtualnej (VM) Finance and Operations, otwórz program SQL Server Management Studio (SSMSE) i wyszukaj wiersze w tabeli DUALWRITEPROJECTCONFIGURATIONENTITY, gdzie **internalentityname** oznacza **Odbiorców v3** i **externalentityname** równą **konta**.</span><span class="sxs-lookup"><span data-stu-id="f8b72-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="f8b72-148">Oto, co ma wyglądać kwerenda.</span><span class="sxs-lookup"><span data-stu-id="f8b72-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="f8b72-149">Za pomocą nazwy projektu z wyników poprzedniej kwerendy uruchom następującą kwerendę.</span><span class="sxs-lookup"><span data-stu-id="f8b72-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="f8b72-150">Upewnij się, że kolumna **externalenvironmentURL** ma poprawny Dataverse lub adres URL aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f8b72-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="f8b72-151">Usuń wszystkie zduplikowane wiersze, które wskazują na nieprawidłowy adres URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f8b72-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="f8b72-152">Usuń odpowiednie wiersze z tabel DUALWRITEPROJECTFIELDCONFIGURATION i DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="f8b72-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="f8b72-153">Zatrzymaj mapowanie tabeli, a następnie uruchom je ponownie</span><span class="sxs-lookup"><span data-stu-id="f8b72-153">Stop the table mapping, and then restart it</span></span>
