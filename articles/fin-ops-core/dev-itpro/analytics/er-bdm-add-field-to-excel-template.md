---
title: Dodawanie nowych pól do szablonu dokumentu biznesowego w formularzu Microsoft Excel
description: Ten temat zawiera informacje dotyczące sposobu dodawania nowych pól do szablonu w Microsoft Excel za pomocą funkcji zarządzania dokumentami biznesowymi systemu.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d6e0f2c914b8d348ef6eac42557fb46c53df04a9
ms.sourcegitcommit: d16d370dab734e09312cb06711beca9cca52d4c9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2019
ms.locfileid: "2809527"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="c0ed3-103">Dodawanie nowych pól do szablonu dokumentu biznesowego w formularzu Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c0ed3-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c0ed3-104">Nowe pola można dodawać do szablonu używanego do generowania dokumentów biznesowych w format Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="c0ed3-105">Pola te można dodawać jako symbole zastępcze używane do wypełniania wygenerowanych dokumentów informacjami wymaganymi z poziomu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="c0ed3-106">Dla każdego dodawanego pola można również określić powiązanie ze źródłami danych, aby określić, jakie dane aplikacji będą wprowadzane do pola w przypadku użycia szablonu do generowania dokumentów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="c0ed3-107">Wykonaj przykład z tego tematu, aby dowiedzieć się więcej na temat tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="c0ed3-108">W tym przykładzie przedstawiono sposób aktualizacji szablonu w celu wypełniania pól w wygenerowanych formularzach faktur niezależnych.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="c0ed3-109">konfigurowanie szablonów przy użyciu funkcji zarządzania dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="c0ed3-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="c0ed3-110">Ponieważ zarządzanie dokumentami biznesowymi (BDM) jest zbudowane na podstawie [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md), należy skonfigurować wymagane parametry modułu er i BDM, aby można było rozpocząć pracę z BDM.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="c0ed3-111">Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Finance jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="c0ed3-112">W temacie [Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md) należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c0ed3-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="c0ed3-113">Konfigurowanie parametrów modułu ER.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="c0ed3-114">Włącz BDM.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-114">Turn on BDM.</span></span>

<span data-ttu-id="c0ed3-115">Teraz można rozpocząć używanie BDM do edytowania szablonów dokumentów biznesowych.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="c0ed3-116">Importuj rozwiązania ER, które zawierają szablon</span><span class="sxs-lookup"><span data-stu-id="c0ed3-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="c0ed3-117">W przykładzie tej procedury użyto oficjalnie opublikowanego rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="c0ed3-118">Należy zaimportować konfiguracje klasy ER tego rozwiązania do bieżącego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="c0ed3-119">Konfiguracja **Darmowy tekst faktury (Excel)** tego rozwiązania zawiera szablon dokumentu biznesowego w formacie programu Excel, który można edytować za pomocą BDM.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="c0ed3-120">Zaimportuj najnowszą wersję tej konfiguracji formatu na podstawie Microsoft Dynamics usługi Lifecycle Service (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="c0ed3-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="c0ed3-121">Odpowiednie konfiguracje mapowań modelu danych i modelu ER zostaną zaimportowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="c0ed3-122">Aby uzyskać więcej informacji jak importować konfiguracji ER, zapoznaj się z [Zarządzanie cyklem życia konfiguracji Raportowania elektronicznego](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed3-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Strona biblioteki udostępnionych elementów zawartości LCS](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="c0ed3-124">Edytuj szablon rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="c0ed3-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="c0ed3-125">Zaloguj się jako użytkownik z dostępem do strony obszaru roboczego **zarządzania dokumentami biznesowymi**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="c0ed3-126">Otwórz obszaru roboczy **zarządzania dokumentami biznesowymi**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-126">Open the **Business document management** workspace.</span></span>

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="c0ed3-128">W siatce wybierz szablon **Darmowy tekst faktury (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="c0ed3-129">W prawym okienku wybierz opcję **nowy szablon**, aby utworzyć nowy szablon oparty na wybranym szablonie.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="c0ed3-130">W polu **tytuł** wprowadź **Darmowy tekst faktury (Excel) contoso** jako tytuł nowego szablonu.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="c0ed3-131">Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="c0ed3-132">Pojawia się strona Edytor szablonów BDM.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-132">The BDM template editor page appears.</span></span> <span data-ttu-id="c0ed3-133">Można wykorzystać Microsoft Office 365 do edytowania wybranego szablonu w trybie online w osadzonym formancie.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-133">You can use Microsoft Office 365 to edit the selected template online in the embedded control.</span></span>

![Strona edytora szablonów BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="c0ed3-135">Dodaj etykietę nowego pola do szablonu</span><span class="sxs-lookup"><span data-stu-id="c0ed3-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="c0ed3-136">Na stronie Edytor szablonów BDM na wstążce programu Excel na karcie **Widok** zaznacz pola wyboru **nagłówki i linie siatki** dla edytowalnego szablonu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Zaznaczone pola wyboru nagłówki i linie siatki](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="c0ed3-138">Zaznacz komórki **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="c0ed3-139">Na wstążce programu Excel na karcie **Widok główny** wybierz opcję **Scal & Scentruj**, aby scalić wybrane komórki do nowej, scalonej komórki **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="c0ed3-140">W Scalonej komórce **E8:F8** wprowadź adres **URL**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="c0ed3-141">Wybierz scaloną komórkę **E7:F7**, wybierz opcję **Malarz formatów**, a następnie wybierz scaloną komórkę **E8:F8**, aby ją sformatować w ten sam sposób,co scalona komórka **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Pole nowej etykiety dodanej do szablonu](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="c0ed3-143">Sformatuj szablon, aby zarezerwować miejsce dla nowego pola</span><span class="sxs-lookup"><span data-stu-id="c0ed3-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="c0ed3-144">Na stronie Edytor szablonów BDM wybierz scaloną komórkę **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="c0ed3-145">Na wstążce programu Excel na karcie **Widok główny** wybierz opcję **Scal & Scentruj**, aby scalić wybrane komórki do nowej, scalonej komórki **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="c0ed3-146">Wybierz scaloną komórkę **G7:H7**, wybierz opcję **Malarz formatów**, a następnie wybierz scaloną komórkę **G8:H8**, aby ją sformatować w ten sam sposób,co scalona komórka **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Miejsce zarezerwowane dla nowego pola](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="c0ed3-148">W polu **nazwa** wybierz opcję **companyinfo**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="c0ed3-149">**Companyinfo** zakres bieżącego szablonu programu Excel zawiera wszystkie pola, które są używane do wypełniania nagłówka wygenerowanego raportu ze szczegółami bieżącej firmy jako strony sprzedającej.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Wybrano zakres CompanyInfo](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="c0ed3-151">Dodaj nowego pola do szablonu</span><span class="sxs-lookup"><span data-stu-id="c0ed3-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="c0ed3-152">Na stronie **Edytor szablonów BDM** w okienku akcji wybierz opcję **show format**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="c0ed3-153">W okienku **struktura szablonów** wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0ed3-154">Musisz zmienić sekcję szablonu, która ma być używana jako nowe pole.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="c0ed3-155">Ta korekta została już dokonana przez formatowanie Scalonej komórki **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Dodawa nowego pola do szablonu](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="c0ed3-157">Wybierz **Excel\Cell**, aby dodać nowe pole jako komórkę w szablonie.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="c0ed3-158">Jeśli chcesz dodać zakres do szablonu, możesz wybrać **Excel\Zakres**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="c0ed3-159">Wprowadzony zakres może zawierać wiele komórek.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="c0ed3-160">Możesz dodać te komórki później.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="c0ed3-161">Zauważ, że składnik szablonu **CompanyInfo** jest automatycznie wybierany w panelu **struktura szablonów**, ponieważ jest to najbardziej odpowiedni składnik nadrzędny w strukturze bieżącego szablonu dla dodawanego pola.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="c0ed3-162">W polu **zakres programu Excel** wprowadź **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="c0ed3-163">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-163">Select **OK**.</span></span>

    ![Do struktury szablonu dodano CompanyURL_Value pole](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="c0ed3-165">W okienku **struktura szablonów** wybierz przycisk wielokropka (...), a następnie wybierz opcję **pokazuj powiązania**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Pokaż wybrane powiązania](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="c0ed3-167">W okienku **struktury szablonów** są teraz wyświetlane źródła danych dostępne w odpowiednim formacie modułu ER.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="c0ed3-168">Wybierz **CompanyInfo_Value** jako pole, które chcesz powiązać ze źródłem danych źródłowego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="c0ed3-169">W sekcji **źródła danych** w panelu **Struktura szablonów** rozwiń gałąź **Model \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="c0ed3-170">W obszarze **CompanyInfo** wybierz pozycję **WebsiteURL**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Wybrane elementy WebsiteURL](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="c0ed3-172">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-172">Select **Bind**.</span></span>
11. <span data-ttu-id="c0ed3-173">W okienku **struktura szablonu** wybierz opcję **Zapisz**, a następnie zamknij stronę Edytor szablonów BDM.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="c0ed3-174">W obszarze roboczym **zarządzanie dokumentami biznesowymi** na karcie **szablon** w prawym okienku jest wyświetlany zaktualizowany szablon.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="c0ed3-175">W siatce Zwróć uwagę, że pole **stan** edytowanego szablonu zostało zmienione na wartość **wersja robocza**, a pole **Poprawka** nie jest już puste.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="c0ed3-176">Zmiany te wskazują, że proces edycji tego szablonu został rozpoczęty.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-176">These changes indicate that the process of editing this template has been started.</span></span>

![Szablon edytowany w obszarze roboczym zarządzanie dokumentami biznesowymi](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="c0ed3-178">Przejrzyj ustawienia firmy</span><span class="sxs-lookup"><span data-stu-id="c0ed3-178">Review company settings</span></span>

1.  <span data-ttu-id="c0ed3-179">Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Firmy**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="c0ed3-180">Na skróconej karcie **informacji kontaktowych** sprawdź, czy adres URL firmy został wprowadzony.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![Adres URL firmy wprowadzony na stronie firmy](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="c0ed3-182">Generowanie dokumentów biznesowych w celu przetestowania zaktualizowanego szablonu</span><span class="sxs-lookup"><span data-stu-id="c0ed3-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="c0ed3-183">W aplikacji Zmień firmę na **USMF** i przejdź do **Rozrachunki z odbiorcami \> Faktury \> Wszystkie faktury niezależne**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="c0ed3-184">Wybierz fakturę **FTI-00000002**, a następnie wybierz opcję **Zarządzanie drukowaniem**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="c0ed3-185">W lewym okienku rozwiń węzeł **Moduł — Rozrachunki z odbiorcami \> Dokumenty \> Faktura niezależna**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="c0ed3-186">Pod **Faktura niezależna** wybierz **Dokument oryginalny**, aby określić zakres faktur do przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="c0ed3-187">W prawym okienku w polu **Format raportu** wybierz szablon **Darmowy tekst faktury (Excel) Contoso** dla określonego poziomu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Wybrany szablon Contoso — Faktura niezależna (Excel)](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="c0ed3-189">Naciśnij klawisz **Esc**, aby zamknąć bieżącą stronę.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="c0ed3-190">Wybierz opcje **Drukuj \> Wybrane**.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="c0ed3-191">Pobierz wygenerowany dokument i otwórz go w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-191">Download the generated document, and open it in Excel.</span></span>

    ![Faktura niezależna w Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="c0ed3-193">Zmodyfikowany szablon jest używany do generowania raportu faktury niezależnej dla wybranego towaru.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="c0ed3-194">Aby przeanalizować wpływ, jaki na ten raport mają zmiany wprowadzone w szablonie, uruchom raport w jednej sesji aplikacji natychmiast po zmianie szablonu w innej sesji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c0ed3-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="c0ed3-195">Powiązane linki</span><span class="sxs-lookup"><span data-stu-id="c0ed3-195">Related links</span></span>

[<span data-ttu-id="c0ed3-196">Omówienie raportowania elektronicznego (RE)</span><span class="sxs-lookup"><span data-stu-id="c0ed3-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="c0ed3-197">Omówienie zarządzania dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="c0ed3-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="c0ed3-198">Projektowanie konfiguracji do generowania raportów w formacie OPENXML</span><span class="sxs-lookup"><span data-stu-id="c0ed3-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)
