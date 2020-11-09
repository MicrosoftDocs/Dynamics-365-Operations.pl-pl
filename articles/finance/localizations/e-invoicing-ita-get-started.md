---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Włoch
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Włoch w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c513141f820c95fe3842478361693701f1e3641b
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039799"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="25c60-103">Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Włoch</span><span class="sxs-lookup"><span data-stu-id="25c60-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="25c60-104">Dodatek Faktury elektroniczne dla Włoch może obecnie nie obsługiwać wszystkich funkcji dostępnych dla faktur elektronicznych w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="25c60-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="25c60-105">Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne dla Włoch.</span><span class="sxs-lookup"><span data-stu-id="25c60-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="25c60-106">Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Services (RCS) i Finance.</span><span class="sxs-lookup"><span data-stu-id="25c60-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="25c60-107">Prowadzi również użytkownika przez proces przesyłania faktur elektronicznych, które są generowane za pośrednictwem usługi w formacie **FatturaPA** specyficznym dla Włoch, oraz wyjaśnia, jak przeglądać wyniki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="25c60-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25c60-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="25c60-108">Prerequisites</span></span>

<span data-ttu-id="25c60-109">Przed wykonaniem kroków opisanych w tym temacie należy wykonać kroki opisane w temacie [Rozpoczynanie pracy z dodatkiem Faktury elektroniczne](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="25c60-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="25c60-110">Konfiguracja RCS</span><span class="sxs-lookup"><span data-stu-id="25c60-110">RCS setup</span></span>

<span data-ttu-id="25c60-111">Podczas instalacji RCS należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="25c60-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="25c60-112">Zaimportuj funkcję fakturowania elektronicznego do eksportu faktur elektronicznych odbiorcy w formacie **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="25c60-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="25c60-113">Przejrzyj konfiguracje formatów wymagane do generowania, przesyłania i odbierania odpowiedzi na faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="25c60-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="25c60-114">Skonfiguruj zdarzenia obsługujące scenariusze przesyłania faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="25c60-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="25c60-115">Opublikuj funkcję fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="25c60-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="25c60-116">„Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera dodatku Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="25c60-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="25c60-117">W takim przypadku eksport elektronicznych faktur klienta jest funkcją fakturowania elektronicznego, którą skonfigurujesz.</span><span class="sxs-lookup"><span data-stu-id="25c60-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="25c60-118">Importuj funkcję fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="25c60-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="25c60-119">Zaloguj się do swojego konta RCS.</span><span class="sxs-lookup"><span data-stu-id="25c60-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="25c60-120">Otwórz nowy obszar roboczy **Funkcje globalizacji** , a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="25c60-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="25c60-121">Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj** w celu zaimportowania funkcji fakturowania elektronicznego z repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="25c60-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25c60-122">Jeśli lista dostępnych funkcji jest niewidoczna, wybierz opcję **Synchronizuj**.</span><span class="sxs-lookup"><span data-stu-id="25c60-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="25c60-123">Wybierz funkcję **Eksport faktur elektronicznych (IT)** , a następnie wybierz opcję **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="25c60-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importowanie funkcji eksportu faktur elektronicznych (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="25c60-125">Po zaimportowaniu funkcji **Eksportowanie faktur elektronicznych (IT)** z repozytorium globalnego zostaną również zaimportowane wszystkie ustawienia opisane w następnych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="25c60-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="25c60-126">Utwórz nową wersję funkcji Eksportowania faktur elektronicznych (IT)</span><span class="sxs-lookup"><span data-stu-id="25c60-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="25c60-127">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="25c60-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Dodawanie nowej wersji funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="25c60-129">Następnie skonfigurujesz formaty raportowania elektronicznego (ER), które są skojarzone z funkcją fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="25c60-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="25c60-130">Na karcie **Konfiguracje** wybierz opcję **Dodaj** , aby zarządzać wersjami konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="25c60-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Zarządzanie wersjami konfiguracji funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="25c60-132">W tym kroku są dodawane i konfigurowane formaty ER różnych plików używanych do eksportowania włoskich faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="25c60-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="25c60-133">W przypadku włoskich faktur elektronicznych FatturaPA należy stosować następujące standardowe konfiguracje lub odpowiednie niestandardowe konfiguracje używane do fakturowania elektronicznego:</span><span class="sxs-lookup"><span data-stu-id="25c60-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="25c60-134">Faktura sprzedaży (IT)</span><span class="sxs-lookup"><span data-stu-id="25c60-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="25c60-135">Faktura projektu (IT)</span><span class="sxs-lookup"><span data-stu-id="25c60-135">Project invoice (IT)</span></span>

    <span data-ttu-id="25c60-136">Podczas tworzenia funkcji fakturowania elektronicznego pochodzącej z innej funkcji fakturowania elektronicznego, wszystkie formaty ER są dziedziczone z oryginalnej funkcji.</span><span class="sxs-lookup"><span data-stu-id="25c60-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="25c60-137">Wybierz określoną konfigurację pliku formatu ER.</span><span class="sxs-lookup"><span data-stu-id="25c60-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="25c60-138">Wybierz opcję **Edytuj** lub **Wyświetl** , aby otworzyć stronę **Projektant formatów**.</span><span class="sxs-lookup"><span data-stu-id="25c60-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Otwieranie strony Projektanta formatów](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="25c60-140">Strona **Projektant formatów** umożliwia edytowanie i wyświetlanie konfiguracji plików formatu ER.</span><span class="sxs-lookup"><span data-stu-id="25c60-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Strona projektanta formatu](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="25c60-142">Zarządzaj konfiguracjami funkcji fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="25c60-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="25c60-143">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** wybierz opcję **Dodaj** , **Usuń** lub **Edytuj** , aby zarządzać konfiguracjami funkcji fakturowania w systemie.</span><span class="sxs-lookup"><span data-stu-id="25c60-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add** , **Delete** , or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="25c60-145">W tym kroku można skonfigurować zdarzenia dotyczące faktur elektronicznych, łącznie z generowaniem plików wyjściowych XML w formacie **FatturaPA** i cyfrowym (jeśli jest to wymagane).</span><span class="sxs-lookup"><span data-stu-id="25c60-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="25c60-146">Konfigurowanie ustawień funkcji faktur sprzedaży</span><span class="sxs-lookup"><span data-stu-id="25c60-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="25c60-147">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="25c60-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="25c60-148">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="25c60-148">Select **Edit**.</span></span>
3. <span data-ttu-id="25c60-149">Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje** , aby zarządzać listą akcji.</span><span class="sxs-lookup"><span data-stu-id="25c60-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="25c60-150">Akcje definiują listę operacji, które muszą być uruchomione w kolejności sekwencyjnej, aby wykonać pełne wykonanie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="25c60-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Karta Akcje](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="25c60-152">Identyfikator akcji</span><span class="sxs-lookup"><span data-stu-id="25c60-152">Action ID</span></span> | <span data-ttu-id="25c60-153">Nazwa akcji</span><span class="sxs-lookup"><span data-stu-id="25c60-153">Action name</span></span>        | <span data-ttu-id="25c60-154">Opis akcji</span><span class="sxs-lookup"><span data-stu-id="25c60-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="25c60-155">1</span><span class="sxs-lookup"><span data-stu-id="25c60-155">1</span></span>         | <span data-ttu-id="25c60-156">Przekształcanie dokumentu</span><span class="sxs-lookup"><span data-stu-id="25c60-156">Transform document</span></span> | <span data-ttu-id="25c60-157">Utwórz plik XML faktury elektronicznej w formacie **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="25c60-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="25c60-158">2</span><span class="sxs-lookup"><span data-stu-id="25c60-158">2</span></span>         | <span data-ttu-id="25c60-159">Podpisz dokument</span><span class="sxs-lookup"><span data-stu-id="25c60-159">Sign document</span></span>      | <span data-ttu-id="25c60-160">Zastosuj podpis cyfrowy do pliku XML.</span><span class="sxs-lookup"><span data-stu-id="25c60-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="25c60-161">Wybierz kartę **Reguły stosowania** , aby wyświetlić i zachować reguły stosowania.</span><span class="sxs-lookup"><span data-stu-id="25c60-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="25c60-162">Reguły stosowania definiują kontekst, w którym akcja będzie uruchamiana.</span><span class="sxs-lookup"><span data-stu-id="25c60-162">Applicability rules define the context where the action will be run.</span></span>

    ![Karta Reguły zastosowania](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="25c60-164">Wybierz kartę **Zmienne** , aby wyświetlić i zachować zmienne.</span><span class="sxs-lookup"><span data-stu-id="25c60-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Karta Zmienne](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="25c60-166">Umożliwia zdefiniowanie zmiennych publicznych wymaganych do uruchomienia akcji.</span><span class="sxs-lookup"><span data-stu-id="25c60-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="25c60-167">Konfigurowanie ustawień funkcji faktur projektu</span><span class="sxs-lookup"><span data-stu-id="25c60-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="25c60-168">Kroki i ustawienia wymagane do skonfigurowania funkcji **Faktura projektu** są bardzo podobne do kroków i ustawień konfiguracji funkcji **Faktura sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="25c60-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="25c60-169">Podczas pracy z fakturami projektu należy zapoznać się z procedurami faktur sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="25c60-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="25c60-170">Przypisz funkcję fakturowania elektronicznego do środowiska</span><span class="sxs-lookup"><span data-stu-id="25c60-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="25c60-171">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Środowisko** wybierz **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="25c60-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="25c60-172">W polu **Środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="25c60-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="25c60-173">W polu **Obowiązuje od** wybierz datę, kiedy nowe środowisko powinno zostać wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="25c60-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="25c60-174">Wybierz **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="25c60-174">Select **Enable**.</span></span> 

![Włączanie środowiska fakturowania elektronicznego](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="25c60-176">Opublikuj funkcję fakturowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="25c60-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="25c60-177">Funkcję fakturowania elektronicznego można opublikować, zmieniając stan wersji na **Ukończono** lub **Opublikowano**.</span><span class="sxs-lookup"><span data-stu-id="25c60-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="25c60-178">Zmień stan wersji na Ukończone</span><span class="sxs-lookup"><span data-stu-id="25c60-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="25c60-179">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="25c60-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="25c60-180">Wybierz **Zmień status \> Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="25c60-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="25c60-181">Zmień stan wersji na Opublikowane</span><span class="sxs-lookup"><span data-stu-id="25c60-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="25c60-182">Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Ukończono**.</span><span class="sxs-lookup"><span data-stu-id="25c60-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="25c60-183">Wybierz **Zmień status \> Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="25c60-183">Select **Change status \> Publish**.</span></span>

![Zmiana stanu funkcji fakturowania elektronicznego](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="25c60-185">Skonfiguruj integrację dodatku Faktury elektroniczne w Finance</span><span class="sxs-lookup"><span data-stu-id="25c60-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="25c60-186">Podczas instalacji Finance należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="25c60-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="25c60-187">Importuj model danych modelu ER, mapowanie modelu danych ER i konfiguracje kontekstowe dla faktur elektronicznych FatturaPA.</span><span class="sxs-lookup"><span data-stu-id="25c60-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="25c60-188">Skonfiguruj certyfikat, który jest wymagany do cyfrowego podpisywania włoskich faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="25c60-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="25c60-189">Importowanie modelu danych ER, mapowania modelu danych i formatów</span><span class="sxs-lookup"><span data-stu-id="25c60-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="25c60-190">W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy dostawca konfiguracji **Usługi dokumentów biznesowych** jest skonfigurowany jako **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="25c60-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="25c60-191">Wybierz **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="25c60-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="25c60-192">Wybierz pozycję **Zasób globalny \> Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="25c60-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="25c60-193">Importowanie **Modelu faktury** , **Mapowania modelu faktury** i **Modelu kontekstu faktury dla odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="25c60-193">Import **Invoice model** , **Invoice model mapping** , and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="25c60-194">Włącz funkcję, aby wyeksportować faktury elektroniczne dla odbiorcy we Włoszech</span><span class="sxs-lookup"><span data-stu-id="25c60-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="25c60-195">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="25c60-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="25c60-196">Na karcie **Funkcje** zaznacz pole wyboru **Włączone** w wierszu dla odwołania do funkcji **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="25c60-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Włączanie funkcji FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="25c60-198">Konfiguracja dokumentów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="25c60-198">Configure electronic documents</span></span>

1. <span data-ttu-id="25c60-199">Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="25c60-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="25c60-200">Na karcie **Dokument elektroniczny** wybierz opcję **Dodaj** i wprowadź tabele wymagane do generowania włoskich faktur elektronicznych:</span><span class="sxs-lookup"><span data-stu-id="25c60-200">On the **Electronic document** tab, select **Add** , and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="25c60-201">**Nazwa tabeli:** Arkusz faktur dla odbiorcy</span><span class="sxs-lookup"><span data-stu-id="25c60-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="25c60-202">**Nazwa tabeli:** Faktura projektu</span><span class="sxs-lookup"><span data-stu-id="25c60-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="25c60-203">Dla każdej tabeli zdefiniuj powiązany kontekst dokumentu:</span><span class="sxs-lookup"><span data-stu-id="25c60-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="25c60-204">W przypadku **Arkusza faktur dla odbiorcy** wybierz **Kontekst faktury dla odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="25c60-204">For **Customer invoice journal** , select **Customer invoice context**.</span></span>
    - <span data-ttu-id="25c60-205">W przypadku **Faktury projektu** wybierz **Kontekst faktury projektu**.</span><span class="sxs-lookup"><span data-stu-id="25c60-205">For **Project invoice** , select **Project invoice context**.</span></span>

![Konfigurowanie typów odpowiedzi](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="25c60-207">Przetwarzanie faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="25c60-207">Electronic invoice processing</span></span>

<span data-ttu-id="25c60-208">Podczas przetwarzania w Finance należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="25c60-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="25c60-209">Generuj włoskie faktury e-fakturowane za pomocą dodatku Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="25c60-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="25c60-210">Wyświetl dzienniki wykonywania i przejrzyj wyniki przetwarzania</span><span class="sxs-lookup"><span data-stu-id="25c60-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="25c60-211">Generuj faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="25c60-211">Generate electronic invoices</span></span>

<span data-ttu-id="25c60-212">Po włączeniu funkcji **Konfigurowalna integracja z dodatkiem Faktur elektronicznych** i aktywowaniu funkcji **IT00036** nie można już używać starego procesu Finance do generowania włoskich faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="25c60-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="25c60-213">Zastępuje go nowym procesem o nazwie **Prześlij dokumenty elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="25c60-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="25c60-214">Dokumenty można przesyłać ręcznie na podstawie zapotrzebowania na dokumenty fakturowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="25c60-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="25c60-215">Przed kontynuowaniem sprawdź, czy zostało zakończone wymagane ustawienie dla włoskich faktur elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="25c60-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="25c60-216">Aby uzyskać więcej informacji, zobacz [Faktury elektroniczne odbiorcy](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="25c60-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="25c60-217">Należy pamiętać, że niektóre kroki konfiguracji opisane w tym temacie mogą być niedostępne z powodu aktywacji dodatku Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="25c60-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="25c60-218">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="25c60-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="25c60-219">W przypadku pierwszego przesłania dokumentu należy w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="25c60-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="25c60-220">Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.</span><span class="sxs-lookup"><span data-stu-id="25c60-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="25c60-221">Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj** , aby otworzyć okno dialogowe **Zapytania** , w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.</span><span class="sxs-lookup"><span data-stu-id="25c60-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Przesyłanie dokumentów elektronicznych, okno dialogowe](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="25c60-223">Kwerenda filtra</span><span class="sxs-lookup"><span data-stu-id="25c60-223">Filter query</span></span>

1. <span data-ttu-id="25c60-224">W oknie dialogowym **Zapytania** skonfiguruj warunki filtrowania zarówno dla faktur sprzedaży, jak i faktury projektu, albo pozostaw te warunki puste, aby uwzględnić wszystkie nieprzesłane faktury.</span><span class="sxs-lookup"><span data-stu-id="25c60-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Konfigurowanie kryteriów filtru przesyłania](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="25c60-226">Kliknij przycisk **OK** , aby zamknąć okno dialogowe **Zapytania**.</span><span class="sxs-lookup"><span data-stu-id="25c60-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="25c60-227">Wybierz przycisk **OK** , aby przesłać wybrane dokumenty.</span><span class="sxs-lookup"><span data-stu-id="25c60-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="25c60-228">! [UWAGA] Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z dodatkiem Faktury elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="25c60-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="25c60-229">Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.</span><span class="sxs-lookup"><span data-stu-id="25c60-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="25c60-230">Wyświetlanie dzienników przesyłania</span><span class="sxs-lookup"><span data-stu-id="25c60-230">View submission logs</span></span>

<span data-ttu-id="25c60-231">Dzienniki przesyłania można wyświetlić dla wszystkich przesłanych dokumentów.</span><span class="sxs-lookup"><span data-stu-id="25c60-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="25c60-232">Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.</span><span class="sxs-lookup"><span data-stu-id="25c60-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="25c60-233">W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy** lub **Faktura projektu** , aby odfiltrować wymagane dokumenty elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="25c60-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Wybór typu dokumentu, aby wyświetlić dzienniki przedłożenia](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="25c60-235">Wartość wyświetlana w kolumnie **Stan przesyłania** reprezentuje stan procesu przesyłania.</span><span class="sxs-lookup"><span data-stu-id="25c60-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="25c60-236">Wskazuje on, czy proces został uruchomiony zgodnie z konfiguracją i czy jest wymagane wykonanie dodatkowych działań.</span><span class="sxs-lookup"><span data-stu-id="25c60-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="25c60-237">W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania** , aby wyświetlić szczegóły dzienników wykonywania przesyłania.</span><span class="sxs-lookup"><span data-stu-id="25c60-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Wyświetlanie szczegółów dziennika przesyłania](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="25c60-239">Na skróconej karcie **Przetwarzanie akcji** można przejrzeć dziennik wykonywania akcji skonfigurowanych w wersji funkcji skonfigurowanej w RCS.</span><span class="sxs-lookup"><span data-stu-id="25c60-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="25c60-240">Kolumna **Stan** wskazuje, czy akcja została pomyślnie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="25c60-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="25c60-241">Na skróconej karcie **Pliki akcji** można wyświetlać pliki pośrednie wygenerowane podczas wykonywania akcji.</span><span class="sxs-lookup"><span data-stu-id="25c60-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="25c60-242">Można wybrać opcję **Widok** , aby pobrać wyjściowy plik XML w formacie **FatturaPA** i wyświetlić jego zawartość.</span><span class="sxs-lookup"><span data-stu-id="25c60-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25c60-243">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="25c60-243">Related topics</span></span>

- [<span data-ttu-id="25c60-244">Omówienie dodatku Faktur elektronicznych</span><span class="sxs-lookup"><span data-stu-id="25c60-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="25c60-245">Rozpocznij pracę z dodatkiem Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="25c60-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="25c60-246">Skonfiguruj dodatek Faktury elektroniczne</span><span class="sxs-lookup"><span data-stu-id="25c60-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
