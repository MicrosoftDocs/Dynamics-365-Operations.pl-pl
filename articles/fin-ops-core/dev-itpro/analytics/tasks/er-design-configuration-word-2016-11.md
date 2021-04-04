---
title: Ponowne używanie konfiguracji ER z szablonami programu Excel do generowania raportów w formacie programu Word
description: W tym temacie opisano sposób konfigurowania formatów raportów zaprojektowanych do generowania raportów jako skoroszytów programu Excel, tak aby raporty były generowane jako dokumenty programu Word.
author: NickSelin
manager: AnnBe
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 601896bad72b079759b1a07efba8717101e94362
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569318"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="0803a-103">Ponowne używanie konfiguracji ER z szablonami programu Excel do generowania raportów w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="0803a-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0803a-104">Aby generować raporty jako dokumenty programu Microsoft Word, można [skonfigurować](../er-design-configuration-word.md) nowy [format](../general-electronic-reporting.md#FormatComponentOutbound) [raportowania elektronicznego (ER)](../general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="0803a-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="0803a-105">Można również ponownie użyć formatu ER, który pierwotnie został zaprojektowany w celu generowania raportów jako skoroszytów programu Excel.</span><span class="sxs-lookup"><span data-stu-id="0803a-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="0803a-106">W takim przypadku należy zastąpić szablon programu Excel szablonem programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="0803a-107">Poniższe procedury pokazują, w jaki sposób użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może skonfigurować format raportowania elektronicznego, aby generować raporty jako pliki programu Word, ponownie korzystając z formatu ER przeznaczonego do generowania raportów jako plików programu Excel.</span><span class="sxs-lookup"><span data-stu-id="0803a-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="0803a-108">Te procedury można wykonać na danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="0803a-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0803a-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="0803a-109">Prerequisites</span></span>

<span data-ttu-id="0803a-110">W celu wykonania tych procedur należy najpierw kroki z przewodnika zadania [Projektowanie konfiguracji do generowania raportów w formacie OPENXML](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0803a-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="0803a-111">Należy również pobrać i lokalnie zapisać następujące szablony dla przykładowego raportu:</span><span class="sxs-lookup"><span data-stu-id="0803a-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="0803a-112">Szablon raportu o płatnościach (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="0803a-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="0803a-113">Ograniczony szablon raportu o płatnościach (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="0803a-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)

<span data-ttu-id="0803a-114">Te procedury mają być stosowane w przypadku funkcji dodanej w aplikacji Dynamics 365 for Operations w wersji 1611 (listopad 2016 r.).</span><span class="sxs-lookup"><span data-stu-id="0803a-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="0803a-115">Zaznaczenie istniejącej konfiguracji raportu ER</span><span class="sxs-lookup"><span data-stu-id="0803a-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="0803a-116">W aplikacji Dynamics 365 Finance wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="0803a-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="0803a-117">Upewnij się, że dostawca konfiguracji **Litware, Inc.** jest oznaczony jako **Aktywny**.</span><span class="sxs-lookup"><span data-stu-id="0803a-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="0803a-118">Jeśli nie, wykonaj kroki opisane w przewodniku zadania [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0803a-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="0803a-119">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="0803a-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="0803a-120">Ponownie wykorzystasz istniejącą konfigurację ER, który została pierwotnie zaprojektowana do generowania danych wyjściowych raportu w formacie OPENXML.</span><span class="sxs-lookup"><span data-stu-id="0803a-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="0803a-121">Na stronie **Konfiguracje** w drzewie konfiguracji w okienku po lewej wybierz pozycję **Model płatności**, a potem wybierz **Przykładowy raport arkusza**.</span><span class="sxs-lookup"><span data-stu-id="0803a-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0803a-122">Roboczą wersję wybranego formatu ER można edytować na skróconej karcie **Wersje**.</span><span class="sxs-lookup"><span data-stu-id="0803a-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="0803a-123">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="0803a-123">Select **Designer**.</span></span>
6. <span data-ttu-id="0803a-124">Na stronie **projektanta formatów** zwróć uwagę, że tytuł elementu formatu głównego wskazuje, że szablon programu Excel jest obecnie używany.</span><span class="sxs-lookup"><span data-stu-id="0803a-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Wybieranie istniejącej konfiguracji](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="0803a-126">Przeglądanie pobranego szablonu programu Word</span><span class="sxs-lookup"><span data-stu-id="0803a-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="0803a-127">W aplikacji programu Word otwórz pobrany wcześniej plik szablonu **SampleVendPaymDocReport.docx**.</span><span class="sxs-lookup"><span data-stu-id="0803a-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="0803a-128">Sprawdź, czy ten szablon zawiera tylko układ dokumentu, który chcesz wygenerować jako dane wyjściowe raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0803a-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![Układ szablonu programu Word w aplikacji na komputerze](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="0803a-130">Zamień szablon programu Excel na szablon programu Word i dodaj niestandardową część XML</span><span class="sxs-lookup"><span data-stu-id="0803a-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="0803a-131">Obecnie dokument programu Excel jest używany jako szablon do generowania danych wyjściowych w formacie OPENXML.</span><span class="sxs-lookup"><span data-stu-id="0803a-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="0803a-132">Zastąpisz ten szablon szablonem programu Word (SampleVendPaymDocReport.docx), który został pobrany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="0803a-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="0803a-133">Rozszerzysz również szablonu programu Word przez dodanie niestandardowej części XML.</span><span class="sxs-lookup"><span data-stu-id="0803a-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="0803a-134">W aplikacji Finance na stronie **Projektant formatów** na karcie **Format** wybierz **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="0803a-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="0803a-135">Na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć istniejący szablon programu Excel.</span><span class="sxs-lookup"><span data-stu-id="0803a-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="0803a-136">Wybierz **Tak**, aby potwierdzić zmianę.</span><span class="sxs-lookup"><span data-stu-id="0803a-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="0803a-137">Wybierz pozycję **Nowy** \> **Plik**.</span><span class="sxs-lookup"><span data-stu-id="0803a-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0803a-138">Musisz wybrać typ dokumentu [skonfigurowany](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) w parametrach ER, aby przechowywać szablony formatów ER.</span><span class="sxs-lookup"><span data-stu-id="0803a-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="0803a-139">Wybierz pozycję **Przeglądaj**, a następnie przejdź do pliku **SampleVendPaymDocReport.docx**, który został pobrany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="0803a-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="0803a-140">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0803a-140">Select **OK**.</span></span>
6. <span data-ttu-id="0803a-141">Zamknij stronę **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="0803a-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="0803a-142">Na stronie **Projektant formatów** w polu **Szablon** wprowadź lub wybierz plik **SampleVendPaymDocReport.docx**, aby użyć tego szablonu programu Word, a nie wcześniej używanego szablonu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="0803a-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="0803a-143">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0803a-143">Select **Save**.</span></span>

    <span data-ttu-id="0803a-144">Oprócz zapisania zmian w konfiguracji akcja **Zapisz** aktualizuje dołączony szablon programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="0803a-145">Hierarchiczna struktura zaprojektowanego formatu jest dodawana do dołączonego dokumentu programu Word jako nowa niestandardowa część w postaci kodu źródłowego XML o nazwie **Raport**.</span><span class="sxs-lookup"><span data-stu-id="0803a-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="0803a-146">Dołączony szablon programu Word zawiera układ dokumentu, który zostanie wygenerowany jako dane wyjściowe modułu ER, oraz strukturę danych, które moduł raportowania elektronicznego umieści w tym szablonie podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0803a-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="0803a-147">Zauważ, że tytuł elementu formatu głównego wskazuje, że szablon programu Word jest obecnie używany.</span><span class="sxs-lookup"><span data-stu-id="0803a-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Zamienianie szablonu programu Excel na szablon programu Word i dodawanie niestandardowej części XML](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="0803a-149">Na karcie **format** wybierz opcję **załączniki**.</span><span class="sxs-lookup"><span data-stu-id="0803a-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="0803a-150">Możesz teraz zamapować elementy niestandardowej części XML **Raport** do formantów zawartości dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="0803a-151">Jeśli znasz proces projektowania dokumentów programu Word jako formularzy zawierających [kontrolki zawartości](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) i mapowanych na elementy [niestandardowych części XML](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), wykonaj wszystkie kroki następnej procedury w celu utworzenia dokumentu.</span><span class="sxs-lookup"><span data-stu-id="0803a-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="0803a-152">Więcej informacji zawiera sekcja [Tworzenie formularzy, które użytkownicy wypełniają lub drukują w aplikacji Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="0803a-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="0803a-153">W przeciwnym razie pomiń następną procedurę.</span><span class="sxs-lookup"><span data-stu-id="0803a-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="0803a-154">Pobieranie dokumentu programu Word z niestandardową częścią XML i mapowanie danych</span><span class="sxs-lookup"><span data-stu-id="0803a-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="0803a-155">W aplikacji Finance na stronie **Załączniki** wybierz pozycję **Otwórz**, aby pobrać wybrany szablon z aplikacji Finance i zapisać go lokalnie jako dokument programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="0803a-156">W aplikacji klasycznej Word otwórz pobrany właśnie dokument.</span><span class="sxs-lookup"><span data-stu-id="0803a-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="0803a-157">Na karcie **Deweloper** wybierz opcję **Okienko mapowania XML**.</span><span class="sxs-lookup"><span data-stu-id="0803a-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0803a-158">Jeśli karta **Deweloper** nie jest wyświetlana na wstążce, dostosuj ją, aby dodać tę kartę.</span><span class="sxs-lookup"><span data-stu-id="0803a-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="0803a-159">W okienku **Mapowanie XML** w polu **Niestandardowa część XML** wybierz niestandardową część XML **Raport**.</span><span class="sxs-lookup"><span data-stu-id="0803a-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="0803a-160">Zamapuj elementy wybranej niestandardowej części XML **Raport** i kontrolki zawartości dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="0803a-161">Zapisz zaktualizowany dokument programu Word lokalnie jako plik **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="0803a-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="0803a-162">Przeglądanie szablonu programu Word, w którym niestandardowy element XML jest mapowany na kontrolki zawartości</span><span class="sxs-lookup"><span data-stu-id="0803a-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="0803a-163">W aplikacji programu Word otwórz plik szablonu **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="0803a-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="0803a-164">Sprawdź, czy ten szablon zawiera układ dokumentu, który chcesz wygenerować jako dane wyjściowe raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="0803a-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="0803a-165">Kontrolki zawartości używane jako symbole zastępcze danych, które będą wprowadzane w tym szablonie w czasie wykonywania w modelu ER, są oparte na mapowaniach skonfigurowanych między elementami niestandardowej części XML **Raport** a kontrolkami zawartości dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="0803a-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Podgląd szablonu programu Word w aplikacji na komputerze](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="0803a-167">Przekazywanie szablonu programu Word, w którym niestandardowy element XML jest mapowany na kontrolki zawartości</span><span class="sxs-lookup"><span data-stu-id="0803a-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="0803a-168">W aplikacji Finance na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć szablon programu Word, który nie ma mapowań między elementami niestandardowej części XML **Raport** i kontrolkami zawartości.</span><span class="sxs-lookup"><span data-stu-id="0803a-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="0803a-169">Wybierz **Tak**, aby potwierdzić zmianę.</span><span class="sxs-lookup"><span data-stu-id="0803a-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="0803a-170">Wybierz pozycję **Nowy** \> **Plik**, aby dodać nowy plik szablonu zawierający mapowania między elementami niestandardowej części XML **Raport** i kontrolkami zawartości.</span><span class="sxs-lookup"><span data-stu-id="0803a-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0803a-171">Musisz wybrać typ dokumentu [skonfigurowany](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) w parametrach ER, aby przechowywać szablony formatów ER.</span><span class="sxs-lookup"><span data-stu-id="0803a-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="0803a-172">Wybierz pozycję **Przeglądaj**, a następnie odszukaj i wybierz plik **SampleVendPaymDocReportBounded.docx** pobrany lub przygotowany przez wykonanie procedury w sekcji [Pobieranie dokumentu programu Word, która zawiera niestandardową część XML, w celu mapowania danych](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="0803a-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="0803a-173">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0803a-173">Select **OK**.</span></span>
5. <span data-ttu-id="0803a-174">Zamknij stronę **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="0803a-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="0803a-175">Na stronie **Projektant formatów** w polu **Szablon** wybierz pobrany właśnie dokument.</span><span class="sxs-lookup"><span data-stu-id="0803a-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="0803a-176">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0803a-176">Select **Save**.</span></span>
8. <span data-ttu-id="0803a-177">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="0803a-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="0803a-178">Oznaczanie skonfigurowanego formatu jako możliwego do uruchomienia</span><span class="sxs-lookup"><span data-stu-id="0803a-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="0803a-179">Aby uruchomić wersję roboczą formatu edytowalnego, należy oznaczyć go jako [możliwy do uruchomienia](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="0803a-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="0803a-180">W aplikacji Finance na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="0803a-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="0803a-181">W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="0803a-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="0803a-182">W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była możliwa do edycji.</span><span class="sxs-lookup"><span data-stu-id="0803a-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="0803a-183">W przypadku aktualnie wybranej konfiguracji **Przykładowy raport arkusza** ustaw opcję **Uruchom wersję roboczą** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0803a-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="0803a-184">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0803a-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="0803a-185">Uruchamianie formatu w celu utworzenia danych wyjściowych w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="0803a-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="0803a-186">W aplikacji Finance przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="0803a-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="0803a-187">W wprowadzonym wcześniej arkuszu płatności wybierz opcję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="0803a-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="0803a-188">Na stronie **Płatności dostawcy** zaznacz wszystkie wiersze w siatce.</span><span class="sxs-lookup"><span data-stu-id="0803a-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="0803a-189">Wybierz pozycję **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="0803a-189">Select **Payment status** \> **None**.</span></span>

    ![Płatności do przetwarzania na stronie Płatności dostawcy](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="0803a-191">W okienku akcji wybierz pozycję **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="0803a-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="0803a-192">W wyświetlonym oknie dialogowym wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="0803a-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="0803a-193">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="0803a-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="0803a-194">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="0803a-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="0803a-195">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0803a-195">Select **OK**.</span></span>

7. <span data-ttu-id="0803a-196">W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0803a-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="0803a-197">Wygenerowane dane wyjściowe są przedstawione w formacie programu Word i zawierają szczegóły przetworzonych płatności.</span><span class="sxs-lookup"><span data-stu-id="0803a-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="0803a-198">Zbadaj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="0803a-198">Analyze the generated output.</span></span>

    ![Wygenerowane dane wyjściowe w formacie programu Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="0803a-200">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0803a-200">Additional resources</span></span>

- [<span data-ttu-id="0803a-201">Projektowanie nowej konfiguracji ER w celu generowania raportów w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="0803a-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="0803a-202">Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="0803a-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]