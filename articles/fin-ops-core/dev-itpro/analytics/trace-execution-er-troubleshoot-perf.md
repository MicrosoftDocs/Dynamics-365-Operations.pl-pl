---
title: Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością
description: Ten temat zawiera informacje dotyczące korzystania z funkcji śledzenia wydajności w module Raportowanie elektroniczne (ER) w celu rozwiązywania problemów z wydajnością.
author: NickSelin
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a1a6b3711e58964ff266d84c75e79f741218ee23
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561155"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a><span data-ttu-id="bd287-103">Śledzenie wykonywania formatów ER w celu rozwiązywania problemów z wydajnością</span><span class="sxs-lookup"><span data-stu-id="bd287-103">Trace the execution of ER formats to troubleshoot performance issues</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bd287-104">W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych należy zdefiniować metodę, która jest używana do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="bd287-104">As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="bd287-105">Funkcja śledzenia wydajności systemu ER pozwala znacznie zmniejszyć koszty i czas, jakie pochłania zbieranie szczegółów dotyczących wykonywania formatów ER i używanie ich do rozwiązywania problemów z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="bd287-105">The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</span></span> <span data-ttu-id="bd287-106">Ten samouczek zawiera wskazówki dotyczące zbierania śladów wydajności wykonywanych formatów ER w module oraz sposobu używania informacji z tych śladów w celu zwiększania wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-106">This tutorial provides guidelines about how to take performance traces for executed ER formats, and how to use the information from these traces to help improve performance.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd287-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="bd287-107">Prerequisites</span></span>

<span data-ttu-id="bd287-108">Aby wykonać przykłady opisane w tym samouczku, musisz mieć następujące uprawnienia dostępu:</span><span class="sxs-lookup"><span data-stu-id="bd287-108">To complete the examples in this tutorial, you must have the following access:</span></span>

- <span data-ttu-id="bd287-109">Dostęp do jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="bd287-109">Access to one of the following roles:</span></span>

    - <span data-ttu-id="bd287-110">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="bd287-110">Electronic reporting developer</span></span>
    - <span data-ttu-id="bd287-111">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="bd287-111">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="bd287-112">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="bd287-112">System administrator</span></span>

- <span data-ttu-id="bd287-113">Dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co aplikacja, dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="bd287-113">Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as the application, for one of the following roles:</span></span>

    - <span data-ttu-id="bd287-114">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="bd287-114">Electronic reporting developer</span></span>
    - <span data-ttu-id="bd287-115">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="bd287-115">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="bd287-116">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="bd287-116">System administrator</span></span>

<span data-ttu-id="bd287-117">Musisz również pobrać i lokalnie zapisać następujące pliki.</span><span class="sxs-lookup"><span data-stu-id="bd287-117">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="bd287-118">Plik</span><span class="sxs-lookup"><span data-stu-id="bd287-118">File</span></span>                                  | <span data-ttu-id="bd287-119">Zawartość</span><span class="sxs-lookup"><span data-stu-id="bd287-119">Content</span></span>                               |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="bd287-120">Model śledzenia wydajności, wersja 1</span><span class="sxs-lookup"><span data-stu-id="bd287-120">Performance trace model.version.1</span></span>     | [<span data-ttu-id="bd287-121">Przykładowa konfiguracja modelu danych ER</span><span class="sxs-lookup"><span data-stu-id="bd287-121">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)    |
| <span data-ttu-id="bd287-122">Metadane śledzenia wydajności, wersja 1</span><span class="sxs-lookup"><span data-stu-id="bd287-122">Performance trace metadata.version.1</span></span>  | [<span data-ttu-id="bd287-123">Przykładowa konfiguracja metadanych ER</span><span class="sxs-lookup"><span data-stu-id="bd287-123">Sample ER metadata configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)      |
| <span data-ttu-id="bd287-124">Mapowanie śledzenia wydajności, wersja 1.1</span><span class="sxs-lookup"><span data-stu-id="bd287-124">Performance trace mapping.version.1.1</span></span> | [<span data-ttu-id="bd287-125">Przykładowa konfiguracja mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-125">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="bd287-126">Format śladu wydajności, wersja 1.1</span><span class="sxs-lookup"><span data-stu-id="bd287-126">Performance trace format.version.1.1</span></span>  | [<span data-ttu-id="bd287-127">Przykładowa konfiguracja formatu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-127">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)       |

### <a name="configure-er-parameters"></a><span data-ttu-id="bd287-128">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-128">Configure ER parameters</span></span>

<span data-ttu-id="bd287-129">Każdy ślad wydajności modułu ER generowany w aplikacji jest przechowywany jako załącznik do rekordu dziennika wykonania.</span><span class="sxs-lookup"><span data-stu-id="bd287-129">Each ER performance trace that is generated in the application is stored as an attachment of the execution log record.</span></span> <span data-ttu-id="bd287-130">Do zarządzania tymi załącznikami służy struktura zarządzania dokumentami (DM).</span><span class="sxs-lookup"><span data-stu-id="bd287-130">The Document management (DM) framework is used to manage these attachments.</span></span> <span data-ttu-id="bd287-131">Parametry ER należy skonfigurować z wyprzedzeniem, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-131">You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="bd287-132">W obszarze roboczym **Raportowanie elektroniczne** wybierz łącze **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="bd287-132">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="bd287-133">Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-133">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Strona parametrów raportowania elektronicznego](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

<span data-ttu-id="bd287-135">Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):</span><span class="sxs-lookup"><span data-stu-id="bd287-135">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="bd287-136">**Klasa:** Dołącz plik</span><span class="sxs-lookup"><span data-stu-id="bd287-136">**Class:** Attach file</span></span>
- <span data-ttu-id="bd287-137">**Grupa:** Plik</span><span class="sxs-lookup"><span data-stu-id="bd287-137">**Group:** File</span></span>

![Strona Typy dokumentów](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> <span data-ttu-id="bd287-139">Wybrany typ dokumentu musi być dostępny we wszystkich firmach bieżącego wystąpienia, ponieważ załączniki DM są specyficzne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="bd287-139">The selected document type must be available in every company of the current instance, because DM attachments are company-specific.</span></span>

### <a name="configure-rcs-parameters"></a><span data-ttu-id="bd287-140">Konfigurowanie parametrów RCS</span><span class="sxs-lookup"><span data-stu-id="bd287-140">Configure RCS parameters</span></span>

<span data-ttu-id="bd287-141">Ślady wydajności ER generowane zostaną zaimportowane do RCS w celu analizy za pomocą projektanta formatu ER i projektanta mapowania ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-141">ER performance traces that are generated will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</span></span> <span data-ttu-id="bd287-142">Ponieważ dane śledzenia wydajności ER są przechowywane jako załączniki rekordu dziennika wykonania powiązanego z formatem ER, należy z wyprzedzeniem skonfigurować parametry RCS, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-142">Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="bd287-143">W wystąpieniu RCS, które zostało zainicjowane dla danej firmy, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="bd287-143">In the instance of RCS that has been provisioned for your company, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="bd287-144">Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-144">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Strona parametrów raportowania elektronicznego w RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

<span data-ttu-id="bd287-146">Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):</span><span class="sxs-lookup"><span data-stu-id="bd287-146">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="bd287-147">**Klasa:** Dołącz plik</span><span class="sxs-lookup"><span data-stu-id="bd287-147">**Class:** Attach file</span></span>
- <span data-ttu-id="bd287-148">**Grupa:** Plik</span><span class="sxs-lookup"><span data-stu-id="bd287-148">**Group:** File</span></span>

## <a name="design-an-er-solution"></a><span data-ttu-id="bd287-149">Projektowanie rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="bd287-149">Design an ER solution</span></span>

<span data-ttu-id="bd287-150">Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bd287-150">Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</span></span> <span data-ttu-id="bd287-151">Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**).</span><span class="sxs-lookup"><span data-stu-id="bd287-151">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable \> Vendors \> All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="bd287-152">Chcesz jednak mieć wszystkie transakcje dostawcy równocześnie w jednym dokumencie elektronicznym w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="bd287-152">However, you want to have all vendor transaction at the same time in one electronic document in XML format.</span></span> <span data-ttu-id="bd287-153">To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.</span><span class="sxs-lookup"><span data-stu-id="bd287-153">This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</span></span>

1. <span data-ttu-id="bd287-154">Zaloguj się do wystąpienia RCS, które zostało zainicjowane dla danej firmy.</span><span class="sxs-lookup"><span data-stu-id="bd287-154">Sign in to the instance of RCS that has been provisioned for your company.</span></span>
2. <span data-ttu-id="bd287-155">W tym samouczku utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="bd287-155">In this tutorial, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="bd287-156">Upewnij się zatem, że ten dostawca konfiguracji jest dodany do RCS i wybrany jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="bd287-156">Therefore, make sure that this configuration provider has been added to RCS and selected as active.</span></span> <span data-ttu-id="bd287-157">Szczegółowe instrukcje znajdują się w procedurze [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="bd287-157">For instructions, see the [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) procedure.</span></span>
3. <span data-ttu-id="bd287-158">W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bd287-158">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="bd287-159">Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do RCS, w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="bd287-159">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="bd287-160">Dla każdej konfiguracji wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="bd287-160">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="bd287-161">W okienku akcji wybierz opcję **Wymiana \> Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="bd287-161">On the Action Pane, select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="bd287-162">Kliknij przycisk **Przeglądaj**, aby wybrać odpowiedni plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="bd287-162">Select **Browse** to select the appropriate file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="bd287-163">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd287-163">Select **OK**.</span></span>

    ![Strona Konfiguracje w RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a><span data-ttu-id="bd287-165">Uruchom rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="bd287-165">Run the ER solution to trace execution</span></span>

<span data-ttu-id="bd287-166">Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-166">Assume that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="bd287-167">Chcesz teraz przetestować je w swoim wystąpieniu oraz przeanalizować wydajność wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bd287-167">You now want to test it in your instance and analyze execution performance.</span></span>

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a><span data-ttu-id="bd287-168">Importowanie konfiguracji ER z RCS do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd287-168">Import an ER configuration from RCS into Finance and Operations</span></span>

1. <span data-ttu-id="bd287-169">Zaloguj się do swojego wystąpienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bd287-169">Sign in to your application instance.</span></span>
2. <span data-ttu-id="bd287-170">W tym samouczku zaimportujesz konfiguracje z wystąpienia RCS (w którym projektujesz składniki ER) do swojego wystąpienia (w którym je testujesz i ostatecznie ich używasz).</span><span class="sxs-lookup"><span data-stu-id="bd287-170">For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your instance (where you test and finally use them).</span></span> <span data-ttu-id="bd287-171">Upewnij się zatem, że zostały przygotowane wszystkie wymagane artefakty.</span><span class="sxs-lookup"><span data-stu-id="bd287-171">Therefore, you must make sure that all the required artifacts have been prepared.</span></span> <span data-ttu-id="bd287-172">Szczegółowe instrukcje zawiera procedura [Importowanie konfiguracji raportowania elektronicznego (RE) z usługi Regulatory Configuration Services (RCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations).</span><span class="sxs-lookup"><span data-stu-id="bd287-172">For instructions, see the [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations) procedure.</span></span>
3. <span data-ttu-id="bd287-173">Aby zaimportować konfiguracje z RCS do aplikacji, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="bd287-173">Follow these steps to import the configurations from RCS into the application:</span></span>

    1. <span data-ttu-id="bd287-174">W obszarze roboczym **Raportowanie elektroniczne** na kafelku dostawcy konfiguracji **Litware, Inc.** wybierz opcję **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="bd287-174">In the **Electronic reporting** workspace, on the tile for the **Litware, Inc.** configuration provider, select **Repositories**.</span></span>
    2. <span data-ttu-id="bd287-175">Na stronie **Repozytorium konfiguracji** zaznacz repozytorium typu **RCS**, a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="bd287-175">On the **Configuration repository** page, select the repository of the **RCS** type, and then select **Open**.</span></span>
    3. <span data-ttu-id="bd287-176">Na skróconej karcie **Konfiguracje** wybierz konfigurację **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-176">On the **Configurations** FastTab, select the **Performance trace format** configuration.</span></span>
    4. <span data-ttu-id="bd287-177">Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji, a następnie kliknij przycisk **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="bd287-177">On the **Versions** FastTab, select version **1.1** of the selected configuration, and then select **Import**.</span></span>

    ![Strona Repozytorium konfiguracji](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

<span data-ttu-id="bd287-179">Odpowiednie wersje konfiguracji modelu danych i mapowania modelu są automatycznie importowane jako wymagania wstępne dla importowanej konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-179">The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="bd287-180">Włączanie śledzenia wydajności ER</span><span class="sxs-lookup"><span data-stu-id="bd287-180">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="bd287-181">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bd287-181">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="bd287-182">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="bd287-182">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="bd287-183">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="bd287-183">In the **User parameters** dialog box, in the **Execution tracing** section, follow these steps:</span></span>

    1. <span data-ttu-id="bd287-184">W polu **Format śladu wykonania** wybierz opcję **Format śladu debugowania**, aby rozpocząć zbieranie szczegółowych informacji dotyczących wykonania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-184">In the **Execution trace format** field, select **Debug trace format** to start to collect the details of ER format execution.</span></span> <span data-ttu-id="bd287-185">Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="bd287-185">When this value is selected, the performance trace will collect information about the time that is spent on the following actions:</span></span>

        - <span data-ttu-id="bd287-186">Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych</span><span class="sxs-lookup"><span data-stu-id="bd287-186">Running each data source in the model mapping that is called to get data</span></span>
        - <span data-ttu-id="bd287-187">Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="bd287-187">Processing each format item to enter data in the output that is generated</span></span>

        <span data-ttu-id="bd287-188">W polu **Format śladu wykonania** możesz określić format generowanego śladu wydajności, w którym są przechowywane szczegóły dotyczące wykonania, w odniesieniu do formatu ER i elementów mapowania.</span><span class="sxs-lookup"><span data-stu-id="bd287-188">You use the **Execution trace format** field to specify the format of the generated performance trace that the execution details are stored in for ER format and mapping elements.</span></span> <span data-ttu-id="bd287-189">Wybranie opcji **Format śladu debugowania** jako wartości umożliwia analizę zawartości śladu w projektancie operacji ER oraz wyświetlenie formatu lub elementów mapowania wymienionych w śladzie.</span><span class="sxs-lookup"><span data-stu-id="bd287-189">By selecting **Debug trace format** as the value, you will be able to analyze the content of the trace in ER Operation designer, and see the ER format or mapping elements that are mentioned in the trace.</span></span>

    2. <span data-ttu-id="bd287-190">Wybór ustawienia **Tak** następujących opcji umożliwia zbieranie szczegółów wykonania mapowania modelu ER i składników formatu ER:</span><span class="sxs-lookup"><span data-stu-id="bd287-190">Set the following options to **Yes** to collect specific details of the execution of the ER model mapping and ER format components:</span></span>

        - <span data-ttu-id="bd287-191">**Zbieraj statystyki zapytań** — po włączeniu tej opcji śledzenie wydajności będzie zbierać następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="bd287-191">**Collect query statistics** – When this option is turned on, the performance trace will collect the following information:</span></span>

            - <span data-ttu-id="bd287-192">Liczba wywołań bazy danych przez źródła danych</span><span class="sxs-lookup"><span data-stu-id="bd287-192">The number of database calls that were made by data sources</span></span>
            - <span data-ttu-id="bd287-193">Liczba powielonych wywołań do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-193">The number of duplicate calls to the database</span></span>
            - <span data-ttu-id="bd287-194">Szczegóły instrukcji SQL użytych w wywołaniach bazy danych</span><span class="sxs-lookup"><span data-stu-id="bd287-194">Details of the SQL statements that were used to make database calls</span></span>

        - <span data-ttu-id="bd287-195">**Śledzenie dostępu funkcji buforowania** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o użyciu buforu mapowania modelu ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-195">**Trace access of caching** – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</span></span>
        - <span data-ttu-id="bd287-196">**Śledzenie dostępu do danych** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie wywołań do bazy danych dla wykonywanych źródeł danych typu listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="bd287-196">**Trace data access** – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</span></span>
        - <span data-ttu-id="bd287-197">**Element stałotekstowy listy śledzenia** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie rekordów, których żądają źródła danych typu listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="bd287-197">**Trace list enumeration** – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd287-198">Parametry w oknie dialogowym **Parametry użytkownika** są specyficzne dla użytkownika i bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="bd287-198">The parameters in the **User parameters** dialog box are specific to the user and the current company.</span></span>

    ![Okno dialogowe parametry użytkownika](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a><span data-ttu-id="bd287-200">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-200">Run the ER format</span></span>

1. <span data-ttu-id="bd287-201">Wybierz pole firmę **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="bd287-201">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="bd287-202">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bd287-202">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3. <span data-ttu-id="bd287-203">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-203">On the **Configurations** page, in the configuration tree, select the **Performance trace format** item.</span></span>
4. <span data-ttu-id="bd287-204">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="bd287-204">On the Action Pane, select **Run**.</span></span>

<span data-ttu-id="bd287-205">Generowany plik zawiera informacje dotyczące 265 transakcji dla sześciu dostawców.</span><span class="sxs-lookup"><span data-stu-id="bd287-205">Notice that the file that is generated presents information about 265 transactions for six vendors.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="bd287-206">Przeglądanie śladu wykonania</span><span class="sxs-lookup"><span data-stu-id="bd287-206">Review the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a><span data-ttu-id="bd287-207">Eksportowanie wygenerowanego śledzenia z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bd287-207">Export the generated trace from the application</span></span>

<span data-ttu-id="bd287-208">Ślady wydajności są odłączane od źródłowego formatu ER i można je serializować w zewnętrznym pliku zip.</span><span class="sxs-lookup"><span data-stu-id="bd287-208">Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</span></span>

1. <span data-ttu-id="bd287-209">Otwórz **Administracja organizacji \> Elektroniczne raportowanie \> Dzienniki debugowania konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="bd287-209">Go to **Organization administration \> Electronic reporting \> Configuration debug logs**.</span></span>
2. <span data-ttu-id="bd287-210">Na stronie **Dzienniki przebiegu raportowania elektronicznego** w lewym okienku w polu **Nazwa konfiguracji** wybierz opcję **Format śladu wydajności**, aby znaleźć rekordy dziennika wygenerowane przez wykonanie konfiguracji **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-210">On the **Electronic reporting run logs** page, in the left pane, in the **Configuration name** field, select **Performance trace format** to find the log records that have been generated by the execution of the **Performance trace format** configuration.</span></span>
3. <span data-ttu-id="bd287-211">Naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony lub naciśnij **Ctrl+Shift+A**.</span><span class="sxs-lookup"><span data-stu-id="bd287-211">Select the **Attachments** button (the paper clip symbol) in the upper-right corner of the page, or press **Ctrl+Shift+A**.</span></span>

    ![Przycisk Załączniki na stronie Dzienniki przebiegu raportowania elektronicznego.](./media/GER-PerfTrace-GER-DebugLog.png)

4. <span data-ttu-id="bd287-213">Na stronie **Załączniki do dzienników przebiegu raportowania elektronicznego** w okienku akcji kliknij przycisk **Otwórz**, aby pobrać ślad wydajności jako plik zip i zapisać go lokalnie.</span><span class="sxs-lookup"><span data-stu-id="bd287-213">On the **Attachments for Electronic reporting run logs** page, on the Action Pane, select **Open** to get the performance trace as a zip file and store it locally.</span></span>

    ![Załączniki do dzienników przebiegu raportowania elektronicznego](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> <span data-ttu-id="bd287-215">Generowany ślad zawiera odwołanie do źródłowego raportu ER w postaci unikatowego identyfikatora raportu tylko w formacie **GUID**.</span><span class="sxs-lookup"><span data-stu-id="bd287-215">The trace that is generated has a reference to the source ER report via a unique report identifier in **GUID** format only.</span></span> <span data-ttu-id="bd287-216">Numerowanie wersji formatu nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="bd287-216">The version numbering of the format isn't considered.</span></span>

<span data-ttu-id="bd287-217">Skojarzenie między śladem wydajności, który został wygenerowany dla wykonywanego formatu ER, a mapowaniem modelu ER jest oparte na użytym deskryptorze głównym i wspólnym modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-217">Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</span></span> <span data-ttu-id="bd287-218">Numerowanie wersji formatu i mapowania modelu nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="bd287-218">The version numbering of the format and model mapping isn't considered.</span></span> <span data-ttu-id="bd287-219">Ustawienie opcji **Domyślne mapowanie modelu** mapowania modelu również nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="bd287-219">The setting of the **Default for model mapping** flag for the model mapping also isn't considered.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a><span data-ttu-id="bd287-220">Importowanie wygenerowanego śladu do RCS</span><span class="sxs-lookup"><span data-stu-id="bd287-220">Import the generated trace into RCS</span></span>

1. <span data-ttu-id="bd287-221">W RCS w obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bd287-221">In RCS, in the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
2. <span data-ttu-id="bd287-222">Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń pozycję **Model śladu wydajności** i wybierz opcję **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-222">On the **Configurations** page, in the configuration tree, expand the **Performance trace model** item, and select the **Performance trace format** item.</span></span>
3. <span data-ttu-id="bd287-223">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="bd287-223">On the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="bd287-224">Na stronie **Projektant formatu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-224">On the **Format designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="bd287-225">W oknie dialogowym **Ustawienia wyników śledzenia wydajności** wybierz opcję **Importuj ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-225">In the **Performance trace result settings** dialog box, select **Import performance trace**.</span></span>
6. <span data-ttu-id="bd287-226">Kliknij przycisk **Przeglądaj**, a następnie zaznacz plik zip, który został wcześniej eksportowany.</span><span class="sxs-lookup"><span data-stu-id="bd287-226">Select **Browse** to select the zip file that you exported earlier.</span></span>
7. <span data-ttu-id="bd287-227">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd287-227">Select **OK**.</span></span>

    ![Okno dialogowe ustawień wyników śledzenia wydajności w RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a><span data-ttu-id="bd287-229">Użycie śledzenia wydajności do analizy w RCS — wykonanie formatu</span><span class="sxs-lookup"><span data-stu-id="bd287-229">Use the performance trace for analysis in RCS – Format execution</span></span>

1. <span data-ttu-id="bd287-230">W RCS na stronie **Projektant formatu** kliknij przycisk **Rozwiń/Zwiń**, aby rozwinąć zawartość wszystkich elementów formatu.</span><span class="sxs-lookup"><span data-stu-id="bd287-230">In RCS, on the **Format designer** page, select **Expand/collapse** to expand the content of all format items.</span></span>

    <span data-ttu-id="bd287-231">Zostaną wyświetlone dodatkowe informacje dotyczące niektórych pozycji bieżącego formatu:</span><span class="sxs-lookup"><span data-stu-id="bd287-231">Notice that additional information is shown for some items of the current format:</span></span>

    - <span data-ttu-id="bd287-232">Rzeczywisty czas spędzony na wprowadzaniu danych w wygenerowanych danych wyjściowych przy użyciu elementu formatu</span><span class="sxs-lookup"><span data-stu-id="bd287-232">The actual time that was spent entering data in the generated output by using the format item</span></span>
    - <span data-ttu-id="bd287-233">Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wygenerowanie wszystkich danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="bd287-233">The same time expressed as a percentage of the total time that was spent generating the whole output</span></span>

    ![Strona projektanta formatu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. <span data-ttu-id="bd287-235">Zamknij stronę **Projektant formatu**.</span><span class="sxs-lookup"><span data-stu-id="bd287-235">Close **Format designer** page.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a><span data-ttu-id="bd287-236">Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu</span><span class="sxs-lookup"><span data-stu-id="bd287-236">Use the performance trace for analysis in RCS – Model mapping</span></span>

1. <span data-ttu-id="bd287-237">W RCS na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-237">In RCS, on the **Configurations** page, in the configuration tree, select the **Performance trace mapping** item.</span></span>
2. <span data-ttu-id="bd287-238">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="bd287-238">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="bd287-239">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="bd287-239">Select **Designer**.</span></span>
4. <span data-ttu-id="bd287-240">Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-240">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="bd287-241">Wybierz ślad, który zaimportowano wcześniej.</span><span class="sxs-lookup"><span data-stu-id="bd287-241">Select the trace that you imported earlier.</span></span>
6. <span data-ttu-id="bd287-242">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd287-242">Select **OK**.</span></span>

<span data-ttu-id="bd287-243">Zostaną udostępnione nowe informacje dotyczące niektórych pozycji źródła danych bieżącego mapowania modelu:</span><span class="sxs-lookup"><span data-stu-id="bd287-243">Notice that new information becomes available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="bd287-244">Rzeczywisty czas poświęcony na uzyskiwanie danych przy użyciu źródła danych</span><span class="sxs-lookup"><span data-stu-id="bd287-244">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="bd287-245">Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wykonywanie całego mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bd287-245">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

<span data-ttu-id="bd287-246">Podczas uruchamiania źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum ER poinformuje, że bieżące mapowanie modelu duplikuje żądania bazy danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-246">Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source is run.</span></span> <span data-ttu-id="bd287-247">To duplikowanie wynika z tego, że lista transakcji dostawcy jest wywoływana dwukrotnie dla każdego rekordu dostawcy przetwarzanego w ramach iteracji:</span><span class="sxs-lookup"><span data-stu-id="bd287-247">This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</span></span>

- <span data-ttu-id="bd287-248">Jedno wywołanie jest wykonywane w celu wprowadzenia szczegółów poszczególnych transakcji do modelu danych na podstawie skonfigurowanych powiązań.</span><span class="sxs-lookup"><span data-stu-id="bd287-248">One call is made to enter details of each transaction in the data model, based on configured bindings.</span></span>
- <span data-ttu-id="bd287-249">Jedno wywołanie jest wykonywane w celu wprowadzenia obliczonej liczby transakcji danego dostawcy do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-249">One call is made to enter the calculated number of transactions per vendor in the data model.</span></span>

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

<span data-ttu-id="bd287-251">Wartość **\[Q:530\]** wskazuje, że tabela VendTrans została wywołana 530 razy, aby zwrócić rekord z tej tabeli do źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum.</span><span class="sxs-lookup"><span data-stu-id="bd287-251">The value **\[Q:530\]** indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source.</span></span> <span data-ttu-id="bd287-252">Wartość **\[530\]** wskazuje, że źródło danych VendTable\</Relations/VendTrans.VendTable\_AccountNum zostało wywołane 530 razy, aby zwrócić rekord z tego źródła danych i wprowadzić jego szczegóły do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-252">The value **\[530\]** indicates that the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</span></span>

<span data-ttu-id="bd287-253">Zaleca się buforowanie źródła danychVendTable/\<Relations/VendTrans.VendTable\_AccountNum w celu zmniejszenia liczby wywołań wykonywanych w celu uzyskania szczegółów dotyczących 265 transakcji i zwiększenia wydajności mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="bd287-253">We recommend that you use caching for the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</span></span>

<span data-ttu-id="bd287-254">Przydatne może być także zmniejszenie liczby wywołań źródła danych LedgerTransTypeList.</span><span class="sxs-lookup"><span data-stu-id="bd287-254">It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</span></span> <span data-ttu-id="bd287-255">To źródło danych służy do kojarzenia poszczególnych wartości wyliczenia **LedgerTransType** z etykietą.</span><span class="sxs-lookup"><span data-stu-id="bd287-255">This data source is used to associate each value of the **LedgerTransType** enumeration with its label.</span></span> <span data-ttu-id="bd287-256">Korzystając z tego źródła danych, można znaleźć odpowiednią etykietę i wprowadzić ją do modelu danych dla poszczególnych transakcji dostawcy.</span><span class="sxs-lookup"><span data-stu-id="bd287-256">By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</span></span> <span data-ttu-id="bd287-257">Bieżąca liczba wywołań tego źródła danych (9027) jest dość duża jak na 265 transakcji.</span><span class="sxs-lookup"><span data-stu-id="bd287-257">The current number of calls to this data source (9,027) is quite high for 265 transactions.</span></span>

![Strona projektanta mapowania modelu w RCS pokazująca 9027 wywołań źródła danych](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="bd287-259">Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania</span><span class="sxs-lookup"><span data-stu-id="bd287-259">Improve the model mapping based on information from the execution trace</span></span>

### <a name="modify-the-logic-of-the-model-mapping"></a><span data-ttu-id="bd287-260">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bd287-260">Modify the logic of the model mapping</span></span>

1. <span data-ttu-id="bd287-261">Aby zapobiec duplikowaniu wywołań bazy danych, należy użyć buforowania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="bd287-261">Follow these steps to use caching, to help prevent duplicate calls to the database:</span></span>

    1. <span data-ttu-id="bd287-262">W RCS na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz pozycję **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="bd287-262">In RCS, on the **Model mapping designer** page, in the **Data sources** pane, select the **VendTable** item.</span></span>
    2. <span data-ttu-id="bd287-263">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="bd287-263">Select **Cache**.</span></span>
    3. <span data-ttu-id="bd287-264">Rozwiń pozycję **VendTable**, rozwiń listę relacji jeden-do-wielu źródła danych VendTable (pozycja **\<Relacje**) i wybierz opcję **VendTrans.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="bd287-264">Expand the **VendTable** item, expand the list of one-to-many relations for the VendTable data source (the **\<Relations** item), and select the **VendTrans.VendTable\_AccountNum** item.</span></span>
    4. <span data-ttu-id="bd287-265">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="bd287-265">Select **Cache**.</span></span>

    ![Włączanie buforowania w celu zapobiegania duplikowaniu wywołań](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. <span data-ttu-id="bd287-267">Aby sprowadzić źródło danych LedgerTransTypeList do zakresu źródła danych VendTable, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="bd287-267">Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</span></span>

    1. <span data-ttu-id="bd287-268">W okienku **Typy źródła danych** rozwiń pozycję **Funkcje** i wybierz pozycję **Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bd287-268">In the **Data source types** pane, expand the **Functions** item, and select the **Calculated field** item.</span></span>
    2. <span data-ttu-id="bd287-269">W okienku **Źródła danych** wybierz pozycję **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="bd287-269">In the **Data sources** pane, select the **VendTable** item.</span></span>
    3. <span data-ttu-id="bd287-270">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bd287-270">Select **Add**.</span></span>
    4. <span data-ttu-id="bd287-271">W polu **Nazwa** wprowadź nazwę **\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="bd287-271">In the **Name** field, enter **\$TransType**.</span></span>
    5. <span data-ttu-id="bd287-272">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bd287-272">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="bd287-273">W polu **Formuła** wpisz tekst **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="bd287-273">In the **Formula** field, enter **LedgerTransTypeList**.</span></span>
    7. <span data-ttu-id="bd287-274">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bd287-274">Select **Save**.</span></span>
    8. <span data-ttu-id="bd287-275">Zamknij stronę **Edytor formuł**.</span><span class="sxs-lookup"><span data-stu-id="bd287-275">Close the **Formula editor** page.</span></span>
    9. <span data-ttu-id="bd287-276">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd287-276">Click **OK**.</span></span>

3. <span data-ttu-id="bd287-277">Wykonaj następujące kroki w celu buforowania pola **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="bd287-277">Follow these steps to do caching of the **\$TransType** field:</span></span>

    1. <span data-ttu-id="bd287-278">Wybierz pozycję **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="bd287-278">Select the **LedgerTransTypeList** item.</span></span>
    2. <span data-ttu-id="bd287-279">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="bd287-279">Select **Cache**.</span></span>
    3. <span data-ttu-id="bd287-280">Wybierz pozycję **VendTable.\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="bd287-280">Select the **VendTable.\$TransType** item.</span></span>
    4. <span data-ttu-id="bd287-281">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="bd287-281">Select **Cache**.</span></span>

    ![Włączanie buforowania pola $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. <span data-ttu-id="bd287-283">Aby pole **\$TransTypeRecord** zaczęło korzystać z buforowanego pola **\$TransType**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bd287-283">Follow these steps to change the **\$TransTypeRecord** field so that it starts to use the cached **\$TransType** field:</span></span>

    1. <span data-ttu-id="bd287-284">W okienku **Źródła danych** rozwiń pozycję **VendTable**, rozwiń pozycję **\<Relacje**, rozwiń pozycję **VendTrans.VendTable\_AccountNum** i wybierz pozycję **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.</span><span class="sxs-lookup"><span data-stu-id="bd287-284">In the **Data sources** pane, expand the **VendTable** item, expand the **\<Relations** item, expand the **VendTrans.VendTable\_AccountNum** item, and select the **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** item.</span></span>
    2. <span data-ttu-id="bd287-285">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="bd287-285">Select **Edit**.</span></span>
    3. <span data-ttu-id="bd287-286">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bd287-286">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="bd287-287">W polu **Formuła** znajdź następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="bd287-287">In the **Formula** field, find the following expression:</span></span>

        <span data-ttu-id="bd287-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span><span class="sxs-lookup"><span data-stu-id="bd287-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span></span>

    5. <span data-ttu-id="bd287-289">W polu **Formuła** wprowadź następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="bd287-289">In the **Formula** field, enter the following expression:</span></span>

        <span data-ttu-id="bd287-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span><span class="sxs-lookup"><span data-stu-id="bd287-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span></span>

    6. <span data-ttu-id="bd287-291">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bd287-291">Select **Save**.</span></span>
    7. <span data-ttu-id="bd287-292">Zamknij stronę **Edytor formuł**.</span><span class="sxs-lookup"><span data-stu-id="bd287-292">Close the **Formula editor** page.</span></span>
    8. <span data-ttu-id="bd287-293">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd287-293">Select **OK**.</span></span>

5. <span data-ttu-id="bd287-294">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bd287-294">Select **Save**.</span></span>
6. <span data-ttu-id="bd287-295">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="bd287-295">Close the **Model mapping designer** page.</span></span>
7. <span data-ttu-id="bd287-296">Zamknij stronę **Mapowanie modelu**.</span><span class="sxs-lookup"><span data-stu-id="bd287-296">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="bd287-297">Kończenie zmodyfikowanej wersji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-297">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="bd287-298">W RCS na stronie **Konfiguracje** na karcie skróconej **Wersje** wybierz wersję **1.2** konfiguracji **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-298">In RCS, on the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance trace mapping** configuration.</span></span>
2. <span data-ttu-id="bd287-299">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="bd287-299">Select **Change status**.</span></span>
3. <span data-ttu-id="bd287-300">Wybierz opcję **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bd287-300">Select **Complete**.</span></span>

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a><span data-ttu-id="bd287-301">Importowanie konfiguracji mapowania modelu ER z RCS do aplikacji</span><span class="sxs-lookup"><span data-stu-id="bd287-301">Import the modified ER model mapping configuration from RCS into the application</span></span>

<span data-ttu-id="bd287-302">Powtórz kroki opisane w sekcji [Importowanie konfiguracji ER z RCS do Finance and Operations](#import-configuration) tego tematu, aby zaimportować wersję 1.2 konfiguracji **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="bd287-302">Repeat the steps in the [Import an ER configuration from RCS into Finance and Operations](#import-configuration) section earlier in this topic to import version 1.2 of the **Performance trace mapping** configuration.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="bd287-303">Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="bd287-303">Run the modified ER solution to trace execution</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="bd287-304">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-304">Run the ER format</span></span>

<span data-ttu-id="bd287-305">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-305">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="work-with-the-execution-trace"></a><span data-ttu-id="bd287-306">Pracuj z śladem wykonania</span><span class="sxs-lookup"><span data-stu-id="bd287-306">Work with the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><span data-ttu-id="bd287-307">Eksportowanie wygenerowanego śledzenia z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bd287-307">Export the generated trace from the application</span></span>

<span data-ttu-id="bd287-308">Powtórz kroki opisane w sekcji [Eksportowanie wygenerowanego śladu z aplikacji](#export-trace) tego tematu, aby zapisać lokalnie nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-308">Repeat the steps in the [Export the generated trace from the application](#export-trace) section earlier in this topic to save a new performance trace locally.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><span data-ttu-id="bd287-309">Importowanie wygenerowanego śladu do RCS</span><span class="sxs-lookup"><span data-stu-id="bd287-309">Import the generated trace into RCS</span></span>

<span data-ttu-id="bd287-310">Powtórz kroki opisane w sekcji [Importowanie wygenerowanego śladu do RCS](#import-trace) tego tematu, aby zaimportować nowy ślad wydajności do RCS.</span><span class="sxs-lookup"><span data-stu-id="bd287-310">Repeat the steps in the [Import the generated trace into RCS](#import-trace) section earlier in this topic to import the new performance trace into RCS.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><span data-ttu-id="bd287-311">Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu</span><span class="sxs-lookup"><span data-stu-id="bd287-311">Use the performance trace for analysis in RCS – Model mapping</span></span>

<span data-ttu-id="bd287-312">Powtórz kroki opisane w sekcji [Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu](#use-trace) tego tematu, aby przeanalizować najnowszy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-312">Repeat the steps in the [Use the performance trace for analysis in RCS – Model mapping](#use-trace) section earlier in this topic to analyze the latest performance trace.</span></span>

<span data-ttu-id="bd287-313">Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="bd287-313">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="bd287-314">Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona.</span><span class="sxs-lookup"><span data-stu-id="bd287-314">The number of calls to database tables and data sources for this model mapping has been also reduced.</span></span> <span data-ttu-id="bd287-315">Wydajność całego rozwiązania ER uległa zatem poprawie.</span><span class="sxs-lookup"><span data-stu-id="bd287-315">Therefore, the performance of the whole ER solution has improved.</span></span>

![Informacje o śladzie źródła danych VendTable na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

<span data-ttu-id="bd287-317">Wartość **\[12\]** dla tabeli VendTable w śladzie wskazuje, że to źródło danych było wywoływane 12 razy.</span><span class="sxs-lookup"><span data-stu-id="bd287-317">In the trace information, the value **\[12\]** for the VendTable data source indicates that this data source was called 12 times.</span></span> <span data-ttu-id="bd287-318">Wartość **\[Q:6\]** wskazuje, że sześć wywołań zostało przetłumaczonych na wywołania bazy danych do tabeli VendTable.</span><span class="sxs-lookup"><span data-stu-id="bd287-318">The value **\[Q:6\]** indicates that six calls were translated to database calls to the VendTable table.</span></span> <span data-ttu-id="bd287-319">Wartość **\[C:6\]** wskazuje, że rekordy pobrane z bazy danych były buforowane i sześć innych wywołań zostało przetworzonych przy użyciu pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="bd287-319">The value **\[C:6\]** indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</span></span>

<span data-ttu-id="bd287-320">Liczba wywołań źródła danych LedgerTransTypeList została zmniejszona z z 9027 do 240.</span><span class="sxs-lookup"><span data-stu-id="bd287-320">Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</span></span>

![Informacje o śladzie źródła danych LedgerTransTypeList na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a><span data-ttu-id="bd287-322">Przejrzyj wyniki śledzenia wykonania w aplikacji</span><span class="sxs-lookup"><span data-stu-id="bd287-322">Review the execution trace in the application</span></span>

<span data-ttu-id="bd287-323">Oprócz RCS niektóre wersje mogą oferować możliwości korzystania z projektanta struktury ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-323">In addition to RCS, some versions might offer capabilities for an ER framework designer experience.</span></span> <span data-ttu-id="bd287-324">Te wersje zawierają opcję **Włącz tryb projektowania**, którą można włączyć.</span><span class="sxs-lookup"><span data-stu-id="bd287-324">These versions have an **Enable design mode** option that can be turned on.</span></span> <span data-ttu-id="bd287-325">Ta opcja znajduje się na karcie **Ogólne** strony **Parametry raportowania elektronicznego** otwieranej z obszaru roboczego **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bd287-325">You can find this option on the **General** tab of the **Electronic reporting parameters** page, which you can open from the **Electronic reporting** workspace.</span></span>

![Włącz opcję trybu projektowania na stronie parametry raportowania elektronicznego](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

<span data-ttu-id="bd287-327">W przypadku korzystania z jednej z tych wersji modułu Finance and Operations można analizować szczegóły generowanych śladów wydajności bezpośrednio w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bd287-327">If you use one of these versions, you can analyze the details of generated performance traces directly in the application.</span></span> <span data-ttu-id="bd287-328">Nie trzeba ich eksportować z aplikacji i importować do RCS.</span><span class="sxs-lookup"><span data-stu-id="bd287-328">You don't have to export them from the application and import them into RCS.</span></span>

## <a name="review-the-execution-trace-by-using-external-tools"></a><span data-ttu-id="bd287-329">Przeglądanie śladu wykonania za pomocą narzędzi zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="bd287-329">Review the execution trace by using external tools</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="bd287-330">Konfigurowanie parametrów użytkownika</span><span class="sxs-lookup"><span data-stu-id="bd287-330">Configure user parameters</span></span>

1. <span data-ttu-id="bd287-331">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bd287-331">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="bd287-332">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="bd287-332">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="bd287-333">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** w polu **Format śladu wykonania** wybierz opcję **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="bd287-333">In the **User parameters** dialog box, in the **Execution tracing** section, in the **Execution trace format** field, select **PerfView XML**.</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="bd287-334">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-334">Run the ER format</span></span>

<span data-ttu-id="bd287-335">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-335">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="bd287-336">Przeglądarka sieci Web zaproponuje pobranie pliku zip.</span><span class="sxs-lookup"><span data-stu-id="bd287-336">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="bd287-337">Ten plik zawiera ślad wydajności w formacie PerfView.</span><span class="sxs-lookup"><span data-stu-id="bd287-337">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="bd287-338">Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.</span><span class="sxs-lookup"><span data-stu-id="bd287-338">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span>

![Informacje o śledzeniu wydajności w formacie PerfView](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a><span data-ttu-id="bd287-340">Narzędzia zewnętrzne umożliwiają przejrzenie śledzenie wykonywania obejmującego kwerendy bazy danych</span><span class="sxs-lookup"><span data-stu-id="bd287-340">Use external tools to review an execution trace that includes database queries</span></span>

<span data-ttu-id="bd287-341">Ze względu na udoskonalenia, które zostały wprowadzone w ramach systemu, śledzenie wydajności generowane w formacie PerfView zawiera więcej szczegółów dotyczących wykonywania operacji na formacie ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-341">Because of improvements that have been made to the ER framework, the performance trace that is generated in PerfView format now offers more details about ER format execution.</span></span> <span data-ttu-id="bd287-342">W Microsoft Dynamics 365 for Finance and Operations wersji 10.0.4 (lipiec 2019) ten ślad może również zawierać szczegóły wykonanych kwerend SQL w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bd287-342">In Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019), this trace can also include details of executed SQL queries to the application database.</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="bd287-343">Konfigurowanie parametrów użytkownika</span><span class="sxs-lookup"><span data-stu-id="bd287-343">Configure user parameters</span></span>

1. <span data-ttu-id="bd287-344">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bd287-344">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bd287-345">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="bd287-345">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="bd287-346">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="bd287-346">In the **User parameters** dialog box, in the **Execution tracing** section, set the following parameters:</span></span>

    - <span data-ttu-id="bd287-347">W polu **Format śledzenia wykonania** wybierz opcję **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="bd287-347">In the **Execution trace format** field, select **PerfView XML**.</span></span>
    - <span data-ttu-id="bd287-348">Ustawienie opcji **Zbierz statystyki kwerendy** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bd287-348">Set the **Collect query statistics** option to **Yes**.</span></span>
    - <span data-ttu-id="bd287-349">Ustawienie opcji wartość **śledzenie kwerendy** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bd287-349">Set the **Trace query** option to **Yes**.</span></span>

    ![Sekcja śledzenia wykonania, okno dialogowe Parametry użytkownika](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a><span data-ttu-id="bd287-351">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="bd287-351">Run the ER format</span></span>

<span data-ttu-id="bd287-352">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="bd287-352">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="bd287-353">Przeglądarka sieci Web zaproponuje pobranie pliku zip.</span><span class="sxs-lookup"><span data-stu-id="bd287-353">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="bd287-354">Ten plik zawiera ślad wydajności w formacie PerfView.</span><span class="sxs-lookup"><span data-stu-id="bd287-354">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="bd287-355">Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.</span><span class="sxs-lookup"><span data-stu-id="bd287-355">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span> <span data-ttu-id="bd287-356">Teraz ten ślad zawiera szczegóły dostępu do bazy danych SQL podczas wykonywania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bd287-356">This trace now includes the details of SQL database access during the execution of the ER format.</span></span>

![Informacje o śledzeniu dla wykonanego formatu ER w PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a><span data-ttu-id="bd287-358">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bd287-358">Additional resources</span></span>

- [<span data-ttu-id="bd287-359">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="bd287-359">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="bd287-360">Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH</span><span class="sxs-lookup"><span data-stu-id="bd287-360">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]