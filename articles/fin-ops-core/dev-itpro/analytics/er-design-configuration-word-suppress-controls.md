---
title: Pomijanie formantów zawartości programu Word w generowanych raportach
description: W tym temacie wyjaśniono, jak skonfigurować format raportowania elektronicznego w celu generowania raportów jako plików Microsoft Word, w których są pomijane formanty zawartości.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 8c99203110cfdc7f8123c30488611d55f48e8f67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753610"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="5e254-103">Pomijanie formantów zawartości programu Word w generowanych raportach</span><span class="sxs-lookup"><span data-stu-id="5e254-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e254-104">Aby generować raporty jako dokumenty Microsoft Word, musisz zaprojektować szablon raportów jako dokument Word.</span><span class="sxs-lookup"><span data-stu-id="5e254-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="5e254-105">Ten szablon musi zawierać kontrolki zawartości programu Word jako symbole zastępcze dla danych, które zostaną wypełnione w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5e254-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="5e254-106">Aby użyć dokumentu Word, który jest tworzony jako szablon dla twoich raportów, możesz [skonfigurować](er-design-configuration-word.md) nowe [rozwiązanie](er-quick-start1-new-solution.md) [Raportowania elektronicznego (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="5e254-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="5e254-107">To rozwiązanie musi zawierać [konfigurację](general-electronic-reporting.md#Configuration) zawierającą składnik [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="5e254-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="5e254-108">Ten format raportu ER musi być skonfigurowany do używania zaprojektowanego szablonu do generowania raportów.</span><span class="sxs-lookup"><span data-stu-id="5e254-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="5e254-109">W wersji 10.0.6 i nowszych Dynamics 365 Finance możesz skonfigurować formuły w formacie ER, aby pomijać niektóre kontrolki zawartości programu Word w generowanych dokumentach.</span><span class="sxs-lookup"><span data-stu-id="5e254-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="5e254-110">Poniższe kroki wyjaśniają, w jaki sposób użytkownik przypisany do roli administratora systemu lub konsultanta funkcjonalnego raportowania elektronicznego może skonfigurować format ER, który generuje raporty jako pliki programu Word i pomija niektóre elementy sterujące zawartością w wygenerowanych raportach, które zostały skonfigurowane za pomocą szablonu programu Word.</span><span class="sxs-lookup"><span data-stu-id="5e254-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="5e254-111">Kroki można wykonać na danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="5e254-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e254-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5e254-112">Prerequisites</span></span>

<span data-ttu-id="5e254-113">Aby wykonać te kroki, musisz najpierw wykonać kroki opisane w następujących przewodnikach po zadaniach:</span><span class="sxs-lookup"><span data-stu-id="5e254-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="5e254-114">Projektowanie konfiguracji do generowania raportów w formacie OPENXML</span><span class="sxs-lookup"><span data-stu-id="5e254-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="5e254-115">Ponowne użycie konfiguracji modułu Raportowanie elektroniczne z szablonami programu Excel do generowania raportów w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="5e254-116">Po ukończeniu kroków tych przewodników po zadaniach przygotowane zostaną następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="5e254-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="5e254-117">**Raport przykładowego arkusza skonfigurowany** formatu ER do generowania dokumentu w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="5e254-118">[Wersja robocza](general-electronic-reporting.md#component-versioning) **Przykładowego arkusza** formatu raportu ER, który jest oznaczony jako **Możliwy do uruchomienia**.</span><span class="sxs-lookup"><span data-stu-id="5e254-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="5e254-119">**Elektroniczna** metoda płatności skonfigurowana do używania formatu **Raportu przykładowego arkusza** ER do przetwarzania płatności dostawców</span><span class="sxs-lookup"><span data-stu-id="5e254-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="5e254-120">Musisz również pobrać i zapisać następujący szablon przykładowego raportu:</span><span class="sxs-lookup"><span data-stu-id="5e254-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="5e254-121">Ograniczony szablon raportu 2 o płatnościach (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="5e254-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="5e254-122">Przeglądanie pobranego szablonu programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="5e254-123">W aplikacji programu Word otwórz pobrany wcześniej plik szablonu **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="5e254-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="5e254-124">Sprawdź, czy plik szablonu zawiera sekcję podsumowania, która pokazuje łączne kwoty płatności dla każdego kodu waluty, który został osiągnięty w przetworzonych płatnościach.</span><span class="sxs-lookup"><span data-stu-id="5e254-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="5e254-125">Sekcja podsumowania znajduje się w oddzielnej tabeli dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="5e254-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="5e254-126">Pierwszy wiersz tej tabeli zawiera nagłówki kolumn tabeli jako nagłówki sekcji.</span><span class="sxs-lookup"><span data-stu-id="5e254-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="5e254-127">Drugi wiersz tej tabeli zawiera powtarzającą się kontrolkę zawartości jako szczegóły sekcji.</span><span class="sxs-lookup"><span data-stu-id="5e254-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="5e254-128">Ta kontrolka zawartości jest zamapowana na pole **SummaryLines** w niestandardowej części XML **Raportu**.</span><span class="sxs-lookup"><span data-stu-id="5e254-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="5e254-129">Na podstawie tego mapowania kontrola zawartości jest skojarzona z elementem **SummaryLines** w edytowalnym formacie raportu ER.</span><span class="sxs-lookup"><span data-stu-id="5e254-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e254-130">Powtarzający się formant zawartości jest otagowany przez klucz **SummaryLines**, który pasuje do pola niestandardowej części XML, do której została zmapowana.</span><span class="sxs-lookup"><span data-stu-id="5e254-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Układ szablonu programu Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="5e254-132">Zaznaczenie istniejącej konfiguracji raportu ER</span><span class="sxs-lookup"><span data-stu-id="5e254-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="5e254-133">W następnych krokach ponownie użyjesz istniejącej konfiguracji ER skonfigurowanej po wykonaniu kroków opisanych we wcześniej wspomnianych przewodnikach po zadaniach.</span><span class="sxs-lookup"><span data-stu-id="5e254-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="5e254-134">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="5e254-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="5e254-135">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="5e254-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="5e254-136">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model płatności**, a potem wybierz **Przykładowy raport arkusza**.</span><span class="sxs-lookup"><span data-stu-id="5e254-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="5e254-137">Wybierz pozycję **Konstruktor**, aby edytować wersję roboczą wybranego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="5e254-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="5e254-138">Zastąp bieżący szablon nowym szablonem</span><span class="sxs-lookup"><span data-stu-id="5e254-138">Replace the current template with the new template</span></span>

<span data-ttu-id="5e254-139">Obecnie plik SampleVendPaymDocReportBounded.docx jest używany jako szablon do generowania danych wyjściowych w formacie Word.</span><span class="sxs-lookup"><span data-stu-id="5e254-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="5e254-140">W kolejnych krokach zastąpisz ten szablon programu Word nowym szablonem programu Word, SampleVendPaymDocReportBounded2.docx, który został pobrany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="5e254-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="5e254-141">Na stronie **Projektant formatów** wybierz opcję **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="5e254-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="5e254-142">Na stronie **Załączniki** wybierz pozycję **Usuń**, aby usunąć istniejący szablon.</span><span class="sxs-lookup"><span data-stu-id="5e254-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="5e254-143">Wybierz **Tak**, aby potwierdzić usunięcie.</span><span class="sxs-lookup"><span data-stu-id="5e254-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="5e254-144">Wybierz pozycję **Nowy** \> **Plik**.</span><span class="sxs-lookup"><span data-stu-id="5e254-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="5e254-145">Wybierz pozycję **Przeglądaj**, a następnie przejdź do pliku **SampleVendPaymDocReportBounded2.docx**, który został pobrany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="5e254-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="5e254-146">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e254-146">Select **OK**.</span></span>
7. <span data-ttu-id="5e254-147">Zamknij stronę **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="5e254-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="5e254-148">Na stronie **Projektant formatów** w polu **Szablon** wprowadź lub wybierz plik **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="5e254-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="5e254-149">Uruchomienie formatu w celu utworzenia danych wyjściowych programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="5e254-150">Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="5e254-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="5e254-151">Na stronie **Płatności dostawcy** na karcie **Lista** zaznacz wszystkie płatności.</span><span class="sxs-lookup"><span data-stu-id="5e254-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="5e254-152">Wybierz pozycję **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="5e254-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="5e254-153">Wybierz **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="5e254-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="5e254-154">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="5e254-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="5e254-155">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="5e254-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="5e254-156">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e254-156">Select **OK**.</span></span>
8. <span data-ttu-id="5e254-157">W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK** i analizuj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="5e254-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Płatności do przetwarzania na stronie Płatności dostawcy](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="5e254-159">Wynik jest prezentowany w formacie programu Word i zawiera sekcję podsumowania.</span><span class="sxs-lookup"><span data-stu-id="5e254-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="5e254-160">Skonfiguruj edytowalny format, aby pomijać sekcję podsumowania</span><span class="sxs-lookup"><span data-stu-id="5e254-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="5e254-161">Jeśli chcesz pominąć sekcję podsumowania w wygenerowanym dokumencie, na podstawie żądania użytkownika, który uruchamia ten format ER, musisz zmodyfikować edytowalny format ER.</span><span class="sxs-lookup"><span data-stu-id="5e254-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="5e254-162">Przejdź do **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne** i otwórz wersję roboczą formatu raportowania elektronicznego w celu edycji.</span><span class="sxs-lookup"><span data-stu-id="5e254-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="5e254-163">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="5e254-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="5e254-164">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model płatności** \> **Przykładowy raport arkusza**.</span><span class="sxs-lookup"><span data-stu-id="5e254-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="5e254-165">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="5e254-165">Select **Designer**.</span></span>
5. <span data-ttu-id="5e254-166">Na stronie **Projektant formatów** rozwiń pozycję **Word** i wybierz pozycję **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="5e254-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="5e254-167">Na karcie **Mapowanie** dodaj nowe źródło danych, aby w czasie wykonywania zadać pytanie, czy sekcja podsumowania ma zostać pominięta:</span><span class="sxs-lookup"><span data-stu-id="5e254-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="5e254-168">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="5e254-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="5e254-169">W oknie dialogowym **Dodawanie źródła danych** wybierz opcję **Ogólne\Parametr wejściowy użytkownika**, aby otworzyć okno dialogowe Właściwości źródła danych **Parametr wejściowy użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="5e254-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="5e254-170">W polu **Nazwa** wpisz **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="5e254-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="5e254-171">W polu **Etykieta wprowadź** sekcję **Pomiń podsumowanie**.</span><span class="sxs-lookup"><span data-stu-id="5e254-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="5e254-172">W polu **Nazwa typu danych w programie Operations** wybierz lub wprowadź wartość **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="5e254-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="5e254-173">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e254-173">Select **OK**.</span></span>

7. <span data-ttu-id="5e254-174">Następnie należy dodać nowe źródło danych typu **Kod NoYes**:</span><span class="sxs-lookup"><span data-stu-id="5e254-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="5e254-175">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="5e254-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="5e254-176">W oknie dialogowym **Dodawanie źródła danych** wybierz opcję **Dynamics 365 for Operations\Wyliczenie**, aby otworzyć okno dialogowe **Właściwości źródła danych „Wyliczenie”**.</span><span class="sxs-lookup"><span data-stu-id="5e254-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="5e254-177">W polu **Nazwa** wpisz **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="5e254-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="5e254-178">W polu **Etykieta wprowadź** sekcję **Pomiń opcje**.</span><span class="sxs-lookup"><span data-stu-id="5e254-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="5e254-179">W polu **Nazwa typu danych w programie Operations** wybierz lub wprowadź wartość **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="5e254-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="5e254-180">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e254-180">Select **OK**.</span></span>

8. <span data-ttu-id="5e254-181">Dla wybranego elementu formatu **SummaryLines** skonfiguruj formułę, aby określić, kiedy ma zostać pominięta kontrola zawartości programu Word skojarzona z wybranym elementem formatu:</span><span class="sxs-lookup"><span data-stu-id="5e254-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="5e254-182">N karcie **Mapowanie** w sekcji **Usunięte** wybierz **Edytuj**, aby otworzyć kartę **[Projektant formuł](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="5e254-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="5e254-183">W polu **Formuła** wprowadź następujące `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="5e254-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="5e254-184">Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="5e254-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5e254-185">Ta formuła zostanie zastosowana do wygenerowanego dokumentu **po uruchomieniu wszystkich innych elementów formatu**.</span><span class="sxs-lookup"><span data-stu-id="5e254-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="5e254-186">Aby zastosować tę formułę, w generowanym dokumencie znajduje się formant zawartości programu Word, który jest oznaczony jako element formatu, dla których jest skonfigurowana formuła (w tym przypadku **SummaryLines**).</span><span class="sxs-lookup"><span data-stu-id="5e254-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="5e254-187">Ta kontrola zawartości zostanie całkowicie usunięta wraz z wierszem w tabeli programu Word, który ją zawiera.</span><span class="sxs-lookup"><span data-stu-id="5e254-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="5e254-188">Wiersz szczegółów sekcji podsumowania jest usuwany z wygenerowanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5e254-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="5e254-189">W czasie projektowania można skonfigurować formułę **Usunięta** dla elementu formatu, nawet jeśli w szablonie programu Word nie ma formantu zawartości, który jest używany, ma znacznik, który pasuje do nazwy elementu formatu, dla których skonfigurowano właściwość **Usunięte**.</span><span class="sxs-lookup"><span data-stu-id="5e254-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="5e254-190">Podczas sprawdzania poprawności formatu w czasie projektowania jest wyświetlane [ostrzeżenie](er-components-inspections.md#i14) o niezgodności.</span><span class="sxs-lookup"><span data-stu-id="5e254-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="5e254-191">W czasie wykonywania występuje wyjątek, jeśli żaden formant zawartości w szablonie programu Word, który jest używany, ma znacznik, który pasuje do nazwy elementu formatu, dla których skonfigurowano właściwość **Usunięte**.</span><span class="sxs-lookup"><span data-stu-id="5e254-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="5e254-192">Na karcie **Mapowanie** w sekcji **Usunięte** dla opcji **Z elementem nadrzędnym** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5e254-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5e254-193">Musisz ustawić tę opcję na wartość **Tak**, aby usunąć całą tabelę programu Word jako obiekt nadrzędny wiersza, który zawiera szczegóły sekcji podsumowania.</span><span class="sxs-lookup"><span data-stu-id="5e254-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="5e254-194">Jeśli zostanie ustawiona opcja **Nie**, wiersz nagłówka sekcji pozostanie w generowanym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="5e254-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="5e254-195">Wybierz **Zapisz**, by zapisać zmiany w formacie do edycji.</span><span class="sxs-lookup"><span data-stu-id="5e254-195">Select **Save** to save your changes to the editable format.</span></span>

    ![Wygenerowane dane wyjściowe w formacie programu Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="5e254-197">Uruchomienie zmodyfikowanego formatu w celu utworzenia danych wyjściowych programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="5e254-198">Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="5e254-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="5e254-199">Wybierz utworzony przez siebie arkusz płatności, a następnie wybierz **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="5e254-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="5e254-200">Na stronie **Płatności dostawcy** zaznacz wszystkie wiersze, a następnie wybierz **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="5e254-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="5e254-201">Wybierz **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="5e254-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="5e254-202">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="5e254-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="5e254-203">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="5e254-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="5e254-204">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e254-204">Select **OK**.</span></span>
8. <span data-ttu-id="5e254-205">W oknie dialogowym **Parametry raportu elektronicznego** w polu **Pomiń podsumowanie** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5e254-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="5e254-206">Wybierz przycisk **OK** i przeanalizuj wygenerowane dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="5e254-206">Select **OK**, and analyze the generated output.</span></span>

    ![Wygenerowane dane wyjściowe w formacie programu Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="5e254-208">Zauważ, że dane wyjściowe nie zawierają sekcji podsumowania, ponieważ została pominięta.</span><span class="sxs-lookup"><span data-stu-id="5e254-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e254-209">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5e254-209">Additional resources</span></span>

- [<span data-ttu-id="5e254-210">Projektowanie konfiguracji do generowania raportów w formacie OPENXML</span><span class="sxs-lookup"><span data-stu-id="5e254-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="5e254-211">Projektowanie nowej konfiguracji modułu Raportowanie elektroniczne w celu generowania raportów w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="5e254-212">Ponowne użycie konfiguracji modułu Raportowanie elektroniczne z szablonami programu Excel do generowania raportów w formacie programu Word</span><span class="sxs-lookup"><span data-stu-id="5e254-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="5e254-213">Sprawdzanie skonfigurowanego składnika ER, aby zapobiec problemom w czasie wykonywania</span><span class="sxs-lookup"><span data-stu-id="5e254-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]