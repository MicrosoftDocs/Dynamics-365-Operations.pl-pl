---
title: Kopiowanie wystąpienia
description: Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox).
author: andreabichsel
manager: AnnBe
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6b52b696d323df6bafead2418ae322d1a9cdf64a
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706235"
---
# <a name="copy-an-instance"></a><span data-ttu-id="8033d-103">Kopiowanie wystąpienia</span><span class="sxs-lookup"><span data-stu-id="8033d-103">Copy an instance</span></span>

<span data-ttu-id="8033d-104">Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox).</span><span class="sxs-lookup"><span data-stu-id="8033d-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="8033d-105">Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="8033d-106">Aby skopiować wystąpienie, należy pamiętać o następujących wskazówkach:</span><span class="sxs-lookup"><span data-stu-id="8033d-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="8033d-107">Instancja Human Resources, którą chcesz zastąpić, musi być środowiskiem piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="8033d-108">Środowisko kopiowane z systemu i do systemu musi znajdować się w tym samym regionie.</span><span class="sxs-lookup"><span data-stu-id="8033d-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="8033d-109">Nie można kopiować między regionami.</span><span class="sxs-lookup"><span data-stu-id="8033d-109">You can't copy across regions.</span></span>

- <span data-ttu-id="8033d-110">Użytkownik musi być administratorem w środowisku docelowym, aby mógł się w nim zalogować po skopiowaniu instancji.</span><span class="sxs-lookup"><span data-stu-id="8033d-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="8033d-111">Podczas kopiowania bazy danych Human Resources nie są kopiowane elementy (aplikacje lub dane) zawarte w środowisku Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8033d-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="8033d-112">Aby uzyskać informacje o kopiowaniu elementów w środowisku Power Apps, zapoznaj się z tematem [Kopiuj środowisko](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="8033d-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="8033d-113">Środowisko Power Apps, które chcesz zastąpić, musi być środowiskiem piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="8033d-114">Musisz być globalnym administratorem dzierżawy, aby zmienić środowisko produkcyjne Power Apps w środowisko piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="8033d-115">Aby uzyskać więcej informacji o zmienianiu środowiska Power Apps, zapoznaj się z tematem [Przełącz wystąpienie](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="8033d-115">For more information about changing a Power Apps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="8033d-116">Jeśli użytkownik skopiuje wystąpienie do środowiska piaskownicy i chce zintegrować środowisko piaskownicy z systemem Common Data Service, należy ponownie zastosować pola niestandardowe do encji Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8033d-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span> <span data-ttu-id="8033d-117">Zobacz [Zastosuj niestandardowe pola do Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="8033d-117">See [Apply custom fields to Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="8033d-118">Efekty kopiowania bazy danych Human Resources</span><span class="sxs-lookup"><span data-stu-id="8033d-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="8033d-119">Podczas kopiowania bazy danych Human Resources zachodzą następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="8033d-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="8033d-120">Proces kopiowania kasuje istniejącą bazę danych w środowisku docelowym.</span><span class="sxs-lookup"><span data-stu-id="8033d-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="8033d-121">Po zakończeniu procesu kopiowania nie można odzyskać istniejącej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="8033d-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="8033d-122">Środowisko docelowe nie będzie dostępne do czasu zakończenia procesu kopiowania.</span><span class="sxs-lookup"><span data-stu-id="8033d-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="8033d-123">Dokumenty w magazynie obiektów BLOB Microsoft Azure nie są kopiowane z jednego środowiska do drugiego.</span><span class="sxs-lookup"><span data-stu-id="8033d-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="8033d-124">Z tego też powodu żadne dołączone dokumenty i szablony nie zostaną skopiowane i pozostaną w środowisku źródłowym.</span><span class="sxs-lookup"><span data-stu-id="8033d-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="8033d-125">Wszyscy użytkownicy, z wyjątkiem użytkownika o statusie Administrator i innych wewnętrznych użytkowników usługi, będą niedostępni.</span><span class="sxs-lookup"><span data-stu-id="8033d-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="8033d-126">Administrator może usunąć lub ukryć dane, zanim użytkownicy ponownie uzyskają dostęp do systemu.</span><span class="sxs-lookup"><span data-stu-id="8033d-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="8033d-127">Administrator musi wprowadzić wymagane zmiany konfiguracji, takie jak ponowne podłączenie punktów końcowych integracji do określonych usług lub adresów URL.</span><span class="sxs-lookup"><span data-stu-id="8033d-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="8033d-128">Kopiowanie bazy danych Human Resources</span><span class="sxs-lookup"><span data-stu-id="8033d-128">Copy the Human Resources database</span></span>

<span data-ttu-id="8033d-129">Aby wykonać to zadanie, najpierw należy skopiować instancję, a następnie zalogować się do centrum administracyjnego Microsoft Power Platform w celu skopiowania swojego środowiska Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8033d-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="8033d-130">Po skopiowaniu isntancji baza danych jest usuwana w obiekcie docelowym.</span><span class="sxs-lookup"><span data-stu-id="8033d-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="8033d-131">Instancja docelowa jest niedostępna w trakcie tego procesu.</span><span class="sxs-lookup"><span data-stu-id="8033d-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="8033d-132">Zaloguj się do usługi LCS i wybierz projekt usługi LCS zawierający instancję, którą chcesz skopiować.</span><span class="sxs-lookup"><span data-stu-id="8033d-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="8033d-133">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="8033d-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="8033d-134">Wybierz instancję do skopiowania, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="8033d-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="8033d-135">W okienku zadań **Kopiuj instancję** wybierz instancję, która ma zostać zastąpiona, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="8033d-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="8033d-136">Poczekaj na zaktualizowanie wartości pola **Stan kopiowania** na **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="8033d-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="8033d-137">Wybierz instancję do zastąpienia</span><span class="sxs-lookup"><span data-stu-id="8033d-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="8033d-138">Wybierz **Power Platform**, zaloguj się do Centrum administracyjnego Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8033d-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="8033d-139">Wybierz Power Platform</span><span class="sxs-lookup"><span data-stu-id="8033d-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="8033d-140">Wybierz środowisko Power Apps do skopiowania, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="8033d-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="8033d-141">Po zakończeniu procesu kopiowania zaloguj się do instancji docelowej i włącz integrację Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8033d-141">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="8033d-142">Aby uzyskać więcej informacji i instrukcji, zobacz [Konfigurowanie integracji Common Data Service dla przestrzeni roboczych](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="8033d-142">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="8033d-143">Elementy danych i stany</span><span class="sxs-lookup"><span data-stu-id="8033d-143">Data elements and statuses</span></span>

<span data-ttu-id="8033d-144">Następujące elementy danych nie są kopiowane podczas kopiowania instancji Human Resources:</span><span class="sxs-lookup"><span data-stu-id="8033d-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="8033d-145">Adresy e-mail w tabeli **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="8033d-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="8033d-146">Historia zadań wsadowych w tabelach **BatchJobHistory**, **BatchHistory**i **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="8033d-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="8033d-147">Hasło protokołu SMTP (Simple Mail Transfer Protocol) w tabeli **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="8033d-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="8033d-148">Serwer przekaźnika SMTP w tabeli **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="8033d-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="8033d-149">Ustawienia zarządzania drukowaniem w tabelach **PrintMgmtSettings** oraz **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="8033d-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="8033d-150">Rekordy właściwe dla środowiska w tabelach **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** i **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="8033d-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="8033d-151">Załączniki dokumentów w tabeli DocuValue.</span><span class="sxs-lookup"><span data-stu-id="8033d-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="8033d-152">Do tych załączników należą wszystkie szablony Microsoft Office, które zostały zastąpione w środowisku źródłowym</span><span class="sxs-lookup"><span data-stu-id="8033d-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="8033d-153">Ciąg połączenia w tabeli **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="8033d-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="8033d-154">Niektóre z tych elementów nie są kopiowane, ponieważ są specyficzne dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="8033d-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="8033d-155">Przykłady to m.in. rekordy **BatchServerConfig** czy **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="8033d-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="8033d-156">Inne elementy nie są kopiowane z powodu wolumenu biletów pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="8033d-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="8033d-157">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="8033d-157">For example:</span></span>

- <span data-ttu-id="8033d-158">Mogą zostać wysłane zduplikowane wiadomości e-mail, ponieważ protokół SMTP jest nadal włączony w środowisku testowania akceptacji użytkowników (piaskownicy).</span><span class="sxs-lookup"><span data-stu-id="8033d-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="8033d-159">Mogą zostać wysłane nieprawidłowe komunikaty integracji, ponieważ zadania wsadowe są nadal włączone.</span><span class="sxs-lookup"><span data-stu-id="8033d-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="8033d-160">Dostęp użytkowników może być włączony zanim administratorzy będą mogli wykonywać akcje oczyszczania po odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="8033d-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="8033d-161">Ponadto podczas kopiowania istnieją zmieniają się następujące stany:</span><span class="sxs-lookup"><span data-stu-id="8033d-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="8033d-162">Wszyscy użytkownicy z wyjątkiem administratora są **Wyłączeni**.</span><span class="sxs-lookup"><span data-stu-id="8033d-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="8033d-163">Wszystkie zadania wsadowe, z wyjątkiem niektórych zadań systemowych, są ustawione na **Wstrzymane**.</span><span class="sxs-lookup"><span data-stu-id="8033d-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="8033d-164">Administrator środowiska</span><span class="sxs-lookup"><span data-stu-id="8033d-164">Environment admin</span></span>

<span data-ttu-id="8033d-165">Wszyscy użytkownicy w docelowym środowisku piaskownicy, w tym Administratorzy, są zastępowani przez użytkowników środowiska źródłowego.</span><span class="sxs-lookup"><span data-stu-id="8033d-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="8033d-166">Przed skopiowaniem wystąpienia należy upewnić się, że jesteś Administratorem w środowisku źródłowym.</span><span class="sxs-lookup"><span data-stu-id="8033d-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="8033d-167">Jeśli nie, po zakończeniu kopiowania nie będzie można zalogować się do docelowego środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="8033d-168">Wszyscy użytkownicy niebędący Administratorami w docelowym środowisku piaskownicy są wyłączeni w celu zapobiegania niepotrzebnego rejestrowania w środowisku piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="8033d-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="8033d-169">W razie potrzeby Administratorzy mogą ponownie włączyć użytkowników.</span><span class="sxs-lookup"><span data-stu-id="8033d-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-common-data-service"></a><span data-ttu-id="8033d-170">Zastosuj niestandardowe pola do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8033d-170">Apply custom fields to Common Data Service</span></span>

<span data-ttu-id="8033d-171">Jeśli użytkownik skopiuje wystąpienie do środowiska piaskownicy i chce zintegrować środowisko piaskownicy z systemem Common Data Service, należy ponownie zastosować pola niestandardowe do encji Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8033d-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span>

<span data-ttu-id="8033d-172">Dla każdego pola niestandardowego, które jest uwidocznione na encjach Common Data Service należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8033d-172">For each custom field that's exposed on Common Data Service entities, do the following steps:</span></span>

1. <span data-ttu-id="8033d-173">Przejdź do pola niestandardowego i wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8033d-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="8033d-174">Usuń zaznaczenie pola **Włączone** dla każdej jednostki cdm_\*, dla której włączono pole niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8033d-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="8033d-175">Wybierz opcję **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="8033d-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="8033d-176">Wybierz ponownie przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="8033d-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="8033d-177">Wybierz pole **Włączone** dla każdej jednostki cdm_\*, dla której włączono pole niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8033d-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="8033d-178">Ponownie wybierz opcję **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="8033d-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="8033d-179">Proces cofania wyboru, stosowania zmian, ponownego wybierania i ponownego stosowania zmian powoduje wyświetlenie w schemacie, w którym w Common Data Service będą uwzględniane pola niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="8033d-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Common Data Service to include the custom fields.</span></span>

<span data-ttu-id="8033d-180">Aby uzyskać więcej informacji na temat tworzenia pól niestandardowych, zobacz [Tworzenie pól niestandardowych i praca z nimi](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span><span class="sxs-lookup"><span data-stu-id="8033d-180">For more information about custom fields, see [Create and work with custom fields](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span></span>

## <a name="see-also"></a><span data-ttu-id="8033d-181">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="8033d-181">See also</span></span>

[<span data-ttu-id="8033d-182">Aprowizowanie rozwiązania Human Resources</span><span class="sxs-lookup"><span data-stu-id="8033d-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="8033d-183">Usuwanie wystąpienie</span><span class="sxs-lookup"><span data-stu-id="8033d-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="8033d-184">Aktualizowanie procesu</span><span class="sxs-lookup"><span data-stu-id="8033d-184">Update process</span></span>](hr-admin-setup-update-process.md)

