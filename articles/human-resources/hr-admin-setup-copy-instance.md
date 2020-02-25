---
title: Kopiowanie wystąpienia
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010156"
---
# <a name="copy-an-instance"></a><span data-ttu-id="38364-102">Kopiowanie wystąpienia</span><span class="sxs-lookup"><span data-stu-id="38364-102">Copy an instance</span></span>

<span data-ttu-id="38364-103">Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox).</span><span class="sxs-lookup"><span data-stu-id="38364-103">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="38364-104">Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-104">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="38364-105">Aby skopiować instancję, należy upewnić się, co następuje:</span><span class="sxs-lookup"><span data-stu-id="38364-105">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="38364-106">Instancja Human Resources, którą chcesz zastąpić, musi być środowiskiem piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-106">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="38364-107">Środowisko kopiowane z systemu i do systemu musi znajdować się w tym samym regionie.</span><span class="sxs-lookup"><span data-stu-id="38364-107">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="38364-108">Nie można kopiować między regionami.</span><span class="sxs-lookup"><span data-stu-id="38364-108">You can't copy across regions.</span></span>

- <span data-ttu-id="38364-109">Użytkownik musi być administratorem w środowisku docelowym, aby mógł się w nim zalogować po skopiowaniu instancji.</span><span class="sxs-lookup"><span data-stu-id="38364-109">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="38364-110">Podczas kopiowania bazy danych Human Resources nie są kopiowane elementy (aplikacje lub dane) zawarte w środowisku Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="38364-110">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="38364-111">Aby uzyskać informacje o kopiowaniu elementów w środowisku PowerApps, zapoznaj się z tematem [Kopiuj środowisko](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="38364-111">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="38364-112">Środowisko PowerApps, które chcesz zastąpić, musi być środowiskiem piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-112">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="38364-113">Musisz być globalnym administratorem dzierżawy, aby zmienić środowisko produkcyjne PowerApps w środowisko piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-113">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="38364-114">Aby uzyskać więcej informacji o zmienianiu środowiska PowerApps, zapoznaj się z tematem [Przełącz wystąpienie](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="38364-114">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="38364-115">Efekty kopiowania bazy danych Human Resources</span><span class="sxs-lookup"><span data-stu-id="38364-115">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="38364-116">Podczas kopiowania bazy danych Human Resources zachodzą następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="38364-116">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="38364-117">Proces kopiowania kasuje istniejącą bazę danych w środowisku docelowym.</span><span class="sxs-lookup"><span data-stu-id="38364-117">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="38364-118">Po zakończeniu procesu kopiowania nie można odzyskać istniejącej bazy danych.</span><span class="sxs-lookup"><span data-stu-id="38364-118">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="38364-119">Środowisko docelowe nie będzie dostępne do czasu zakończenia procesu kopiowania.</span><span class="sxs-lookup"><span data-stu-id="38364-119">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="38364-120">Dokumenty w magazynie obiektów BLOB Microsoft Azure nie są kopiowane z jednego środowiska do drugiego.</span><span class="sxs-lookup"><span data-stu-id="38364-120">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="38364-121">Z tego powodu wszystkie dołączone dokumenty i szablony nie zostaną skopiowane i pozostaną w środowisku źródłowym.</span><span class="sxs-lookup"><span data-stu-id="38364-121">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="38364-122">Wszyscy użytkownicy, z wyjątkiem użytkownika o statusie Administrator i innych wewnętrznych użytkowników usługi, będą niedostępni.</span><span class="sxs-lookup"><span data-stu-id="38364-122">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="38364-123">W związku z tym Administrator może usunąć lub ukryć dane, zanim inni użytkownicy nie będą mogli z powrotem w systemie.</span><span class="sxs-lookup"><span data-stu-id="38364-123">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="38364-124">Administrator musi wprowadzić wymagane zmiany konfiguracji, takie jak ponowne podłączenie punktów końcowych integracji do określonych usług lub adresów URL.</span><span class="sxs-lookup"><span data-stu-id="38364-124">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="38364-125">Kopiowanie bazy danych Human Resources</span><span class="sxs-lookup"><span data-stu-id="38364-125">Copy the Human Resources database</span></span>

<span data-ttu-id="38364-126">Aby wykonać to zadanie, najpierw należy skopiować instancję, a następnie zalogować się do centrum administracyjnego Microsoft Power Platform w celu skopiowania swojego środowiska PowerApps.</span><span class="sxs-lookup"><span data-stu-id="38364-126">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="38364-127">Po skopiowaniu isntancji baza danych jest usuwana w obiekcie docelowym.</span><span class="sxs-lookup"><span data-stu-id="38364-127">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="38364-128">Instancja docelowa jest niedostępna w trakcie tego procesu.</span><span class="sxs-lookup"><span data-stu-id="38364-128">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="38364-129">Zaloguj się do usługi LCS i wybierz projekt usługi LCS zawierający instancję, którą chcesz skopiować.</span><span class="sxs-lookup"><span data-stu-id="38364-129">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="38364-130">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="38364-130">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="38364-131">Wybierz instancję do skopiowania, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="38364-131">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="38364-132">W okienku zadań **Kopiuj instancję** wybierz instancję, która ma zostać zastąpiona, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="38364-132">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="38364-133">Poczekaj na zaktualizowanie wartości pola **Stan kopiowania** na **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="38364-133">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="38364-134">Wybierz instancję do zastąpienia</span><span class="sxs-lookup"><span data-stu-id="38364-134">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="38364-135">Wybierz **Power Platform**, zaloguj się do Centrum administracyjnego Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="38364-135">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="38364-136">Wybierz Power Platform</span><span class="sxs-lookup"><span data-stu-id="38364-136">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="38364-137">Wybierz środowisko PowerApps do skopiowania, a następnie wybierz **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="38364-137">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="38364-138">Po zakończeniu procesu kopiowania zaloguj się do instancji docelowej i włącz integrację Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38364-138">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="38364-139">Aby uzyskać więcej informacji i instrukcji, zobacz [Konfigurowanie integracji Common Data Service dla przestrzeni roboczych](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="38364-139">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="38364-140">Elementy danych i stany</span><span class="sxs-lookup"><span data-stu-id="38364-140">Data elements and statuses</span></span>

<span data-ttu-id="38364-141">Następujące elementy danych nie są kopiowane podczas kopiowania instancji Human Resources:</span><span class="sxs-lookup"><span data-stu-id="38364-141">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="38364-142">Adresy e-mail w tabeli **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="38364-142">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="38364-143">Historia zadań wsadowych w tabelach **BatchJobHistory**, **BatchHistory**i **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="38364-143">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="38364-144">Hasło protokołu SMTP (Simple Mail Transfer Protocol) w tabeli **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="38364-144">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="38364-145">Serwer przekaźnika SMTP w tabeli **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="38364-145">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="38364-146">Ustawienia zarządzania drukowaniem w tabelach **PrintMgmtSettings** oraz **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="38364-146">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="38364-147">Rekordy właściwe dla środowiska w tabelach **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** i **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="38364-147">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="38364-148">Załączniki dokumentów w tabeli DocuValue.</span><span class="sxs-lookup"><span data-stu-id="38364-148">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="38364-149">Do tych załączników należą wszystkie szablony Microsoft Office, które zostały zastąpione w środowisku źródłowym</span><span class="sxs-lookup"><span data-stu-id="38364-149">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="38364-150">Ciąg połączenia w tabeli **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="38364-150">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="38364-151">Niektóre z tych elementów nie są kopiowane, ponieważ są specyficzne dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="38364-151">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="38364-152">Przykłady to m.in. rekordy **BatchServerConfig** czy **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="38364-152">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="38364-153">Inne elementy nie są kopiowane z powodu wolumenu biletów pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="38364-153">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="38364-154">Na przykład mogą zostać wysłane zduplikowane wiadomości e-mail, ponieważ protokół SMTP jest nadal włączony w środowisku testowania akceptacji użytkownika (piaskownicy), mogą zostać wysłane nieprawidłowe komunikaty integracji, ponieważ zadania wsadowe są nadal włączone, a użytkownicy mogą być włączani przed wykonaniem przez administratora akcji oczyszczania po odświeżeniu.</span><span class="sxs-lookup"><span data-stu-id="38364-154">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="38364-155">Ponadto podczas kopiowania istnieją zmieniają się następujące stany:</span><span class="sxs-lookup"><span data-stu-id="38364-155">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="38364-156">Wszyscy użytkownicy z wyjątkiem administratora są **Wyłączeni**.</span><span class="sxs-lookup"><span data-stu-id="38364-156">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="38364-157">Wszystkie zadania wsadowe, z wyjątkiem niektórych zadań systemowych, są ustawione na **Wstrzymane**.</span><span class="sxs-lookup"><span data-stu-id="38364-157">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="38364-158">Administrator środowiska</span><span class="sxs-lookup"><span data-stu-id="38364-158">Environment admin</span></span>

<span data-ttu-id="38364-159">Wszyscy użytkownicy w docelowym środowisku piaskownicy, w tym Administratorzy, są zastępowani przez użytkowników środowiska źródłowego.</span><span class="sxs-lookup"><span data-stu-id="38364-159">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="38364-160">Przed skopiowaniem wystąpienia należy upewnić się, że jesteś Administratorem w środowisku docelowym.</span><span class="sxs-lookup"><span data-stu-id="38364-160">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="38364-161">Jeśli nie, po zakończeniu kopiowania nie będzie można zalogować się do docelowego środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-161">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="38364-162">Wszyscy użytkownicy niebędący Administratorami w docelowym środowisku piaskownicy są wyłączeni w celu zapobiegania niepotrzebnego rejestrowania w środowisku piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="38364-162">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="38364-163">W razie potrzeby Administratorzy mogą ponownie włączyć użytkowników.</span><span class="sxs-lookup"><span data-stu-id="38364-163">Administrators can reenable users if needed.</span></span>
