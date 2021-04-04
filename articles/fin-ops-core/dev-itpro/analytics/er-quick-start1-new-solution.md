---
title: Zaprojektowanie nowego rozwiązania ER w celu wydrukowania raportu niestandardowego
description: W tym temacie opisano sposób projektowania rozwiązania do tworzenia raportów elektronicznych (ER) w celu wydrukowania raportu niestandardowego.
author: NickSelin
manager: AnnBe
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5bbfae36fb15437f2baadc66663cbfdb28691e8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562618"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a><span data-ttu-id="bcc0a-103">Zaprojektowanie nowego rozwiązania ER w celu wydrukowania raportu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="bcc0a-103">Design a new ER solution to print a custom report</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bcc0a-104">Poniższe kroki wyjaśniają, w jaki sposób użytkownik pełniący rolę administratora systemu, dewelopera raportowania elektronicznego lub konsultanta funkcjonalnego raportowania elektronicznego może konfigurować parametry struktury ER, projektować wymagane konfiguracje ER nowego rozwiązania ER, aby uzyskać dostęp do danych z określonej domeny biznesowej, i wygeneruj niestandardowy raport w formacie Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-104">The following steps explain how a user in the System Administrator, Electronic Reporting Developer, or Electronic Reporting Functional Consultant role can configure parameters of the ER framework, design the required ER configurations of a new ER solution to access the data of a particular business domain, and generate a custom report in Microsoft Office format.</span></span> <span data-ttu-id="bcc0a-105">Kroki można wykonać na danych firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-105">These steps can be completed in the **USMF** company.</span></span>

- [<span data-ttu-id="bcc0a-106">Konfigurowanie struktury ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-106">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="bcc0a-107">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-107">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="bcc0a-108">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-108">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="bcc0a-109">Przejrzenie listy dostawców konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-109">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="bcc0a-110">Dodawanie nowego dostawcy formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-110">Add a new ER configuration provider</span></span>](#AddProvider)
        - [<span data-ttu-id="bcc0a-111">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-111">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="bcc0a-112">Projektowanie modelu danych specyficznego dla domeny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-112">Design a domain-specific data model</span></span>](#DesignModel)

    - [<span data-ttu-id="bcc0a-113">Importowanie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-113">Import a new data model configuration</span></span>](#ImportDataModel)
    - [<span data-ttu-id="bcc0a-114">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-114">Create a new data model configuration</span></span>](#DesignDataModel)

        - [<span data-ttu-id="bcc0a-115">Nazywanie modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-115">Name the data model</span></span>](#NameDataModel)
        - [<span data-ttu-id="bcc0a-116">Dodaj pola modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-116">Add data model fields</span></span>](#FieldsEntry)
        - [<span data-ttu-id="bcc0a-117">Umożliwia zakończenie projektu modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-117">Complete the design of the data model</span></span>](#CompleteDataModel)

- [<span data-ttu-id="bcc0a-118">Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-118">Design a model mapping for the configured data model</span></span>](#DesignMapping)

    - [<span data-ttu-id="bcc0a-119">Importowanie nowej konfiguracji mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-119">Import a new model mapping configuration</span></span>](#ImportModelMapping)
    - [<span data-ttu-id="bcc0a-120">Stwórz nowy model konfiguracji mapowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-120">Create a new model mapping configuration</span></span>](#CreateModelMapping)

        - [<span data-ttu-id="bcc0a-121">Projektowanie nowego składnika mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-121">Design a new model mapping component</span></span>](#DesignMappingComponent)
        - [<span data-ttu-id="bcc0a-122">Dodawanie źródeł danych w celu uzyskania dostępu do tabel aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-122">Add data sources to access application tables</span></span>](#AddMmDataSource1)
        - [<span data-ttu-id="bcc0a-123">Dodawanie źródeł danych w celu uzyskania dostępu do wyliczenia aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-123">Add data sources to access application enumerations</span></span>](#AddMmDataSource2)
        - [<span data-ttu-id="bcc0a-124">Dodawanie etykiet ER w celu wygenerowania raportu w określonym języku</span><span class="sxs-lookup"><span data-stu-id="bcc0a-124">Add ER labels to generate a report in a specified language</span></span>](#AddMmLabels)
        - [<span data-ttu-id="bcc0a-125">Dodaj źródło danych w celu przekształcenia wyników porównywania wartości wyliczenia z wartością tekstową</span><span class="sxs-lookup"><span data-stu-id="bcc0a-125">Add a data source to transform the results of comparing enumeration values to a text value</span></span>](#AddMmDataSource3)
        - [<span data-ttu-id="bcc0a-126">Powiąż źródła danych z polami modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-126">Bind data sources to data model fields</span></span>](#AddMmBindings1)
        - [<span data-ttu-id="bcc0a-127">Umożliwia zakończenie projektu mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-127">Complete the design of the model mapping</span></span>](#CompleteModelMapping)

- [<span data-ttu-id="bcc0a-128">Projektowanie szablonu raportu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="bcc0a-128">Design a template for a custom report</span></span>](#DesignReportTemplate)
- [<span data-ttu-id="bcc0a-129">Projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-129">Design a format</span></span>](#DesignFormat)

    - [<span data-ttu-id="bcc0a-130">Import zaprojektowanej konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-130">Import a designed format configuration</span></span>](#FormatImport)
    - [<span data-ttu-id="bcc0a-131">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-131">Create a new format configuration</span></span>](#FormatCreate)

        - [<span data-ttu-id="bcc0a-132">Zaimportuj szablon raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-132">Import a report template</span></span>](#ImportReportTemplate)
        - [<span data-ttu-id="bcc0a-133">Konfigurowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-133">Configure a format</span></span>](#ConfigureFormat)
        - [<span data-ttu-id="bcc0a-134">Definiowanie powiązania danych dla tytułu raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-134">Define the data binding for a report title</span></span>](#DefineFormatBindings)
        - [<span data-ttu-id="bcc0a-135">Przejrzyj źródło danych modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-135">Review the model data source</span></span>](#ReviewModelDataSource)
        - [<span data-ttu-id="bcc0a-136">Powiązanie elementów formatu na pola źródła danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-136">Bind format elements to data source fields</span></span>](#BindFormatElements)

    - [<span data-ttu-id="bcc0a-137">Uruchamianie zaprojektowanego formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-137">Run a designed format from ER</span></span>](#RunFormatFromER)

- [<span data-ttu-id="bcc0a-138">Dostrajanie zaprojektowanego formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-138">Tune a designed format</span></span>](#TuneFormat)

    - [<span data-ttu-id="bcc0a-139">Modyfikowanie formatu w celu zmiany nazwy wygenerowanego dokumentu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-139">Modify a format to change the name of a generated document</span></span>](#ModifyToChangeName)
    - [<span data-ttu-id="bcc0a-140">Umożliwia zmodyfikowanie formatu w celu zmiany kolejności pytań</span><span class="sxs-lookup"><span data-stu-id="bcc0a-140">Modify a format to change the order of questions</span></span>](#ModifyToOrder)
    - [<span data-ttu-id="bcc0a-141">Uruchamianie zmodyfikowanego formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-141">Run a modified format from ER</span></span>](#RunFormatFromER2)
    - [<span data-ttu-id="bcc0a-142">Zakończ projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-142">Complete the format design</span></span>](#CompleteFormat)

- [<span data-ttu-id="bcc0a-143">Opracowywanie Artefacts aplikacji w celu wywołania zaprojektowanego raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-143">Develop application artefacts to call the designed report</span></span>](#DevelopCustomCode)

    - [<span data-ttu-id="bcc0a-144">Zmień kod źródłowy</span><span class="sxs-lookup"><span data-stu-id="bcc0a-144">Modify source code</span></span>](#ModifySourceCode)

        - [<span data-ttu-id="bcc0a-145">Dodawanie klasy kontraktu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-145">Add a data contract class</span></span>](#DataContractClass)
        - [<span data-ttu-id="bcc0a-146">Dodaj klasę konstruktora UI</span><span class="sxs-lookup"><span data-stu-id="bcc0a-146">Add a UI builder class</span></span>](#UIBuilderClass)
        - [<span data-ttu-id="bcc0a-147">Dodawanie klasy dostawcy danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-147">Add a data provider class</span></span>](#DataProviderClass)
        - [<span data-ttu-id="bcc0a-148">Dodaj plik etykiet</span><span class="sxs-lookup"><span data-stu-id="bcc0a-148">Add a labels file</span></span>](#LabelsFile)
        - [<span data-ttu-id="bcc0a-149">Dodawanie klasy usługi raportowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-149">Add a report service class</span></span>](#ServiceClass)
        - [<span data-ttu-id="bcc0a-150">Dodawanie klasy kontrolera raportowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-150">Add a report controller class</span></span>](#ControllerClass)
        - [<span data-ttu-id="bcc0a-151">Dodaj element menu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-151">Add a menu item</span></span>](#MenuItem)
        - [<span data-ttu-id="bcc0a-152">Dodawanie elementu menu do menu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-152">Add a menu item to a menu</span></span>](#Menu)
        - [<span data-ttu-id="bcc0a-153">Budowanie projektu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bcc0a-153">Build a Visual Studio project</span></span>](#BuildVSProject)

    - [<span data-ttu-id="bcc0a-154">Umożliwia uruchomienie formatu z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-154">Run a format from the application</span></span>](#RunFormatFromApp)

- [<span data-ttu-id="bcc0a-155">Dostrajanie zaprojektowanego rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-155">Tune a designed ER solution</span></span>](#TuneSolution)

    - [<span data-ttu-id="bcc0a-156">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-156">Modify a model mapping</span></span>](#ModifyModelMapping)

        - [<span data-ttu-id="bcc0a-157">Dodaj źródła danych, aby uzyskać dostęp do obiektu kontraktu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-157">Add data sources to access a data contract object</span></span>](#AddDataSource1)
        - [<span data-ttu-id="bcc0a-158">Dodaj źródło danych, aby uzyskać dostęp do rekordów mapowania formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-158">Add a data source to access ER format mapping records</span></span>](#AddDataSource2)
        - [<span data-ttu-id="bcc0a-159">Dodaj źródło danych, aby uzyskać dostęp do rekordu odwzorowania formatu działającego formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-159">Add a data source to access a format mapping record of a running ER format</span></span>](#AddDataSource3)
        - [<span data-ttu-id="bcc0a-160">Umożliwia wprowadzenie nazwy uruchomionego formatu ER w modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-160">Enter the name of the running ER format in the data model</span></span>](#AddBinding)
        - [<span data-ttu-id="bcc0a-161">Umożliwia zakończenie projektu mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-161">Complete the design of the model mapping</span></span>](#CompleteModelMapping2)

    - [<span data-ttu-id="bcc0a-162">Modyfikowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-162">Modify a format</span></span>](#ModifyFormat)

        - [<span data-ttu-id="bcc0a-163">Dodaj nowy element formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-163">Add a new format element</span></span>](#AddFormatElement)
        - [<span data-ttu-id="bcc0a-164">Powiąż dodany element formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-164">Bind the added format element</span></span>](#BindAddedFormatElement)
        - [<span data-ttu-id="bcc0a-165">Zakończ projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-165">Complete the format design</span></span>](#CompleteFormat2)

    - [<span data-ttu-id="bcc0a-166">Umożliwia uruchomienie formatu z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-166">Run a format from the application</span></span>](#RunFormatFromApp2)
    - [<span data-ttu-id="bcc0a-167">Uruchamianie formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-167">Run a format from ER</span></span>](#RunFormatFromER3)
    - [<span data-ttu-id="bcc0a-168">Skonfiguruj miejsce docelowe formatu dla podglądu na ekranie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-168">Configure a format destination for on-screen preview</span></span>](#ConfigureDestination)
    - [<span data-ttu-id="bcc0a-169">Umożliwia uruchomienie formatu z aplikacji w celu wyświetlenia podglądu go jako dokumentu PDF</span><span class="sxs-lookup"><span data-stu-id="bcc0a-169">Run a format from the application to preview it as a PDF document</span></span>](#RunFormatFromApp3)

- [<span data-ttu-id="bcc0a-170">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bcc0a-170">Additional resources</span></span>](#References)

<span data-ttu-id="bcc0a-171">W tym przykładzie zostanie utworzone nowe rozwiązanie ER dla modułu [kwestionariusza](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-171">In this example, you will create a new ER solution for the [Questionnaire](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires) module.</span></span> <span data-ttu-id="bcc0a-172">To nowe rozwiązanie ER umożliwia zaprojektowanie raportu za pomocą arkusza Microsoft Excel jako szablonu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-172">This new ER solution lets you design a report by using a Microsoft Excel worksheet as a template.</span></span> <span data-ttu-id="bcc0a-173">Następnie można wygenerować raport **kwestionariusza** w formacie programu Excel lub PDF, oprócz generowania istniejącego raportu usług SQL Server Reporting Services (SSRS).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-173">You can then generate the **Questionnaire** report in Excel or PDF format, in addition to generating the existing SQL Server Reporting Services (SSRS) report.</span></span> <span data-ttu-id="bcc0a-174">Nowy raport można także zmodyfikować później, na życzenie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-174">You can also modify the new report later, upon request.</span></span> <span data-ttu-id="bcc0a-175">Nie są wymagane umiejętności kodowania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-175">No coding is required.</span></span>

1. <span data-ttu-id="bcc0a-176">Aby uruchomić istniejący raport, przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-176">To run the existing report, go to **Questionnaire** \> **Design** \> **Questionnaires report**.</span></span>

    ![Wybranie elementu menu raportu kwestionariuszy w module kwestionariusza w celu uruchomienia istniejącego raportu usług SSRS](./media/er-quick-start1-application-menu-origin.png)

2. <span data-ttu-id="bcc0a-178">W oknie dialogowym **Raport z kwestionariuszy** określ kryteria wyboru.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-178">In the **Questionnaires report** dialog box, specify selection criteria.</span></span> <span data-ttu-id="bcc0a-179">Zastosuj filtr, aby raport zawierał tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-179">Apply a filter so that the report includes only the **SBCCrsExam** questionnaire.</span></span>

    ![Określenie kryteriów wyboru w oknie dialogowym Raport z kwestionariuszy](./media/er-quick-start1-ssrs-report-dialog.png)

<span data-ttu-id="bcc0a-181">Na poniższej ilustracji przedstawiono wygenerowaną wersję raportu SSRS dla kwestionariusza **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-181">The following illustration shows the generated version of the SSRS report for the **SBCCrsExam** questionnaire.</span></span>

![Wygenerowany raport SSRS](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a><span data-ttu-id="bcc0a-183">Konfigurowanie struktury ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-183">Configure the ER framework</span></span>

<span data-ttu-id="bcc0a-184">Jako użytkownik w roli dewelopera raportowania elektronicznego, musisz skonfigurować minimalny zestaw parametrów ER, zanim będziesz mógł zacząć używać struktury ER do projektowania nowego rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-184">As a user in the Electronic Reporting Developer role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design your new ER solution.</span></span>

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a><span data-ttu-id="bcc0a-185">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-185">Configure ER parameters</span></span>

1. <span data-ttu-id="bcc0a-186">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-186">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="bcc0a-187">W obszarze roboczym **Raportowanie elektroniczne** wybierz łącze **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-187">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="bcc0a-188">Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-188">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="bcc0a-189">Na karcie **Załączniki** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-189">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="bcc0a-190">Ustaw pole **Konfiguracje** na **Plik** dla firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-190">Set the **Configurations** field to **File** for the **USMF** company.</span></span>
    - <span data-ttu-id="bcc0a-191">W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy ustawić typ **Plik**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-191">Set **Job archive**, **Temporary**, **Baseline**, and **Others** fields to **File**.</span></span>

<span data-ttu-id="bcc0a-192">Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-192">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a><span data-ttu-id="bcc0a-193">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-193">Activate an ER configuration provider</span></span>

<span data-ttu-id="bcc0a-194">Każda konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-194">Every ER configuration is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="bcc0a-195">Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-195">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit any ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc0a-196">Tylko właściciel konfiguracji ER może ją edytować.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-196">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="bcc0a-197">Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-197">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a><span data-ttu-id="bcc0a-198">Przejrzenie listy dostawców konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-198">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="bcc0a-199">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-199">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="bcc0a-200">W module **Powiązane odnośniki**, w obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-200">In the **Electronic reporting** workspace, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="bcc0a-201">Na stronie **Dostawcy konfiguracji** każde ustawienie dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-201">On the **Configuration providers** page, each configuration provider record has a unique name and URL.</span></span> <span data-ttu-id="bcc0a-202">Przejrzyj zawartość tej strony.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-202">Review the contents of this page.</span></span> <span data-ttu-id="bcc0a-203">Jeśli rekord dla **Litware, Inc.** (`https://www.litware.com`) już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-203">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a><span data-ttu-id="bcc0a-204">Dodawanie nowego dostawcy formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-204">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="bcc0a-205">Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-205">On the **Configuration providers** page, select **New**.</span></span>
2. <span data-ttu-id="bcc0a-206">W polu **Nazwa** wpisz **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-206">In the **Name** field, enter **Litware, Inc.**</span></span>
3. <span data-ttu-id="bcc0a-207">W polu **Adres internetowy** wprowadź `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-207">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
4. <span data-ttu-id="bcc0a-208">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-208">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a><span data-ttu-id="bcc0a-209">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-209">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="bcc0a-210">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-210">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="bcc0a-211">W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Litware, Inc.** dla dostawcy konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-211">In the **Electronic reporting** workspace, select the **Litware, Inc.** configuration provider.</span></span>
3. <span data-ttu-id="bcc0a-212">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-212">Select **Set active**.</span></span>

<span data-ttu-id="bcc0a-213">Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-213">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a><span data-ttu-id="bcc0a-214">Projektowanie modelu danych specyficznego dla domeny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-214">Design a domain-specific data model</span></span>

<span data-ttu-id="bcc0a-215">Należy utworzyć nową konfigurację ER, która zawiera składnik [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components) dla domeny biznesowej **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-215">You must create a new ER configuration that contains a [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** business domain.</span></span> <span data-ttu-id="bcc0a-216">Ten model danych będzie później używany jako źródło danych podczas projektowania formatu ER w celu wygenerowania raportu **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-216">This data model will later be used as a data source when you design an ER format to generate the **Questionnaire** report.</span></span>

<span data-ttu-id="bcc0a-217">Wykonując kroki opisane w sekcji [Importowanie nowej konfiguracji modelu danych](#ImportDataModel), można zaimportować wymagany model danych z podanego pliku XML.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-217">By completing the steps in the [Import a new data model configuration](#ImportDataModel) section, you can import the required data model from the provided XML file.</span></span> <span data-ttu-id="bcc0a-218">Można również wykonać kroki opisane w sekcji [Tworzenie nowej konfiguracji modelu danych](#DesignDataModel), aby zaprojektować ten model danych od podstaw.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-218">Alternatively, you can complete the steps in the [Create a new data model configuration](#DesignDataModel) section to design this data model from scratch.</span></span>

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a><span data-ttu-id="bcc0a-219">Importowanie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-219">Import a new data model configuration</span></span>

1. <span data-ttu-id="bcc0a-220">Pobierz [model kwestionariuszy.wersja.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-220">Download the [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="bcc0a-221">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-221">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="bcc0a-222">W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-222">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="bcc0a-223">W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-223">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="bcc0a-224">Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **model kwestionariuszy.wersja.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-224">Select **Browse**, and then find and select the **Questionnaires model.version.1.xml** file.</span></span>
6. <span data-ttu-id="bcc0a-225">Wybierz przycisk **OK**, aby importować konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-225">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="bcc0a-226">Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację modelu danych](#DesignDataModel).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-226">To continue, skip the next procedure, [Create a new data model configuration](#DesignDataModel).</span></span>

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a><span data-ttu-id="bcc0a-227">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-227">Create a new data model configuration</span></span>

1. <span data-ttu-id="bcc0a-228">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-228">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="bcc0a-229">W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-229">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
3. <span data-ttu-id="bcc0a-230">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-230">Select **Create configuration**.</span></span>
4. <span data-ttu-id="bcc0a-231">W rozwijanym menu w polu **Nazwa** wpisz **Model kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-231">In the drop-down dialog box, in the **Name** field, enter **Questionnaire model**.</span></span>
5. <span data-ttu-id="bcc0a-232">Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-232">Select **Create configuration** to create the configuration.</span></span>

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a><span data-ttu-id="bcc0a-233">Nazywanie modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-233">Name the data model</span></span>

1. <span data-ttu-id="bcc0a-234">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-234">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
2. <span data-ttu-id="bcc0a-235">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-235">Select **Designer**.</span></span>
3. <span data-ttu-id="bcc0a-236">Na stronie **Projektant modelu danych** na skróconej karcie **Ogólne** w polu **Nazwa** wprowadź <a name="DataModeName"></a>**Kwestionariusze**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-236">On the **Data model designer** page, on the **General** FastTab, in the **Name** field, enter <a name="DataModeName"></a>**Questionnaires**.</span></span>

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a><span data-ttu-id="bcc0a-237">Dodaj nowe pola modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-237">Add new data model fields</span></span>

1. <span data-ttu-id="bcc0a-238">Na stronie **Projektant modelu danych** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-238">On the **Data model designer** page, select **New**.</span></span>
2. <span data-ttu-id="bcc0a-239">W oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-239">In the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-240">Wybierz **Element główny modelu** jako typ nowego węzła.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-240">Select **Model root** as the type of the new node.</span></span>
    2. <span data-ttu-id="bcc0a-241">W polu **Nazwa** wprowadź nazwę <a name="RootDefinitionName"></a>**Element główny**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-241">In the **Name** field, enter <a name="RootDefinitionName"></a>**Root**.</span></span>
    3. <span data-ttu-id="bcc0a-242">Wybierz **Dodaj**, aby dodać nowy węzeł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-242">Select **Add** to add the new node.</span></span>

    <span data-ttu-id="bcc0a-243">Ten główny deskryptor będzie używany do dostarczania danych dla raportu **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-243">This root descriptor will be used to provide data for the **Questionnaire** report.</span></span> <span data-ttu-id="bcc0a-244">Jeden model danych może mieć wiele deskryptorów.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-244">A single data model can have multiple descriptors.</span></span> <span data-ttu-id="bcc0a-245">Każdy deskryptor można określić dla pojedynczego formatu ER, aby zidentyfikować dane wymagane do wygenerowania raportu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-245">Each descriptor can be specified for a single ER format, to identify data that is required to generate the report.</span></span>

3. <span data-ttu-id="bcc0a-246">Wybierz ponownie **Nowe**, a następnie w oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-246">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-247">Wybierz **Element podrzędny aktywnego węzła** jako typ nowego węzła.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-247">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="bcc0a-248">W polu **Nazwa** wpisz **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-248">In the **Name** field, enter **CompanyName**.</span></span>
    3. <span data-ttu-id="bcc0a-249">W polu **Typ przedmiotu** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-249">In the **Item type** field, select **String**.</span></span>
    4. <span data-ttu-id="bcc0a-250">Wybierz **Dodaj**, aby dodać nowe pole.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-250">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="bcc0a-251">To pole jest wymagane do przekazania nazwy bieżącej firmy do raportu o roli właściciela, który korzysta z tego modelu danych jako źródła danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-251">This field is required to pass the name of the current company to an ER report that consumes this data model as a data source.</span></span>

4. <span data-ttu-id="bcc0a-252">Wybierz ponownie **Nowe**, a następnie w oknie dialogowym rozwijanym dotyczącym dodawania węzła modelu danych wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-252">Select **New** again, and then, in the drop-down dialog box for adding a data model node, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-253">Wybierz **Element podrzędny aktywnego węzła** jako typ nowego węzła.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-253">Select **Child of an active node** as the type of the new node.</span></span>
    2. <span data-ttu-id="bcc0a-254">W polu **Nazwa** wpisz **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-254">In the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="bcc0a-255">W polu **Kod przedmiotu** wybierz **Lista tabel**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-255">In the **Item type** field, select **Record list**.</span></span>
    4. <span data-ttu-id="bcc0a-256">Wybierz **Dodaj**, aby dodać nowe pole.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-256">Select **Add** to add the new field.</span></span>

    <span data-ttu-id="bcc0a-257">To pole będzie używane do przekazywania listy kwestionariuszy do raportu ER, który wykorzystuje ten model danych jako źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-257">This field will be used to pass the list of questionnaires to an ER report that consumes this data model as a data source.</span></span>

5. <span data-ttu-id="bcc0a-258">Wybierz węzeł **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-258">Select the **Questionnaire** node.</span></span>
6. <span data-ttu-id="bcc0a-259">Umożliwia kontynuowanie dodawania wymaganych pól edytowalnego modelu danych w taki sam sposób, dopóki nie zostanie wykonana następująca struktura modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-259">Continue to add the required fields of the editable data model in the same manner until you complete the following data model structure.</span></span>

    | <span data-ttu-id="bcc0a-260">Ścieżka pola</span><span class="sxs-lookup"><span data-stu-id="bcc0a-260">Field path</span></span>                                                    | <span data-ttu-id="bcc0a-261">Typ danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-261">Data type</span></span>   | <span data-ttu-id="bcc0a-262">Oznaczenie pola/wartość zwrócona</span><span class="sxs-lookup"><span data-stu-id="bcc0a-262">Field designation/returned value</span></span> |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | <span data-ttu-id="bcc0a-263">Element główny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-263">Root</span></span>                                                          |             | <span data-ttu-id="bcc0a-264">Punkt odniesienia do żądania danych kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-264">The reference point to request questionnaire data.</span></span> |
    | <span data-ttu-id="bcc0a-265">Element główny\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="bcc0a-265">Root\\CompanyName</span></span>                                             | <span data-ttu-id="bcc0a-266">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-266">String</span></span>      | <span data-ttu-id="bcc0a-267">Nazwa bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-267">The name of the current company.</span></span> |
    | <span data-ttu-id="bcc0a-268">Element główny\\ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="bcc0a-268">Root\\ExecutionContext</span></span>                                        | <span data-ttu-id="bcc0a-269">Zarejestruj</span><span class="sxs-lookup"><span data-stu-id="bcc0a-269">Record</span></span>      | <span data-ttu-id="bcc0a-270">Szczegóły formatu wykonania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-270">Format execution details.</span></span> |
    | <span data-ttu-id="bcc0a-271">Element główny\\ExecutionContext\\FormatName</span><span class="sxs-lookup"><span data-stu-id="bcc0a-271">Root\\ExecutionContext\\FormatName</span></span>                            | <span data-ttu-id="bcc0a-272">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-272">String</span></span>      | <span data-ttu-id="bcc0a-273">Nazwa uruchamianego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-273">The name of the ER format that is being run.</span></span> |
    | <span data-ttu-id="bcc0a-274">Element główny\\Kwestionariusz</span><span class="sxs-lookup"><span data-stu-id="bcc0a-274">Root\\Questionnaire</span></span>                                           | <span data-ttu-id="bcc0a-275">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-275">Record list</span></span> | <span data-ttu-id="bcc0a-276">Lista kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="bcc0a-276">The list of questionnaires</span></span> |
    | <span data-ttu-id="bcc0a-277">Element główny\\Kwestionariusz\\Aktywny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-277">Root\\Questionnaire\\Active</span></span>                                   | <span data-ttu-id="bcc0a-278">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-278">String</span></span>      | <span data-ttu-id="bcc0a-279">Stan obecnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-279">The status of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-280">Element główny\\Kwestionariusz\\Kod</span><span class="sxs-lookup"><span data-stu-id="bcc0a-280">Root\\Questionnaire\\Code</span></span>                                     | <span data-ttu-id="bcc0a-281">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-281">String</span></span>      | <span data-ttu-id="bcc0a-282">Kod obecnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-282">The code of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-283">Element główny\\Kwestionariusz\\Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-283">Root\\Questionnaire\\Description</span></span>                              | <span data-ttu-id="bcc0a-284">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-284">String</span></span>      | <span data-ttu-id="bcc0a-285">Opis obecnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-285">The description of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-286">Element główny\\Kwestionariusz\\TypKwestionariusza</span><span class="sxs-lookup"><span data-stu-id="bcc0a-286">Root\\Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="bcc0a-287">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-287">String</span></span>      | <span data-ttu-id="bcc0a-288">Typ obecnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-288">The type of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-289">Element główny\\Kwestionariusz\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="bcc0a-289">Root\\Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="bcc0a-290">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-290">String</span></span>      | <span data-ttu-id="bcc0a-291">Kolejność numeryczna obecnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-291">The numerical order of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-292">Element główny\\Kwestionariusz\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="bcc0a-292">Root\\Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="bcc0a-293">Zarejestruj</span><span class="sxs-lookup"><span data-stu-id="bcc0a-293">Record</span></span>      | <span data-ttu-id="bcc0a-294">Parametry wynikowe aktualnego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-294">The result parameters of the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-295">Element główny\\Kwestionariusz\\ResultsGroup\\Kod</span><span class="sxs-lookup"><span data-stu-id="bcc0a-295">Root\\Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="bcc0a-296">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-296">String</span></span>      | <span data-ttu-id="bcc0a-297">Kod identyfikacyjny bieżącej grupy wyników.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-297">The identification code of the current result group.</span></span> |
    | <span data-ttu-id="bcc0a-298">Element główny\\Kwestionariusz\\ResultsGroup\\Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-298">Root\\Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="bcc0a-299">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-299">String</span></span>      | <span data-ttu-id="bcc0a-300">Opis bieżącej grupy wyników.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-300">The description of the current result group.</span></span> |
    | <span data-ttu-id="bcc0a-301">Element główny\\Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="bcc0a-301">Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="bcc0a-302">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-302">Real</span></span>        | <span data-ttu-id="bcc0a-303">Maksymalna liczba punktów, jaka może zostać uzyskana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-303">The maximum number of points that could be earned.</span></span> |
    | <span data-ttu-id="bcc0a-304">Element główny\\Kwestionariusz\\Pytanie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-304">Root\\Questionnaire\\Question</span></span>                                 | <span data-ttu-id="bcc0a-305">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-305">Record list</span></span> | <span data-ttu-id="bcc0a-306">Lista pytań dla bieżącego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-306">The list of questions for the current questionnaire.</span></span> |
    | <span data-ttu-id="bcc0a-307">Element główny\\Kwestionariusz\\Pytanie\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-307">Root\\Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="bcc0a-308">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-308">Integer</span></span>     | <span data-ttu-id="bcc0a-309">Numer sekwencyjny bieżącej kolekcji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-309">The sequence number of the current answer collection.</span></span> |
    | <span data-ttu-id="bcc0a-310">Element główny\\Kwestionariusz\\Pytanie\\Identyfikator</span><span class="sxs-lookup"><span data-stu-id="bcc0a-310">Root\\Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="bcc0a-311">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-311">String</span></span>      | <span data-ttu-id="bcc0a-312">Kod identyfikacyjny bieżącego pytania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-312">The identification code of the current question.</span></span> |
    | <span data-ttu-id="bcc0a-313">Element główny\\Kwestionariusz\\Pytanie\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="bcc0a-313">Root\\Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="bcc0a-314">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-314">String</span></span>      | <span data-ttu-id="bcc0a-315">Flaga wskazująca, czy ma być udzielona odpowiedź na bieżące pytanie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-315">A flag that indicates whether the current question must be answered.</span></span> |
    | <span data-ttu-id="bcc0a-316">Element główny\\Kwestionariusz\\Pytanie\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="bcc0a-316">Root\\Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="bcc0a-317">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-317">String</span></span>      | <span data-ttu-id="bcc0a-318">Flaga wskazująca, czy bieżące pytanie jest podstawowe.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-318">A flag that indicates whether the current question is primary.</span></span> |
    | <span data-ttu-id="bcc0a-319">Element główny\\Kwestionariusz\\Pytanie\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-319">Root\\Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="bcc0a-320">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-320">Integer</span></span>     | <span data-ttu-id="bcc0a-321">Numer porządkowy aktualnego pytania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-321">The sequence number of the current question.</span></span> |
    | <span data-ttu-id="bcc0a-322">Element główny\\Kwestionariusz\\Pytanie\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-322">Root\\Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="bcc0a-323">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-323">String</span></span>      | <span data-ttu-id="bcc0a-324">Tekst aktualnego pytania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-324">The text of the current question.</span></span> |
    | <span data-ttu-id="bcc0a-325">Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź</span><span class="sxs-lookup"><span data-stu-id="bcc0a-325">Root\\Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="bcc0a-326">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-326">Record list</span></span> | <span data-ttu-id="bcc0a-327">Lista odpowiedzi na aktualne pytanie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-327">The list of answers for the current question.</span></span> |
    | <span data-ttu-id="bcc0a-328">Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="bcc0a-328">Root\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="bcc0a-329">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-329">String</span></span>      | <span data-ttu-id="bcc0a-330">Flaga wskazująca, czy aktualna odpowiedź jest poprawna.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-330">A flag that indicates whether the current answer is correct.</span></span> |
    | <span data-ttu-id="bcc0a-331">Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-331">Root\\Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="bcc0a-332">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-332">Real</span></span>        | <span data-ttu-id="bcc0a-333">Punkty zdobyte po wybraniu bieżącej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-333">The points that are earned when the current answer is selected.</span></span> |
    | <span data-ttu-id="bcc0a-334">Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-334">Root\\Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="bcc0a-335">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-335">Integer</span></span>     | <span data-ttu-id="bcc0a-336">Numer kolejny bieżącej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-336">The sequence number of the current answer.</span></span> |
    | <span data-ttu-id="bcc0a-337">Element główny\\Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-337">Root\\Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="bcc0a-338">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-338">String</span></span>      | <span data-ttu-id="bcc0a-339">Tekst aktualnej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-339">The text of the current answer.</span></span> |

    <span data-ttu-id="bcc0a-340">Na poniższej ilustracji przedstawiono ukończony edytowalny model danych na stronie **Projektant modelu danych**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-340">The following illustration shows the completed editable data model on the **Data model designer** page.</span></span>

    ![Skonfigurowany model danych w projektancie modeli danych ER](./media/er-quick-start1-model2.png)

7. <span data-ttu-id="bcc0a-342">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-342">Save your changes.</span></span>
8. <span data-ttu-id="bcc0a-343">Zamknij stronę **Projektant modelu danych**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-343">Close the **Data model designer** page.</span></span>

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a><span data-ttu-id="bcc0a-344">Ukończenie projektu modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-344">Complete the design of the data model</span></span>

1. <span data-ttu-id="bcc0a-345">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-345">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-346">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-346">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="bcc0a-347">Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-347">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="bcc0a-348">Wybierz **Zmień status** \> **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-348">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="bcc0a-349">Stan wersja 1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-349">The status of version 1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="bcc0a-350">Wersja 1 nie może być już zmieniana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-350">Version 1 can no longer be changed.</span></span> <span data-ttu-id="bcc0a-351">Ta wersja zawiera skonfigurowany model danych i może być używana jako podstawa dla innych konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-351">This version contains the configured data model and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="bcc0a-352">Wersja 2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-352">Version 2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="bcc0a-353">Tę wersję można edytować, aby skorygować model danych **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-353">You can edit this version to adjust the **Questionnaire** data model.</span></span>

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-model-configuration.png)

<span data-ttu-id="bcc0a-355">Aby uzyskać więcej informacji na temat wersji konfiguracji funkcji ER, zajrzyj do [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-355">For more information about versioning for ER configurations, see [Electronic reporting (ER) overview](general-electronic-reporting.md#component-versioning).</span></span>

> [!NOTE]
> <span data-ttu-id="bcc0a-356">Skonfigurowany model danych to abstrakcyjna reprezentacja domeny biznesowej **Kwestionariusza** i nie zawiera żadnych powiązań z artefaktami specyficznymi dla Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-356">The configured data model is your abstract representation of the **Questionnaire** business domain and contains no relations to artefacts that are specific to Microsoft Dynamics 365 Finance.</span></span>

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a><span data-ttu-id="bcc0a-357">Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-357">Design a model mapping for the configured data model</span></span>

<span data-ttu-id="bcc0a-358">Jako użytkownik w roli Deweloper raportowania elektronicznego musisz utworzyć nową konfigurację ER zawierającą zawiera składnik [mapowania modelu](general-electronic-reporting.md#data-model-and-model-mapping-components) dla modelu danych **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-358">As a user in the Electronic Reporting Developer role, you must create a new ER configuration that contains a [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) component for the **Questionnaire** data model.</span></span> <span data-ttu-id="bcc0a-359">Ten składnik implementuje skonfigurowany model danych dla Finance, dlatego jest on związany z Finance.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-359">Because this component implements the configured data model for Finance, it's Finance-specific.</span></span> <span data-ttu-id="bcc0a-360">Należy skonfigurować składnik mapowanie modelu, aby określić obiekty aplikacji, które muszą być używane do wypełniania skonfigurowanego modelu danych za pomocą danych aplikacji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-360">You must configure the model mapping component to specify the application objects that must be used to fill in the configured data model with application data at runtime.</span></span> <span data-ttu-id="bcc0a-361">Aby wykonać to zadanie, należy zapoznać się ze szczegółami implementacji struktury danych w domenie biznesowej **Kwestionariusza** w Finance.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-361">To complete this task, you must be aware of the implementation details of the data structure of the **Questionnaire** business domain in Finance.</span></span>

<span data-ttu-id="bcc0a-362">Wykonując kroki opisane w następujaćej sekcji [Importowanie nowej konfiguracji mapowania modelu](#ImportModelMapping), można zaimportować wymagany model mapowania konfiguracji z podanego pliku XML.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-362">By completing the steps in the [Import a new model mapping configuration](#ImportModelMapping) section that follows, you can import the required model mapping configuration from the provided XML file.</span></span> <span data-ttu-id="bcc0a-363">Można również wykonać kroki opisane w sekcji [Stwórz nowy model konfiguracji mapowania](#CreateModelMapping), aby zaprojektować ten model mapowania od podstaw.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-363">Alternatively, you can complete the steps in the [Create a new model mapping configuration](#CreateModelMapping) section to design this model mapping from scratch.</span></span>

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a><span data-ttu-id="bcc0a-364">Importowanie nowej konfiguracji mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-364">Import a new model mapping configuration</span></span>

1. <span data-ttu-id="bcc0a-365">Pobierz [Mapowanie kwestionariuszy.wersja.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-365">Download the [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="bcc0a-366">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-366">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="bcc0a-367">W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-367">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="bcc0a-368">W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-368">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="bcc0a-369">Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Mapowanie kwestionariuszy.wersja.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-369">Select **Browse**, and then find and select the **Questionnaires mapping.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="bcc0a-370">Wybierz przycisk **OK**, aby importować konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-370">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="bcc0a-371">Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację modelu mapowania](#CreateModelMapping).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-371">To continue, skip the next procedure, [Create a new model mapping configuration](#CreateModelMapping).</span></span>

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a><span data-ttu-id="bcc0a-372">Stwórz nowy model konfiguracji mapowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-372">Create a new model mapping configuration</span></span>

1. <span data-ttu-id="bcc0a-373">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-373">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-374">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-374">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="bcc0a-375">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-375">Select **Create configuration**.</span></span>
4. <span data-ttu-id="bcc0a-376">W oknie dialogowym rozwijanym wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-376">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-377">W polu **Nowy** wybierz **Mapowanie modelu oparte na modelu danych Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-377">In the **New** field, select **Model Mapping based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="bcc0a-378">W polu **Nazwa** wpisz **Mapowanie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-378">In the **Name** field, enter **Questionnaire mapping**.</span></span>
    3. <span data-ttu-id="bcc0a-379">W polu **Definicja modelu danych** wybierz definicję **Główną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-379">In the **Data model definition** field, select the **Root** definition.</span></span>
    4. <span data-ttu-id="bcc0a-380">Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-380">Select **Create configuration** to create the configuration.</span></span>

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a><span data-ttu-id="bcc0a-381">Projektowanie nowego składnika mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-381">Design a new model mapping component</span></span>

1. <span data-ttu-id="bcc0a-382">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Mapowanie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-382">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
2. <span data-ttu-id="bcc0a-383">Wybierz opcję **Projektant**, aby otworzyć listę mapowań.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-383">Select **Designer** to open the list of mappings.</span></span>
3. <span data-ttu-id="bcc0a-384">Wybierz **Mapowanie kwestionariuszy**, które zostało dodane automatycznie do definicji **Głównej**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-384">Select the **Questionnaires mapping** mapping that was automatically added for the **Root** definition</span></span>
4. <span data-ttu-id="bcc0a-385">Wybierz opcję **Projektant**, aby rozpocząć konfigurowanie wybranego mapowania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-385">Select **Designer** to start to configure the selected mapping.</span></span>

<span data-ttu-id="bcc0a-386">Nowe mapowanie jest automatycznie dodawane do definicji **Głównej**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-386">A new mapping is automatically added for the **Root** definition.</span></span> <span data-ttu-id="bcc0a-387">Mapowanie ma kierunek **Do modelu**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-387">This mapping has the **To model** direction.</span></span> <span data-ttu-id="bcc0a-388">Dlatego mapowanie może być używane do wypełniania modelu danych z wymaganymi danymi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-388">Therefore, this mapping can be used to fill in a data model with required data.</span></span>

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a><span data-ttu-id="bcc0a-389">Dodawanie źródeł danych w celu uzyskania dostępu do tabel aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-389">Add data sources to access application tables</span></span>

<span data-ttu-id="bcc0a-390">Należy skonfigurować źródła danych, aby uzyskać dostęp do tabel aplikacji zawierających szczegóły kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-390">You must configure data sources to access the application tables that contain questionnaire details.</span></span>

1. <span data-ttu-id="bcc0a-391">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-391">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="bcc0a-392">Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do tabeli KMCollection, gdzie każdy rekord reprezentuje jeden kwestionariusz:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-392">Add a new data source that will be used to access the KMCollection table, where every record represents a single questionnaire:</span></span>

    1. <span data-ttu-id="bcc0a-393">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-393">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-394">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-394">In dialog box, in the **Name** field, enter **Questionnaire**.</span></span>
    3. <span data-ttu-id="bcc0a-395">W polu **Tabela** wprowadź **KMCollection**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-395">In the **Table** field, enter **KMCollection**.</span></span>
    4. <span data-ttu-id="bcc0a-396">Ustaw wartość **Monituj o zapytanie** opcji **Włącz profil**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-396">Set the **Ask for query** option to **Yes**.</span></span> <span data-ttu-id="bcc0a-397">Będziesz wtedy mógł określić opcje [filtrowania](../../fin-ops/get-started/advanced-filtering-query-options.md) dla tej tabeli w oknie dialogowym zapytania systemowego w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-397">You will then be able to specify [filtering](../../fin-ops/get-started/advanced-filtering-query-options.md) options for this table in the system query dialog box at runtime.</span></span>
    5. <span data-ttu-id="bcc0a-398">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-398">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="bcc0a-399">W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-399">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
4. <span data-ttu-id="bcc0a-400">Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do tabeli KMQuestion, gdzie każdy rekord reprezentuje jedno pytanie w kwestionariuszu:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-400">Add a new data source that will be used to access the KMQuestion table, where every record represents a single question in a questionnaire:</span></span>

    1. <span data-ttu-id="bcc0a-401">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-401">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-402">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pytanie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-402">In the dialog box, in the **Name** field, enter **Question**.</span></span>
    3. <span data-ttu-id="bcc0a-403">W polu **Tabela** wprowadź **KMQuestion**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-403">In the **Table** field, enter **KMQuestion**.</span></span>
    4. <span data-ttu-id="bcc0a-404">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-404">Select **OK** to add the new data source.</span></span>

5. <span data-ttu-id="bcc0a-405">W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-405">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
6. <span data-ttu-id="bcc0a-406">Dodaj nową próbę źródła danych, które będzie używane w celu uzyskania dostępu do tabeli KMQuestion, gdzie każdy rekord reprezentuje jedną odpowiedź w kwestionariuszu:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-406">Add a new data source try that will be used to access the KMAnswer table, where every record represents a single answer to a question in a questionnaire:</span></span>

    1. <span data-ttu-id="bcc0a-407">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-407">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-408">W polu **Nazwa** wprowadź nazwę **Odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-408">In the **Name** field, enter **Answer**.</span></span>
    3. <span data-ttu-id="bcc0a-409">W polu **Tabela** wprowadź **KMAnswer**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-409">In the **Table** field, enter **KMAnswer**.</span></span>
    4. <span data-ttu-id="bcc0a-410">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-410">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="bcc0a-411">W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-411">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="bcc0a-412">Dodaj nowe pole obliczeniowe, które będzie używane w celu uzyskania dostępu do rekordu tabeli KMQuestionResultGroup z każdego rekordu tabeli KMCollection nadrzędnego:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-412">Add a new calculated field that will be used to access a record of the KMQuestionResultGroup table from every record of the parent KMCollection table:</span></span>

    1. <span data-ttu-id="bcc0a-413">W okienku **Źródła danych** wybierz **kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-413">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="bcc0a-414">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-414">Select **Add**.</span></span>
    3. <span data-ttu-id="bcc0a-415">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$ResultGroup**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-415">In the dialog box, in the **Name** field, enter **\$ResultGroup**.</span></span>
    4. <span data-ttu-id="bcc0a-416">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-416">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="bcc0a-417">W [Edytorze formuł ER](general-electronic-reporting-formula-designer.md) w polu **Formuła** wprowadź **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** do używania [ścieżki](er-formula-language.md#paths) relacji jeden-do-wielu między tabelami KMCollection i KMQuestionResultGroup.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-417">In the [ER formula editor](general-electronic-reporting-formula-designer.md), in the **Formula** field, enter **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** to use the [path](er-formula-language.md#paths) of the one-to-many relation between the KMCollection and KMQuestionResultGroup tables.</span></span>
    6. <span data-ttu-id="bcc0a-418">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-418">Select **Save**, and close the formula editor.</span></span>
    7. <span data-ttu-id="bcc0a-419">Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-419">Select **OK** to add the new calculated field.</span></span>

9. <span data-ttu-id="bcc0a-420">W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-420">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
10. <span data-ttu-id="bcc0a-421">Dodaj nowe pole obliczeniowe, które będzie używane do uzyskiwania dostępu do rekordów pytań w tabeli KMQuestion z każdego rekordu nadrzędnej tabeli KMCollectionQuestion:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-421">Add a new calculated field that will be used to access question records of the KMQuestion table from every record of the parent KMCollectionQuestion table:</span></span>

    1. <span data-ttu-id="bcc0a-422">W okienku **Źródła danych** wybierz **kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-422">In the **Data sources** pane, select **Questionnaire**.</span></span>
    2. <span data-ttu-id="bcc0a-423">Rozwiń węzeł **\<Relacje**, który zawiera relacje jeden-do-wielu w tabeli KMCollection.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-423">Expand the **\<Relations** node that contains one-to-many relations of the KMCollection table.</span></span>
    3. <span data-ttu-id="bcc0a-424">Zaznacz powiązaną tabelę **KMCollectionQuestion**, a następnie wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-424">Select the related **KMCollectionQuestion** table, and then select **Add**.</span></span>
    4. <span data-ttu-id="bcc0a-425">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$Pytanie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-425">In the dialog box, in the **Name** field, enter **\$Question**.</span></span>
    5. <span data-ttu-id="bcc0a-426">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-426">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="bcc0a-427">W edytorze formuł, w polu **Formuła** wprowadź **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))**, aby zwrócić odpowiednie rekordy pytań z tabeli KMQuestion.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-427">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** to return the appropriate question records from the KMQuestion table.</span></span>
    7. <span data-ttu-id="bcc0a-428">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-428">Select **Save**, and close the formula editor.</span></span>
    8. <span data-ttu-id="bcc0a-429">Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-429">Select **OK** to add the new calculated field.</span></span>

11. <span data-ttu-id="bcc0a-430">W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-430">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
12. <span data-ttu-id="bcc0a-431">Dodaj nowe pole obliczeniowe, które będzie używane do uzyskiwania dostępu do rekordów odpowiedzi tabeli KMAnswer z każdego rekordu nadrzędnej tabeli KMQuestion:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-431">Add a new calculated field that will be used to access answer records of the KMAnswer table from every record of the parent KMQuestion table:</span></span>

    1. <span data-ttu-id="bcc0a-432">W okienku **Źródła danych** wybierz opcję **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, a następnie wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-432">In the **Data sources** pane, select **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, and then select **Add**.</span></span>
    2. <span data-ttu-id="bcc0a-433">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **\$Odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-433">In the dialog box, in the **Name** field, enter **\$Answer**.</span></span>
    3. <span data-ttu-id="bcc0a-434">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-434">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="bcc0a-435">W edytorze formuł, w polu **Formuła** wprowadź **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)**, aby zwrócić odpowiednie rekordy odpowiedzi z tabeli KMAnswer.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-435">In the formula editor, in the **Formula** field, enter **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** to return the appropriate answer records from the KMAnswer table.</span></span>
    5. <span data-ttu-id="bcc0a-436">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-436">Select **Save**, and close the formula editor.</span></span>
    6. <span data-ttu-id="bcc0a-437">Wybierz przycisk **OK**, aby dodać nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-437">Select **OK** to add the new calculated field.</span></span>

13. <span data-ttu-id="bcc0a-438">W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Tabele**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-438">In the **Data source types** pane, select **Dynamics 365 for Operations\\Table**.</span></span>
14. <span data-ttu-id="bcc0a-439">Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do metod tabeli CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-439">Add a new data source that will be used to access methods of the CompanyInfo table.</span></span> <span data-ttu-id="bcc0a-440">Należy zauważyć, że metoda **find()** tej tabeli zwraca rekord reprezentujący firmę bieżącego wystąpienia Finance, które to mapowanie jest wywoływane w kontekście.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-440">Note that the **find()** method of this table returns a record that represents a company of the current Finance instance that this mapping is called in the context of.</span></span>

    1. <span data-ttu-id="bcc0a-441">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-441">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-442">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-442">In the dialog box, in the **Name** field, enter **CompanyInfo**.</span></span>
    3. <span data-ttu-id="bcc0a-443">W polu **Tabela** wprowadź **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-443">In the **Table** field, enter **CompanyInfo**.</span></span>
    4. <span data-ttu-id="bcc0a-444">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-444">Select **OK** to add the new data source.</span></span>

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a><span data-ttu-id="bcc0a-445">Dodawanie źródeł danych w celu uzyskania dostępu do wyliczenia aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-445">Add data sources to access application enumerations</span></span>

<span data-ttu-id="bcc0a-446">Należy skonfigurować źródła danych, aby uzyskać dostęp do wyliczeń aplikacji i porównać ich wartości z wartościami pól typu **Wyliczenie** w tabelach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-446">You must configure data sources to access application enumerations and compare their values with values of fields of the **Enumeration** type in the application tables.</span></span> <span data-ttu-id="bcc0a-447">Aby wypełnić odpowiednie pola modelu danych, należy skorzystać z wyników porównania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-447">You must use the result of the comparison to fill in appropriate fields of the data model.</span></span>

1. <span data-ttu-id="bcc0a-448">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Wyliczenie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-448">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
2. <span data-ttu-id="bcc0a-449">Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do wartości wyliczenia **EnumAppNoYes**:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-449">Add a new data source that will be used to access values of the **EnumAppNoYes** enumeration:</span></span>

    1. <span data-ttu-id="bcc0a-450">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-450">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-451">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **EnumAppNoYes**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-451">In the dialog box, in the **Name** field, enter **EnumAppNoYes**.</span></span>
    3. <span data-ttu-id="bcc0a-452">W polu **Wyliczenie** wprowadź **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-452">In the **Enumeration** field, enter **NoYes**.</span></span>
    4. <span data-ttu-id="bcc0a-453">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-453">Select **OK** to add the new data source.</span></span>

3. <span data-ttu-id="bcc0a-454">W okienku **Typy źródła danych** wybierz opcję **Dynamics 365 for Operations\\Wyliczenie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-454">In the **Data source types** pane, select **Dynamics 365 for Operations\\Enumeration**.</span></span>
4. <span data-ttu-id="bcc0a-455">Dodaj nowe źródło danych, które będzie używane w celu uzyskania dostępu do wartości wyliczenia **KMCollectionQuestionMode**:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-455">Add a new data source that will be used to access the values of the **KMCollectionQuestionMode** enumeration:</span></span>

    1. <span data-ttu-id="bcc0a-456">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-456">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-457">W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **EnumAppQuestionOrder**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-457">In the dialog box, in the **Name** field, enter **EnumAppQuestionOrder**.</span></span>
    3. <span data-ttu-id="bcc0a-458">W polu **Wyliczenie** wprowadź **EnumAppQuestionOrder**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-458">In the **Enumeration** field, enter **KMCollectionQuestionMode**.</span></span>
    4. <span data-ttu-id="bcc0a-459">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-459">Select **OK** to add the new data source.</span></span>

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a><span data-ttu-id="bcc0a-460">Dodawanie etykiet ER w celu wygenerowania raportu w określonym języku</span><span class="sxs-lookup"><span data-stu-id="bcc0a-460">Add ER labels to generate a report in a specified language</span></span>

<span data-ttu-id="bcc0a-461">Możesz dodać etykiety ER, aby skonfigurować niektóre źródła danych, aby zwracały wartości zależne od języka zdefiniowanego w kontekście wywołania mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-461">You can add ER labels to configure some of your data sources to return values that depend on the language that is defined in the context of the model mapping's call.</span></span>

1. <span data-ttu-id="bcc0a-462">Na stronie **Projektant mapowania modelu** w okienku **Źródła danych** wybierz **Odpowiedź**, a następnie wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-462">On the **Model mapping designer** page, in the **Data sources** pane, select **Answer**, and then select **Edit**.</span></span>
2. <span data-ttu-id="bcc0a-463">Aktywuj pole **Etykieta**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-463">Activate the **Label** field.</span></span>
3. <span data-ttu-id="bcc0a-464">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-464">Select **Translate**.</span></span>
4. <span data-ttu-id="bcc0a-465">W oknie dialogowym **Tłumaczenie tekstu** wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-465">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-466">W polu **Identyfikator etykiety** wejdź do **PositiveAnswer**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-466">In the **Label Id** field, enter **PositiveAnswer**.</span></span>
    2. <span data-ttu-id="bcc0a-467">W polu **tekst w języku domyślnym** wprowadź wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-467">In the **Text in default language** field, enter **Yes**.</span></span>
    3. <span data-ttu-id="bcc0a-468">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-468">Select **Translate**.</span></span>
    4. <span data-ttu-id="bcc0a-469">W polu **Identyfikator etykiety** wejdź do **NegativeAnswer**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-469">In the **Label Id** field, enter **NegativeAnswer**.</span></span>
    5. <span data-ttu-id="bcc0a-470">W polu **Tekst w języku domyślnym** wprowadź wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-470">In the **Text in default language** field, enter **No**.</span></span>
    6. <span data-ttu-id="bcc0a-471">Wybierz **Tłumacz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-471">Select **Translate**.</span></span>

5. <span data-ttu-id="bcc0a-472">Zamknij okno dialogowe **Tłumaczenie tekstu**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-472">Close the **Text translation** dialog box.</span></span>
6. <span data-ttu-id="bcc0a-473">Wybierz **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-473">Select **Cancel**.</span></span>

![Dodawanie etykiet ER dla mapowania edytowalnego modelu](./media/er-quick-start1-adding-labels.png)

<span data-ttu-id="bcc0a-475">Wprowadziłeś etykiety ER tylko dla języka domyślnego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-475">You've entered ER labels only for the default language.</span></span> <span data-ttu-id="bcc0a-476">Aby uzyskać informacje o tym, jak można tłumaczyć etykiety ER na inne języki, zobacz [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-476">For information about how ER labels can be translated into other languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a><span data-ttu-id="bcc0a-477">Dodaj źródło danych w celu przekształcenia wyników porównywania wartości wyliczenia z wartością tekstową</span><span class="sxs-lookup"><span data-stu-id="bcc0a-477">Add a data source to transform the results of comparing enumeration values to a text value</span></span>

<span data-ttu-id="bcc0a-478">Ponieważ należy kilkakrotnie przekształcić wyniki porównania między wartościami wyliczenia i wartościami tekstowymi w przypadku źródeł różnic, warto skonfigurować tę logikę jako pojedyncze źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-478">Because you must transform the results of the comparison between enumeration values and text values several times for difference sources, it's a good idea to configure this logic as a single data source.</span></span> <span data-ttu-id="bcc0a-479">Jednak aby to źródło danych było wielokrotnego użytku, należy skonfigurować je jako parametry źródła danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-479">However, to make this data source reusable, you must then configure it as the parametrized data source.</span></span> <span data-ttu-id="bcc0a-480">Aby uzyskać więcej informacji, zobacz [Obsługa sparametryzowanych wywołań źródeł danych narzędzia Raportowanie elektroniczne typu pola obliczeniowego](er-calculated-field-type.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-480">For more information, see [Support parameterized calls of ER data sources of the Calculated field type](er-calculated-field-type.md).</span></span>

1. <span data-ttu-id="bcc0a-481">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz **Ogólne\\Pusty kontener**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-481">On the **Model mapping designer** page, in the **Data source types** pane, select **General\\Empty container**.</span></span>
2. <span data-ttu-id="bcc0a-482">Dodaj nowe źródło danych kontenera:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-482">Add a new container data source:</span></span>

    1. <span data-ttu-id="bcc0a-483">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-483">In the **Data sources** pane, select **Add root**.</span></span>
    2. <span data-ttu-id="bcc0a-484">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pomocnik**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-484">In the dialog box, in the **Name** field, enter **Helper**.</span></span>
    3. <span data-ttu-id="bcc0a-485">Wybierz przycisk **OK**, aby dodać nowe źródło danych kontenera.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-485">Select **OK** to add the new container data source.</span></span>

3. <span data-ttu-id="bcc0a-486">W okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-486">In the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="bcc0a-487">Dodaj nowe źródło danych:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-487">Add a new data source:</span></span>

    1. <span data-ttu-id="bcc0a-488">W okienku **Źródła danych** wybierz **Pomocnik**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-488">In the **Data sources** pane, select **Helper**.</span></span>
    2. <span data-ttu-id="bcc0a-489">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-489">Select **Add**.</span></span>
    3. <span data-ttu-id="bcc0a-490">W oknie dialogowym rozwijanym w polu **nazwa** wprowadź **NoYesEnumToString**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-490">In the dialog box, in the **Name** field, enter **NoYesEnumToString**.</span></span>
    4. <span data-ttu-id="bcc0a-491">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-491">Select **Edit formula**.</span></span>
    5. <span data-ttu-id="bcc0a-492">W edytorze formuł wybierz opcję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-492">In the formula editor, select **Parameters**.</span></span>
    6. <span data-ttu-id="bcc0a-493">Wykonaj następujące kroki, aby określić parametry dla skonfigurowanego wyrażenia:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-493">Follow these steps to specify parameters for the configured expression:</span></span>

        1. <span data-ttu-id="bcc0a-494">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-494">Select **New**.</span></span>
        2. <span data-ttu-id="bcc0a-495">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Argument**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-495">In the dialog box, in the **Name** field, enter **Argument**.</span></span>
        3. <span data-ttu-id="bcc0a-496">W polu **Typ** wybierz typ danych **Wartość logiczna**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-496">In the **Type** field, select the **Boolean** data type.</span></span>
        4. <span data-ttu-id="bcc0a-497">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-497">Select **OK**.</span></span>

    7. <span data-ttu-id="bcc0a-498">W polu **Formuła** wprowadź **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")**, aby zwrócić tekst odpowiedniej etykiety ER, w zależności od języka kontekstu wykonywania i wartości określonego parametru.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-498">In the **Formula** field, enter **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** to return the text of the appropriate ER label, depending on the language of the execution context and value of the specified parameter.</span></span>
    8. <span data-ttu-id="bcc0a-499">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-499">Select **Save**, and close the formula editor.</span></span>
    9. <span data-ttu-id="bcc0a-500">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-500">Select **OK** to add the new data source.</span></span>

![Skonfigurowany model mapowania w projektancie modeli mapowania ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a><span data-ttu-id="bcc0a-502">Powiąż źródła danych z polami modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-502">Bind data sources to data model fields</span></span>

<span data-ttu-id="bcc0a-503">Aby określić sposób, w jaki model danych będzie wypełniał dane aplikacji w czasie wykonywania, należy powiązać skonfigurowane źródła danych z polami modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-503">You must bind the configured data sources to the fields of the data model to specify how the data model will by filled in with application data at runtime.</span></span>

1. <span data-ttu-id="bcc0a-504">Na stronie **Projektant mapowania modelu** w okienku **Model danych** wybierz **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-504">On the **Model mapping designer** page, in the **Data model** pane, select **CompanyName**.</span></span>
2. <span data-ttu-id="bcc0a-505">W okienku **Źródła danych** rozwiń węzeł **CompanyInfo**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-505">In the **Data sources** pane, expand **CompanyInfo**, and then follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-506">Rozwiń węzeł **CompanyInfo.find()**, który reprezentuje metodę **find()** tabeli CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-506">Expand the **CompanyInfo.find()** node that represents the **find()** method of the CompanyInfo table.</span></span>
    2. <span data-ttu-id="bcc0a-507">Wybierz **CompanyInfo.find().Name**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-507">Select **CompanyInfo.find().Name**.</span></span>
    3. <span data-ttu-id="bcc0a-508">Wybierz opcję **Powiąż**, aby wpisać nazwę firmy, z której wywoływane jest skonfigurowane mapowanie modelu w kontekście at runtime.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-508">Select **Bind** to fill in the name of the company that the configured model mapping is called in the context of at runtime.</span></span>

3. <span data-ttu-id="bcc0a-509">W okienku **Model danych** wybierz **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-509">In the **Data model** pane, select **Questionnaire**.</span></span>
4. <span data-ttu-id="bcc0a-510">W okienku **Źródła danych** wybierz opcję **Kwestionariusz**, a następnie wybierz **Powiąż**, aby wypełnić rekordy kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-510">In the **Data sources** pane, select **Questionnaire**, and then select **Bind** to fill in questionnaire records.</span></span>
5. <span data-ttu-id="bcc0a-511">W okienku **Model danych** rozwiń węzeł **Kwestionariusz**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-511">In the **Data model** pane, expand **Questionnaire**, and then follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-512">W okienku **Model danych** wybierz **Aktywne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-512">In the **Data model** pane, select **Active**.</span></span>
    2. <span data-ttu-id="bcc0a-513">W okienku **Model danych** wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-513">In the **Data model** pane, select **Edit**.</span></span>
    3. <span data-ttu-id="bcc0a-514">W polu **Formuła** wprowadź wartość **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)**, aby wypełnić wynik porównania między wartościami wyliczenia zależne od tekstu i języka.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-514">In the **Formula** field, enter **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** to fill the text-dependent and language-dependent result of the comparison between enumeration values.</span></span>

6. <span data-ttu-id="bcc0a-515">Kontynuuj wiązanie źródeł danych z polami modelu danych w ten sam sposób, aż uzyskasz następujący wynik.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-515">Continue to bind data sources to data model fields in the same manner until you achieve the following result.</span></span>

    | <span data-ttu-id="bcc0a-516">Ścieżka pola</span><span class="sxs-lookup"><span data-stu-id="bcc0a-516">Field path</span></span>                                              | <span data-ttu-id="bcc0a-517">Typ danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-517">Data type</span></span>   | <span data-ttu-id="bcc0a-518">Akcja</span><span class="sxs-lookup"><span data-stu-id="bcc0a-518">Action</span></span> | <span data-ttu-id="bcc0a-519">Wyrażenie wiązania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-519">Binding expression</span></span> |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | <span data-ttu-id="bcc0a-520">CompanyName</span><span class="sxs-lookup"><span data-stu-id="bcc0a-520">CompanyName</span></span>                                             | <span data-ttu-id="bcc0a-521">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-521">String</span></span>      | <span data-ttu-id="bcc0a-522">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-522">Bind</span></span>   | <span data-ttu-id="bcc0a-523">CompanyInfo.'find()'.Name</span><span class="sxs-lookup"><span data-stu-id="bcc0a-523">CompanyInfo.'find()'.Name</span></span> |
    | <span data-ttu-id="bcc0a-524">Kwestionariusz</span><span class="sxs-lookup"><span data-stu-id="bcc0a-524">Questionnaire</span></span>                                           | <span data-ttu-id="bcc0a-525">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-525">Record list</span></span> | <span data-ttu-id="bcc0a-526">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-526">Bind</span></span>   | <span data-ttu-id="bcc0a-527">Kwestionariusz</span><span class="sxs-lookup"><span data-stu-id="bcc0a-527">Questionnaire</span></span> |
    | <span data-ttu-id="bcc0a-528">Kwestionariusz\\Aktywny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-528">Questionnaire\\Active</span></span>                                   | <span data-ttu-id="bcc0a-529">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-529">String</span></span>      | <span data-ttu-id="bcc0a-530">Edycja</span><span class="sxs-lookup"><span data-stu-id="bcc0a-530">Edit</span></span>   | <span data-ttu-id="bcc0a-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="bcc0a-531">Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="bcc0a-532">Kwestionariusz\\Kod</span><span class="sxs-lookup"><span data-stu-id="bcc0a-532">Questionnaire\\Code</span></span>                                     | <span data-ttu-id="bcc0a-533">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-533">String</span></span>      | <span data-ttu-id="bcc0a-534">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-534">Bind</span></span>   | <span data-ttu-id="bcc0a-535">\@.kmCollectionId</span><span class="sxs-lookup"><span data-stu-id="bcc0a-535">\@.kmCollectionId</span></span> |
    | <span data-ttu-id="bcc0a-536">Kwestionariusz\\Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-536">Questionnaire\\Description</span></span>                              | <span data-ttu-id="bcc0a-537">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-537">String</span></span>      | <span data-ttu-id="bcc0a-538">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-538">Bind</span></span>   | <span data-ttu-id="bcc0a-539">\@.Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-539">\@.Description</span></span> |
    | <span data-ttu-id="bcc0a-540">Kwestionariusz\\TypKwestionariusza</span><span class="sxs-lookup"><span data-stu-id="bcc0a-540">Questionnaire\\QuestionnaireType</span></span>                        | <span data-ttu-id="bcc0a-541">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-541">String</span></span>      | <span data-ttu-id="bcc0a-542">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-542">Bind</span></span>   | <span data-ttu-id="bcc0a-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span><span class="sxs-lookup"><span data-stu-id="bcc0a-543">\@.'&gt;Relations'.kmCollectionTypeId.Description</span></span> |
    | <span data-ttu-id="bcc0a-544">Kwestionariusz\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="bcc0a-544">Questionnaire\\QuestionOrder</span></span>                            | <span data-ttu-id="bcc0a-545">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-545">String</span></span>      | <span data-ttu-id="bcc0a-546">Edycja</span><span class="sxs-lookup"><span data-stu-id="bcc0a-546">Edit</span></span>   | <span data-ttu-id="bcc0a-547">CASE (\@.questionMode,</span><span class="sxs-lookup"><span data-stu-id="bcc0a-547">CASE (\@.questionMode,</span></span><br><span data-ttu-id="bcc0a-548">EnumAppQuestionOrder.Conditional, "Conditional",</span><span class="sxs-lookup"><span data-stu-id="bcc0a-548">EnumAppQuestionOrder.Conditional, "Conditional",</span></span><br><span data-ttu-id="bcc0a-549">EnumAppQuestionOrder.Random, „Losowo (procent w kwestionariuszu)”,</span><span class="sxs-lookup"><span data-stu-id="bcc0a-549">EnumAppQuestionOrder.Random, "Random (percentage in questionnaire)",</span></span><br><span data-ttu-id="bcc0a-550">EnumAppQuestionOrder.RandomGroup, „Losowo (procent w grupach wyników)”,</span><span class="sxs-lookup"><span data-stu-id="bcc0a-550">EnumAppQuestionOrder.RandomGroup, "Random (percentage in result groups)",</span></span><br><span data-ttu-id="bcc0a-551">EnumAppQuestionOrder.Sequence, „Sekwencyjne”,</span><span class="sxs-lookup"><span data-stu-id="bcc0a-551">EnumAppQuestionOrder.Sequence, "Sequential",</span></span><br><span data-ttu-id="bcc0a-552">"")</span><span class="sxs-lookup"><span data-stu-id="bcc0a-552">"")</span></span> |
    | <span data-ttu-id="bcc0a-553">Kwestionariusz\\ResultsGroup</span><span class="sxs-lookup"><span data-stu-id="bcc0a-553">Questionnaire\\ResultsGroup</span></span>                             | <span data-ttu-id="bcc0a-554">Zarejestruj</span><span class="sxs-lookup"><span data-stu-id="bcc0a-554">Record</span></span>      |        | |
    | <span data-ttu-id="bcc0a-555">Kwestionariusz\\ResultsGroup\\Kod</span><span class="sxs-lookup"><span data-stu-id="bcc0a-555">Questionnaire\\ResultsGroup\\Code</span></span>                       | <span data-ttu-id="bcc0a-556">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-556">String</span></span>      | <span data-ttu-id="bcc0a-557">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-557">Bind</span></span>   | <span data-ttu-id="bcc0a-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span><span class="sxs-lookup"><span data-stu-id="bcc0a-558">\@.'\$ResultGroup'.kmQuestionResultGroupId</span></span> |
    | <span data-ttu-id="bcc0a-559">Kwestionariusz\\ResultsGroup\\Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-559">Questionnaire\\ResultsGroup\\Description</span></span>                | <span data-ttu-id="bcc0a-560">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-560">String</span></span>      | <span data-ttu-id="bcc0a-561">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-561">Bind</span></span>   | <span data-ttu-id="bcc0a-562">\@.'\$ResultGroup'.description</span><span class="sxs-lookup"><span data-stu-id="bcc0a-562">\@.'\$ResultGroup'.description</span></span> |
    | <span data-ttu-id="bcc0a-563">Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="bcc0a-563">Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>          | <span data-ttu-id="bcc0a-564">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-564">Real</span></span>        | <span data-ttu-id="bcc0a-565">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-565">Bind</span></span>   | <span data-ttu-id="bcc0a-566">\@.'\$ResultGroup'.maxPoint</span><span class="sxs-lookup"><span data-stu-id="bcc0a-566">\@.'\$ResultGroup'.maxPoint</span></span> |
    | <span data-ttu-id="bcc0a-567">Kwestionariusz\\Pytanie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-567">Questionnaire\\Question</span></span>                                 | <span data-ttu-id="bcc0a-568">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-568">Record list</span></span> | <span data-ttu-id="bcc0a-569">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-569">Bind</span></span>   | <span data-ttu-id="bcc0a-570">\@.'&lt;Relations'.KMCollectionQuestion</span><span class="sxs-lookup"><span data-stu-id="bcc0a-570">\@.'&lt;Relations'.KMCollectionQuestion</span></span> |
    | <span data-ttu-id="bcc0a-571">Kwestionariusz\\Pytanie\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-571">Questionnaire\\Question\\CollectionSequenceNumber</span></span>       | <span data-ttu-id="bcc0a-572">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-572">Integer</span></span>     | <span data-ttu-id="bcc0a-573">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-573">Bind</span></span>   | <span data-ttu-id="bcc0a-574">\@.answerCollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-574">\@.answerCollectionSequenceNumber</span></span> |
    | <span data-ttu-id="bcc0a-575">Kwestionariusz\\Pytanie\\Identyfikator</span><span class="sxs-lookup"><span data-stu-id="bcc0a-575">Questionnaire\\Question\\Id</span></span>                             | <span data-ttu-id="bcc0a-576">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-576">String</span></span>      | <span data-ttu-id="bcc0a-577">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-577">Bind</span></span>   | <span data-ttu-id="bcc0a-578">\@.kmQuestionId</span><span class="sxs-lookup"><span data-stu-id="bcc0a-578">\@.kmQuestionId</span></span> |
    | <span data-ttu-id="bcc0a-579">Kwestionariusz\\Pytanie\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="bcc0a-579">Questionnaire\\Question\\MustBeCompleted</span></span>                | <span data-ttu-id="bcc0a-580">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-580">String</span></span>      | <span data-ttu-id="bcc0a-581">Edycja</span><span class="sxs-lookup"><span data-stu-id="bcc0a-581">Edit</span></span>   | <span data-ttu-id="bcc0a-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="bcc0a-582">Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="bcc0a-583">Kwestionariusz\\Pytanie\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="bcc0a-583">Questionnaire\\Question\\PrimaryQuestion</span></span>                | <span data-ttu-id="bcc0a-584">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-584">String</span></span>      | <span data-ttu-id="bcc0a-585">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-585">Bind</span></span>   | <span data-ttu-id="bcc0a-586">\@.parentQuestionId</span><span class="sxs-lookup"><span data-stu-id="bcc0a-586">\@.parentQuestionId</span></span> |
    | <span data-ttu-id="bcc0a-587">Kwestionariusz\\Pytanie\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-587">Questionnaire\\Question\\SequenceNumber</span></span>                 | <span data-ttu-id="bcc0a-588">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-588">Integer</span></span>     | <span data-ttu-id="bcc0a-589">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-589">Bind</span></span>   | <span data-ttu-id="bcc0a-590">\@.SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-590">\@.SequenceNumber</span></span> |
    | <span data-ttu-id="bcc0a-591">Kwestionariusz\\Pytanie\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-591">Questionnaire\\Question\\Text</span></span>                           | <span data-ttu-id="bcc0a-592">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-592">String</span></span>      | <span data-ttu-id="bcc0a-593">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-593">Bind</span></span>   | <span data-ttu-id="bcc0a-594">\@.'\$Question'.text</span><span class="sxs-lookup"><span data-stu-id="bcc0a-594">\@.'\$Question'.text</span></span> |
    | <span data-ttu-id="bcc0a-595">Kwestionariusz\\Pytanie\\Odpowiedź</span><span class="sxs-lookup"><span data-stu-id="bcc0a-595">Questionnaire\\Question\\Answer</span></span>                         | <span data-ttu-id="bcc0a-596">Lista rekordów</span><span class="sxs-lookup"><span data-stu-id="bcc0a-596">Record list</span></span> | <span data-ttu-id="bcc0a-597">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-597">Bind</span></span>   | <span data-ttu-id="bcc0a-598">\@.'\$Question'.'\$Answer'</span><span class="sxs-lookup"><span data-stu-id="bcc0a-598">\@.'\$Question'.'\$Answer'</span></span> |
    | <span data-ttu-id="bcc0a-599">Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="bcc0a-599">Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>          | <span data-ttu-id="bcc0a-600">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-600">String</span></span>      | <span data-ttu-id="bcc0a-601">Edycja</span><span class="sxs-lookup"><span data-stu-id="bcc0a-601">Edit</span></span>   | <span data-ttu-id="bcc0a-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span><span class="sxs-lookup"><span data-stu-id="bcc0a-602">Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes)</span></span> |
    | <span data-ttu-id="bcc0a-603">Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-603">Questionnaire\\Question\\Answer\\Points</span></span>                 | <span data-ttu-id="bcc0a-604">Rzeczywisty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-604">Real</span></span>        | <span data-ttu-id="bcc0a-605">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-605">Bind</span></span>   | <span data-ttu-id="bcc0a-606">\@.point</span><span class="sxs-lookup"><span data-stu-id="bcc0a-606">\@.point</span></span> |
    | <span data-ttu-id="bcc0a-607">Kwestionariusz\\Pytanie\\Odpowiedź\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-607">Questionnaire\\Question\\Answer\\SequenceNumber</span></span>         | <span data-ttu-id="bcc0a-608">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="bcc0a-608">Integer</span></span>     | <span data-ttu-id="bcc0a-609">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-609">Bind</span></span>   | <span data-ttu-id="bcc0a-610">\@.sequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-610">\@.sequenceNumber</span></span> |
    | <span data-ttu-id="bcc0a-611">Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-611">Questionnaire\\Question\\Answer\\Text</span></span>                   | <span data-ttu-id="bcc0a-612">Ciąg</span><span class="sxs-lookup"><span data-stu-id="bcc0a-612">String</span></span>      | <span data-ttu-id="bcc0a-613">Powiąż</span><span class="sxs-lookup"><span data-stu-id="bcc0a-613">Bind</span></span>   | <span data-ttu-id="bcc0a-614">\@.text</span><span class="sxs-lookup"><span data-stu-id="bcc0a-614">\@.text</span></span> |

    <span data-ttu-id="bcc0a-615">Na poniższej ilustracji przedstawiono ostatni stan skonfigurowanego mapowania modelu na stronie **Projektanta mapowania modeli**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-615">The following illustration shows the final state of the configured model mapping on the **Model mapping designer** page.</span></span>

    ![W pełni skonfigurowany model mapowania w projektancie modeli mapowania ER](./media/er-quick-start1-mapping2.png)

7. <span data-ttu-id="bcc0a-617">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-617">Save your changes.</span></span>
8. <span data-ttu-id="bcc0a-618">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-618">Close the **Model mapping designer** page.</span></span>

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a><span data-ttu-id="bcc0a-619">Umożliwia zakończenie projektu mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-619">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="bcc0a-620">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-620">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-621">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Mapowanie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-621">On the **Configurations** page, in the configuration tree, select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="bcc0a-622">Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-622">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="bcc0a-623">Wybierz **Zmień status** \> **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-623">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="bcc0a-624">Stan wersja 1.1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-624">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="bcc0a-625">Wersja 1.1 nie może być już zmieniana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-625">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="bcc0a-626">Ta wersja zawiera skonfigurowany model mapowania i może być używana jako podstawa dla innych konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-626">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="bcc0a-627">Wersja 1.2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-627">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="bcc0a-628">Tę wersję można edytować, aby skorygować konfigurację **Mapowanie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-628">You can edit this version to adjust the **Questionnaire mapping** configuration.</span></span>

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> <span data-ttu-id="bcc0a-630">Skonfigurowane mapowanie modelu to specyficzna dla finansów implementacja abstrakcyjnego modelu danych, który reprezentuje domenę biznesową **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-630">The configured model mapping is your Finance-specific implementation of the abstract data model that represents the **Questionnaire** business domain.</span></span>

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a><span data-ttu-id="bcc0a-631">Projektowanie szablonu raportu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="bcc0a-631">Design a template for a custom report</span></span>

<span data-ttu-id="bcc0a-632">Struktura ER wykorzystuje predefiniowane szablony do generowania raportów w formatach Microsoft Office (skoroszyty programu Excel lub dokumenty Word).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-632">The ER framework uses predefined templates to generate reports in Microsoft Office formats (Excel workbooks or Word documents).</span></span> <span data-ttu-id="bcc0a-633">Podczas generowania wymaganego raportu szablon jest wypełniany wymaganymi danymi zgodnie ze skonfigurowanym przepływem danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-633">While the required report is being generated, a template is filled in with required data according to the configured dataflow.</span></span> <span data-ttu-id="bcc0a-634">Dlatego należy najpierw zaprojektować szablon raportu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-634">Therefore, you must first design a template for your custom report.</span></span> <span data-ttu-id="bcc0a-635">Ten szablon musi być zaprojektowany jako skoroszyt programu Excel, którego struktura reprezentuje układ raportu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-635">This template must be designed as an Excel workbook, the structure of which represents the layout of a custom report.</span></span> <span data-ttu-id="bcc0a-636">Należy nazwać każdy element programu Excel, który ma być wypełniony wymaganymi danymi.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-636">You must name every Excel item that you plan to fill in with required data.</span></span>

1. <span data-ttu-id="bcc0a-637">Pobierz [Szablon raportu kwestionariusza.xslx](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-637">Download the [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="bcc0a-638">Otwórz plik w programie Excel i przejrzyj strukturę skoroszytu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-638">Open the file in Excel, and review the structure of the workbook.</span></span>

<span data-ttu-id="bcc0a-639">Jak pokazuje poniższa ilustracja, pobrany szablon został zaprojektowany w celu wydrukowania określonych kwestionariuszy, które zawierają pytania zawarte w kwestionariuszu wraz z odpowiednimi odpowiedziami.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-639">As the following illustration shows, the downloaded template has been designed to print specified questionnaires that present a questionnaire's questions together with appropriate answers.</span></span>

![Szablon programu Excel do drukowania określonych kwestionariuszy](./media/er-quick-start1-template-layout.png)

<span data-ttu-id="bcc0a-641">Do tego szablonu zostały dodane nazwy programu Excel, aby wypełnić szczegóły kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-641">Excel names have been added to this template to fill in the questionnaire details.</span></span> <span data-ttu-id="bcc0a-642">Do przeglądania nazw Excel można użyć Menedżera nazw.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-642">You can use Name Manager to review the Excel names.</span></span>

![Przeglądanie nazw programu Excel w podanym szablonie programu Excel za pomocą Menedżera nazw](./media/er-quick-start1-template-names.png)

<span data-ttu-id="bcc0a-644">Etykiety raportów zostały dodane jako stały tekst w języku angielskim.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-644">Report labels have been added as fixed text in the English language.</span></span> <span data-ttu-id="bcc0a-645">Etykiety raportów można zastąpić nowymi nazwami programu Excel, które wypełniają etykiety tekstem zależnym od języka, używając [etykiet](#AddMmLabels) formatu ER, tak jak w przypadku wyrażeń zależnych od języka w skonfigurowanym mapowaniu modelu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-645">You can replace the report labels with new Excel names that fill in the labels with language-dependent text by using the ER format [labels](#AddMmLabels), as you did for language-dependent expressions in the configured model mapping.</span></span> <span data-ttu-id="bcc0a-646">W takim przypadku do edytowalnego formatu ER trzeba dodać etykiety ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-646">In this case, ER labels must be added in the editable ER format.</span></span>

<span data-ttu-id="bcc0a-647">Na poniższej ilustracji przedstawiono nagłówek raportu niestandardowego, który umożliwia stronicowanie w Excel.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-647">As the following illustration shows, the custom report header has been specified to enable Excel to do paging.</span></span>

![Niestandardowy nagłówek raportu w podanym szablonie programu Excel](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a><span data-ttu-id="bcc0a-649">Projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-649">Design a format</span></span>

<span data-ttu-id="bcc0a-650">Jako użytkownik pełniący rolę konsultanta funkcjonalnego raportowania elektronicznego należy utworzyć nową konfigurację ER zawierającą komponent [formatu](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-650">As a user in the Electronic Reporting Functional Consultant role, you must create a new ER configuration that contains a [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="bcc0a-651">Należy skonfigurować składnik formatu w celu określenia sposobu, w jaki szablon raportu będzie wypełniał wymagane dane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-651">You must configure the format component to specify how a report template will be filled in with required data at runtime.</span></span>

<span data-ttu-id="bcc0a-652">Wykonując kroki opisane w sekcji [Import zaprojektowanej konfiguracji formatu](#FormatImport), można zaimportować wymagany format z podanego pliku XML.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-652">By completing the steps in the [Import a designed format configuration](#FormatImport) section, you can import the required format from the provided XML file.</span></span> <span data-ttu-id="bcc0a-653">Można również wykonać kroki opisane w sekcji [Utwórz nową konfigurację formatu](#FormatCreate), aby zaprojektować ten format od podstaw.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-653">Alternatively, you can complete the steps in the [Create a new format configuration](#FormatCreate) section to design this format from scratch.</span></span>

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a><span data-ttu-id="bcc0a-654">Import zaprojektowanej konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-654">Import a designed format configuration</span></span>

1. <span data-ttu-id="bcc0a-655">Pobierz [Kwestionariusze formatu.wersja.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) i zapisz go na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-655">Download the [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) file, and save it to your local computer.</span></span>
2. <span data-ttu-id="bcc0a-656">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-656">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="bcc0a-657">W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-657">In the **Electronic reporting** workspace, select **Reporting configurations**.</span></span>
4. <span data-ttu-id="bcc0a-658">W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-658">On the Action pane, Select **Exchange** \> **Load from XML file**.</span></span>
5. <span data-ttu-id="bcc0a-659">Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Format kwestionariuszy.wersja.1.1.xml**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-659">Select **Browse**, and then find and select the **Questionnaires format.version.1.1.xml** file.</span></span>
6. <span data-ttu-id="bcc0a-660">Wybierz przycisk **OK**, aby importować konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-660">Select **OK** to import the configuration.</span></span>

<span data-ttu-id="bcc0a-661">Aby kontynuować, pomiń następną procedurę, [Utwórz nową konfigurację formatu](#FormatCreate).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-661">To continue, skip the next procedure, [Create a new format configuration](#FormatCreate).</span></span>

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a><span data-ttu-id="bcc0a-662">Utwórz nową konfigurację formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-662">Create a new format configuration</span></span>
 
1. <span data-ttu-id="bcc0a-663">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-663">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-664">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Model kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-664">On the **Configurations** page, in the configuration tree, select **Questionnaire model**.</span></span>
3. <span data-ttu-id="bcc0a-665">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-665">Select **Create configuration**.</span></span>
4. <span data-ttu-id="bcc0a-666">W oknie dialogowym rozwijanym wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-666">In the drop-down dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-667">W polu **Nowy** wybierz **Format oparty na modelu danych Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-667">In the **New** field, select **Format based on data model Questionnaires**.</span></span>
    2. <span data-ttu-id="bcc0a-668">W polu **Nazwa** wpisz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-668">In the **Name** field, enter **Questionnaire report**.</span></span>
    3. <span data-ttu-id="bcc0a-669">W polu **Wersja modelu danych** wybierz **1**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-669">In the **Data model version** field, select **1**.</span></span>

        > [!NOTE]
        > - <span data-ttu-id="bcc0a-670">W przypadku wybrania określonej wersji podstawowego modelu danych, struktura odpowiedniej wersji modelu danych zostanie przedstawiona jako struktura **Modelu** źródła danych w utworzonym formacie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-670">If you select a specific version of the base data model, the structure of the corresponding version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span>
        > - <span data-ttu-id="bcc0a-671">Można pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-671">You can leave this field blank.</span></span> <span data-ttu-id="bcc0a-672">W takim przypadku struktura **Wersji roboczej** modelu danych zostanie przedstawiona jako struktura źródła danych **Modelu** w utworzonym formacie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-672">In that case, the structure of the **Draft** version of the data model will be presented to you as the structure of the **Model** data source in the format that is created.</span></span> <span data-ttu-id="bcc0a-673">Następnie można dostosować model i natychmiast zobaczyć te zmiany w formacie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-673">You can then adjust your model and immediately see those adjustments in your format.</span></span> <span data-ttu-id="bcc0a-674">Takie podejście może poprawić wydajność projektu rozwiązania ER podczas konfigurowania modelu danych, mapowania modelu i formatowania jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-674">This approach might improve the efficiency of ER solution design when you configure your data model, model mapping, and format simultaneously.</span></span>
        > - <span data-ttu-id="bcc0a-675">W przypadku wybrania konkretnej wersji podstawowego modelu danych można użyć **Wersji roboczej** w późniejszym czasie, gdy zaczniesz edytować format.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-675">If you select a specific version of the base data model, you can switch to using the **Draft** version later, when you start to edit a format.</span></span>

    4. <span data-ttu-id="bcc0a-676">W polu **Definicja modelu danych** wybierz definicję **Główną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-676">In the **Data model definition** field, select the **Root** definition.</span></span>

5. <span data-ttu-id="bcc0a-677">Wybierz **Stwórz konfiguracj**, aby stworzyć konfigurację.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-677">Select **Create configuration** to create the configuration.</span></span>

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a><span data-ttu-id="bcc0a-678">Zaimportuj szablon raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-678">Import a report template</span></span>

1. <span data-ttu-id="bcc0a-679">Na stronie **Konfiguracje** w drzewie konfiguracje wybierz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-679">On the **Configurations** page, in the configuration tree, select **Questionnaire report**.</span></span>
2. <span data-ttu-id="bcc0a-680">Wybierz opcję **Projektant**, aby rozpocząć konfigurowanie formatu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-680">Select **Designer** to start to configure a custom format.</span></span>
3. <span data-ttu-id="bcc0a-681">Na stronie **Projektant formatu** w okienku akcji wybierz **Importuj** \> **Importuj z programu Excel**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-681">On the **Format designer** page, on the Action Pane, select **Import** \> **Import from Excel**.</span></span>
4. <span data-ttu-id="bcc0a-682">W oknie dialogowym wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-682">In the dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-683">Wybierz **Dodaj szablon**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-683">Select **Add template**.</span></span>
    2. <span data-ttu-id="bcc0a-684">Znajdź i wybierz lokalnie zapisany plik **Szablon raportu kwestionariusza.xslx**, a następnie wybierz opcję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-684">Find and select the locally saved **Questionnaires report template.xslx** file, and then select **Open**.</span></span>
    3. <span data-ttu-id="bcc0a-685">Wybierz przycisk **OK**, aby importować szablon.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-685">Select **OK** to import the template.</span></span>

    ![Importowanie szablonu raportu](./media/er-quick-start1-template-import.png)

<span data-ttu-id="bcc0a-687">Element formatu **Excel\\Plik** jest automatycznie dodawany do formatu edytowalnego jako element główny.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-687">The **Excel\\File** format element is automatically added to the editable format as a root element.</span></span> <span data-ttu-id="bcc0a-688">Dodatkowo, element formatu **Excel\\Zakres** lub element formatu **Excel\\Komórka** jest automatycznie dodawany do każdej rozpoznanej nazwy Excela importowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-688">Additionally, either the **Excel\\Range** format element or the **Excel\\Cell** format element is automatically added for every recognized Excel name of the imported template.</span></span> <span data-ttu-id="bcc0a-689">Format **Excel\\Nagłówek** z zagnieżdżonym elementem **Ciąg** jest dodawany automatycznie w celu odzwierciedlenia ustawień nagłówka zaimportowanego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-689">The **Excel\\Header** format that has the nested **String** element is automatically added to reflect the header settings of the imported template.</span></span>

![Struktura formatu obejmująca automatycznie dodane elementy w projektancie operacji ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a><span data-ttu-id="bcc0a-691">Konfigurowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-691">Configure a format</span></span>

1. <span data-ttu-id="bcc0a-692">Na stronie **Projektant formatów** w drzewie formatu wybierz element główny programu **Excel**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-692">On the **Format designer** page, in the format tree, select the **Excel** root element.</span></span>
2. <span data-ttu-id="bcc0a-693">Na karcie **Format** po prawej stronie strony, w polu **Nazwa** wprowadź <a name="AddFormatRootElement"></a>**Raport**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-693">On the **Format** tab on the right side of the page, in the **Name** field, enter <a name="AddFormatRootElement"></a>**Report**.</span></span>
3. <span data-ttu-id="bcc0a-694">W polu **Preferencje języka** wybierz opcję **Preferencje użytkownika**, aby uruchomić raport w preferowanym języku użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-694">In the **Language preference** field, select **User preference** to run the report in the user's preferred language.</span></span>
4. <span data-ttu-id="bcc0a-695">W polu **Preferencje dotyczące kultury** wybierz opcję **Preferencje użytkownika**, aby uruchomić raport dostosowany do preferencji kulturowych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-695">In the **Culture preference** field, select **User preference** to run the report in the user's preferred culture.</span></span>

    <span data-ttu-id="bcc0a-696">Aby uzyskać informacje dotyczące sposobu określania kontekstu języka i kultury dla procesu ER, zapoznaj się z tematem [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-696">For information about how to specify the language and culture contexts for an ER process, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

    ![Konfigurowanie ustawień języka i kultury dla zaprojektowanego raportu w projektancie operacji ER](./media/er-quick-start1-template-format-structure1.png)

5. <span data-ttu-id="bcc0a-698">W drzewie formatu rozwiń węzeł główny, a następnie wybierz pozycję **ResultsGroup**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-698">In the format tree, expand the root node, and then select **ResultsGroup**.</span></span>
6. <span data-ttu-id="bcc0a-699">Na karcie **Format** w polu **Kierunek replikacji** wybierz opcję **Brak replikacji**, ponieważ nie ma oczekiwanego wielu grup wyników dla jednego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-699">On the **Format** tab, in the **Replication direction** field, select **No replication**, because you don't expect to have multiple result groups for a single questionnaire.</span></span>

    ![Definiowanie kierunku replikacji dla elementów formatu zakresu w projektancie operacji ER](./media/er-quick-start1-template-format-structure2.png)

7. <span data-ttu-id="bcc0a-701">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-701">Select **Save**.</span></span>

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a><span data-ttu-id="bcc0a-702">Definiowanie powiązania danych dla tytułu raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-702">Define the data binding for a report title</span></span>

<span data-ttu-id="bcc0a-703">Należy określić powiązanie danych dla elementu formatu używanego do wypełniania tytułu wygenerowanego raportu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-703">You must specify a data binding for a format element that is used to fill in the title of a generated report.</span></span>

1. <span data-ttu-id="bcc0a-704">Na stronie **Projektant formatów** na karcie **Mapowanie** po prawej stronie wybierz element pliku **Raport\\ReportTitle** w drzewie formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-704">On the **Format designer** page, on the **Mapping** tab on the right, select the **Report\\ReportTitle** element.</span></span>
2. <span data-ttu-id="bcc0a-705">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-705">Select **Edit formula**.</span></span>
3. <span data-ttu-id="bcc0a-706">W edytorze formuł wybierz opcję **Przetłumacz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-706">In the formula editor, select **Translate**.</span></span>
4. <span data-ttu-id="bcc0a-707">W oknie dialogowym **Tłumaczenie tekstu** wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-707">In the **Text translation** dialog box, follow these steps:</span></span>

    1. <span data-ttu-id="bcc0a-708">W polu **Identyfikator etykiety** wejdź do **ReportTitle**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-708">In the **Label ID** field, enter **ReportTitle**.</span></span>
    2. <span data-ttu-id="bcc0a-709">W polu **Tekst w języku domyślnym** wprowadź wartość **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-709">In the **Text in default language** field, enter **Questionnaires report**.</span></span>
    3. <span data-ttu-id="bcc0a-710">Zaznacz element **Przetłumacz** i kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-710">Select **Translate**, and then select **Save**.</span></span>
    4. <span data-ttu-id="bcc0a-711">Wybierz opcję **Przetłumacz**, aby zamknąć okno dialogowe **Tłumaczenie tekstu**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-711">Select **Translate** to close the **Text translation** dialog box.</span></span>

5. <span data-ttu-id="bcc0a-712">Zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-712">Close the formula editor.</span></span>

    ![Konfigurowanie powiązania do wypełnienia w tytule wygenerowanego raportu](./media/er-quick-start1-add-report-title-label.png)

<span data-ttu-id="bcc0a-714">Tę technikę można stosować do tworzenia wszystkich etykiet zależnych od języka bieżącego szablonu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-714">You can use this technique to make all other labels of the current template language-dependent.</span></span> <span data-ttu-id="bcc0a-715">Aby uzyskać informacje dotyczące sposobu tłumaczenia dodanych etykiet jednej konfiguracji ER na wszystkie obsługiwane języki, zapoznaj się z tematami [Projektowanie raportów wielojęzycznych](er-design-multilingual-reports.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-715">For information about how the added labels of a single ER configuration can be translated into all supported languages, see [Design multilingual reports](er-design-multilingual-reports.md).</span></span>

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a><span data-ttu-id="bcc0a-716">Przejrzyj źródło danych modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-716">Review model data source</span></span>

1. <span data-ttu-id="bcc0a-717">Na stronie **Projektant formatów** na karcie **Mapowanie** wybierz <a name="ModelDSName"></a>**model** źródła danych, który reprezentuje podstawowy model danych tego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-717">On the **Format designer** page, on the **Mapping** tab, select the <a name="ModelDSName"></a>**model** data source that represents the base data model of this ER format.</span></span>
2. <span data-ttu-id="bcc0a-718">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-718">Select **Edit**.</span></span>
3. <span data-ttu-id="bcc0a-719">Przejrzyj informacje w oknie dialogowym **Właściwości źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-719">Review the information in the **Data source properties** dialog box.</span></span> <span data-ttu-id="bcc0a-720">To źródło danych reprezentuje wersję 1 składnika modelu danych **Kwestionariuszy**, który znajduje się w konfiguracji ER dla **Modelu kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-720">This data source represents version 1 of the **Questionnaires** data model component that resides in the **Questionnaires model** ER configuration.</span></span>

![Właściwości źródła danych modelu w projektancie operacji ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a><span data-ttu-id="bcc0a-722">Powiązanie elementów formatu na pola źródła danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-722">Bind format elements to data source fields</span></span>

<span data-ttu-id="bcc0a-723">Aby określić sposób wypełniania szablonu w czasie wykonywania, należy powiązać każdy element formatu powiązany z odpowiednią nazwą programu Excel z pojedynczym polem źródła danych tego formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-723">To specify how a template is filled in at runtime, you must bind every format element that is associated with an appropriate Excel name to a single field of this format's data source.</span></span>

1. <span data-ttu-id="bcc0a-724">Na stronie **Projektant formatów** w drzewie formatu wybierz element formatu **Raport\\CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-724">On the **Format designer** page, in the format tree, select the **Report\\CompanyName** format element.</span></span>
2. <span data-ttu-id="bcc0a-725">Na karcie **Mapowanie** wybierz pole źródła danych **model.CompanyName** typu **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-725">On the **Mapping** tab, select the **model.CompanyName** data source field of the **String** type.</span></span>
3. <span data-ttu-id="bcc0a-726">Wybierz opcję **Powiąż**, aby wprowadzić nazwę firmy w szablonie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-726">Select **Bind** to enter a company name in a template.</span></span>
4. <span data-ttu-id="bcc0a-727">W drzewie formatu zaznacz element **Report\\Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-727">In the format tree, select the **Report\\Questionnaire** element.</span></span>
5. <span data-ttu-id="bcc0a-728">Na karcie **Mapowanie** wybierz pole źródła danych **model.Questionnaire** typu **Lista rekordów**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-728">On the **Mapping** tab, select the **model.Questionnaire** data source field of the **Record list** type.</span></span>
6. <span data-ttu-id="bcc0a-729">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-729">Select **Bind**.</span></span>
7. <span data-ttu-id="bcc0a-730">Wybierz opcję **Pokaż szczegóły**, aby wyświetlić więcej szczegółów dotyczących elementów formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-730">Select **Show details** to see more details for format elements.</span></span>

    <span data-ttu-id="bcc0a-731">Element formatu zakresu **Kwestionariusza** jest skonfigurowany jako replikowany pionowo.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-731">The **Questionnaire** range format element is configured as vertically replicated.</span></span> <span data-ttu-id="bcc0a-732">Jeśli jest powiązany ze źródłem danych typu **Lista rekordów**, odpowiedni zakres **Kwestionariusza** w szablonie programu Excel jest powtarzany dla każdego rekordu powiązanego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-732">When it's bound to a data source of the **Record list** type, the appropriate **Questionnaire** range of the Excel template is repeated for every record of the bound data source.</span></span>
 
    ![Powiązanie elementu formatu zakresu kwestionariusza z odpowiednimi źródłami danych listy rekordów w projektancie operacji ER](./media/er-quick-start1-bindings1.png)

    <span data-ttu-id="bcc0a-734">Ponieważ zakres **Kwestionariusza** szablonu programu Excel jest zdefiniowany między wierszami od 5 do 14, te wiersze są powtarzane dla każdego raportowanego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-734">Because the **Questionnaire** range of the Excel template is defined between rows 5 through 14, these rows are repeated for every reported questionnaire.</span></span>

    ![Wiersze w szablonie programu Excel, które zostaną powtórzone w wygenerowanym raporcie dla każdego rekordu źródeł danych Listy rekordów](./media/er-quick-start1-template-questionnaire-range.png)

8. <span data-ttu-id="bcc0a-736">Skonfiguruj podobne powiązania dla pozostałych elementów formatu, tak jak to opisano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-736">Configure similar bindings for the remaining format elements, as described in the following table.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcc0a-737">W tej tabeli informacje w kolumnie „ścieżka źródła danych” zakładają, że funkcja ER [ścieżka względna](relative-path-data-bindings-er-models-format.md) jest włączona.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-737">In this table, the information in the "Data source path" column assumes that the [relative path](relative-path-data-bindings-er-models-format.md) ER feature is turned on.</span></span>

    | <span data-ttu-id="bcc0a-738">Ścieżka elementu formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-738">Format element path</span></span>                                      | <span data-ttu-id="bcc0a-739">Ścieżka źródła danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-739">Data source path</span></span> |
    |----------------------------------------------------------|------------------|
    | <span data-ttu-id="bcc0a-740">Excel\\ReportTitle</span><span class="sxs-lookup"><span data-stu-id="bcc0a-740">Excel\\ReportTitle</span></span>                                       | <span data-ttu-id="bcc0a-741">**\@"GER\_LABEL:ReportTitle"**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-741">**\@"GER\_LABEL:ReportTitle"**</span></span> |
    | <span data-ttu-id="bcc0a-742">Excel\\CompanyName</span><span class="sxs-lookup"><span data-stu-id="bcc0a-742">Excel\\CompanyName</span></span>                                       | <span data-ttu-id="bcc0a-743">**model.CompanyName**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-743">**model.CompanyName**</span></span> |
    | <span data-ttu-id="bcc0a-744">Excel\\Kwestionariusz</span><span class="sxs-lookup"><span data-stu-id="bcc0a-744">Excel\\Questionnaire</span></span>                                     | <span data-ttu-id="bcc0a-745">**model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-745">**model.Questionnaire**</span></span> |
    | <span data-ttu-id="bcc0a-746">Excel\\Kwestionariusz\\Aktywny</span><span class="sxs-lookup"><span data-stu-id="bcc0a-746">Excel\\Questionnaire\\Active</span></span>                             | <span data-ttu-id="bcc0a-747">**\@.Active**, gdzie **\@** to **model.Questionnaire**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-747">**\@.Active**, where **\@** is **model.Questionnaire**</span></span> |
    | <span data-ttu-id="bcc0a-748">Excel\\Kwestionariusz\\Kod</span><span class="sxs-lookup"><span data-stu-id="bcc0a-748">Excel\\Questionnaire\\Code</span></span>                               | <span data-ttu-id="bcc0a-749">**\@.Code**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-749">**\@.Code**</span></span> |
    | <span data-ttu-id="bcc0a-750">Excel\\Kwestionariusz\\Opis</span><span class="sxs-lookup"><span data-stu-id="bcc0a-750">Excel\\Questionnaire\\Description</span></span>                        | <span data-ttu-id="bcc0a-751">**\@.Opis**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-751">**\@.Description**</span></span> |
    | <span data-ttu-id="bcc0a-752">Excel\\Kwestionariusz\\TypKwestionariusza</span><span class="sxs-lookup"><span data-stu-id="bcc0a-752">Excel\\Questionnaire\\QuestionnaireType</span></span>                  | <span data-ttu-id="bcc0a-753">**\@.QuestionnaireType**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-753">**\@.QuestionnaireType**</span></span> |
    | <span data-ttu-id="bcc0a-754">Excel\\Kwestionariusz\\QuestionOrder</span><span class="sxs-lookup"><span data-stu-id="bcc0a-754">Excel\\Questionnaire\\QuestionOrder</span></span>                      | <span data-ttu-id="bcc0a-755">**\@.QuestionOrder**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-755">**\@.QuestionOrder**</span></span> |
    | <span data-ttu-id="bcc0a-756">Excel\\Kwestionariusz\\ResultsGroup\\Kod\_</span><span class="sxs-lookup"><span data-stu-id="bcc0a-756">Excel\\Questionnaire\\ResultsGroup\\Code\_</span></span>               | <span data-ttu-id="bcc0a-757">**\@.ResultsGroup.Code**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-757">**\@.ResultsGroup.Code**</span></span> |
    | <span data-ttu-id="bcc0a-758">Excel\\Kwestionariusz\\ResultsGroup\\Opis\_</span><span class="sxs-lookup"><span data-stu-id="bcc0a-758">Excel\\Questionnaire\\ResultsGroup\\Description\_</span></span>        | <span data-ttu-id="bcc0a-759">**\@.ResultsGroup.Description**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-759">**\@.ResultsGroup.Description**</span></span> |
    | <span data-ttu-id="bcc0a-760">Excel\\Kwestionariusz\\ResultsGroup\\MaxNumberOfPoints</span><span class="sxs-lookup"><span data-stu-id="bcc0a-760">Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints</span></span>    | <span data-ttu-id="bcc0a-761">**\@.ResultsGroup.MaxNumberOfPoint**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-761">**\@.ResultsGroup.MaxNumberOfPoint**</span></span> |
    | <span data-ttu-id="bcc0a-762">Excel\\Kwestionariusz\\Pytanie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-762">Excel\\Questionnaire\\Question</span></span>                           | <span data-ttu-id="bcc0a-763">**\@.Pytanie**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-763">**\@.Question**</span></span> |
    | <span data-ttu-id="bcc0a-764">Excel\\Kwestionariusz\\Pytanie\\CollectionSequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-764">Excel\\Questionnaire\\Question\\CollectionSequenceNumber</span></span> | <span data-ttu-id="bcc0a-765">**\@.CollectionSequenceNumber**, gdzie **\@** to **model.Questionnaire.Question**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-765">**\@.CollectionSequenceNumber**, where **\@** is **model.Questionnaire.Question**</span></span> |
    | <span data-ttu-id="bcc0a-766">Excel\\Kwestionariusz\\Pytanie\\Identyfikator</span><span class="sxs-lookup"><span data-stu-id="bcc0a-766">Excel\\Questionnaire\\Question\\Id</span></span>                       | <span data-ttu-id="bcc0a-767">**\@.Id**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-767">**\@.Id**</span></span> |
    | <span data-ttu-id="bcc0a-768">Excel\\Kwestionariusz\\Pytanie\\MustBeCompleted</span><span class="sxs-lookup"><span data-stu-id="bcc0a-768">Excel\\Questionnaire\\Question\\MustBeCompleted</span></span>          | <span data-ttu-id="bcc0a-769">**\@.MustBeCompleted**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-769">**\@.MustBeCompleted**</span></span> |
    | <span data-ttu-id="bcc0a-770">Excel\\Kwestionariusz\\Pytanie\\PrimaryQuestion</span><span class="sxs-lookup"><span data-stu-id="bcc0a-770">Excel\\Questionnaire\\Question\\PrimaryQuestion</span></span>          | <span data-ttu-id="bcc0a-771">**\@.PrimaryQuestion**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-771">**\@.PrimaryQuestion**</span></span> |
    | <span data-ttu-id="bcc0a-772">Excel\\Kwestionariusz\\Pytanie\\SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="bcc0a-772">Excel\\Questionnaire\\Question\\SequenceNumber</span></span>           | <span data-ttu-id="bcc0a-773">**\@.SequenceNumber**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-773">**\@.SequenceNumber**</span></span> |
    | <span data-ttu-id="bcc0a-774">Excel\\Kwestionariusz\\Pytanie\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-774">Excel\\Questionnaire\\Question\\Text</span></span>                     | <span data-ttu-id="bcc0a-775">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-775">**\@.Text**</span></span> |
    | <span data-ttu-id="bcc0a-776">Excel\\Kwestionariusz\\Pytanie\\Odpowiedź</span><span class="sxs-lookup"><span data-stu-id="bcc0a-776">Excel\\Questionnaire\\Question\\Answer</span></span>                   | <span data-ttu-id="bcc0a-777">**\@.Answer**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-777">**\@.Answer**</span></span> |
    | <span data-ttu-id="bcc0a-778">Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\CorrectAnswer</span><span class="sxs-lookup"><span data-stu-id="bcc0a-778">Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer</span></span>    | <span data-ttu-id="bcc0a-779">**\@.CorrectAnswer**, gdzie **\@** to **model.Questionnaire.Answer**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-779">**\@.CorrectAnswer**, where **\@** is **model.Questionnaire.Answer**</span></span> |
    | <span data-ttu-id="bcc0a-780">Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\Punkty</span><span class="sxs-lookup"><span data-stu-id="bcc0a-780">Excel\\Questionnaire\\Question\\Answer\\Points</span></span>           | <span data-ttu-id="bcc0a-781">**\@.Points**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-781">**\@.Points**</span></span> |
    | <span data-ttu-id="bcc0a-782">Excel\\Kwestionariusz\\Pytanie\\Odpowiedź\\Tekst</span><span class="sxs-lookup"><span data-stu-id="bcc0a-782">Excel\\Questionnaire\\Question\\Answer\\Text</span></span>             | <span data-ttu-id="bcc0a-783">**\@.Text**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-783">**\@.Text**</span></span> |

9. <span data-ttu-id="bcc0a-784">Po zakończeniu wybierz przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-784">When you've finished, select **Save**.</span></span>

<span data-ttu-id="bcc0a-785">Na poniższej ilustracji przedstawiono ostatni stan skonfigurowanych powiązaniań danych na stronie **Projektanta formatów**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-785">The following illustration shows the final state of the configured data bindings on the **Format designer** page.</span></span>

![Skonfigurowane powiązania danych w projektancie operacji ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> <span data-ttu-id="bcc0a-787">Cała kolekcja określonych źródeł danych i powiązań reprezentuje składnik odwzorowania formatu skonfigurowanego formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-787">The whole collection of specified data sources and bindings represents a format mapping component of the configured format.</span></span> <span data-ttu-id="bcc0a-788">To mapowanie formatu jest wywoływane w przypadku uruchomienia skonfigurowanego formatu generowania raportu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-788">This format mapping is called when you run the configured format for report generation.</span></span>

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a><span data-ttu-id="bcc0a-789">Uruchamianie zaprojektowanego formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-789">Run a designed format from ER</span></span>

<span data-ttu-id="bcc0a-790">Możesz teraz uruchomić zaprojektowany format do celów testowych ze strony **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-790">You can now run a designed format for testing purposes from the **Configurations** page.</span></span>

1. <span data-ttu-id="bcc0a-791">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-791">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-792">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-792">On the **Configuration** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="bcc0a-793">Wybierz opcję **Projektant** dla wersji formatu, która ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-793">Select **Designer** for the format version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="bcc0a-794">Na stronie **Projektant formatów** wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-794">On the **Format designer** page, select **Run**.</span></span>
5. <span data-ttu-id="bcc0a-795">W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-795">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
6. <span data-ttu-id="bcc0a-796">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-796">Select **OK** to confirm the filtering option.</span></span>
7. <span data-ttu-id="bcc0a-797">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-797">Select **OK** to run the report.</span></span>
8. <span data-ttu-id="bcc0a-798">Przejrzyj wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-798">Review the generated report.</span></span>

<span data-ttu-id="bcc0a-799">[Domyślnie](electronic-reporting-destinations.md#default-behavior) wygenerowany raport jest dostarczany jako plik programu Excel, który można pobrać.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-799">By [default](electronic-reporting-destinations.md#default-behavior), a generated report is delivered as an Excel file that you can download.</span></span> <span data-ttu-id="bcc0a-800">Na poniższych ilustracjach przedstawiono dwie strony wygenerowanego raportu w formacie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-800">The following illustrations show two pages of the generated report in Excel format.</span></span>

![Przykład wygenerowanego raportu w formacie programu Excel, Strona 1](./media/er-quick-start1-report1a.png)

![Przykład wygenerowanego raportu w formacie programu Excel, Strona 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a><span data-ttu-id="bcc0a-803">Dostrajanie zaprojektowanego formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-803">Tune a designed format</span></span>

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a><span data-ttu-id="bcc0a-804">Modyfikowanie formatu w celu zmiany nazwy wygenerowanego dokumentu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-804">Modify a format to change the name of a generated document</span></span>

<span data-ttu-id="bcc0a-805">Domyślnie wygenerowany dokument ma nazwę, używając aliasu bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-805">By default, a generated document is named by using the alias of the current user.</span></span> <span data-ttu-id="bcc0a-806">Modyfikując format, można zmienić to zachowanie, tak aby wygenerowany dokument mógł zostać nazwany na podstawie logiki niestandardowej użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-806">By modifying the format, you can change this behavior so that a generated document is named based on your custom logic.</span></span> <span data-ttu-id="bcc0a-807">Na przykład nazwa wygenerowanego dokumentu może być oparta na dacie i godzinie bieżącej sesji oraz na tytule raportu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-807">For example, the name of a generated document can be based on the current session date and time, and on the report's title.</span></span>

1. <span data-ttu-id="bcc0a-808">Na stronie **Projektant formatów** wybierz element główny **Raport**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-808">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="bcc0a-809">Na karcie **Mapowanie** wybierz opcję **Edytuj nazwę pliku**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-809">On the **Mapping** tab, select **Edit file name**.</span></span>
3. <span data-ttu-id="bcc0a-810">W polu **Formuła** wprowadź **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-810">In the **Formula** field, enter **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.</span></span>
4. <span data-ttu-id="bcc0a-811">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-811">Select **Save**, and close the formula editor.</span></span>
5. <span data-ttu-id="bcc0a-812">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-812">Select **Save**.</span></span>

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a><span data-ttu-id="bcc0a-813">Umożliwia zmodyfikowanie formatu w celu zmiany kolejności pytań</span><span class="sxs-lookup"><span data-stu-id="bcc0a-813">Modify a format to change the order of questions</span></span>

<span data-ttu-id="bcc0a-814">Pytania nie są poprawnie uporządkowane w wygenerowanym raporcie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-814">The questions aren't correctly ordered in a generated report.</span></span> <span data-ttu-id="bcc0a-815">Kolejność można zmienić, modyfikując format.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-815">You can change the order by modifying the format.</span></span>

1. <span data-ttu-id="bcc0a-816">Na stronie **Projektant formatów** wybierz element główny **Raport**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-816">On the **Format designer** page, select the **Report** root item.</span></span>
2. <span data-ttu-id="bcc0a-817">Na karcie **Mapowanie** w drzewie formatu rozwiń **Raport\\Kwestionariusz\\Pytanie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-817">On the **Mapping** tab, in the format tree, expand **Report\\Questionnaire\\Question**.</span></span>

    ![Element formatu pytań dla zakresu typu Projektant operacji ER](./media/er-quick-start1-bindings3.png)

3. <span data-ttu-id="bcc0a-819">Na karcie **Mapowanie** wybierz opcję **model.Questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-819">On the **Mapping** tab, select **model.Questionnaire**.</span></span>
4. <span data-ttu-id="bcc0a-820">Wybierz opcję **Dodaj** \> **Funkcje\\Pole obliczeniowe**, a następnie w polu **Nazwa** wprowadź **OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-820">Select **Add** \> **Functions\\Calculated field**, and then, in the **Name** field, enter **OrderedQuestions**.</span></span>
5. <span data-ttu-id="bcc0a-821">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-821">Select **Edit formula**.</span></span>
6. <span data-ttu-id="bcc0a-822">W edytorze formuł w polu **Formuła** wprowadź **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** w celu uporządkowania listy pytań bieżącego kwestionariusza według numeru porządkowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-822">In the formula editor, in the **Formula** field, enter **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** to order the list of questions of the current questionnaire by the sequence order number.</span></span>
7. <span data-ttu-id="bcc0a-823">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-823">Select **Save**, and close the formula editor.</span></span>
8. <span data-ttu-id="bcc0a-824">Wybierz przycisk **OK**, aby ukończyć wprowadzanie nowego pola obliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-824">Select **OK** to complete the entry of a new calculated field.</span></span>
9. <span data-ttu-id="bcc0a-825">Na karcie **Mapowanie** wybierz opcję **model.Questionnaire.OrderedQuestions**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-825">On the **Mapping** tab, select **model.Questionnaire.OrderedQuestions**.</span></span>
10. <span data-ttu-id="bcc0a-826">W drzewie formatu wybierz **Excel\\Kwestionariusz\\Pytanie**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-826">In the format tree, select **Excel\\Questionnaire\\Question**.</span></span>
11. <span data-ttu-id="bcc0a-827">Wybierz opcję **Powiąż**, a następnie potwierdź, że bieżąca ścieżka **model.Questionnaire.Questions** jest zastępowana nową ścieżką **model.Questionnaire.OrderedQuestions** we wszystkich powiązaniach elementów zagnieżdżonych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-827">Select **Bind**, and then confirm that the current **model.Questionnaire.Questions** path is replaced by the new **model.Questionnaire.OrderedQuestions** path in all bindings of nested elements.</span></span>
12. <span data-ttu-id="bcc0a-828">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-828">Select **Save**.</span></span>

![Powiązanie elementu formatu pytania ze skonfigurowanym źródłem danych OrderedQuestions w projektancie operacji ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a><span data-ttu-id="bcc0a-830">Uruchamianie zmodyfikowanego formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-830">Run a modified format from ER</span></span>

<span data-ttu-id="bcc0a-831">Możesz teraz uruchomić zmodyfikowany format do celów testowych ze środowiska ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-831">You can now run a modified format for testing purposes from the ER framework.</span></span>

1. <span data-ttu-id="bcc0a-832">Na stronie **Projektant formatów** wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-832">On the **Format designer** page, select **Run**.</span></span>
2. <span data-ttu-id="bcc0a-833">W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-833">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
3. <span data-ttu-id="bcc0a-834">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-834">Select **OK** to confirm the filtering option.</span></span>
4. <span data-ttu-id="bcc0a-835">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-835">Select **OK** to run the report.</span></span>
5. <span data-ttu-id="bcc0a-836">Przejrzyj wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-836">Review the generated report.</span></span>

<span data-ttu-id="bcc0a-837">Poniższa ilustracja przedstawia wygenerowany raport w formacie Excel, w którym pytania są poprawnie uporządkowane.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-837">The following illustration shows a generated report in Excel format where the questions are correctly ordered.</span></span>

![Wygenerowany raport w formacie Excel z poprawnie uporządkowanymi pytaniami](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a><span data-ttu-id="bcc0a-839">Zakończ projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-839">Complete the format design</span></span>

1. <span data-ttu-id="bcc0a-840">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-840">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-841">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-841">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="bcc0a-842">Na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-842">On the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
4. <span data-ttu-id="bcc0a-843">Wybierz **Zmień status** \> **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-843">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="bcc0a-844">Stan wersja 1.1 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-844">The status of version 1.1 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="bcc0a-845">Wersja 1.1 nie może być już zmieniana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-845">Version 1.1 can no longer be changed.</span></span> <span data-ttu-id="bcc0a-846">Ta wersja zawiera skonfigurowany format i może być używana do drukowania raportu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-846">This version contains the configured format and can be used to print your custom report.</span></span> <span data-ttu-id="bcc0a-847">Wersja 1.2 tej konfiguracji jest utworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-847">Version 1.2 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="bcc0a-848">Tę wersję można edytować, aby skorygować format raportu **Kwestionariusz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-848">You can edit this version to adjust the format of your **Questionnaire** report.</span></span>

![Wersje edytowalnej konfiguracji ER na stronie konfiguracje](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> <span data-ttu-id="bcc0a-850">Skonfigurowany format to projekt raportu **Kwestionariusz** i nie zawiera żadnych relacji z artefaktami specyficznymi dla Finance.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-850">The configured format is your design of the **Questionnaire** report and contains no relations to the Finance-specific artefacts.</span></span>

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a><span data-ttu-id="bcc0a-851">Opracowywanie Artefacts aplikacji w celu wywołania zaprojektowanego raportu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-851">Develop application artefacts to call the designed report</span></span>

<span data-ttu-id="bcc0a-852">Jako użytkownik w roli administratora systemu musisz opracować nową logikę, tak aby skonfigurowany format ER mógł być wywoływany z interfejsu użytkownika aplikacji (UI) w celu wygenerowania raportu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-852">As a user in the System Administrator role, you must develop new logic so that the configured ER format can be called from the application user interface (UI) to generate your custom report.</span></span> <span data-ttu-id="bcc0a-853">Obecnie moduł ER nie oferuje żadnych możliwości konfigurowania tego typu logiki.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-853">Currently, ER doesn't offer any capability for configuring this type of logic.</span></span> <span data-ttu-id="bcc0a-854">W związku z tym wymagane są pewne prace technologiczne.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-854">Therefore, some engineering work is required.</span></span> 

<span data-ttu-id="bcc0a-855">Aby opracować nową logikę, należy wdrożyć topologię obsługującą ciągłe budowanie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-855">To develop the new logic, you must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="bcc0a-856">Więcej informacji znajdziesz w [Wdrażanie topologii obsługujących ciągłą budowę i automatyzację testów](../perf-test/continuous-build-test-automation.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-856">For more information, see [Deploy topologies that support continuous build and test automation](../perf-test/continuous-build-test-automation.md).</span></span> <span data-ttu-id="bcc0a-857">Ponadto musisz także mieć dostęp do środowiska programowania dla tej topologii.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-857">You must also have access to the development environment for this topology.</span></span> <span data-ttu-id="bcc0a-858">Aby uzyskać więcej informacji na temat dostępnego interfejsu API ER, zapoznaj się z tematem [Interfejs API struktury modułu Raportowanie elektroniczne](er-apis-app73.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-858">For more information about the available ER API, see [ER framework API](er-apis-app73.md).</span></span>

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a><span data-ttu-id="bcc0a-859">Zmień kod źródłowy</span><span class="sxs-lookup"><span data-stu-id="bcc0a-859">Modify source code</span></span>

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a><span data-ttu-id="bcc0a-860">Dodawanie klasy kontraktu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-860">Add a data contract class</span></span>

<span data-ttu-id="bcc0a-861">Dodaj nową klasę **QuestionnairesErReportContract** do projektu programu Microsoft Visual Studio i wpisz kod określający kontrakt danych, który ma być używany do uruchamiania skonfigurowanego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-861">Add the new **QuestionnairesErReportContract** class to your Microsoft Visual Studio project, and write code that specifies the data contract that should be used to run the configured ER format.</span></span>

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a><span data-ttu-id="bcc0a-862">Dodaj klasę konstruktora UI</span><span class="sxs-lookup"><span data-stu-id="bcc0a-862">Add a UI builder class</span></span>

<span data-ttu-id="bcc0a-863">Dodaj nową klasę **QuestionnairesErReportUIBuilder** do projektu Visual Studio i wpisz kod, aby wygenerować okno dialogowe środowiska uruchomieniowego, które będzie używane do wyszukiwania identyfikatora mapowania formatu ER, który musi zostać uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-863">Add the new **QuestionnairesErReportUIBuilder** class to your Visual Studio project, and write code to generate a runtime dialog box that will be used to look up the format mapping ID of the ER format that must be run.</span></span> <span data-ttu-id="bcc0a-864">Podany kod wyszukuje tylko formaty ER, które zawierają źródło danych typu **modelu danych**, które odwołują się do modelu danych **[Kwestionariuszy](#DataModeName)** przy użyciu definicji **[głównej](#RootDefinitionName)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-864">The provided code looks up only ER formats that contain a data source of the **Data model** type that refers to the **[Questionnaires](#DataModeName)** data model by using the **[Root](#RootDefinitionName)** definition.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc0a-865">Alternatywnie możesz użyć punktów integracji ER do filtrowania formatów ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-865">Alternatively, you can use ER integration points to filter ER formats.</span></span> <span data-ttu-id="bcc0a-866">Aby uzyskać więcej informacji, zobacz [API, aby wyświetlić wyszukiwanie mapowania formatu](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-866">For more information, see [API to show a format mapping lookup](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).</span></span>

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a><span data-ttu-id="bcc0a-867">Dodawanie klasy dostawcy danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-867">Add a data provider class</span></span>

<span data-ttu-id="bcc0a-868">Dodaj nową klasę **QuestionnairesErReportDP** do projektu programu Microsoft Visual Studio i napisz kod wprowadzający dostawcę danych, który powinien być używany do uruchamiania skonfigurowanego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-868">Add the new **QuestionnairesErReportDP** class to your Visual Studio project, and write code that introduces the data provider that should used to run the configured ER format.</span></span> <span data-ttu-id="bcc0a-869">Podany kod zawiera tylko umowę dotyczącą danych dla tego dostawcy danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-869">The provided code includes only the data contract for this data provider.</span></span>

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a><span data-ttu-id="bcc0a-870">Dodaj plik etykiet</span><span class="sxs-lookup"><span data-stu-id="bcc0a-870">Add a labels file</span></span>

<span data-ttu-id="bcc0a-871">Dodaj nowy plik etykiet **QuestionnairesErReportLabels\_en-US** do projektu Visual Studio, a następnie określ następujące etykiety dla nowych zasobów interfejsu użytkownika:</span><span class="sxs-lookup"><span data-stu-id="bcc0a-871">Add the new **QuestionnairesErReportLabels\_en-US** labels file to your Visual Studio project, and specify the following labels for new UI resources:</span></span>

- <span data-ttu-id="bcc0a-872">Etykieta **\@QuestionnairesReport** dla nowego elementu menu, zawierająca następujący tekst w amerykańskiej odmianie języka angielskiego (en-US): **Raport z kwestionariuszy (zasilany przez ER)**</span><span class="sxs-lookup"><span data-stu-id="bcc0a-872">The **\@QuestionnairesReport** label for a new menu item that contains the following text in US English (en-US): **Questionnaires report (powered by ER)**</span></span>
- <span data-ttu-id="bcc0a-873">Etykieta **\@QuestionnairesReportBatchJobDescription** dla stanowiska wsadowego, jeśli wybrany format ER jest zaplanowany do wykonania jako zadanie wsadowe</span><span class="sxs-lookup"><span data-stu-id="bcc0a-873">The **\@QuestionnairesReportBatchJobDescription** label for a batch job title if a selected ER format is scheduled for execution as a batch job</span></span>

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a><span data-ttu-id="bcc0a-874">Dodawanie klasy usługi raportowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-874">Add a report service class</span></span>

<span data-ttu-id="bcc0a-875">Dodaj nową klasę **QuestionnairesErReportService** do projektu Visual Studio i wpisz kod wywołujący format ER, identyfikując go za pomocą identyfikatora mapowania formatu i dostarcza kontrakt danych jako parametr.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-875">Add the new **QuestionnairesErReportService** class to your Visual Studio project, and write code that calls an ER format, identifies it by a format mapping ID, and provides a data contract as a parameter.</span></span>

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

<span data-ttu-id="bcc0a-876">Jeśli musisz użyć formatu ER, który uruchamia dane aplikacji, musisz skonfigurować źródło danych typu **Model danych** w mapowaniu formatu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-876">When you must use an ER format that runs application data, you must configure a data source of the **Data model** type in the format mapping.</span></span> <span data-ttu-id="bcc0a-877">To źródło danych odwołuje się do określonej części określonego modelu danych za pomocą jednej definicji głównej.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-877">This data source refers to a specific part of the specified data model by using a single root definition.</span></span> <span data-ttu-id="bcc0a-878">Po uruchomieniu formatu ER, wywołuje to źródło danych w celu uzyskania dostępu do odpowiedniego mapowania modelu ER skonfigurowanego dla danego modelu i definicji katalogu głównego.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-878">When the ER format is run, it calls this data source to access the appropriate ER model mapping that is configured for a given model and root definition.</span></span>

<span data-ttu-id="bcc0a-879">Wszystkie informacje, które można przygotować w kodzie źródłowym i przechowywać w ramach kontraktu danych, można przekazać do działającego formatu ER przy użyciu mapowania modelu ER tego typu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-879">All the information that you might prepare in the source code and store as part of the data contract can be passed to the running ER format by using an ER model mapping of this type.</span></span> <span data-ttu-id="bcc0a-880">W mapowaniu modelu ER należy skonfigurować źródło danych typu **Obiektu**, który odwołuje się do klasy **[QuestionnairesErReportContract](#DataContractClass)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-880">In the ER model mapping, you must configure a data source of the **Object** type that refers to the **[QuestionnairesErReportContract](#DataContractClass)** class.</span></span> <span data-ttu-id="bcc0a-881">Informacje, które można przygotować w kodzie źródłowym i dane w ramach kontraktu, można do działającego formatu ER przy użyciu mapowania modelu ER tego typu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-881">To identify a model mapping, you must specify a data source that calls this model mapping.</span></span> <span data-ttu-id="bcc0a-882">W podanym kodzie to źródło danych określone przez stałą **ERModelDataSourceName**, która ma wartość **[modelu](#ModelDSName)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-882">In the provided code, this data source specified by the **ERModelDataSourceName** constant that has the **[model](#ModelDSName)** value.</span></span> <span data-ttu-id="bcc0a-883">Aby określić, które źródło danych jest używane do ujawnienia kontraktu danych w mapowaniu modeli, należy określić nazwę źródła danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-883">To identify which data source is used to expose the data contract in the model mapping, you must specify a data source name.</span></span> <span data-ttu-id="bcc0a-884">W podanym kodzie ta nazwa jest określona przez stałą **ParametersDataSourceName**, która ma wartość <a name="DataContractDSName"></a>**RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-884">In the provided code, this name is specified by the **ParametersDataSourceName** constant that has <a name="DataContractDSName"></a>**RunTimeParameters** value.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc0a-885">W nowym środowisku może być konieczne odświeżenie metadanych ER, aby ten typ klasy był dostępny w projektancie mapowania modelu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-885">In a new environment, you might have to refresh the ER metadata so that this type of class is available in the ER model mapping designer.</span></span> <span data-ttu-id="bcc0a-886">Aby uzyskać więcej informacji, zobacz [Konfigurowanie struktury ER](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="bcc0a-886">For more information, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).</span></span>

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a><span data-ttu-id="bcc0a-887">Dodawanie klasy kontrolera raportowania</span><span class="sxs-lookup"><span data-stu-id="bcc0a-887">Add a report controller class</span></span>

<span data-ttu-id="bcc0a-888">Dodaj nową klasę **QuestionnairesErReportController** do projektu Visual Studio i wpisz kod uruchamiający format ER w trybie synchronicznym lub wsadowym, w zależności od preferowanego sposobu w oknie dialogowym, które jest oparte na logice dostarczonej klasy **QuestionnairesErReportUIBuilder**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-888">Add the new **QuestionnairesErReportController** class to your Visual Studio project, and write code that runs an ER format in either synchronous mode or batch mode, as you prefer, in the dialog box that is built based on the logic of the provided **QuestionnairesErReportUIBuilder** class.</span></span>

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a><span data-ttu-id="bcc0a-889">Dodaj element menu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-889">Add a menu item</span></span>

<span data-ttu-id="bcc0a-890">Dodaj nowy element menu **QuestionnairesErReport** do projektu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-890">Add the new **QuestionnairesErReport** menu item to your Visual Studio project.</span></span> <span data-ttu-id="bcc0a-891">We właściwości **Obiektu** ten element menu odwołuje się do klasy **QuestionnairesErReportController** i jest używany do określania uprawnień użytkownika do wybierania i uruchamiania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-891">In the **Object** property, this menu item refers to the **QuestionnairesErReportController** class, and it's used to specify a user permission to select and run an ER format.</span></span> <span data-ttu-id="bcc0a-892">We właściwości **Etykieta** ten element menu odwołuje się do etykiety **\@QuestionnairesReport** utworzonej wcześniej, dzięki czemu w interfejsie aplikacji jest wyświetlany poprawny tekst.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-892">In the **Label** property, this menu item refers to the **\@QuestionnairesReport** label that you created earlier, so that correct text is presented in the application UI.</span></span>

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a><span data-ttu-id="bcc0a-893">Dodawanie elementu menu do menu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-893">Add a menu item to a menu</span></span>

<span data-ttu-id="bcc0a-894">Dodaj istniejące menu **KM** do projektu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-894">Add the existing **KM** menu to your Visual Studio project.</span></span> <span data-ttu-id="bcc0a-895">Do tego menu należy dodać nowy element **QuestionnairesErReport** typu **Dane wyjściowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-895">You must add a new **QuestionnairesErReport** item of the **Output** type to this menu.</span></span> <span data-ttu-id="bcc0a-896">Ten element musi odwoływać się do elementu menu **QuestionnairesErReport** opisanego w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-896">This item must refer to the **QuestionnairesErReport** menu item that is described in the previous section.</span></span>

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a><span data-ttu-id="bcc0a-897">Budowanie projektu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bcc0a-897">Build a Visual Studio project</span></span>

<span data-ttu-id="bcc0a-898">Umożliwia utworzenie projektu w celu udostępnienia nowego elementu menu użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-898">Build your project to make a new menu item available to users.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a><span data-ttu-id="bcc0a-899">Umożliwia uruchomienie formatu z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-899">Run a format from the application</span></span>

1. <span data-ttu-id="bcc0a-900">Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-900">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>

    ![Wybranie elementu menu Raport z kwestionariuszy (zasilany przez ER) w module kwestionariusza w celu uruchomienia skonfigurowanego formatu ER](./media/er-quick-start1-application-menu-modified.png)

2. <span data-ttu-id="bcc0a-902">W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-902">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="bcc0a-903">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-903">Select **OK**.</span></span>
4. <span data-ttu-id="bcc0a-904">W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-904">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="bcc0a-905">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-905">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="bcc0a-906">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-906">Select **OK** to run the report.</span></span>

    ![Określenie kryteriów wyboru w oknie dialogowym Raport elektroniczny](./media/er-quick-start1-report-run-dialog-page.png)

7. <span data-ttu-id="bcc0a-908">Przejrzyj wygenerowany raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-908">Review the generated report.</span></span>

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a><span data-ttu-id="bcc0a-909">Dostrajanie zaprojektowanego rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-909">Tune a designed ER solution</span></span>

<span data-ttu-id="bcc0a-910">Skonfigurowane rozwiązanie ER można zmodyfikować tak, aby korzystało z utworzonej przez siebie klasy dostawcy danych w celu uzyskania dostępu do szczegółów działającego formatu ER i wprowadzało nazwę tego formatu ER w wygenerowanym raporcie.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-910">You can modify the configured ER solution so that it uses the data provider class that you developed to access details of the running ER format, and so that it enters the name of this ER format in a generated report.</span></span>

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a><span data-ttu-id="bcc0a-911">Modyfikowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-911">Modify a model mapping</span></span>

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a><span data-ttu-id="bcc0a-912">Dodaj źródła danych, aby uzyskać dostęp do obiektu kontraktu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-912">Add data sources to access a data contract object</span></span>

1. <span data-ttu-id="bcc0a-913">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-913">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-914">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Mapowanie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-914">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire mapping**.</span></span>
3. <span data-ttu-id="bcc0a-915">Wybierz opcję **Projektant**, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-915">Select **Designer** to open the **Model to datasource mapping** page.</span></span>
4. <span data-ttu-id="bcc0a-916">Wybierz opcję **Projektant**, aby otworzyć wybrane mapowanie w konstruktorze mapowania modeli.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-916">Select **Designer** to open the selected mapping in the model mapping designer.</span></span>
5. <span data-ttu-id="bcc0a-917">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Objekt**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-917">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Object**.</span></span>
6. <span data-ttu-id="bcc0a-918">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-918">In the **Data sources** pane, select **Add root**.</span></span>
7. <span data-ttu-id="bcc0a-919">W oknie dialogowym w polu **Nazwa** wprowadź **[RunTimeParameters](#DataContractDSName)**, zgodnie z definicją w kodzie źródłowym klasy **QuestionnairesErReportService**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-919">In the dialog box, in the **Name** field, enter **[RunTimeParameters](#DataContractDSName)**, as defined in the source code of the **QuestionnairesErReportService** class.</span></span>
8. <span data-ttu-id="bcc0a-920">W polu **Klasa** wprowadź **[QuestionnairesErReportContract](#DataContractClass)**, który został wcześniej zakodowany.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-920">In the **Class** field, enter **[QuestionnairesErReportContract](#DataContractClass)**, which was coded earlier.</span></span>
9. <span data-ttu-id="bcc0a-921">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-921">Select **OK**.</span></span>
10. <span data-ttu-id="bcc0a-922">Rozwiń **RunTimeParameters**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-922">Expand **RunTimeParameters**.</span></span>

<span data-ttu-id="bcc0a-923">Dodane źródło danych zawiera informacje o identyfikatorze rekordu działającego mapowania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-923">The added data source provides information about the record ID of the running ER format mapping.</span></span>

![Dodano źródło danych w konstruktorze mapowania modelu ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a><span data-ttu-id="bcc0a-925">Dodaj źródło danych, aby uzyskać dostęp do rekordów mapowania formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-925">Add a data source to access ER format mapping records</span></span>

<span data-ttu-id="bcc0a-926">Kontynuuj edycję wybranego mapowania modelu, dodając źródło danych w celu uzyskania dostępu do rekordów mapowania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-926">Continue to edit the selected model mapping by adding a data source to access ER format mapping records.</span></span>

1. <span data-ttu-id="bcc0a-927">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz pozycję **Dynamics 365 for Operations\\Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-927">On the **Model mapping designer** page, in the **Data source types** pane, select **Dynamics 365 for Operations\\Table records**.</span></span>
2. <span data-ttu-id="bcc0a-928">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-928">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="bcc0a-929">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **ER1**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-929">In the dialog box, in the **Name** field, enter **ER1**.</span></span>
4. <span data-ttu-id="bcc0a-930">W polu **Tabela** wprowadź **ERFormatMappingTable**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-930">In the **Table** field, enter **ERFormatMappingTable**.</span></span>
5. <span data-ttu-id="bcc0a-931">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-931">Select **OK**.</span></span>

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a><span data-ttu-id="bcc0a-932">Dodaj źródło danych, aby uzyskać dostęp do rekordu mapowania formatu działającego formatu ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-932">Add a data source to access a format mapping record of a running ER format</span></span>

<span data-ttu-id="bcc0a-933">Kontynuuj edycję wybranego mapowania modelu, dodając źródło danych, aby uzyskać dostęp do rekordu mapowania formatu działającego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-933">Continue to edit the selected model mapping by adding a data source to access the format mapping record of the running ER format.</span></span>

1. <span data-ttu-id="bcc0a-934">Na stronie **Projektant mapowania modelu** w okienku **Typy źródła danych** wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-934">On the **Model mapping designer** page, in the **Data source types** pane, select **Functions\\Calculated field**.</span></span>
2. <span data-ttu-id="bcc0a-935">W okienku **Źródła danych** wybierz **Dodaj źródło**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-935">In the **Data sources** pane, select **Add root**.</span></span>
3. <span data-ttu-id="bcc0a-936">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **ER2**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-936">In the dialog box, in the **Name** field, enter **ER2**.</span></span>
4. <span data-ttu-id="bcc0a-937">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-937">Select **Edit formula**.</span></span>
5. <span data-ttu-id="bcc0a-938">W edytorze formuł w polu **Formuła** wprowadź **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-938">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.</span></span>
6. <span data-ttu-id="bcc0a-939">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-939">Select **Save**, and close the formula editor.</span></span>
7. <span data-ttu-id="bcc0a-940">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-940">Select **OK**.</span></span>

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a><span data-ttu-id="bcc0a-941">Umożliwia wprowadzenie nazwy uruchomionego formatu ER w modelu danych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-941">Enter the name of the running ER format in the data model</span></span>

<span data-ttu-id="bcc0a-942">Kontynuuj edytowanie wybranego mapowania modelu, tak aby nazwa uruchomionego formatu ER była wprowadzana w modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-942">Continue to edit the selected model mapping so that the name of the running ER format is entered in the data model.</span></span>

1. <span data-ttu-id="bcc0a-943">Na stronie **Projektant mapowania modelu** w okienku **Model danych** rozwiń **ExecutionContext**, a następnie wybierz **ExecutionContext\\FormatName**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-943">On the **Model mapping designer** page, in the **Data model** pane, expand **ExecutionContext**, and then select **ExecutionContext\\FormatName**.</span></span>
2. <span data-ttu-id="bcc0a-944">W okienku **Model danych** wybierz opcję **Edytuj**, aby skonfigurować powiązanie danych dla pola wybranego modelu danych.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-944">In the **Data model** pane, select **Edit** to configure a data binding for the selected data model's field.</span></span>
3. <span data-ttu-id="bcc0a-945">W edytorze formuł w polu **Formuła** wprowadź **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-945">In the formula editor, in the **Formula** field, enter **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.</span></span>
4. <span data-ttu-id="bcc0a-946">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-946">Select **Save**, and close the formula editor.</span></span>

<span data-ttu-id="bcc0a-947">Ponieważ użyto pola **FormatName**, skonfigurowane mapowanie modelu ujawnia teraz nazwę formatu ER, który wywołuje to mapowanie modelu podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-947">Because you used the **FormatName** field, the configured model mapping now exposes the name of an ER format that calls this model mapping during execution.</span></span>

![Powiązanie pola modelu danych z metodą dodanego źródła danych w projektancie mapowania modelu ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a><span data-ttu-id="bcc0a-949">Umożliwia zakończenie projektu mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-949">Complete the design of the model mapping</span></span>

1. <span data-ttu-id="bcc0a-950">Na stronie **Projektant mapowania modelu** wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-950">On the **Model mapping designer** page, select **Save**.</span></span>
2. <span data-ttu-id="bcc0a-951">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-951">Close the page.</span></span>
3. <span data-ttu-id="bcc0a-952">Zamknij stronę mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-952">Close the model mappings page.</span></span>
4. <span data-ttu-id="bcc0a-953">Na stronie **Konfiguracje** w drzewie konfiguracji upewnij się, że wybrana została konfiguracja **Mapowania kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-953">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire mapping** configuration is still selected.</span></span> <span data-ttu-id="bcc0a-954">Następnie na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-954">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
5. <span data-ttu-id="bcc0a-955">Wybierz **Zmień status** \> **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-955">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="bcc0a-956">Stan wersja 1.2 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-956">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="bcc0a-957">Wersja 1.2 nie może być już zmieniana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-957">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="bcc0a-958">Ta wersja zawiera skonfigurowany model mapowania i może być używana jako podstawa dla innych konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-958">This version contains the configured model mapping and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="bcc0a-959">Wersja 1.3 tej konfiguracji jest utworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-959">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="bcc0a-960">Tę wersję można edytować, aby skorygować model mapowania **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-960">You can edit this version to adjust the **Questionnaire** model mapping.</span></span>

### <a name="modify-a-format"></a><a name="ModifyFormat"></a><span data-ttu-id="bcc0a-961">Modyfikowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-961">Modify a format</span></span>

<span data-ttu-id="bcc0a-962">Skonfigurowany format ER można zmodyfikować, tak aby jego nazwa była wyświetlana w stopce raportu generowanego po uruchomieniu formatu ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-962">You can modify the configured ER format so that its name is shown in the footer of a report that is generated when the ER format is run.</span></span>

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a><span data-ttu-id="bcc0a-963">Dodaj nowy element formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-963">Add a new format element</span></span>

1. <span data-ttu-id="bcc0a-964">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-964">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-965">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-965">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="bcc0a-966">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-966">Select **Designer**.</span></span>
4. <span data-ttu-id="bcc0a-967">Na stronie **Projektant formatów** wybierz element główny **Raport**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-967">On the **Format designer** page, select the **Report** root item.</span></span>
5. <span data-ttu-id="bcc0a-968">Wybierz przycisk **Dodaj**, aby dodać nowy element formatu zagnieżdżonego dla wybranego elementu głównego **Raportu**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-968">Select **Add** to add a new nested format element for the selected **Report** root item.</span></span>
6. <span data-ttu-id="bcc0a-969">Wybierz **Excel\\Stopka**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-969">Select **Excel\\Footer**.</span></span>
7. <span data-ttu-id="bcc0a-970">W polu **Nazwa** wprowadź nazwę **Stopka**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-970">In the **Name** field, enter **Footer**.</span></span>
8. <span data-ttu-id="bcc0a-971">Wybierz opcję **Raport\Stopka**, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-971">Select **Report\Footer**, and then select **Add**.</span></span>
9. <span data-ttu-id="bcc0a-972">Wybierz **Tekst\\Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-972">Select **Text\\String**.</span></span>

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a><span data-ttu-id="bcc0a-973">Powiąż dodany element formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-973">Bind the added format element</span></span>

1. <span data-ttu-id="bcc0a-974">Na stronie **Projektant formatów** na karcie **Mapowanie** w drzewie formatu dla aktywnego elementu **Stopka\\Ciąg** wybierz **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-974">On the **Format designer** page, on the **Mapping** tab, in the format tree, for the active **Footer\\String** element, select **Edit formula**.</span></span>
2. <span data-ttu-id="bcc0a-975">W edytorze formuł, w polu **Formuła** wprowadź **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-975">In the formula editor, in the **Formula** field, enter **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**.</span></span>
3. <span data-ttu-id="bcc0a-976">Wybierz przycisk **Zapisz** i zamknij edytor formuł.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-976">Select **Save**, and close the formula editor.</span></span>
4. <span data-ttu-id="bcc0a-977">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-977">Select **Save**.</span></span>

<span data-ttu-id="bcc0a-978">Skonfigurowany format został zmodyfikowany, tak aby jego nazwa była wprowadzana do stopki wygenerowanego raportu przy użyciu elementu **Stopka\\Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-978">The configured format has now been modified so that its name will be entered in the footer of a generated report by using the **Footer\\String** element.</span></span>

![Dodanie elementu formatu Footer do skonfigurowanego formatu w projektancie operacji ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a><span data-ttu-id="bcc0a-980">Zakończ projektowanie formatu</span><span class="sxs-lookup"><span data-stu-id="bcc0a-980">Complete the format design</span></span>

1. <span data-ttu-id="bcc0a-981">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-981">Close the **Format designer** page.</span></span>
2. <span data-ttu-id="bcc0a-982">Na stronie **Konfiguracje** w drzewie konfiguracji upewnij się, że wybrana została konfiguracja **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-982">On the **Configurations** page, in the configuration tree, make sure that the **Questionnaire report** configuration is still selected.</span></span> <span data-ttu-id="bcc0a-983">Następnie na skróconej karcie **wersje** szybkie wybierz wersję konfiguracji o stanie **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-983">Then, on the **Versions** FastTab, select the configuration version that has a status of **Draft**.</span></span>
3. <span data-ttu-id="bcc0a-984">Wybierz **Zmień status** \> **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-984">Select **Change status** \> **Complete**.</span></span>

<span data-ttu-id="bcc0a-985">Stan wersja 1.2 tej konfiguracji zostanie zmieniony z wersji **Roboczej** na **Ukończoną**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-985">The status of version 1.2 of this configuration is changed from **Draft** to **Completed**.</span></span> <span data-ttu-id="bcc0a-986">Wersja 1.2 nie może być już zmieniana.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-986">Version 1.2 can no longer be changed.</span></span> <span data-ttu-id="bcc0a-987">Ta wersja zawiera skonfigurowany format i może być używana jako podstawa dla innych konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-987">This version contains the configured format and can be used as the basis for other ER configurations.</span></span> <span data-ttu-id="bcc0a-988">Wersja 1.3 tej konfiguracji jest utworzona i ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-988">Version 1.3 of this configuration is created and has a status of **Draft**.</span></span> <span data-ttu-id="bcc0a-989">Tę wersję można edytować, aby skorygować raport **Kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-989">You can edit this version to adjust the **Questionnaire** report.</span></span>

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a><span data-ttu-id="bcc0a-990">Umożliwia uruchomienie formatu z aplikacji</span><span class="sxs-lookup"><span data-stu-id="bcc0a-990">Run a format from the application</span></span>

1. <span data-ttu-id="bcc0a-991">Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-991">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="bcc0a-992">W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-992">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="bcc0a-993">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-993">Select **OK**.</span></span>
4. <span data-ttu-id="bcc0a-994">W oknie dialogowym **Parametry ER**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-994">In the **ER parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="bcc0a-995">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-995">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="bcc0a-996">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-996">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="bcc0a-997">Przejrzyj wygenerowany raport w formacie Excel.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-997">Review the generated report in Excel format.</span></span>

<span data-ttu-id="bcc0a-998">Należy zauważyć, że stopka wygenerowanego raportu zawiera nazwę formatu ER użytego do jego wygenerowania.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-998">Notice that the footer of the generated report contains the name of the ER format that was used to generate it.</span></span>

![Wygenerowany raport w formacie Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a><span data-ttu-id="bcc0a-1000">Uruchamianie formatu od ER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1000">Run a format from ER</span></span>

1. <span data-ttu-id="bcc0a-1001">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1001">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="bcc0a-1002">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model kwestionariusza**, a potem wybierz **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1002">On the **Configurations** page, in the configuration tree, expand **Questionnaire model**, and then select **Questionnaire report**.</span></span>
3. <span data-ttu-id="bcc0a-1003">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1003">On the Action Pane, select **Run**.</span></span>
4. <span data-ttu-id="bcc0a-1004">W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1004">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="bcc0a-1005">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1005">Select **OK** to confirm the filtering option.</span></span>
6. <span data-ttu-id="bcc0a-1006">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1006">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="bcc0a-1007">Przejrzyj wygenerowany raport w formacie Excel.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1007">Review the generated report in Excel format.</span></span>

<span data-ttu-id="bcc0a-1008">Zwróć uwagę, że stopka wygenerowanego raportu nie zawiera nazwy formatu ER, który został użyty do jego wygenerowania, ponieważ obiekt kontraktu danych nie został przekazany do uruchomionego mapowania modelu, gdy został wywołany przez format ER, który został uruchomiony z ER.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1008">Notice that the footer of the generated report doesn't contain the name of ER format that was used to generate it, because the data contract object wasn't passed to the running model mapping when it was called by the ER format that was run from ER.</span></span>

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a><span data-ttu-id="bcc0a-1009">Skonfiguruj miejsce docelowe formatu dla podglądu na ekranie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1009">Configure a format destination for on-screen preview</span></span>

1. <span data-ttu-id="bcc0a-1010">Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Aplikacja docelowa raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1010">Go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting destination**.</span></span>
2. <span data-ttu-id="bcc0a-1011">Na stronie **Aplikacja docelowa raportowania elektronicznego** dodaj rekord docelowy dla skonfigurowanego formatu ER **Raport kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1011">On the **Electronic reporting destination** page, add a destination record for the configured **Questionnaire report** ER format.</span></span>
3. <span data-ttu-id="bcc0a-1012">Na skróconej karcie **Lokalizacji docelowej pliku** skonfiguruj **Ekran**, czyli [miejsce docelowe](er-destination-type-screen.md), dla składnika formatu **Raportu**, który został [dodany](#AddFormatRootElement) jako element główny skonfigurowanego formatu ER **Raportu kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1012">On the **File destination** FastTab, set up the **Screen** [destination](er-destination-type-screen.md) for the **Report** format component that has been [added](#AddFormatRootElement) as the root element of the configured **Questionnaire report** ER format.</span></span>
4. <span data-ttu-id="bcc0a-1013">Na skróconej karcie **Ustawienia konwersji PDF** skonfiguruj lokalizację docelową w celu przekonwertowania raportu na [format PDF](electronic-reporting-destinations.md#OutputConversionToPDF), w którym jest używana **Pozioma** orientacja strony.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1013">On the **PDF conversion settings** FastTab, configure the destination to convert a report to [PDF format](electronic-reporting-destinations.md#OutputConversionToPDF) that uses the **Landscape** page orientation.</span></span>

![Konfigurowanie niestandardowego miejsca docelowego ekranu dla formatu ER na stronie docelowej raportowania elektronicznego](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a><span data-ttu-id="bcc0a-1015">Umożliwia uruchomienie formatu z aplikacji w celu wyświetlenia podglądu go jako dokumentu PDF</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1015">Run a format from the application to preview it as a PDF document</span></span>

1. <span data-ttu-id="bcc0a-1016">Przejdź do **Kwestionariusz** \> **Projektowanie** \> **Raport z kwestionariuszy (zasilany przez ER)**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1016">Go to **Questionnaire** \> **Design** \> **Questionnaires report (powered by ER)**.</span></span>
2. <span data-ttu-id="bcc0a-1017">W oknie dialogowym w polu **Mapowanie formatu** wybierz opcję **Raport kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1017">In the dialog box, in the **Format mapping** field, select **Questionnaires report**.</span></span>
3. <span data-ttu-id="bcc0a-1018">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1018">Select **OK**.</span></span>
4. <span data-ttu-id="bcc0a-1019">W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Rekordy do uwzględnienia**, skonfiguruj opcję filtrowania tak, aby uwzględniony był tylko kwestionariusz **SBCCrsExam**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1019">In the **Electronic report parameters** dialog box, on the **Records to include** FastTab, configure the filtering option so that only the **SBCCrsExam** questionnaire is included.</span></span>
5. <span data-ttu-id="bcc0a-1020">Wybierz przycisk **OK**, aby filtrować opcje.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1020">Select **OK** to confirm the filtering option.</span></span>

    <span data-ttu-id="bcc0a-1021">Na skróconej karcie **Miejsca docelowe** zwróć uwagę, że pole **Dane wyjściowe** jest ustawione na **Ekran**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1021">On the **Destinations** FastTab, notice that the **Output** field is set to **Screen**.</span></span> <span data-ttu-id="bcc0a-1022">Jeśli chcesz zmienić skonfigurowany cel, wybierz opcję **Zmień**.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1022">If you want to change the configured destination, select **Change**.</span></span>

    ![Okno dialogowe środowiska wykonawczego raportu ER, w którym można zmienić skonfigurowane miejsce docelowe](./media/er-quick-start1-run-settings.png)

6. <span data-ttu-id="bcc0a-1024">Wybierz przycisk **OK**, aby uruchomić raport.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1024">Select **OK** to run the report.</span></span>
7. <span data-ttu-id="bcc0a-1025">Przejrzyj wygenerowany raport w formacie PDF.</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1025">Review the generated report in PDF format.</span></span>

    ![Podgląd wygenerowanego raportu w formacie PDF na ekranie](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a><span data-ttu-id="bcc0a-1027">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1027">Additional resources</span></span>

- [<span data-ttu-id="bcc0a-1028">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1028">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="bcc0a-1029">Język formuł raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1029">Electronic reporting formula language</span></span>](er-formula-language.md)
- [<span data-ttu-id="bcc0a-1030">Projektowanie raportów wielojęzycznych</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1030">Design multilingual reports</span></span>](er-design-multilingual-reports.md)
- [<span data-ttu-id="bcc0a-1031">Interfejs API struktury modułu Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1031">ER framework API</span></span>](er-apis-app73.md)
- [<span data-ttu-id="bcc0a-1032">Funkcja CASE</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1032">CASE function</span></span>](er-functions-logical-case.md)
- [<span data-ttu-id="bcc0a-1033">Funkcja CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1033">CONCATENATE function</span></span>](er-functions-text-concatenate.md)
- [<span data-ttu-id="bcc0a-1034">Funkcja DATETIMEFORMAT</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1034">DATETIMEFORMAT function</span></span>](er-functions-datetime-datetimeformat.md)
- [<span data-ttu-id="bcc0a-1035">Funkcja FILTER</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1035">FILTER function</span></span>](er-functions-list-filter.md)
- [<span data-ttu-id="bcc0a-1036">Funkcja FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1036">FIRSTORNULL function</span></span>](er-functions-list-firstornull.md)
- [<span data-ttu-id="bcc0a-1037">Funkcja FORMAT</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1037">FORMAT function</span></span>](er-functions-text-format.md)
- [<span data-ttu-id="bcc0a-1038">Funkcja IF</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1038">IF function</span></span>](er-functions-logical-if.md)
- [<span data-ttu-id="bcc0a-1039">Funkcja ORDERBY</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1039">ORDERBY function</span></span>](er-functions-list-orderby.md)
- [<span data-ttu-id="bcc0a-1040">Funkcja SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="bcc0a-1040">SESSIONNOW function</span></span>](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]