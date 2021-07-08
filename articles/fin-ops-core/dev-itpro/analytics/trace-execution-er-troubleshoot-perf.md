---
title: Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością
description: Ten temat zawiera informacje dotyczące korzystania z funkcji śledzenia wydajności w module Raportowanie elektroniczne (ER) w celu rozwiązywania problemów z wydajnością.
author: NickSelin
ms.date: 06/22/2021
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
ms.openlocfilehash: 7fbec962fea374afdbabaad48a42dad380708678
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295580"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a><span data-ttu-id="6b1df-103">Śledzenie wykonywania formatów ER w celu rozwiązywania problemów z wydajnością</span><span class="sxs-lookup"><span data-stu-id="6b1df-103">Trace the execution of ER formats to troubleshoot performance issues</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6b1df-104">W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów elektronicznych należy zdefiniować metodę, która jest używana do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-104">As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="6b1df-105">Funkcja śledzenia wydajności systemu ER pozwala znacznie zmniejszyć koszty i czas, jakie pochłania zbieranie szczegółów dotyczących wykonywania formatów ER i używanie ich do rozwiązywania problemów z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="6b1df-105">The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</span></span> <span data-ttu-id="6b1df-106">Ten samouczek zawiera wskazówki dotyczące zbierania śladów wydajności wykonywanych formatów ER w module oraz sposobu używania informacji z tych śladów w celu zwiększania wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-106">This tutorial provides guidelines about how to take performance traces for executed ER formats, and how to use the information from these traces to help improve performance.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b1df-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="6b1df-107">Prerequisites</span></span>

<span data-ttu-id="6b1df-108">Aby wykonać przykłady opisane w tym samouczku, musisz mieć następujące uprawnienia dostępu:</span><span class="sxs-lookup"><span data-stu-id="6b1df-108">To complete the examples in this tutorial, you must have the following access:</span></span>

- <span data-ttu-id="6b1df-109">Dostęp do jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="6b1df-109">Access to one of the following roles:</span></span>

    - <span data-ttu-id="6b1df-110">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6b1df-110">Electronic reporting developer</span></span>
    - <span data-ttu-id="6b1df-111">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6b1df-111">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6b1df-112">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="6b1df-112">System administrator</span></span>

- <span data-ttu-id="6b1df-113">Dostęp do wystąpienia Regulatory Configuration Service (RCS), które zostało zainicjowane dla tej samej dzierżawy co aplikacja, dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="6b1df-113">Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as the application, for one of the following roles:</span></span>

    - <span data-ttu-id="6b1df-114">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6b1df-114">Electronic reporting developer</span></span>
    - <span data-ttu-id="6b1df-115">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="6b1df-115">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6b1df-116">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="6b1df-116">System administrator</span></span>

<span data-ttu-id="6b1df-117">Musisz również pobrać i lokalnie zapisać następujące pliki.</span><span class="sxs-lookup"><span data-stu-id="6b1df-117">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="6b1df-118">Plik</span><span class="sxs-lookup"><span data-stu-id="6b1df-118">File</span></span>                                  | <span data-ttu-id="6b1df-119">Zawartość</span><span class="sxs-lookup"><span data-stu-id="6b1df-119">Content</span></span>                               |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="6b1df-120">Model śledzenia wydajności, wersja 1</span><span class="sxs-lookup"><span data-stu-id="6b1df-120">Performance trace model.version.1</span></span>     | [<span data-ttu-id="6b1df-121">Przykładowa konfiguracja modelu danych ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-121">Sample ER data model configuration</span></span>](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| <span data-ttu-id="6b1df-122">Metadane śledzenia wydajności, wersja 1</span><span class="sxs-lookup"><span data-stu-id="6b1df-122">Performance trace metadata.version.1</span></span>  | [<span data-ttu-id="6b1df-123">Przykładowa konfiguracja metadanych ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-123">Sample ER metadata configuration</span></span>](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| <span data-ttu-id="6b1df-124">Mapowanie śledzenia wydajności, wersja 1.1</span><span class="sxs-lookup"><span data-stu-id="6b1df-124">Performance trace mapping.version.1.1</span></span> | [<span data-ttu-id="6b1df-125">Przykładowa konfiguracja mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-125">Sample ER model mapping configuration</span></span>](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| <span data-ttu-id="6b1df-126">Format śladu wydajności, wersja 1.1</span><span class="sxs-lookup"><span data-stu-id="6b1df-126">Performance trace format.version.1.1</span></span>  | [<span data-ttu-id="6b1df-127">Przykładowa konfiguracja formatu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-127">Sample ER format configuration</span></span>](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a><span data-ttu-id="6b1df-128">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-128">Configure ER parameters</span></span>

<span data-ttu-id="6b1df-129">Każdy ślad wydajności modułu ER generowany w aplikacji jest przechowywany jako załącznik do rekordu dziennika wykonania.</span><span class="sxs-lookup"><span data-stu-id="6b1df-129">Each ER performance trace that is generated in the application is stored as an attachment of the execution log record.</span></span> <span data-ttu-id="6b1df-130">Do zarządzania tymi załącznikami służy struktura zarządzania dokumentami (DM).</span><span class="sxs-lookup"><span data-stu-id="6b1df-130">The Document management (DM) framework is used to manage these attachments.</span></span> <span data-ttu-id="6b1df-131">Parametry ER należy skonfigurować z wyprzedzeniem, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-131">You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="6b1df-132">W obszarze roboczym **Raportowanie elektroniczne** wybierz łącze **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-132">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="6b1df-133">Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-133">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Strona parametrów raportowania elektronicznego](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

<span data-ttu-id="6b1df-135">Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):</span><span class="sxs-lookup"><span data-stu-id="6b1df-135">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="6b1df-136">**Klasa:** Dołącz plik</span><span class="sxs-lookup"><span data-stu-id="6b1df-136">**Class:** Attach file</span></span>
- <span data-ttu-id="6b1df-137">**Grupa:** Plik</span><span class="sxs-lookup"><span data-stu-id="6b1df-137">**Group:** File</span></span>

![Strona Typy dokumentów](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> <span data-ttu-id="6b1df-139">Wybrany typ dokumentu musi być dostępny we wszystkich firmach bieżącego wystąpienia, ponieważ załączniki DM są specyficzne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-139">The selected document type must be available in every company of the current instance, because DM attachments are company-specific.</span></span>

### <a name="configure-rcs-parameters"></a><span data-ttu-id="6b1df-140">Konfigurowanie parametrów RCS</span><span class="sxs-lookup"><span data-stu-id="6b1df-140">Configure RCS parameters</span></span>

<span data-ttu-id="6b1df-141">Ślady wydajności ER generowane zostaną zaimportowane do RCS w celu analizy za pomocą projektanta formatu ER i projektanta mapowania ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-141">ER performance traces that are generated will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</span></span> <span data-ttu-id="6b1df-142">Ponieważ dane śledzenia wydajności ER są przechowywane jako załączniki rekordu dziennika wykonania powiązanego z formatem ER, należy z wyprzedzeniem skonfigurować parametry RCS, aby określić typ dokumentu DM, który ma być używany do dołączania śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-142">Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="6b1df-143">W wystąpieniu RCS, które zostało zainicjowane dla danej firmy, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-143">In the instance of RCS that has been provisioned for your company, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="6b1df-144">Następnie na stronie **Parametry raportowania elektronicznego**, na karcie **Załączniki**, w polu **Inne** wybierz typ dokumentu DM, który będzie używany do śladów wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-144">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Strona parametrów raportowania elektronicznego w RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

<span data-ttu-id="6b1df-146">Aby typ dokumentu DM był dostępny w polu wyszukiwania **Inne**, musi być skonfigurowany w następujący sposób na stronie **Typy dokumentów** (**Administrowanie organizacją \> Zarządzanie dokumentami \> Typy dokumentów**):</span><span class="sxs-lookup"><span data-stu-id="6b1df-146">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="6b1df-147">**Klasa:** Dołącz plik</span><span class="sxs-lookup"><span data-stu-id="6b1df-147">**Class:** Attach file</span></span>
- <span data-ttu-id="6b1df-148">**Grupa:** Plik</span><span class="sxs-lookup"><span data-stu-id="6b1df-148">**Group:** File</span></span>

## <a name="design-an-er-solution"></a><span data-ttu-id="6b1df-149">Projektowanie rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-149">Design an ER solution</span></span>

<span data-ttu-id="6b1df-150">Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-150">Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</span></span> <span data-ttu-id="6b1df-151">Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**).</span><span class="sxs-lookup"><span data-stu-id="6b1df-151">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable \> Vendors \> All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="6b1df-152">Chcesz jednak mieć wszystkie transakcje dostawcy równocześnie w jednym dokumencie elektronicznym w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="6b1df-152">However, you want to have all vendor transaction at the same time in one electronic document in XML format.</span></span> <span data-ttu-id="6b1df-153">To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.</span><span class="sxs-lookup"><span data-stu-id="6b1df-153">This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</span></span>

1. <span data-ttu-id="6b1df-154">Zaloguj się do wystąpienia RCS, które zostało zainicjowane dla danej firmy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-154">Sign in to the instance of RCS that has been provisioned for your company.</span></span>
2. <span data-ttu-id="6b1df-155">W tym samouczku utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="6b1df-155">In this tutorial, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="6b1df-156">Upewnij się zatem, że ten dostawca konfiguracji jest dodany do RCS i wybrany jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="6b1df-156">Therefore, make sure that this configuration provider has been added to RCS and selected as active.</span></span> <span data-ttu-id="6b1df-157">Szczegółowe instrukcje znajdują się w procedurze [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="6b1df-157">For instructions, see the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span>
3. <span data-ttu-id="6b1df-158">W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-158">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="6b1df-159">Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do RCS, w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="6b1df-159">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="6b1df-160">Dla każdej konfiguracji wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b1df-160">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="6b1df-161">W okienku akcji wybierz opcję **Wymiana \> Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-161">On the Action Pane, select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="6b1df-162">Kliknij przycisk **Przeglądaj**, aby wybrać odpowiedni plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="6b1df-162">Select **Browse** to select the appropriate file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="6b1df-163">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-163">Select **OK**.</span></span>

    ![Strona Konfiguracje w RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a><span data-ttu-id="6b1df-165">Uruchom rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="6b1df-165">Run the ER solution to trace execution</span></span>

<span data-ttu-id="6b1df-166">Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-166">Assume that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="6b1df-167">Chcesz teraz przetestować je w swoim wystąpieniu oraz przeanalizować wydajność wykonywania.</span><span class="sxs-lookup"><span data-stu-id="6b1df-167">You now want to test it in your instance and analyze execution performance.</span></span>

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a><span data-ttu-id="6b1df-168">Importowanie konfiguracji ER z RCS do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6b1df-168">Import an ER configuration from RCS into Finance and Operations</span></span>

1. <span data-ttu-id="6b1df-169">Zaloguj się do swojego wystąpienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b1df-169">Sign in to your application instance.</span></span>
2. <span data-ttu-id="6b1df-170">W tym samouczku zaimportujesz konfiguracje z wystąpienia RCS (w którym projektujesz składniki ER) do swojego wystąpienia (w którym je testujesz i ostatecznie ich używasz).</span><span class="sxs-lookup"><span data-stu-id="6b1df-170">For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your instance (where you test and finally use them).</span></span> <span data-ttu-id="6b1df-171">Upewnij się zatem, że zostały przygotowane wszystkie wymagane artefakty.</span><span class="sxs-lookup"><span data-stu-id="6b1df-171">Therefore, you must make sure that all the required artifacts have been prepared.</span></span> <span data-ttu-id="6b1df-172">Szczegółowe instrukcje zawiera procedura [Importowanie konfiguracji raportowania elektronicznego (RE) z usługi Regulatory Configuration Services (RCS)](rcs-download-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="6b1df-172">For instructions, see the [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md) procedure.</span></span>
3. <span data-ttu-id="6b1df-173">Aby zaimportować konfiguracje z RCS do aplikacji, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b1df-173">Follow these steps to import the configurations from RCS into the application:</span></span>

    1. <span data-ttu-id="6b1df-174">W obszarze roboczym **Raportowanie elektroniczne** na kafelku dostawcy konfiguracji **Litware, Inc.** wybierz opcję **Repozytoria**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-174">In the **Electronic reporting** workspace, on the tile for the **Litware, Inc.** configuration provider, select **Repositories**.</span></span>
    2. <span data-ttu-id="6b1df-175">Na stronie **Repozytorium konfiguracji** zaznacz repozytorium typu **RCS**, a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-175">On the **Configuration repository** page, select the repository of the **RCS** type, and then select **Open**.</span></span>
    3. <span data-ttu-id="6b1df-176">Na skróconej karcie **Konfiguracje** wybierz konfigurację **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-176">On the **Configurations** FastTab, select the **Performance trace format** configuration.</span></span>
    4. <span data-ttu-id="6b1df-177">Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji, a następnie kliknij przycisk **Importuj**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-177">On the **Versions** FastTab, select version **1.1** of the selected configuration, and then select **Import**.</span></span>

    ![Strona Repozytorium konfiguracji](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

<span data-ttu-id="6b1df-179">Odpowiednie wersje konfiguracji modelu danych i mapowania modelu są automatycznie importowane jako wymagania wstępne dla importowanej konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-179">The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="6b1df-180">Włączanie śledzenia wydajności ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-180">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="6b1df-181">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-181">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="6b1df-182">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-182">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="6b1df-183">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b1df-183">In the **User parameters** dialog box, in the **Execution tracing** section, follow these steps:</span></span>

    1. <span data-ttu-id="6b1df-184">W polu **Format śladu wykonania** możesz określić format generowanego śladu wydajności, w którym są przechowywane szczegóły dotyczące wykonania, w odniesieniu do formatu ER i elementów mapowania:</span><span class="sxs-lookup"><span data-stu-id="6b1df-184">In the **Execution trace format** field, specify the format of the generated performance trace that the execution details should be stored in for ER format and mapping elements:</span></span>

        - <span data-ttu-id="6b1df-185">**Format śladu debugowania** – wybierz tę wartość, jeśli planujesz interaktywnie uruchomić format ER, który ma krótki czas wykonania.</span><span class="sxs-lookup"><span data-stu-id="6b1df-185">**Debug trace format** – Select this value if you plan to interactively run an ER format that has a short execution time.</span></span> <span data-ttu-id="6b1df-186">Następnie rozpoczyna się zbieranie szczegółów dotyczących wykonania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-186">The collection of details about ER format execution is then started.</span></span> <span data-ttu-id="6b1df-187">Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="6b1df-187">When this value is selected, the performance trace collects information about the time that is spent on the following actions:</span></span>

            - <span data-ttu-id="6b1df-188">Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-188">Running each data source in the model mapping that is called to get data</span></span>
            - <span data-ttu-id="6b1df-189">Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="6b1df-189">Processing each format item to enter data in the output that is generated</span></span>

            <span data-ttu-id="6b1df-190">W przypadku wybrania wartości **Format śladu debugowania** można analizować zawartość śladu w konstruktorze operacji ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-190">If you select the **Debug trace format** value, you can analyze the content of the trace in the ER Operation designer.</span></span> <span data-ttu-id="6b1df-191">Tam można zobaczyć format ER lub elementy mapowania, które są wymienione w śladzie.</span><span class="sxs-lookup"><span data-stu-id="6b1df-191">There, you can view the ER format or mapping elements that are mentioned in the trace.</span></span>

        - <span data-ttu-id="6b1df-192">**Zagregowany format śledzenia** – wybierz tę wartość, jeśli planujesz uruchomić format ER, który ma długi czas wykonania w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="6b1df-192">**Aggregated trace format** – Select this value if you plan to run an ER format that has a long execution time in batch mode.</span></span> <span data-ttu-id="6b1df-193">Następnie rozpoczyna się zbieranie zagregowanych szczegółów dotyczących wykonania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-193">The collection of the aggregated details about ER format execution is then started.</span></span> <span data-ttu-id="6b1df-194">Po wybraniu tej wartości ślad wydajności będzie zbierać informacje o czasie poświęcanym na następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="6b1df-194">When this value is selected, the performance trace collects information about the time that is spent on the following actions:</span></span>

            - <span data-ttu-id="6b1df-195">Uruchamianie poszczególnych źródeł danych w mapowaniu modelu, które są wywoływane w celu uzyskania danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-195">Running each data source in the model mapping that is called to get data</span></span>
            - <span data-ttu-id="6b1df-196">Uruchamianie poszczególnych źródeł danych w mapowaniu formatu, które są wywoływane w celu uzyskania danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-196">Running each data source in the format mapping that is called to get data</span></span>
            - <span data-ttu-id="6b1df-197">Przetwarzanie poszczególnych elementów formatu w celu wprowadzenia danych w generowanych danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="6b1df-197">Processing each format item to enter data in the output that is generated</span></span>

            <span data-ttu-id="6b1df-198">Wartość **Format śladu zagregowanego** jest dostępna w Microsoft Dynamics 365 Finance w wersji 10.0.20 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-198">The **Aggregated trace format** value is available in Microsoft Dynamics 365 Finance version 10.0.20 and later.</span></span>

            <span data-ttu-id="6b1df-199">W projektancie formatu ER i projektancie odwzorowania modelu ER możesz zobaczyć całkowity czas wykonania dla pojedynczego komponentu.</span><span class="sxs-lookup"><span data-stu-id="6b1df-199">In the ER format designer and ER model mapping designer, you can view the total execution time for a single component.</span></span> <span data-ttu-id="6b1df-200">Dodatkowo, ślad zawiera szczegóły dotyczące wykonania, takie jak liczba wykonań oraz minimalny i maksymalny czas pojedynczego wykonania.</span><span class="sxs-lookup"><span data-stu-id="6b1df-200">Additionally, the trace contains details about the execution, such as the number of executions, and the minimum and maximum time of a single execution.</span></span>

            > [!NOTE]
            > <span data-ttu-id="6b1df-201">To śledzenie jest zbierane na podstawie ścieżki śledzonych składników.</span><span class="sxs-lookup"><span data-stu-id="6b1df-201">This trace is collected based on the traced components path.</span></span> <span data-ttu-id="6b1df-202">Dlatego statystyki mogą być niepoprawne, gdy pojedynczy komponent nadrzędny zawiera kilka nienazwanych komponentów podrzędnych lub gdy kilka komponentów podrzędnych ma tę samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="6b1df-202">Therefore, the statistics might be incorrect when a single parent component contains several unnamed child components, or when several child components have the same name.</span></span>

    2. <span data-ttu-id="6b1df-203">Wybór ustawienia **Tak** następujących opcji umożliwia zbieranie szczegółów wykonania mapowania modelu ER i składników formatu ER:</span><span class="sxs-lookup"><span data-stu-id="6b1df-203">Set the following options to **Yes** to collect specific details of the execution of the ER model mapping and ER format components:</span></span>

        - <span data-ttu-id="6b1df-204">**Zbieraj statystyki zapytań** — po włączeniu tej opcji śledzenie wydajności będzie zbierać następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="6b1df-204">**Collect query statistics** – When this option is turned on, the performance trace will collect the following information:</span></span>

            - <span data-ttu-id="6b1df-205">Liczba wywołań bazy danych przez źródła danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-205">The number of database calls that were made by data sources</span></span>
            - <span data-ttu-id="6b1df-206">Liczba powielonych wywołań do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-206">The number of duplicate calls to the database</span></span>
            - <span data-ttu-id="6b1df-207">Szczegóły instrukcji SQL użytych w wywołaniach bazy danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-207">Details of the SQL statements that were used to make database calls</span></span>

        - <span data-ttu-id="6b1df-208">**Śledzenie dostępu funkcji buforowania** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o użyciu buforu mapowania modelu ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-208">**Trace access of caching** – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</span></span>
        - <span data-ttu-id="6b1df-209">**Śledzenie dostępu do danych** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie wywołań do bazy danych dla wykonywanych źródeł danych typu listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="6b1df-209">**Trace data access** – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</span></span>
        - <span data-ttu-id="6b1df-210">**Element stałotekstowy listy śledzenia** — jeśli ta opcja jest włączona, śledzenie wydajności będzie zbierać informacje o liczbie rekordów, których żądają źródła danych typu listy rekordów.</span><span class="sxs-lookup"><span data-stu-id="6b1df-210">**Trace list enumeration** – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b1df-211">Parametry w oknie dialogowym **Parametry użytkownika** są specyficzne dla użytkownika i bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-211">The parameters in the **User parameters** dialog box are specific to the user and the current company.</span></span>

    ![Okno dialogowe parametry użytkownika](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a><span data-ttu-id="6b1df-213">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-213">Run the ER format</span></span>

1. <span data-ttu-id="6b1df-214">Wybierz pole firmę **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-214">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="6b1df-215">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-215">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3. <span data-ttu-id="6b1df-216">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-216">On the **Configurations** page, in the configuration tree, select the **Performance trace format** item.</span></span>
4. <span data-ttu-id="6b1df-217">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-217">On the Action Pane, select **Run**.</span></span>

<span data-ttu-id="6b1df-218">Generowany plik zawiera informacje dotyczące 265 transakcji dla sześciu dostawców.</span><span class="sxs-lookup"><span data-stu-id="6b1df-218">Notice that the file that is generated presents information about 265 transactions for six vendors.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="6b1df-219">Przeglądanie śladu wykonania</span><span class="sxs-lookup"><span data-stu-id="6b1df-219">Review the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a><span data-ttu-id="6b1df-220">Eksportowanie wygenerowanego śledzenia z aplikacji</span><span class="sxs-lookup"><span data-stu-id="6b1df-220">Export the generated trace from the application</span></span>

<span data-ttu-id="6b1df-221">Ślady wydajności są odłączane od źródłowego formatu ER i można je serializować w zewnętrznym pliku zip.</span><span class="sxs-lookup"><span data-stu-id="6b1df-221">Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</span></span>

1. <span data-ttu-id="6b1df-222">Otwórz **Administracja organizacji \> Elektroniczne raportowanie \> Dzienniki debugowania konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-222">Go to **Organization administration \> Electronic reporting \> Configuration debug logs**.</span></span>
2. <span data-ttu-id="6b1df-223">Na stronie **Dzienniki przebiegu raportowania elektronicznego** w lewym okienku w polu **Nazwa konfiguracji** wybierz opcję **Format śladu wydajności**, aby znaleźć rekordy dziennika wygenerowane przez wykonanie konfiguracji **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-223">On the **Electronic reporting run logs** page, in the left pane, in the **Configuration name** field, select **Performance trace format** to find the log records that have been generated by the execution of the **Performance trace format** configuration.</span></span>
3. <span data-ttu-id="6b1df-224">Naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony lub naciśnij **Ctrl+Shift+A**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-224">Select the **Attachments** button (the paper clip symbol) in the upper-right corner of the page, or press **Ctrl+Shift+A**.</span></span>

    ![Przycisk Załączniki na stronie Dzienniki przebiegu raportowania elektronicznego.](./media/GER-PerfTrace-GER-DebugLog.png)

4. <span data-ttu-id="6b1df-226">Na stronie **Załączniki do dzienników przebiegu raportowania elektronicznego** w okienku akcji kliknij przycisk **Otwórz**, aby pobrać ślad wydajności jako plik zip i zapisać go lokalnie.</span><span class="sxs-lookup"><span data-stu-id="6b1df-226">On the **Attachments for Electronic reporting run logs** page, on the Action Pane, select **Open** to get the performance trace as a zip file and store it locally.</span></span>

    ![Załączniki do dzienników przebiegu raportowania elektronicznego](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> <span data-ttu-id="6b1df-228">Generowany ślad zawiera odwołanie do źródłowego raportu ER w postaci unikatowego identyfikatora raportu tylko w formacie **GUID**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-228">The trace that is generated has a reference to the source ER report via a unique report identifier in **GUID** format only.</span></span> <span data-ttu-id="6b1df-229">Numerowanie wersji formatu nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="6b1df-229">The version numbering of the format isn't considered.</span></span>

<span data-ttu-id="6b1df-230">Skojarzenie między śladem wydajności, który został wygenerowany dla wykonywanego formatu ER, a mapowaniem modelu ER jest oparte na użytym deskryptorze głównym i wspólnym modelu danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-230">Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</span></span> <span data-ttu-id="6b1df-231">Numerowanie wersji formatu i mapowania modelu nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="6b1df-231">The version numbering of the format and model mapping isn't considered.</span></span> <span data-ttu-id="6b1df-232">Ustawienie opcji **Domyślne mapowanie modelu** mapowania modelu również nie jest uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="6b1df-232">The setting of the **Default for model mapping** flag for the model mapping also isn't considered.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a><span data-ttu-id="6b1df-233">Importowanie wygenerowanego śladu do RCS</span><span class="sxs-lookup"><span data-stu-id="6b1df-233">Import the generated trace into RCS</span></span>

1. <span data-ttu-id="6b1df-234">W RCS w obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-234">In RCS, in the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
2. <span data-ttu-id="6b1df-235">Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń pozycję **Model śladu wydajności** i wybierz opcję **Format śladu wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-235">On the **Configurations** page, in the configuration tree, expand the **Performance trace model** item, and select the **Performance trace format** item.</span></span>
3. <span data-ttu-id="6b1df-236">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-236">On the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="6b1df-237">Na stronie **Projektant formatu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-237">On the **Format designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="6b1df-238">W oknie dialogowym **Ustawienia wyników śledzenia wydajności** wybierz opcję **Importuj ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-238">In the **Performance trace result settings** dialog box, select **Import performance trace**.</span></span>
6. <span data-ttu-id="6b1df-239">Kliknij przycisk **Przeglądaj**, a następnie zaznacz plik zip, który został wcześniej eksportowany.</span><span class="sxs-lookup"><span data-stu-id="6b1df-239">Select **Browse** to select the zip file that you exported earlier.</span></span>
7. <span data-ttu-id="6b1df-240">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-240">Select **OK**.</span></span>

    ![Okno dialogowe ustawień wyników śledzenia wydajności w RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a><span data-ttu-id="6b1df-242">Użycie śledzenia wydajności do analizy w RCS — wykonanie formatu</span><span class="sxs-lookup"><span data-stu-id="6b1df-242">Use the performance trace for analysis in RCS – Format execution</span></span>

1. <span data-ttu-id="6b1df-243">W RCS na stronie **Projektant formatu** kliknij przycisk **Rozwiń/Zwiń**, aby rozwinąć zawartość wszystkich elementów formatu.</span><span class="sxs-lookup"><span data-stu-id="6b1df-243">In RCS, on the **Format designer** page, select **Expand/collapse** to expand the content of all format items.</span></span>

    <span data-ttu-id="6b1df-244">Zostaną wyświetlone dodatkowe informacje dotyczące niektórych pozycji bieżącego formatu:</span><span class="sxs-lookup"><span data-stu-id="6b1df-244">Notice that additional information is shown for some items of the current format:</span></span>

    - <span data-ttu-id="6b1df-245">Rzeczywisty czas spędzony na wprowadzaniu danych w wygenerowanych danych wyjściowych przy użyciu elementu formatu</span><span class="sxs-lookup"><span data-stu-id="6b1df-245">The actual time that was spent entering data in the generated output by using the format item</span></span>
    - <span data-ttu-id="6b1df-246">Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wygenerowanie wszystkich danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="6b1df-246">The same time expressed as a percentage of the total time that was spent generating the whole output</span></span>

    ![Strona projektanta formatu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. <span data-ttu-id="6b1df-248">Zamknij stronę **Projektant formatu**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-248">Close **Format designer** page.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a><span data-ttu-id="6b1df-249">Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu</span><span class="sxs-lookup"><span data-stu-id="6b1df-249">Use the performance trace for analysis in RCS – Model mapping</span></span>

1. <span data-ttu-id="6b1df-250">W RCS na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-250">In RCS, on the **Configurations** page, in the configuration tree, select the **Performance trace mapping** item.</span></span>
2. <span data-ttu-id="6b1df-251">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-251">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="6b1df-252">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-252">Select **Designer**.</span></span>
4. <span data-ttu-id="6b1df-253">Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-253">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="6b1df-254">Wybierz ślad, który zaimportowano wcześniej.</span><span class="sxs-lookup"><span data-stu-id="6b1df-254">Select the trace that you imported earlier.</span></span>
6. <span data-ttu-id="6b1df-255">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-255">Select **OK**.</span></span>

<span data-ttu-id="6b1df-256">Zostaną udostępnione nowe informacje dotyczące niektórych pozycji źródła danych bieżącego mapowania modelu:</span><span class="sxs-lookup"><span data-stu-id="6b1df-256">Notice that new information becomes available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="6b1df-257">Rzeczywisty czas poświęcony na uzyskiwanie danych przy użyciu źródła danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-257">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="6b1df-258">Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wykonywanie całego mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="6b1df-258">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

<span data-ttu-id="6b1df-259">Podczas uruchamiania źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum ER poinformuje, że bieżące mapowanie modelu duplikuje żądania bazy danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-259">Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source is run.</span></span> <span data-ttu-id="6b1df-260">To duplikowanie wynika z tego, że lista transakcji dostawcy jest wywoływana dwukrotnie dla każdego rekordu dostawcy przetwarzanego w ramach iteracji:</span><span class="sxs-lookup"><span data-stu-id="6b1df-260">This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</span></span>

- <span data-ttu-id="6b1df-261">Jedno wywołanie jest wykonywane w celu wprowadzenia szczegółów poszczególnych transakcji do modelu danych na podstawie skonfigurowanych powiązań.</span><span class="sxs-lookup"><span data-stu-id="6b1df-261">One call is made to enter details of each transaction in the data model, based on configured bindings.</span></span>
- <span data-ttu-id="6b1df-262">Jedno wywołanie jest wykonywane w celu wprowadzenia obliczonej liczby transakcji danego dostawcy do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-262">One call is made to enter the calculated number of transactions per vendor in the data model.</span></span>

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

<span data-ttu-id="6b1df-264">Wartość **\[Q:530\]** wskazuje, że tabela VendTrans została wywołana 530 razy, aby zwrócić rekord z tej tabeli do źródła danych VendTable/\<Relations/VendTrans.VendTable\_AccountNum.</span><span class="sxs-lookup"><span data-stu-id="6b1df-264">The value **\[Q:530\]** indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source.</span></span> <span data-ttu-id="6b1df-265">Wartość **\[530\]** wskazuje, że źródło danych VendTable\</Relations/VendTrans.VendTable\_AccountNum zostało wywołane 530 razy, aby zwrócić rekord z tego źródła danych i wprowadzić jego szczegóły do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-265">The value **\[530\]** indicates that the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</span></span>

<span data-ttu-id="6b1df-266">Zaleca się buforowanie źródła danychVendTable/\<Relations/VendTrans.VendTable\_AccountNum w celu zmniejszenia liczby wywołań wykonywanych w celu uzyskania szczegółów dotyczących 265 transakcji i zwiększenia wydajności mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="6b1df-266">We recommend that you use caching for the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</span></span>

<span data-ttu-id="6b1df-267">Przydatne może być także zmniejszenie liczby wywołań źródła danych LedgerTransTypeList.</span><span class="sxs-lookup"><span data-stu-id="6b1df-267">It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</span></span> <span data-ttu-id="6b1df-268">To źródło danych służy do kojarzenia poszczególnych wartości wyliczenia **LedgerTransType** z etykietą.</span><span class="sxs-lookup"><span data-stu-id="6b1df-268">This data source is used to associate each value of the **LedgerTransType** enumeration with its label.</span></span> <span data-ttu-id="6b1df-269">Korzystając z tego źródła danych, można znaleźć odpowiednią etykietę i wprowadzić ją do modelu danych dla poszczególnych transakcji dostawcy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-269">By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</span></span> <span data-ttu-id="6b1df-270">Bieżąca liczba wywołań tego źródła danych (9027) jest dość duża jak na 265 transakcji.</span><span class="sxs-lookup"><span data-stu-id="6b1df-270">The current number of calls to this data source (9,027) is quite high for 265 transactions.</span></span>

![Strona projektanta mapowania modelu w RCS pokazująca 9027 wywołań źródła danych](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="6b1df-272">Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania</span><span class="sxs-lookup"><span data-stu-id="6b1df-272">Improve the model mapping based on information from the execution trace</span></span>

### <a name="modify-the-logic-of-the-model-mapping"></a><span data-ttu-id="6b1df-273">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="6b1df-273">Modify the logic of the model mapping</span></span>

1. <span data-ttu-id="6b1df-274">Aby zapobiec duplikowaniu wywołań bazy danych, należy użyć buforowania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="6b1df-274">Follow these steps to use caching, to help prevent duplicate calls to the database:</span></span>

    1. <span data-ttu-id="6b1df-275">W RCS na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz pozycję **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-275">In RCS, on the **Model mapping designer** page, in the **Data sources** pane, select the **VendTable** item.</span></span>
    2. <span data-ttu-id="6b1df-276">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-276">Select **Cache**.</span></span>
    3. <span data-ttu-id="6b1df-277">Rozwiń pozycję **VendTable**, rozwiń listę relacji jeden-do-wielu źródła danych VendTable (pozycja **\<Relacje**) i wybierz opcję **VendTrans.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-277">Expand the **VendTable** item, expand the list of one-to-many relations for the VendTable data source (the **\<Relations** item), and select the **VendTrans.VendTable\_AccountNum** item.</span></span>
    4. <span data-ttu-id="6b1df-278">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-278">Select **Cache**.</span></span>

    ![Włączanie buforowania w celu zapobiegania duplikowaniu wywołań](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. <span data-ttu-id="6b1df-280">Aby sprowadzić źródło danych LedgerTransTypeList do zakresu źródła danych VendTable, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6b1df-280">Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</span></span>

    1. <span data-ttu-id="6b1df-281">W okienku **Typy źródła danych** rozwiń pozycję **Funkcje** i wybierz pozycję **Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-281">In the **Data source types** pane, expand the **Functions** item, and select the **Calculated field** item.</span></span>
    2. <span data-ttu-id="6b1df-282">W okienku **Źródła danych** wybierz pozycję **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-282">In the **Data sources** pane, select the **VendTable** item.</span></span>
    3. <span data-ttu-id="6b1df-283">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-283">Select **Add**.</span></span>
    4. <span data-ttu-id="6b1df-284">W polu **Nazwa** wprowadź nazwę **\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-284">In the **Name** field, enter **\$TransType**.</span></span>
    5. <span data-ttu-id="6b1df-285">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-285">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="6b1df-286">W polu **Formuła** wpisz tekst **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-286">In the **Formula** field, enter **LedgerTransTypeList**.</span></span>
    7. <span data-ttu-id="6b1df-287">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-287">Select **Save**.</span></span>
    8. <span data-ttu-id="6b1df-288">Zamknij stronę **Edytor formuł**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-288">Close the **Formula editor** page.</span></span>
    9. <span data-ttu-id="6b1df-289">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-289">Click **OK**.</span></span>

3. <span data-ttu-id="6b1df-290">Wykonaj następujące kroki w celu buforowania pola **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="6b1df-290">Follow these steps to do caching of the **\$TransType** field:</span></span>

    1. <span data-ttu-id="6b1df-291">Wybierz pozycję **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-291">Select the **LedgerTransTypeList** item.</span></span>
    2. <span data-ttu-id="6b1df-292">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-292">Select **Cache**.</span></span>
    3. <span data-ttu-id="6b1df-293">Wybierz pozycję **VendTable.\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-293">Select the **VendTable.\$TransType** item.</span></span>
    4. <span data-ttu-id="6b1df-294">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-294">Select **Cache**.</span></span>

    ![Włączanie buforowania pola $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. <span data-ttu-id="6b1df-296">Aby pole **\$TransTypeRecord** zaczęło korzystać z buforowanego pola **\$TransType**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6b1df-296">Follow these steps to change the **\$TransTypeRecord** field so that it starts to use the cached **\$TransType** field:</span></span>

    1. <span data-ttu-id="6b1df-297">W okienku **Źródła danych** rozwiń pozycję **VendTable**, rozwiń pozycję **\<Relacje**, rozwiń pozycję **VendTrans.VendTable\_AccountNum** i wybierz pozycję **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-297">In the **Data sources** pane, expand the **VendTable** item, expand the **\<Relations** item, expand the **VendTrans.VendTable\_AccountNum** item, and select the **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** item.</span></span>
    2. <span data-ttu-id="6b1df-298">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-298">Select **Edit**.</span></span>
    3. <span data-ttu-id="6b1df-299">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-299">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="6b1df-300">W polu **Formuła** znajdź następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="6b1df-300">In the **Formula** field, find the following expression:</span></span>

        <span data-ttu-id="6b1df-301">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span><span class="sxs-lookup"><span data-stu-id="6b1df-301">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span></span>

    5. <span data-ttu-id="6b1df-302">W polu **Formuła** wprowadź następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="6b1df-302">In the **Formula** field, enter the following expression:</span></span>

        <span data-ttu-id="6b1df-303">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span><span class="sxs-lookup"><span data-stu-id="6b1df-303">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span></span>

    6. <span data-ttu-id="6b1df-304">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-304">Select **Save**.</span></span>
    7. <span data-ttu-id="6b1df-305">Zamknij stronę **Edytor formuł**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-305">Close the **Formula editor** page.</span></span>
    8. <span data-ttu-id="6b1df-306">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-306">Select **OK**.</span></span>

5. <span data-ttu-id="6b1df-307">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-307">Select **Save**.</span></span>
6. <span data-ttu-id="6b1df-308">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-308">Close the **Model mapping designer** page.</span></span>
7. <span data-ttu-id="6b1df-309">Zamknij stronę **Mapowanie modelu**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-309">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="6b1df-310">Kończenie zmodyfikowanej wersji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-310">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="6b1df-311">W RCS na stronie **Konfiguracje** na karcie skróconej **Wersje** wybierz wersję **1.2** konfiguracji **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-311">In RCS, on the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance trace mapping** configuration.</span></span>
2. <span data-ttu-id="6b1df-312">Wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-312">Select **Change status**.</span></span>
3. <span data-ttu-id="6b1df-313">Wybierz opcję **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-313">Select **Complete**.</span></span>

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a><span data-ttu-id="6b1df-314">Importowanie konfiguracji mapowania modelu ER z RCS do aplikacji</span><span class="sxs-lookup"><span data-stu-id="6b1df-314">Import the modified ER model mapping configuration from RCS into the application</span></span>

<span data-ttu-id="6b1df-315">Powtórz kroki opisane w sekcji [Importowanie konfiguracji ER z RCS do Finance and Operations](#import-configuration) tego tematu, aby zaimportować wersję 1.2 konfiguracji **Mapowanie śledzenia wydajności**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-315">Repeat the steps in the [Import an ER configuration from RCS into Finance and Operations](#import-configuration) section earlier in this topic to import version 1.2 of the **Performance trace mapping** configuration.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="6b1df-316">Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="6b1df-316">Run the modified ER solution to trace execution</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="6b1df-317">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-317">Run the ER format</span></span>

<span data-ttu-id="6b1df-318">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-318">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="work-with-the-execution-trace"></a><span data-ttu-id="6b1df-319">Pracuj z śladem wykonania</span><span class="sxs-lookup"><span data-stu-id="6b1df-319">Work with the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><span data-ttu-id="6b1df-320">Eksportowanie wygenerowanego śledzenia z aplikacji</span><span class="sxs-lookup"><span data-stu-id="6b1df-320">Export the generated trace from the application</span></span>

<span data-ttu-id="6b1df-321">Powtórz kroki opisane w sekcji [Eksportowanie wygenerowanego śladu z aplikacji](#export-trace) tego tematu, aby zapisać lokalnie nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-321">Repeat the steps in the [Export the generated trace from the application](#export-trace) section earlier in this topic to save a new performance trace locally.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><span data-ttu-id="6b1df-322">Importowanie wygenerowanego śladu do RCS</span><span class="sxs-lookup"><span data-stu-id="6b1df-322">Import the generated trace into RCS</span></span>

<span data-ttu-id="6b1df-323">Powtórz kroki opisane w sekcji [Importowanie wygenerowanego śladu do RCS](#import-trace) tego tematu, aby zaimportować nowy ślad wydajności do RCS.</span><span class="sxs-lookup"><span data-stu-id="6b1df-323">Repeat the steps in the [Import the generated trace into RCS](#import-trace) section earlier in this topic to import the new performance trace into RCS.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><span data-ttu-id="6b1df-324">Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu</span><span class="sxs-lookup"><span data-stu-id="6b1df-324">Use the performance trace for analysis in RCS – Model mapping</span></span>

<span data-ttu-id="6b1df-325">Powtórz kroki opisane w sekcji [Użycie śledzenia wydajności do analizy w RCS — mapowanie modelu](#use-trace) tego tematu, aby przeanalizować najnowszy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-325">Repeat the steps in the [Use the performance trace for analysis in RCS – Model mapping](#use-trace) section earlier in this topic to analyze the latest performance trace.</span></span>

<span data-ttu-id="6b1df-326">Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="6b1df-326">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="6b1df-327">Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona.</span><span class="sxs-lookup"><span data-stu-id="6b1df-327">The number of calls to database tables and data sources for this model mapping has been also reduced.</span></span> <span data-ttu-id="6b1df-328">Wydajność całego rozwiązania ER uległa zatem poprawie.</span><span class="sxs-lookup"><span data-stu-id="6b1df-328">Therefore, the performance of the whole ER solution has improved.</span></span>

![Informacje o śladzie źródła danych VendTable na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

<span data-ttu-id="6b1df-330">Wartość **\[12\]** dla tabeli VendTable w śladzie wskazuje, że to źródło danych było wywoływane 12 razy.</span><span class="sxs-lookup"><span data-stu-id="6b1df-330">In the trace information, the value **\[12\]** for the VendTable data source indicates that this data source was called 12 times.</span></span> <span data-ttu-id="6b1df-331">Wartość **\[Q:6\]** wskazuje, że sześć wywołań zostało przetłumaczonych na wywołania bazy danych do tabeli VendTable.</span><span class="sxs-lookup"><span data-stu-id="6b1df-331">The value **\[Q:6\]** indicates that six calls were translated to database calls to the VendTable table.</span></span> <span data-ttu-id="6b1df-332">Wartość **\[C:6\]** wskazuje, że rekordy pobrane z bazy danych były buforowane i sześć innych wywołań zostało przetworzonych przy użyciu pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="6b1df-332">The value **\[C:6\]** indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</span></span>

<span data-ttu-id="6b1df-333">Liczba wywołań źródła danych LedgerTransTypeList została zmniejszona z z 9027 do 240.</span><span class="sxs-lookup"><span data-stu-id="6b1df-333">Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</span></span>

![Informacje o śladzie źródła danych LedgerTransTypeList na stronie Projektant mapowania modelu w RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a><span data-ttu-id="6b1df-335">Przejrzyj wyniki śledzenia wykonania w aplikacji</span><span class="sxs-lookup"><span data-stu-id="6b1df-335">Review the execution trace in the application</span></span>

<span data-ttu-id="6b1df-336">Oprócz RCS niektóre wersje mogą oferować możliwości korzystania z projektanta struktury ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-336">In addition to RCS, some versions might offer capabilities for an ER framework designer experience.</span></span> <span data-ttu-id="6b1df-337">Te wersje zawierają opcję **Włącz tryb projektowania**, którą można włączyć.</span><span class="sxs-lookup"><span data-stu-id="6b1df-337">These versions have an **Enable design mode** option that can be turned on.</span></span> <span data-ttu-id="6b1df-338">Ta opcja znajduje się na karcie **Ogólne** strony **Parametry raportowania elektronicznego** otwieranej z obszaru roboczego **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-338">You can find this option on the **General** tab of the **Electronic reporting parameters** page, which you can open from the **Electronic reporting** workspace.</span></span>

![Włącz opcję trybu projektowania na stronie parametry raportowania elektronicznego](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

<span data-ttu-id="6b1df-340">W przypadku korzystania z jednej z tych wersji modułu Finance and Operations można analizować szczegóły generowanych śladów wydajności bezpośrednio w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b1df-340">If you use one of these versions, you can analyze the details of generated performance traces directly in the application.</span></span> <span data-ttu-id="6b1df-341">Nie trzeba ich eksportować z aplikacji i importować do RCS.</span><span class="sxs-lookup"><span data-stu-id="6b1df-341">You don't have to export them from the application and import them into RCS.</span></span>

## <a name="review-the-execution-trace-by-using-external-tools"></a><span data-ttu-id="6b1df-342">Przeglądanie śladu wykonania za pomocą narzędzi zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="6b1df-342">Review the execution trace by using external tools</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="6b1df-343">Konfigurowanie parametrów użytkownika</span><span class="sxs-lookup"><span data-stu-id="6b1df-343">Configure user parameters</span></span>

1. <span data-ttu-id="6b1df-344">Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-344">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="6b1df-345">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-345">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="6b1df-346">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** w polu **Format śladu wykonania** wybierz opcję **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-346">In the **User parameters** dialog box, in the **Execution tracing** section, in the **Execution trace format** field, select **PerfView XML**.</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="6b1df-347">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-347">Run the ER format</span></span>

<span data-ttu-id="6b1df-348">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-348">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="6b1df-349">Przeglądarka sieci Web zaproponuje pobranie pliku zip.</span><span class="sxs-lookup"><span data-stu-id="6b1df-349">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="6b1df-350">Ten plik zawiera ślad wydajności w formacie PerfView.</span><span class="sxs-lookup"><span data-stu-id="6b1df-350">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="6b1df-351">Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.</span><span class="sxs-lookup"><span data-stu-id="6b1df-351">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span>

![Informacje o śledzeniu wydajności w formacie PerfView](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a><span data-ttu-id="6b1df-353">Narzędzia zewnętrzne umożliwiają przejrzenie śledzenie wykonywania obejmującego kwerendy bazy danych</span><span class="sxs-lookup"><span data-stu-id="6b1df-353">Use external tools to review an execution trace that includes database queries</span></span>

<span data-ttu-id="6b1df-354">Ze względu na udoskonalenia, które zostały wprowadzone w ramach systemu, śledzenie wydajności generowane w formacie PerfView zawiera więcej szczegółów dotyczących wykonywania operacji na formacie ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-354">Because of improvements that have been made to the ER framework, the performance trace that is generated in PerfView format now offers more details about ER format execution.</span></span> <span data-ttu-id="6b1df-355">W Microsoft Dynamics 365 for Finance and Operations wersji 10.0.4 (lipiec 2019) ten ślad może również zawierać szczegóły wykonanych kwerend SQL w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6b1df-355">In Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019), this trace can also include details of executed SQL queries to the application database.</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="6b1df-356">Konfigurowanie parametrów użytkownika</span><span class="sxs-lookup"><span data-stu-id="6b1df-356">Configure user parameters</span></span>

1. <span data-ttu-id="6b1df-357">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-357">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="6b1df-358">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-358">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="6b1df-359">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="6b1df-359">In the **User parameters** dialog box, in the **Execution tracing** section, set the following parameters:</span></span>

    - <span data-ttu-id="6b1df-360">W polu **Format śledzenia wykonania** wybierz opcję **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-360">In the **Execution trace format** field, select **PerfView XML**.</span></span>
    - <span data-ttu-id="6b1df-361">Ustawienie opcji **Zbierz statystyki kwerendy** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-361">Set the **Collect query statistics** option to **Yes**.</span></span>
    - <span data-ttu-id="6b1df-362">Ustawienie opcji wartość **śledzenie kwerendy** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-362">Set the **Trace query** option to **Yes**.</span></span>

    ![Sekcja śledzenia wykonania, okno dialogowe Parametry użytkownika](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a><span data-ttu-id="6b1df-364">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="6b1df-364">Run the ER format</span></span>

<span data-ttu-id="6b1df-365">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="6b1df-365">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="6b1df-366">Przeglądarka sieci Web zaproponuje pobranie pliku zip.</span><span class="sxs-lookup"><span data-stu-id="6b1df-366">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="6b1df-367">Ten plik zawiera ślad wydajności w formacie PerfView.</span><span class="sxs-lookup"><span data-stu-id="6b1df-367">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="6b1df-368">Następnie można przeanalizować szczegóły wykonania formatu ER w narzędziu do analizy wydajności PerfView.</span><span class="sxs-lookup"><span data-stu-id="6b1df-368">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span> <span data-ttu-id="6b1df-369">Teraz ten ślad zawiera szczegóły dostępu do bazy danych SQL podczas wykonywania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="6b1df-369">This trace now includes the details of SQL database access during the execution of the ER format.</span></span>

![Informacje o śledzeniu dla wykonanego formatu ER w PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a><span data-ttu-id="6b1df-371">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6b1df-371">Additional resources</span></span>

- [<span data-ttu-id="6b1df-372">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="6b1df-372">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="6b1df-373">Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH</span><span class="sxs-lookup"><span data-stu-id="6b1df-373">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
