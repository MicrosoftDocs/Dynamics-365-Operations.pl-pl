---
title: Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool
description: Ten temat zawiera Samouczek przedstawiający sposób konfigurowania i instalowania narzędzia Regression Suite Automation Tool (RSAT).
author: kfend
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2287cb0281e920de219cb88d41cd69264911f93
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850875"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="ec2f7-103">Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="ec2f7-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="ec2f7-104">Ten temat jest samouczkiem, który pomaga w konfigurowaniu systemu i rozpoczynaniu pracy z narzędziem RSAT oraz innymi narzędziami związanymi z korzystaniem z niego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ec2f7-105">Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="ec2f7-106">Podstawowe pojęcia</span><span class="sxs-lookup"><span data-stu-id="ec2f7-106">Key concepts</span></span>

- <span data-ttu-id="ec2f7-107">Opis instalacji i wymagań wstępnych, które są wymagane w przypadku różnych aplikacji obsługujących narzędzie Regression Suite Automation Tool (RSAT).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="ec2f7-108">Sposób, w jaki funkcja Rejestrator zadań w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, wraz z usługą Microsoft Dynamics Lifecycle Services (LCS) i usługą Microsoft Azure DevOps, umożliwia tworzenie, konfigurowanie, uruchamianie, badanie i raportowanie przypadków testowych.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-108">Understand how the Task recorder feature in Microsoft Dynamics 365 for Finance and Operations, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="ec2f7-109">Umożliwienie użytkownikom rejestrowania zadań biznesowych za pomocą rejestratora zadań w rozwiązaniu Finance and Operations, a następnie konwertowania nagrań zadania na pakiet automatycznych testów bez konieczności pisania kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-109">Empower functional users to record business tasks by using Task recorder in Finance and Operations, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ec2f7-110">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="ec2f7-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ec2f7-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="ec2f7-111">Prerequisites</span></span>

- <span data-ttu-id="ec2f7-112">W tym samouczku jest wymagane środowisko rozwiązania Microsoft Dynamics 365 for Finance and Operations w wersji 10.0 (kwiecień 2019) lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-112">A Finance and Operations environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="ec2f7-113">W przypadku klientów korzystających z rozwiązania Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, obsługiwana jest także aktualizacja Platform update 20 (PU20) lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="ec2f7-114">Użytkownik musi mieć uprawnienia administratora do środowiska rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-114">The user must have admin rights to the Finance and Operations environment.</span></span>
- <span data-ttu-id="ec2f7-115">Użytkownik musi mieć dostęp do dzierżawy klienta usługi LCS oraz usługi Azure DevOps (znanej wcześniej jako Microsoft Visual Studio Team Services \[VSTS\]).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="ec2f7-116">Użytkownik, który tworzy pakiety testów i zarządza nimi, musi mieć licencję Plany testów lub Menedżer testów do usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="ec2f7-117">Następujące licencje również umożliwiają dostęp do planów testów:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="ec2f7-118">Licencja Visual Studio Enterprise</span><span class="sxs-lookup"><span data-stu-id="ec2f7-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="ec2f7-119">Licencja Visual Studio Test Professional</span><span class="sxs-lookup"><span data-stu-id="ec2f7-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="ec2f7-120">Licencja subskrybenta platform MSDN</span><span class="sxs-lookup"><span data-stu-id="ec2f7-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="ec2f7-121">Narzędzie RSAT musi mieć dostęp do środowiska testowego za pośrednictwem przeglądarki sieci web.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="ec2f7-122">Aby generować i edytować parametry testowe, należy mieć zainstalowany program Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="ec2f7-123">Konfigurowanie usługi Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ec2f7-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="ec2f7-124">Uprawnienia użytkownika</span><span class="sxs-lookup"><span data-stu-id="ec2f7-124">User eligibility</span></span>

<span data-ttu-id="ec2f7-125">Użytkownik musi być utworzony w usłudze Azure DevOps i mieć poziom subskrypcji zapewniający dostęp do planów testów usługi Azure.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="ec2f7-126">Licencja Plany testów usługi Azure DevOps jest wymagana tylko wtedy, gdy użytkownik tworzy przypadki testowe i zarządza nimi (czyli nie każdy użytkownik narzędzia RSAT musi mieć tę licencję).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="ec2f7-127">Aby uzyskać informacje dotyczące wymagań dotyczących licencji, zapoznaj się z [wymaganiami dotyczącymi licencji](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="ec2f7-128">Tworzenie nowego projektu w usłudze Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ec2f7-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="ec2f7-129">W narzędziu RSAT do zarządzania przypadkami testowymi i pakietami testów, raportowania ich i analizowania wyników przebiegu testowego jest wykorzystywana usługa Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="ec2f7-130">Użycie istniejącego projektu usługi Azure DevOps jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="ec2f7-131">Jeśli jednak istniejący projekt usługi Azure DevOps jest skonfigurowany w taki sposób, że zawiera szablon niestandardowy, podczas synchronizowania przypadków testowych z narzędziem do modelowania procesów biznesowych (BPM) zostanie wyświetlony komunikat o błędzie „Niepowodzenie synchronizacji usługi VSTS” Azure DevOps (zobacz sekcję [Testowanie synchronizacji między narzędziem BPM a usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="ec2f7-132">Jeśli szablon niestandardowy został wykonany zgodnie z następującymi najlepszymi praktykami, będzie możliwe zsynchronizowanie przypadków testowych z usługą Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="ec2f7-133">(Te najlepsze praktyki są wymienione w komunikacie o błędzie).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="ec2f7-134">Nie usuwaj żadnych typów elementów roboczych ani standardowych pól.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="ec2f7-135">Nie usuwaj żadnego stanu typu elementu roboczego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="ec2f7-136">Nie dodawaj żadnych wymaganych pól do typu elementu roboczego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-136">Do not add any required fields to a work item type.</span></span>

![Komunikat o błędzie z listą najlepszych praktyk](./media/setup_rsa_tool_02.png)

<span data-ttu-id="ec2f7-138">W przeciwnym razie zaleca się utworzenie nowego projektu Azure DevOps i korzystanie z niego w trakcie tego samouczka.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="ec2f7-139">Aby uzyskać więcej informacji, zobacz temat [Problemy występujące podczas synchronizacji z narzędziem BPM przy użyciu niestandardowego szablonu procesu usługi Azure DevOps (VSTS)](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="ec2f7-140">Otwórz adres URL usługi Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="ec2f7-141">Kliknij przycisk **Utwórz projekt** w prawym górnym rogu strony usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Przycisk Utwórz projekt](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="ec2f7-143">Wypełnij następujące pola, a następnie kliknij przycisk **Utwórz**:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="ec2f7-144">**Nazwa projektu**</span><span class="sxs-lookup"><span data-stu-id="ec2f7-144">**Project name**</span></span>
    - <span data-ttu-id="ec2f7-145">**Kontrola wersji** — wybierz opcję **Kontrola wersji serwera Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="ec2f7-146">Domyślna opcja, **Git**, nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="ec2f7-147">**Proces elementu roboczego**</span><span class="sxs-lookup"><span data-stu-id="ec2f7-147">**Work item process**</span></span>

    ![Okno dialogowe Tworzenie nowego projektu](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="ec2f7-149">Tworzenie osobistego tokenu dostępu</span><span class="sxs-lookup"><span data-stu-id="ec2f7-149">Create a personal access token</span></span>

<span data-ttu-id="ec2f7-150">W tym samouczku utworzysz bibliotekę przypadków testowych i zsynchronizujesz przypadki testowe z usługą Azure DevOps przy użyciu narzędzia do modelowania procesów biznesowych (BPM) usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="ec2f7-151">Do synchronizacji narzędzia BPM z usługą Azure DevOps będzie potrzebny osobisty token dostępu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="ec2f7-152">Kliknij ikonę profilu w prawym górnym rogu strony usługi Azure DevOps projektu, a następnie kliknij przycisk **Zabezpieczenia**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Polecenie Zabezpieczenia](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="ec2f7-154">W lewym okienku, w sekcji **Zabezpieczenia** kliknij przycisk **Osobiste tokeny dostępu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="ec2f7-155">Następnie kliknij przycisk **Nowy token**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-155">Then select **New Token**.</span></span>

    ![Przycisk Nowy token na karcie Osobiste tokeny dostępu w oknie Ustawienia użytkownika](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="ec2f7-157">Wypełnij następujące pola, a następnie kliknij przycisk **Utwórz**:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="ec2f7-158">**Nazwisko**</span><span class="sxs-lookup"><span data-stu-id="ec2f7-158">**Name**</span></span>
    - <span data-ttu-id="ec2f7-159">**Wygaśnięcie (UTC)** — kliknij przycisk **Niestandardowe**, a następnie wybierz najpóźniejszą dostępną datę w selektorze daty.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="ec2f7-160">**Zakresy** — wybierz opcję **Pełny dostęp**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Okno dialogowe Tworzenie nowego osobistego tokenu dostępu](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-162">Zanotuj osobisty token dostępu, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="ec2f7-163">Będzie on potrzebny w późniejszym czasie podczas konfigurowania narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Osobisty token dostępu](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="ec2f7-165">Konfigurowanie projektu w usłudze LCS</span><span class="sxs-lookup"><span data-stu-id="ec2f7-165">Configure the LCS project</span></span>

<span data-ttu-id="ec2f7-166">Potrzebujesz projektu w usłudze Lifecycle Services (LCS) na główną bibliotekę testów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="ec2f7-167">Główna biblioteka przypadków testowych będzie zarządzana za pomocą narzędzia do modelowania procesów biznesowych usługi LCS (BPM).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="ec2f7-168">Narzędzie BPM służy do zarządzania bibliotekami testów i dystrybuowania ich w projektach usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="ec2f7-169">Na przykład partner firmy Microsoft lub niezależny dostawca oprogramowania (ISV) tworzyć biblioteki testów będzie publikował przypadki testowe w formie bibliotek narzędzia BPM.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="ec2f7-170">W narzędziu BPM przypadki testowe są zorganizowane według procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="ec2f7-171">Narzędzie BPM nie wyznacza kolejności wykonywania ani częstotliwości przebiegu testowego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="ec2f7-172">Te szczegóły są określane w usłudze Azure DevOps w sposób opisany w dalszej części niniejszego tematu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="ec2f7-173">Jako projektu usługi LCS można użyć istniejącej implementacji klienta lub projektu partnera.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="ec2f7-174">Aktualizowanie języka usługi LCS</span><span class="sxs-lookup"><span data-stu-id="ec2f7-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-175">Aby procesy biznesowe były poprawnie wyświetlane w interfejsie użytkownika, jako preferowany język usługi LCS musi być wybrany **angielski (Stany Zjednoczone)**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="ec2f7-176">Przejdź do projektu implementacji usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ec2f7-177">Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie kliknij przycisk **Preferencje języka**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Polecenia w menu Ustawienia](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="ec2f7-179">W polu **Preferowany język** wybierz opcję **angielski (Stany Zjednoczone)**, a następnie kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Karta Preferencje języka w oknie Ustawienia użytkownika](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="ec2f7-181">Konfigurowanie połączenia z projektem usługi Azure DevOps w usłudze LCS</span><span class="sxs-lookup"><span data-stu-id="ec2f7-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="ec2f7-182">Jeśli wcześniej utworzono nowy projekt usługi Azure DevOps, skonfiguruj połączenie z tym projektem w projekcie usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="ec2f7-183">Jeśli projekt usługi LCS jest już połączony z projektem usługi Azure DevOps, możesz przejść do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="ec2f7-184">Przejdź do projektu implementacji usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ec2f7-185">Kliknij przycisk **Menu**, a następnie kliknij przycisk **Ustawienia projektu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Polecenie Ustawienia projektu](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="ec2f7-187">W lewym okienku kliknij przycisk **Visual Studio Team Services**, a następnie kliknij przycisk **Ustawienia usługi Visual Studio Team Services**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Karta Ustawienia usługi Visual Studio Team Services w oknie Ustawienia projektu](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="ec2f7-189">W polu **Adres URL witryny usługi Azure DevOps** wpisz adres URL witryny usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="ec2f7-190">W polu **Osobisty token dostępu** wpisz osobisty token dostępu, który został utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-191">Chociaż usługa VSTS obecnie jest znana jako Azure DevOps, w celu połączenia usługi LCS z projektem Azure DevOps użyj starego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="ec2f7-192">Na przykład adres URL usługi Azure DevOps używany w tym samouczku to `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="ec2f7-193">Jednak na poniższej ilustracji jest on wprowadzony jako `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Krok 1 w oknie Konfigurowanie usługi Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="ec2f7-195">Kliknij przycisk **Kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-195">Select **Continue**.</span></span>
6. <span data-ttu-id="ec2f7-196">W polu **Projekt usługi Visual Studio Team Services** wybierz projekt usługi VSTS w wybranej witrynie, aby połączyć go z projektem usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="ec2f7-197">Domyślne ustawienie w polu **Szablon procesu** to wartość **Zwinne wytwarzanie oprogramowania**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="ec2f7-198">W przypadku szablonu niestandardowego należy zapoznać się ze najlepszymi praktykami podanymi w sekcji [Tworzenie nowego projektu w usłudze Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="ec2f7-199">Następnie kliknij przycisk **Kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-199">Then select **Continue**.</span></span>

    ![Krok 2 w oknie Konfigurowanie usługi Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="ec2f7-201">Przejrzyj ustawienia, a następnie kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-201">Review your settings, and then select **Save**.</span></span>

    ![Krok 3 w oknie Konfigurowanie usługi Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="ec2f7-203">Kliknij przycisk **Autoryzuj**, aby autoryzować dostęp usługi LCS do skonfigurowanej witryny usługi Azure DevOps w swoim imieniu i włączyć funkcje integrowania z usługą VSTS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Przycisk Autoryzuj](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="ec2f7-205">Zostanie wyświetlony następujący komunikat: „Nastąpi przekierowanie do witryny zewnętrznej w celu autoryzacji usługi LCS do nawiązywania połączenia z usługą Visual Studio Team Services w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="ec2f7-206">Kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="ec2f7-206">Proceed?"</span></span> <span data-ttu-id="ec2f7-207">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-207">Select **Yes**.</span></span>

    ![Okno komunikatu](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="ec2f7-209">Wybierz **Akceptuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-209">Select **Accept**.</span></span>

    ![Autoryzowanie dostępu](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="ec2f7-211">Jeśli jesteś autoryzowanym użytkownikiem, w interfejsie użytkownika powinna zostać ponownie wyświetlona strona Ustawienia projektu usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Autoryzowany użytkownik](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="ec2f7-213">Tworzenie nowej biblioteki BPM</span><span class="sxs-lookup"><span data-stu-id="ec2f7-213">Create a new BPM library</span></span>

1. <span data-ttu-id="ec2f7-214">Przejdź do projektu implementacji usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ec2f7-215">Kliknij przycisk **Menu**, a następnie kliknij przycisk **Narzędzie do modelowania procesów biznesowych**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Polecenie Narzędzie do modelowania procesów biznesowych](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="ec2f7-217">Kliknij przycisk **Nowa biblioteka**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-217">Select **New library**.</span></span>

    ![Przycisk Nowa biblioteka](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="ec2f7-219">W polu **Nazwa biblioteki** wprowadź nazwę, a następnie kliknij przycisk **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="ec2f7-220">W tym samouczku nazwij bibliotekę narzędzia BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Okno dialogowe Tworzenie nowej biblioteki](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="ec2f7-222">Otwórz nową bibliotekę narzędzia BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="ec2f7-223">Wybierz proces **Przykładowy podstawowy proces biznesowy**, a następnie kliknij przycisk **Tryb edycji** po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Przycisk Tryb edycji](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="ec2f7-225">Zmień wartość w polach **Nazwa** i **Opis** na **Tworzenie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="ec2f7-226">Następnie kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-226">Then select **Save**.</span></span>

    ![Pola Nazwa i Opis](./media/setup_rsa_tool_24.png)

## <a name="finance-and-operations-environment"></a><span data-ttu-id="ec2f7-228">Środowisko rozwiązania Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec2f7-228">Finance and Operations environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="ec2f7-229">Wymaganie dotyczące wersji</span><span class="sxs-lookup"><span data-stu-id="ec2f7-229">Version requirement</span></span>

<span data-ttu-id="ec2f7-230">Wymagane jest środowisko testowe lub piaskownicy rozwiązania Finance and Operations w wersji 10.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-230">A Finance and Operations test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="ec2f7-231">W przypadku klientów korzystających z wersji 7.3 obsługiwana jest także aktualizacja Platform update 20 lub nowsza.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-232">Narzędzie RSAT musi mieć dostęp do środowiska testowego rozwiązania Finance and Operations za pośrednictwem przeglądarki sieci web.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-232">RSAT must have access to your Finance and Operations test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="ec2f7-233">Kryteria użytkownika</span><span class="sxs-lookup"><span data-stu-id="ec2f7-233">User criteria</span></span>

<span data-ttu-id="ec2f7-234">Użytkownik musi mieć uprawnienia administratora do tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="ec2f7-235">Konfigurowanie ustawień Pomocy w celu nawiązania połączenia z usługą LCS</span><span class="sxs-lookup"><span data-stu-id="ec2f7-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="ec2f7-236">Ten krok jest wymagany w celu nawiązania połączenia z usługi LCS, aby nagrania zadania mogły być zapisywane w odpowiedniej bibliotece narzędzia BPM w usłudze LCS za pośrednictwem klienta rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the Finance and Operations client.</span></span>

1. <span data-ttu-id="ec2f7-237">Otwórz klienta rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-237">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="ec2f7-238">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="ec2f7-239">Na karcie **Pomoc**, w polu **Konfiguracja pomocy usługi Lifecycle Services** wybierz odpowiedni projekt usługi LCS (**RSAT** w tym samouczku).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Pole Konfiguracja pomocy usługi Lifecycle Services na karcie Pomoc](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="ec2f7-241">Biblioteki narzędzia BPM zostaną wypełnione w odpowiednim projekcie usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="ec2f7-242">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-242">Select **Save**.</span></span>
5. <span data-ttu-id="ec2f7-243">W celu wyświetlenia zaktualizowanej zawartości pomocy może być konieczne odświeżenie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Powiadomienie o odświeżeniu przeglądarki](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="ec2f7-245">Nagrania zadania</span><span class="sxs-lookup"><span data-stu-id="ec2f7-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-246">Wszystkie nagrania zadania muszą być rozpoczynane na głównym pulpicie nawigacyjnym rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-246">Make sure that all your task recordings start on the main dashboard of Finance and Operations.</span></span> <span data-ttu-id="ec2f7-247">Poszczególne nagrania powinny być krótkie i dotyczyć konkretnego zadania biznesowego, jak tworzenie zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="ec2f7-248">Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM</span><span class="sxs-lookup"><span data-stu-id="ec2f7-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="ec2f7-249">Utwórz odpowiednie nagranie zadania, które można dołączyć do prostego procesu biznesowego utworzonego w nowej bibliotece narzędzia BPM.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="ec2f7-250">Otwórz klienta rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-250">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="ec2f7-251">Na głównym pulpicie nawigacyjnym kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Rejestrator zadań**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Polecenia w menu Ustawienia](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="ec2f7-253">Kliknij przycisk **Utwórz nagranie**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-253">Select **Create recording**.</span></span>

    ![Przycisk Utwórz nagranie](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="ec2f7-255">Wypełnij pola **Nazwa nagrania** i **Opis nagrania**, a następnie kliknij przycisk **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Pola Nazwa nagrania i Opis nagrania](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="ec2f7-257">Zarejestruj kroki tworzenia produktu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-257">Record the steps for creating a product.</span></span> <span data-ttu-id="ec2f7-258">Po zakończeniu kliknij przycisk **Zatrzymaj**, aby zatrzymać rejestrowanie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Kroki tworzenia produktu](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="ec2f7-260">Kliknij przycisk **Zapisz w usłudze Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-260">Select **Save to Lifecycle Services**.</span></span>

    ![Opcje zapisywania](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="ec2f7-262">Informacje o bibliotece zostaną załadowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-262">Library information is loaded from LCS.</span></span>

    ![Wskaźnik postępu](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="ec2f7-264">Wybierz bibliotekę narzędzia BPM do skojarzenia z nagraniem zadania.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="ec2f7-265">W tym samouczku wybierz bibliotekę **RSAT** narzędzia BPM, która została utworzona wcześniej, oraz należący do niej proces biznesowy **Tworzenie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="ec2f7-266">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-266">Then select **OK**.</span></span>

    ![Kojarzenie nagrania zadania z biblioteką narzędzia BPM i procesem biznesowym](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="ec2f7-268">Zostanie wyświetlony komunikat „Zapisywanie w usłudze Lifecycle Services zakończyło się pomyślnie”.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Komunikat o pomyślnym zapisaniu w usłudze LCS](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="ec2f7-270">Jeśli chcesz zapisać lokalnie nagranie zadania, a następnie przekazać je do narzędzia BPM za pośrednictwem usługi LCS, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="ec2f7-271">Po zakończeniu rejestrowania kliknij przycisk **Zapisz na tym komputerze**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Opcje zapisywania](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="ec2f7-273">Na pasku powiadomień przeglądarki kliknij przycisk **Zapisz** lub **Zapisz jako,** aby zapisać plik na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Pasek powiadomień](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="ec2f7-275">Przejdź do biblioteki **RSAT** narzędzia BPM i wybierz proces biznesowy, którego nagranie zadania ma zostać zapisane.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="ec2f7-276">Na karcie **Przegląd** kliknij przycisk **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Przycisk Przekaż](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="ec2f7-278">Kliknij przycisk **Przeglądaj**, a następnie zaznacz plik axtr, który został wcześniej zapisany.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="ec2f7-279">Następnie kliknij przycisk **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-279">Then select **Upload**.</span></span>

        ![Wybieranie pliku axtr do przekazania](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="ec2f7-281">Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ec2f7-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="ec2f7-282">Po dołączeniu nagrania zadania do procesu biznesowego należy sprawdzić, czy proces biznesowy może być synchronizowany z usługą Azure DevOps jako funkcją, a skojarzone z nim nagranie zadania z przypadkiem testowym przy użyciu funkcji synchronizacji usługi VSTS w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-283">Odpowiedni typ elementu roboczego, który jest tworzony w usłudze Azure DevOps, zależy od szablonu procesu wybranego podczas konfigurowania projektu usługi LCS za pomocą usługi Azure DevOps, zgodnie z opisem w sekcji [Tworzenie nowego projektu usługi Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="ec2f7-284">Przejdź do biblioteki narzędzia BPM i otwórz utworzoną wcześniej bibliotekę **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="ec2f7-285">Kliknij przycisk wielokropka(**...**) i wybierz polecenie **Synchronizacja z usługą VSTS**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Polecenie Synchronizacja z usługą VSTS w menu wielokropka](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="ec2f7-287">Po zakończeniu synchronizacji z usługą VSTGS po lewej stronie zostanie wyświetlona karta **Wymagania**, która zawiera odpowiedni element roboczy usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-288">Prefiksem tytułu elementu roboczego utworzonego w usłudze Azure DevOps będzie nazwa biblioteki narzędzia BPM.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Karta Wymagania](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="ec2f7-290">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-290">Refresh the page.</span></span>
4. <span data-ttu-id="ec2f7-291">Kliknij przycisk wielokropka(**...**). Zostanie wyświetlona dodatkowa opcja, **Synchronizuj przypadki testowe**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="ec2f7-292">Wybierz tę opcję.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-292">Select this option.</span></span>

    ![Polecenie Synchronizuj przypadki testowe w menu wielokropka](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-294">Jeśli po odświeżeniu strony opcja **Synchronizuj przypadki testowe** nie jest dostępna, przejdź do strony głównej narzędzia BPM i kliknij przycisk **Synchronizuj przypadki testowe** na poziomie całej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="ec2f7-295">W ten sposób wymusisz synchronizację całej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![Klikanie przycisku Synchronizuj przypadki testowe na poziomie całej biblioteki](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="ec2f7-297">Po zakończeniu synchronizacji przypadków testowych na karcie **Wymagania** zostanie utworzony nowy przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Nowy przypadek testowy na karcie Wymagania](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="ec2f7-299">Przejdź do projektu usługi Azure DevOps i wybierz opcje **Tablice \> Elementy robocze**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Polecenie Elementy robocze w menu Tablice](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="ec2f7-301">Sprawdź, czy istnieje element roboczy i przypadek testowy utworzony w trakcie synchronizacji narzędzia BPM.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Element roboczy i przypadek testowy](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="ec2f7-303">Instalowanie i konfigurowanie narzędzia RSAT</span><span class="sxs-lookup"><span data-stu-id="ec2f7-303">Install and Configure RSAT</span></span>

<span data-ttu-id="ec2f7-304">Narzędzie RSAT można zainstalować na dowolnym komputerze z systemem Windows 10, na którym można z poziomu przeglądarki internetowej (Internet Explorer lub Google Chrome) otworzyć środowisko rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the Finance and Operations environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-305">Przed zainstalowaniem nowej wersji narzędzia zaleca się odinstalowanie poprzedniej wersji.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="ec2f7-306">Instalowanie certyfikatu uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="ec2f7-306">Install an authentication certificate</span></span>

<span data-ttu-id="ec2f7-307">Aby włączyć uwierzytelnianie, należy wygenerować i zainstalować certyfikat na tym samym komputerze, na którym uruchomione jest narzędzie RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="ec2f7-308">Generowanie certyfikatu</span><span class="sxs-lookup"><span data-stu-id="ec2f7-308">Generate a certificate</span></span>

1. <span data-ttu-id="ec2f7-309">Aby wygenerować plik certyfikatu, otwórz okno środowiska Microsoft Windows PowerShell jako administrator i uruchom następujące polecenie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="ec2f7-310">Otwórz Menedżera certyfikatów, wpisując nazwę **certlm.msc** w oknie dialogowym **Uruchamianie**, i sprawdź, czy certyfikat **D365 Automated testing certificate** został utworzony w sekcji **Osobiste \> Certyfikaty**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-311">Uważaj, aby wpisać **certlm.msc**, a nie **certmgr.msc**, ponieważ certyfikaty są przechowywane na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![Certyfikat D365 Automated testing certificate](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="ec2f7-313">Kliknij prawym przyciskiem myszy certyfikat, a następnie wybierz polecenie **Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="ec2f7-314">Wybierz kolejno opcje **Zaufane główne urzędy certyfikacji \> Certyfikaty**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Folder Certyfikaty w folderze Zaufane główne urzędy certyfikacji](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="ec2f7-316">W menu **Akcja** wybierz polecenie **wklej**, aby skopiować certyfikat do lokalizacji **Zaufane główne urzędy certyfikacji**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Polecenie Wklej w menu Akcja](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="ec2f7-318">Aby uzyskać odcisk palca zainstalowanego certyfikatu, ale bez spacji i znaków specjalnych, otwórz okno środowiska Windows PowerShell jako administrator i uruchom następujące polecenia.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="ec2f7-319">Zapisz odcisk palca, ponieważ będzie on potrzebny później, gdy zaktualizujesz pliki.WIF dla serwera obiektów aplikacji (AOS) i skonfigurujesz narzędzie RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="ec2f7-320">Konfigurowanie zaufanego połączenia na komputerze AOS</span><span class="sxs-lookup"><span data-stu-id="ec2f7-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="ec2f7-321">Jeśli środowisko rozwiązania Finance and Operations jest środowiskiem warstwy 2 lub wyższej, odcisk palca certyfikatu musi zostać zaktualizowany w pliku wif.config dla **wszystkich** komputerów AOS środowiska.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-321">If the Finance and Operations environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="ec2f7-322">Ustanów połączenie protokołu RDP (Remote Desktop Protocol) z komputerem AOS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="ec2f7-323">Szczegóły logowania są dostępne na stronie szczegółów środowiska w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="ec2f7-324">Otwórz program Microsoft Internet Information Services (IIS) i znajdź pozycję **AOSService** na liście witryn.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService na liście witryn](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="ec2f7-326">Kliknij prawym przyciskiem myszy polecenie **Eksploruj**,aby otworzyć folder **\<dysk\>: \\AosService\\Webroot**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="ec2f7-327">Znajdź plik **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-327">Find the **wif.config** file.</span></span>

    ![Plik Wif.config w folderze WebRoot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="ec2f7-329">Zaktualizuj plik **wif.config**, dodając nowy wpis urzędu dla swojego certyfikatu i nazwę urzędu tak jak w następującym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="ec2f7-330">Jeśli wielu użytkowników korzysta z tej samej aplikacji rozwiązania Finance and Operations, każdy użytkownik musi wygenerować własny odcisk palca, a każdy z tych odcisków palców musi zostać dodany w sekcji **\<keys\>**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-330">If multiple users are using the same Finance and Operations application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="ec2f7-331">Jeśli jest więcej niż jeden komputer AOS, wykonaj kroki od 3 do 4 z każdym dodatkowym komputerem.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-332">W przeciwieństwie do starszych środowisk warstwy 2 nowe środowiska warstwy 2 są wdrażane z dwoma wystąpieniami serwera AOS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="ec2f7-333">Uruchom polecenie **iisreset** na wszystkich komputerach AOS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-334">Jeśli nie masz uprawnień administratora do uruchamiania polecenia **iisreset** na komputerze warstwy 1, na stronie Szczegóły środowiska w usłudze LCS wybierz opcję Zarządzaj > Uruchom ponownie usługi.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="ec2f7-335">Środowisko warstwy 2 lub wyższej</span><span class="sxs-lookup"><span data-stu-id="ec2f7-335">Tier 2+ environment</span></span>

<span data-ttu-id="ec2f7-336">Jeśli jest używane środowisko rozwiązania Finance and Operations warstwy 2 lub wyższej (piaskownica testowania akceptacji wersji Standard lub wyższa warstwa), potwierdź lub wprowadź następujące ustawienie rejestru na komputerze, na którym jest zainstalowane narzędzie RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) Finance and Operations environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="ec2f7-337">Ten krok jest wymagany, ponieważ może pozwolić uniknąć błędów związanych z uwierzytelnianiem lub z połączeniem z narzędziem RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="ec2f7-338">Instalowanie narzędzia RSAT</span><span class="sxs-lookup"><span data-stu-id="ec2f7-338">Install RSAT</span></span>

1. <span data-ttu-id="ec2f7-339">Przejdź do strony <https://www.microsoft.com/download/details.aspx?id=57357> i kliknij przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="ec2f7-340">Zaznacz wszystkie pliki, a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-340">Select all the files, and then select **Next**.</span></span>

    ![Zaznaczanie wszystkich plików](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="ec2f7-342">Kliknij dwukrotnie pakiet MSI, aby uruchomić instalatora.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="ec2f7-343">Następnie, po zakończeniu instalacji, kliknij przycisk **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![Plik instalatora narzędzia RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="ec2f7-345">Instalowanie sterownika Selenium i sterowników przeglądarki</span><span class="sxs-lookup"><span data-stu-id="ec2f7-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="ec2f7-346">W starszych wersjach narzędzia RSAT konieczne było instalowanie sterownika Selenium i sterowników przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="ec2f7-347">Instalowanie tych sterowników nie jest konieczne, ponieważ są one instalowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="ec2f7-348">Podczas uruchamiania narzędzia RSAT po raz pierwszy system wyświetli monit o automatyczne pobranie i zainstalowanie sterownika Selenium.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="ec2f7-349">Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie narzędzia RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="ec2f7-350">Przed uruchomieniem przypadku testowego wyświetlany jest monit o automatyczne pobranie i zainstalowanie sterownika przeglądarki do domyślnej przeglądarki, która została wybrana w konfiguracji narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="ec2f7-351">Aby uzyskać więcej informacji, zobacz sekcję [Ładowanie i uruchamianie przypadków testowych](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="ec2f7-352">Rozpoczęcie korzystania z narzędzia RSAT</span><span class="sxs-lookup"><span data-stu-id="ec2f7-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="ec2f7-353">Tworzenie planu testów i pakietów testów</span><span class="sxs-lookup"><span data-stu-id="ec2f7-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="ec2f7-354">Przejdź do projektu usługi Azure DevOps i wybierz polecenie **Plany testów**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Polecenie Plany testów](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="ec2f7-356">Kliknij przycisk **Nowy plan testów**</span><span class="sxs-lookup"><span data-stu-id="ec2f7-356">Select **New Test Plan**.</span></span>

    ![Przycisk Nowy plan testów](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="ec2f7-358">Wypełnij pole **Nazwa**, a następnie kliknij przycisk **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="ec2f7-359">Nazwa planu testów w tym samouczku to **Plan testów RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Okno dialogowe Nowy plan testów](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="ec2f7-361">Kliknij znak plus (**+**), a następnie kliknij przycisk **Pakiet statyczny**, aby utworzyć pakiet statyczny w ramach nowego planu testów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="ec2f7-362">Nazwij nowy pakiet testów **T01 – Produkcja na magazyn**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-363">Możesz również utworzyć pakiet oparty na kwerendach, jeśli nowe przypadki testowe z narzędzia BPM mają być automatycznie wciągane do pakietu testów narzędzia RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Tworzenie pakietu statycznego](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="ec2f7-365">Dołączanie przypadków testowych do pakietu testów</span><span class="sxs-lookup"><span data-stu-id="ec2f7-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="ec2f7-366">Kliknij przycisk **Dodaj istniejące** po prawej stronie, aby dodać istniejące przypadki testowe do pakietu testów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Przycisk Dodaj istniejące](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="ec2f7-368">Na stronie **Dodawanie przypadków testowych do pakietu** kliknij przycisk **Uruchom kwerendę**, a następnie wybierz przypadek testowy, który ma zostać dodany do pakietu testów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="ec2f7-369">W tym samouczku wybierz przypadek testowy **Tworzenie nowego produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="ec2f7-370">Następnie kliknij przycisk **Dodaj przypadki testowe** w prawym dolnym rogu strony (ten przycisk nie jest widoczny na ilustracji)</span><span class="sxs-lookup"><span data-stu-id="ec2f7-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Przycisk Uruchom kwerendę](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="ec2f7-372">Przypadek testowy zostanie dodany do pakietu testów **T01- Produkcja na magazyn**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Przypadek testowy dodany do pakietu testów](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="ec2f7-374">Konfiguruj usługę RSAT</span><span class="sxs-lookup"><span data-stu-id="ec2f7-374">Configure RSAT</span></span>

1. <span data-ttu-id="ec2f7-375">Otwórz narzędzie RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-375">Open RSAT.</span></span>

    ![Ikona RSAT](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="ec2f7-377">Zostanie wyświetlony komunikat ostrzegawczy „Regression Suite Automation Tool wymaga sterownika Selenium. Czy chcesz go automatycznie pobrać i zainstalować?”</span><span class="sxs-lookup"><span data-stu-id="ec2f7-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="ec2f7-378">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-378">Select **Yes**.</span></span>

    ![Komunikat ostrzegawczy](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="ec2f7-380">Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu, a następnie w wyświetlonym oknie dialogowym wypełnij następujące pola:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="ec2f7-381">**Adres URL usługi Azure DevOps** — wprowadź adres URL projektu usługi Azure DevOps, jak `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="ec2f7-382">**Token dostępu** — wprowadź token dostępu, na mocy którego narzędzie łączy się z usługą Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="ec2f7-383">Użyj osobistego tokenu dostępu utworzonego wcześniej w tym samouczku.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="ec2f7-384">Aby uzyskać więcej informacji, zobacz sekcję [Uwierzytelnianie dostępu za pomocą osobistych tokenów dostępu](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="ec2f7-385">**Nazwa projektu** — wybierz nazwę danego projektu usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="ec2f7-386">**Plan testów** — wybierz plan testów usługi Azure DevOps, który zawiera przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="ec2f7-387">Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie planu testów i pakietów testów](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="ec2f7-388">Po wybraniu planu testów kliknij przycisk **Testuj połączenie**, aby przetestować połączenie z usługą Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="ec2f7-389">**Nazwa hosta** — wprowadź nazwę hosta środowiska rozwiązania Finance and Operations, np. **\<myaos\>. cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-389">**Hostname** – Enter the host name of the Finance and Operations test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="ec2f7-390">Nie należy dodawać prefiksu **https://** ani **http://**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="ec2f7-391">**Nazwa hosta SOAP** — wprowadź nazwę hosta SOAP środowiska testowego rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-391">**SOAP Hostname** – Enter the SOAP host name of the Finance and Operations test environment.</span></span> <span data-ttu-id="ec2f7-392">Zazwyczaj nazwa hosta SOAP jest taka sama jak nazwa hosta, ale ma sufiks **soap**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="ec2f7-393">Oto przykład: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="ec2f7-394">Nie należy dodawać prefiksu **https://** ani **http://**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ec2f7-395">Aby znaleźć nazwę hosta i nazwę hosta SOAP, otwórz Menedżera IIS, kliknij prawym przyciskiem myszy pozycję **Witryny \> AOSService**, a następnie wybierz polecenie **Edytuj powiązania**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="ec2f7-396">Wartości w kolumnie **Nazwa hosta** zawierają nazwę hosta i nazwę hosta SOAP (nazwa hosta SOAP ma sufiks **SOAP** w adresie URL).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Nazwa hosta i nazwa hosta SOAP w kolumnie Nazwa hosta](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="ec2f7-398">**Nazwa użytkownika administratora** — wprowadź adres e-mail użytkownika administratora w środowisku testowym rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-398">**Admin user name** – Enter the email address of an admin user in the Finance and Operations test environment.</span></span>
    - <span data-ttu-id="ec2f7-399">**Odcisk palca** — wprowadź odcisk palca certyfikatu uwierzytelniania, jak opisano wcześniej w tym samouczku.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="ec2f7-400">**Katalog roboczy** — określ lokalizację folderu przechowywania plików automatyzacji testów, takich jak pliki danych testowych programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="ec2f7-401">Na przykład wprowadź lub wybierz katalog **C:\\Temp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ec2f7-402">Jeśli nazwa folderu zawiera spacje, wykonanie nie powiedzie się z powodu nieznalezienia folderu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="ec2f7-403">Ten błąd jest znany i powinien zostać naprawiony w najnowszej wersji narzędzia.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="ec2f7-404">**Domyślna przeglądarka** — wybierz opcję **Internet Explorer** lub **Google Chrome**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="ec2f7-405">Upewnij się, że zostały zainstalowane odpowiednie sterowniki przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="ec2f7-406">**Limit czasu przebiegu testowego** — określ limit czasu trwania (w minutach) przebiegów testowych.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="ec2f7-407">Po upływie limitu czasu wszystkie aktywne okna są zamykane i oczekujące przypadki testowe kończą się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="ec2f7-408">**Limit czasu akcji testowej** — to pole określa limit czasu (w minutach) żądań serwera środowiska operacyjnego rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="ec2f7-409">Zazwyczaj wartość domyślna (2 minuty) powinna być wystarczająca.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="ec2f7-410">Jednak w przypadku wolniejszych środowisk można zwiększyć wartość, jeśli występują błędy związane z przekroczeniem limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="ec2f7-411">**Nazwa firmy** — wprowadź nazwę firmy używanej jako domyślna firma rozwiązania Finance and Operations podczas tworzenia plików parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-411">**Company name** – Enter the company name to use as your default Finance and Operations company when Excel parameter files are created.</span></span> <span data-ttu-id="ec2f7-412">Firmę można później zmienić, edytując plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Okno dialogowe Ustawienia](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="ec2f7-414">Kliknij przycisk **Zastosuj**, aby zastosować i zapisać ustawienia.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="ec2f7-415">Aby zapisać bieżące ustawienia w pliku konfiguracji na komputerze, kliknij przycisk **Zapisz jako**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="ec2f7-416">Aby przywrócić ustawienia z pliku konfiguracji na komputerze, kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="ec2f7-417">Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="ec2f7-418">Ładowanie i uruchamianie przypadków testowych</span><span class="sxs-lookup"><span data-stu-id="ec2f7-418">Load and run test cases</span></span>

1. <span data-ttu-id="ec2f7-419">Kliknij przycisk **Załaduj**, aby załadować **Plan testów narzędzia RSAT** z projektu usługi Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ec2f7-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Przycisk Załaduj](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="ec2f7-421">Wybierz przypadek testowy **Tworzenie nowego produktu** z pakietu testów, a następnie wybierz opcje **Nowy \> Generuj pliki wykonania testu i parametrów**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Polecenie Generuj pliki wykonania testu i parametrów w menu Nowy](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="ec2f7-423">Plik parametrów programu Excel zostanie utworzony w folderze lokalnym określonym w konfiguracji narzędzia RSAT (na przykład **C:\\temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Utworzony plik parametrów programu Excel](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="ec2f7-425">Jeśli chcesz zapisać pliki parametrów, kliknij przycisk **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="ec2f7-426">Pliki automatyzacji testów wszystkich wybranych przypadków testowych zostaną przekazane do usługi Azure DevOps do ewentualnego użycia w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="ec2f7-427">(Te pliki zawierają pliki parametrów testowych programu Excel)</span><span class="sxs-lookup"><span data-stu-id="ec2f7-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="ec2f7-428">W ten sposób można kliknąć przycisk **Załaduj**, aby załadować pliki parametrów (i pliki automatyzacji) z przypadku testowego bezpośrednio z usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="ec2f7-429">Nie ma konieczności ponownego generowania plików parametrów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="ec2f7-430">Ta metoda będzie przydatna w przyszłości, jeśli chcesz zachowywać modyfikacje w pliku parametrów i nie chcesz, aby były one zastępowane.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="ec2f7-431">Aby sprawdzić, czy pliki automatyzacji i pliki parametrów są zapisane w usłudze Azure DevOps, przejdź do projektu usługi Azure DevOps, wybierz opcje **Tablice \> Elementy robocze** i wybierz przypadek testowy **Tworzenie nowego produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="ec2f7-432">Na karcie **Załączniki** powinny być widoczne cztery pliki:</span><span class="sxs-lookup"><span data-stu-id="ec2f7-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="ec2f7-433">**.cs** — plik automatyzacji C\#</span><span class="sxs-lookup"><span data-stu-id="ec2f7-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="ec2f7-434">**.dll** — skompilowany plik automatyzacji jako zestaw</span><span class="sxs-lookup"><span data-stu-id="ec2f7-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="ec2f7-435">**.xlsx** — plik parametrów programu Excel</span><span class="sxs-lookup"><span data-stu-id="ec2f7-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="ec2f7-436">**.xml** – plik nagrania</span><span class="sxs-lookup"><span data-stu-id="ec2f7-436">**.xml** – Recording file</span></span>

    ![Pliki na karcie Załączniki](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="ec2f7-438">Wybierz przypadek testowy, który ma zostać uruchomiony, a następnie kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-439">W przypadku korzystania z przeglądarki Internet Explorer przed uruchomieniem przypadków testowych należy upewnić się, że jako rozdzielczość pulpitu wybrano wartość **100%** w sekcji **Ustawienia ekranu systemu Windows \> Skala i układ**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="ec2f7-440">Jeśli nie możesz zmienić tego ustawienia na maszynie wirtualnej (VM), zmień ją na kliencie (laptopie), z którego próbujesz uzyskać dostęp do maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="ec2f7-441">Ustawienia rozdzielczości zostaną wówczas odziedziczone przez ustawienia ekranu maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Ustawienie 100% rozdzielczości pulpitu](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="ec2f7-443">Jeśli sterowniki przeglądarki nie są zainstalowane w systemie, zostanie wyświetlony komunikat ostrzegawczy „Ta operacja wymaga sterownika \<nazwa przeglądarki\>.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="ec2f7-444">Czy chcesz automatycznie pobrać i zainstalować go teraz?”</span><span class="sxs-lookup"><span data-stu-id="ec2f7-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="ec2f7-445">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-445">Select **Yes**.</span></span>

    ![Komunikat ostrzegawczy dotyczący programu Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Komunikat ostrzegawczy dotyczący programu Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-448">Jeśli korzystasz z przeglądarki Chrome i zostanie wyświetlony komunikat o błędzie informujący o nieutworzeniu sesji z powodu niepoprawnej wersji programu Chrome, pobierz najnowszy sterownik programu Chrome ze strony <http://chromedriver.chromium.org/downloads> do folderu **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Komunikat o błędzie dotyczący programu Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="ec2f7-450">Przypadek testowy zostanie uruchomiony, a pole **Wynik** zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Wskaźnik postępu](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="ec2f7-452">Jeśli postępujesz dokładnie według tego samouczka, przypadek testowy **Tworzenie nowego produktu** nie powiedzie się, ponieważ w nagraniu zadania tworzenia produktu nazwa produktu została zapisana jako wartość niezmienna.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="ec2f7-453">Jeśli ten sam przypadek testowy zostanie ponownie uruchomiony, powinien zostać wyświetlony komunikat o błędzie, ponieważ produkt już istnieje.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Pole Wynik z ustawieniem Niepowodzenie](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="ec2f7-455">Wyświetlanie wyników testu</span><span class="sxs-lookup"><span data-stu-id="ec2f7-455">View the test results</span></span>

1. <span data-ttu-id="ec2f7-456">Kliknij dwukrotnie przypadek testowy zakończony niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="ec2f7-457">Zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-457">You receive an error message.</span></span>

    ![Komunikat o błędzie](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="ec2f7-459">Kliknij przycisk **Szczegóły**, aby wyświetlić cały komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-459">Select **Details** to view the whole error message.</span></span>

    ![Cały komunikat o błędzie](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="ec2f7-461">Aby wyświetlić szczegółową wersję komunikatu o błędzie w usłudze Azure DevOps, kliknij przycisk **Otwórz w usłudze Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="ec2f7-462">W usłudze Azure DevOps można wyświetlić stan przypadku testowego i szczegółowy komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Szczegółowy komunikat o błędzie w usłudze Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="ec2f7-464">Aby wyświetlić wyniki testów bezpośrednio w projekcie usługi Azure DevOps, wybierz kolejno opcje do **Plany testów \> Plany testów \> Przebiegi**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="ec2f7-465">Kliknij dwukrotnie przebieg testowy, o którym chcesz wyświetlić więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-465">Double-click the test run that you want to see more details for.</span></span>

    ![Lista przebiegów testowych w usłudze Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="ec2f7-467">Na karcie **Podsumowanie przebiegu** jest wskazane niepowodzenie przypadku testowego, ale nie jest wyświetlany sam komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="ec2f7-468">Aby wyświetlić szczegółowy komunikat o błędzie, kliknij kartę **Wyniki testów**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Karta Podsumowanie przebiegu](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="ec2f7-470">Karta **Wyniki testów** zawiera informacje o przypadku testowym wraz z wynikami i komunikatem o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Karta Wyniki testów](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="ec2f7-472">Kliknij dwukrotnie odpowiedni rekord, aby wyświetlić szczegółowy komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Szczegółowy komunikat o błędzie](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-474">Wszystkie komunikaty o błędzie są również dostępne lokalnie w folderze **C:\\Users\\\$Twoja_nazwa_użytkownika\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="ec2f7-475">Wyniki przebiegu testowego można również wyeksportować z poziomu planu testów, klikając przycisk **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Eksportowanie planu testów](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="ec2f7-477">Modyfikowanie pliku parametrów programu Excel</span><span class="sxs-lookup"><span data-stu-id="ec2f7-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="ec2f7-478">Otwórz narzędzie RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-478">Open RSAT.</span></span>
2. <span data-ttu-id="ec2f7-479">Wybierz przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="ec2f7-480">W arkuszu **EcoResProductCreate** jest widoczne, że wartość pola **Numer produktu** jest niezmienna.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="ec2f7-481">Musisz wprowadzić w tym polu nową nazwę produktu, aby można było ponownie uruchomić przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="ec2f7-482">Aby podczas każdego uruchomienia był generowany unikatowy numer produktu bez konieczności ponownego otwierania pliku parametrów programu Excel i ręcznego zmieniania numeru produktu za każdym razem, należy wprowadzić następującą formułę programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="ec2f7-483">Oprócz karty **Ogólne** plik parametrów programu Excel zawiera kartę Dane dla każdej strony formularza rozwiązania Finance and Operations, która jest odwiedzana przez przypadek testowy.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every Finance and Operations form page the test case visits.</span></span>

    ![Pole Numer produktu](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="ec2f7-485">Kliknij przycisk **Zapisz**, a następnie zamknij skoroszyt programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="ec2f7-486">Kliknij przycisk **Przekaż**, aby zapisać plik parametrów programu Excel w usłudze Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Komunikat o przekazaniu pliku](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-488">Aby uruchomić przypadki testowe w określonym kontekście użytkownika, należy wprowadzić identyfikator e-mail użytkownika w polu **Użytkownik testowy** na karcie **Ogólne** pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="ec2f7-489">W najnowszej wersji narzędzia RSAT zmieniono układ pól w pliku parametrów programu Excel, ale ogólna zasada pozostała taka sama.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Pole Użytkownik testowy](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="ec2f7-491">Sprawdzanie poprawności wyników</span><span class="sxs-lookup"><span data-stu-id="ec2f7-491">Validate the results</span></span>

- <span data-ttu-id="ec2f7-492">Kliknij przycisk **Uruchom**, aby ponownie uruchomić przypadek testowy i sprawdź, czy przypadek testowy został zaliczony.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="ec2f7-493">Wyniki testów można wyświetlać w sposób opisany w sekcji [Wyświetlanie wyników testów](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Pole Wynik z ustawieniem Powodzenie](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="ec2f7-495">Łączenie przypadków testowych w łańcuchy</span><span class="sxs-lookup"><span data-stu-id="ec2f7-495">Chaining of test cases</span></span>

<span data-ttu-id="ec2f7-496">Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania wartości do innych testów).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="ec2f7-497">Przypadki testowe są uruchamiane w kolejności określonej w planie testów usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="ec2f7-498">(Ta kolejność może również zostać zaktualizowana w samym narzędziu testowym). Dlatego, jeśli zmienne mają być przekazywane z jednego przypadku testowego do innego, bardzo ważne jest, aby testy były wykonywane we właściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="ec2f7-499">W tej sekcji utworzysz zapisaną zmienną w pierwszym przypadku testowym, utworzysz drugi przypadek testowy i przekażesz zapisaną zmienną z pierwszego przypadku testowego do drugiego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="ec2f7-500">Następnie uruchomisz przypadki testowe jako łańcuch przypadków testowych w narzędziu RSAT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="ec2f7-501">Modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej</span><span class="sxs-lookup"><span data-stu-id="ec2f7-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="ec2f7-502">Otwórz klienta rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-502">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="ec2f7-503">Kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Rejestrator zadań**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="ec2f7-504">Kliknij przycisk **Edytuj nagranie**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-504">Select **Edit Recording**.</span></span>

    ![Przycisk Edytuj nagranie](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="ec2f7-506">Kliknij przycisk **Otwórz z usługi Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-506">Select **Open from Lifecycle Services**.</span></span>

    ![Przycisk Otwórz z usługi Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="ec2f7-508">Kliknij przycisk **Wybierz bibliotekę usługi Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Przycisk Wybierz bibliotekę usługi Lifecycle Services](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="ec2f7-510">Biblioteki narzędzia BPM zostaną załadowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-510">BPM libraries are loaded from LCS.</span></span>

    ![Wskaźnik postępu](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="ec2f7-512">Po załadowaniu bibliotek narzędzia BPM z usługi LCS wybierz bibliotekę narzędzia BPM **RSAT** i proces biznesowy **Tworzenie nowego produktu**, z którym skojarzono to nagranie zadania.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="ec2f7-513">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-513">Then select **OK**.</span></span>

    ![Wybieranie biblioteki BPM i procesu biznesowego](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="ec2f7-515">Nazwa odpowiedniego nagrania zadania jest wprowadzana w polu **Nazwa nagrania**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="ec2f7-516">Kliknij przycisk **Rozpocznij**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-516">Select **Start**.</span></span>

    ![Pole nagrania zadania w polu Nazwa nagrania](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="ec2f7-518">Wybierz opcje **Zarządzanie informacjami o produktach \> Produkty** i kliknij przycisk **Nowy**, aby otworzyć stronę, na której zarejestrowano oryginalne nagranie zadania **Tworzenie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="ec2f7-519">Kliknij przycisk **Wstaw krok**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-520">Nowy krok zostanie wstawiony **po** kroku wybranym w okienku.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Przycisk Wstaw krok](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="ec2f7-522">Kliknij prawym przyciskiem myszy pole **Numer produktu**, a następnie wybierz opcje **Rejestrator zadań \> Kopiuj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Polecenie Kopiuj](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="ec2f7-524">W okienku zostanie dodany nowy krok.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-524">A new step is added in the pane.</span></span> <span data-ttu-id="ec2f7-525">Zanotuj wartość w polu **Numer produktu**, ponieważ będzie ona potrzebna później.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Dodany nowy krok](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="ec2f7-527">Kliknij przycisk **Zakończono edycję**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="ec2f7-528">Kliknij przycisk **Zapisz w usłudze Lifecycle Services** i skojarz nowe nagranie zadania z tą samą biblioteką narzędzia BPM i procesem biznesowym, z którymi było skojarzone oryginalne nagranie zadania.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="ec2f7-529">Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="ec2f7-530">Przejdź do biblioteki narzędzia BPM i kliknij przycisk **Synchronizuj przypadki testowe**, aby zastąpić nagranie zadania dołączone do przypadku testowego w usłudze Azure DevOps, zgodnie z opisem w sekcji [Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="ec2f7-531">Otwórz narzędzie RSAT i kliknij przycisk **Załaduj**, aby ponownie załadować przypadki testowe z pakietu testów.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="ec2f7-532">Musisz ponownie wygenerować pliki automatyzacji i parametrów odpowiedniego przypadku testowego, wybierając przypadek testowy, a następnie wybierając opcje **Nowy \> Generuj pliki wykonania testu i parametrów** zgodnie z opisem w sekcji [Ładowanie i uruchamianie przypadków testowych](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-533">Jeśli pozostawiono otwarty plik parametrów programu Excel, ponowne generowanie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="ec2f7-534">Dlatego należy pamiętać o zamknięciu pliku parametrów programu Excel przypadku testowego przed generowaniem nowego pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="ec2f7-535">Kliknij przycisk **Edytuj**, aby otworzyć nowy plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="ec2f7-536">W wierszu 9 zostanie wyświetlony nowy wpis **Zapisana zmienna**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="ec2f7-537">Ta zmienna, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, jest zapisywana w pliku XML nagrania zadania i może być używana w kolejnych testach.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Wpis zapisanej zmiennej](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="ec2f7-539">Tworzenie nowego przypadku testowego</span><span class="sxs-lookup"><span data-stu-id="ec2f7-539">Create a new test case</span></span>

1. <span data-ttu-id="ec2f7-540">Przejdź do biblioteki narzędzia BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="ec2f7-541">Wybierz proces **Przykładowy pomocniczy proces biznesowy**, a następnie kliknij przycisk **Tryb edycji** po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="ec2f7-542">Zmień wartość w polach **Nazwa** i **Opis** na **Wydanie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="ec2f7-543">Następnie kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-543">Then select **Save**.</span></span>

    ![Nazwa i opis zostały zmienione na Wydanie produktu](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="ec2f7-545">Tworzenie nowego nagrania zadania z funkcją sprawdzania poprawności</span><span class="sxs-lookup"><span data-stu-id="ec2f7-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="ec2f7-546">Utwórz nagranie zadania, aby wydać utworzony wcześniej produkt firmie USRT.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="ec2f7-547">Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec2f7-548">W przypadku przypadków testowych połączonych w łańcuch zawsze zaleca się znalezienie lub przefiltrowanie wymaganego rekordu przez *ręczne wpisanie wartości pola*.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="ec2f7-549">W ten sposób narzędzie może określić rekord, na którym ma zostać wykonana akcja w kolejnym przypadku testowym.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Nowe nagranie zadania z funkcją sprawdzania poprawności](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="ec2f7-551">Jak widać na poprzedniej ilustracji, gdy produkt zostanie znaleziony przy użyciu szybkiego filtra, ale przed wybraniem polecenia **Wydaj produkty**, sprawdzasz wartość pola **Numer produktu**, aby upewnić się, że identyfikator produktu jest tym samym identyfikatorem produktu, który został utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="ec2f7-552">Aby sprawdzić poprawność wartości, kliknij prawym przyciskiem myszy pole **Numer produktu**, a następnie wybierz kolejno opcje **Rejestrator zadań \> Sprawdź poprawność \> Bieżąca wartość**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Sprawdzanie poprawności bieżącej wartości](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="ec2f7-554">Zapisywanie nagrania zadania w narzędziu BPM</span><span class="sxs-lookup"><span data-stu-id="ec2f7-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="ec2f7-555">Po zakończeniu rejestrowania zadania kliknij przycisk **Zapisz w usłudze Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Opcje zapisywania](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="ec2f7-557">Informacje o bibliotece zostaną załadowane z usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-557">Library information is loaded from LCS.</span></span>

    ![Wskaźnik postępu](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="ec2f7-559">Wybierz bibliotekę narzędzia BPM do skojarzenia z nagraniem zadania.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="ec2f7-560">W tym samouczku wybierz bibliotekę **RSAT** narzędzia BPM, która została utworzona wcześniej, oraz należący do niej proces biznesowy **Wydanie produktu**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="ec2f7-561">Następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="ec2f7-562">Synchronizuj narzędzie BPM z usługą Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ec2f7-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="ec2f7-563">Przejdź do biblioteki narzędzia BPM i otwórz bibliotekę **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="ec2f7-564">Kliknij przycisk **Synchronizacja z usługą VSTS**, a następnie **Synchronizuj przypadki testowe**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="ec2f7-565">Aby uzyskać więcej informacji, zobacz sekcję [Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="ec2f7-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="ec2f7-566">Po zakończeniu synchronizacji nowy element roboczy i odpowiedni przypadek testowy procesu biznesowego **Wydanie produktu** zostanie wyświetlony w sekcji **Tablice \> Elementy robocze** usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="ec2f7-567">Dodawanie nowego przypadku testowego do istniejącego pakietu testów</span><span class="sxs-lookup"><span data-stu-id="ec2f7-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="ec2f7-568">Wybierz opcje **Plany testów \> Plany testów** i wybierz plan **Plan testów RSAT**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="ec2f7-569">Kliknij przycisk **Dodaj istniejące**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="ec2f7-570">Na stronie **Dodawanie przypadków testowych do pakietu** kliknij przycisk **Uruchom kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="ec2f7-571">Wybierz nowy przypadek testowy, który został utworzony dla procesu **Wydanie produktu**, a następnie kliknij przycisk opcję **Dodaj przypadki testowe** w prawym dolnym rogu strony (ten przycisk nie jest widoczny na ilustracji)</span><span class="sxs-lookup"><span data-stu-id="ec2f7-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Strona Dodawanie przypadków testowy do pakietu](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="ec2f7-573">Pakiet testów zawiera teraz dwa przypadki testowe.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-573">The test suite now has two test cases.</span></span>

    ![Dwa przypadki testowe w pakiecie testów](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="ec2f7-575">Ładowanie przypadków testowych do narzędzia RSAT</span><span class="sxs-lookup"><span data-stu-id="ec2f7-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="ec2f7-576">Otwórz narzędzie RSAT i kliknij przycisk **Załaduj**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="ec2f7-577">Przypadki testowe zostaną załadowane i zostanie wyświetlone ostrzeżenie „Ta akcja spowoduje zastąpienie plików danych testowych programu Excel, zmiany lokalne zostaną utracone.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="ec2f7-578">Czy chcesz kontynuować?”</span><span class="sxs-lookup"><span data-stu-id="ec2f7-578">Do you want to proceed?"</span></span> <span data-ttu-id="ec2f7-579">Kliknij przycisk **Tak**, aby zaktualizować pliki parametrów programu Excel w systemie lokalnym, ale nie pliki parametrów programu Excel, które zostały przekazane do usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Komunikat ostrzegawczy](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="ec2f7-581">Oba przypadki testowe zostaną załadowane wraz z plikiem parametrów programu Excel pierwszego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="ec2f7-582">Z powodu kliknięcia w ostatnim przebiegu przycisku **Przekaż** pliki parametrów są ściągane z usługi Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Przypadki testowe załadowane](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="ec2f7-584">Wybierz tylko drugi przypadek testowy, a następnie wybierz opcje **Nowy \> Generuj pliki wykonania testu i parametrów**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="ec2f7-585">Edytowanie pliku parametrów programu Excel</span><span class="sxs-lookup"><span data-stu-id="ec2f7-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="ec2f7-586">Wybierz tylko drugi przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć odpowiedni plik parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="ec2f7-587">Skopiuj zapisaną zmienną **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (zobacz sekcję the [Modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej](#modify-an-existing-task-recording-to-create-a-saved-variable)) z pierwszego przypadku testowego do wszystkich pól, w których jest używany numer produktu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="ec2f7-588">W tej sytuacji należy skopiować zmienną do pól **Numer produktu** i **Sprawdź poprawność numeru produktu** na arkuszu **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Pola Numer produktu i Sprawdź poprawność numeru produktu](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="ec2f7-590">Zmienne mogą być przekazywane między testami tylko podczas tego samego przebiegu testu.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="ec2f7-591">Nazwy zmiennych muszą być dokładnie takie same.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="ec2f7-592">Kliknij przycisk **Zapisz**, a następnie zamknij skoroszyt programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="ec2f7-593">Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="ec2f7-594">Uruchamianie połączonych w łańcuch przypadków testowych</span><span class="sxs-lookup"><span data-stu-id="ec2f7-594">Run the chained test cases</span></span>

1. <span data-ttu-id="ec2f7-595">Wybierz oba przypadki testowe, a następnie kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="ec2f7-596">Sprawdź, czy oba przypadki testowe zostały zaliczone.</span><span class="sxs-lookup"><span data-stu-id="ec2f7-596">Verify that both test cases have passed.</span></span>

    ![Pole Wynik z ustawieniem Powodzenie obu przypadków testowych](./media/setup_rsa_tool_105.png)
