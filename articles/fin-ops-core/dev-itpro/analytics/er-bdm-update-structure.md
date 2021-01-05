---
title: Aktualizowanie struktury szablonu dokumentu biznesowego
description: W tym temacie opisano sposób aktualizacji struktury szablonu dokumentu biznesowego przy użyciu funkcji zarządzania dokumentami biznesowymi.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: fd279b28c43e22bec6bf814845fe97828bc96d81
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681335"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="6b737-103">Aktualizowanie struktury szablonu dokumentu biznesowego</span><span class="sxs-lookup"><span data-stu-id="6b737-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6b737-104">W okienku **Struktura szablonów** w Edytorze szablonów [Zarządzanie dokumentami biznesowymi](er-business-document-management.md) można zmodyfikować szablon dokumentu biznesowego, [dodając nowe pola](er-bdm-add-field-to-excel-template.md) do szablonu w systemie Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="6b737-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="6b737-105">Struktura szablonu jest następnie automatycznie aktualizowana w systemie Dynamics 365 Finance, tak aby odzwierciedlała zmiany wprowadzone w okienku **Struktura szablonu**.</span><span class="sxs-lookup"><span data-stu-id="6b737-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="6b737-106">Można również zmodyfikować szablon, korzystając z funkcji online systemu Office 365.</span><span class="sxs-lookup"><span data-stu-id="6b737-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="6b737-107">Można na przykład dodać do edytowalnego arkusza nowy nazwany element, taki jak obraz lub kształt.</span><span class="sxs-lookup"><span data-stu-id="6b737-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="6b737-108">W takim przypadku struktura szablonu nie jest automatycznie aktualizowana w module Finance, a dodany element nie jest wyświetlany w okienku **Struktura szablonów**.</span><span class="sxs-lookup"><span data-stu-id="6b737-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="6b737-109">Aby ręcznie zaktualizować strukturę szablonów w module Finance, należy wybrać opcję **Aktualizuj strukturę** na stronie Edytor szablonów.</span><span class="sxs-lookup"><span data-stu-id="6b737-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="6b737-110">Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="6b737-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="6b737-111">Przykład: aktualizowanie struktury szablonu dokumentu biznesowego</span><span class="sxs-lookup"><span data-stu-id="6b737-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="6b737-112">W tym przykładzie pokazano, jak administrator systemu może zaktualizować strukturę szablonu dokumentu biznesowego w module Finance po zmodyfikowaniu szablonu w systemie Office Online.</span><span class="sxs-lookup"><span data-stu-id="6b737-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="6b737-113">W poniższych sekcjach objaśniono wymagane kroki.</span><span class="sxs-lookup"><span data-stu-id="6b737-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="6b737-114">Przygotuj szablon dokumentu biznesowego do edycji</span><span class="sxs-lookup"><span data-stu-id="6b737-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="6b737-115">W tym celu należy wykonać poniższe procedury z sekcji [Omówienie zarządzania dokumentami biznesowymi](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="6b737-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="6b737-116">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="6b737-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="6b737-117">Importowanie rozwiązań ER</span><span class="sxs-lookup"><span data-stu-id="6b737-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="6b737-118">Włącz zarządzanie dokumentem biznesowym</span><span class="sxs-lookup"><span data-stu-id="6b737-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="6b737-119">Konfigurowanie parametrów</span><span class="sxs-lookup"><span data-stu-id="6b737-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="6b737-120">Edytowanie szablonu dokumentów biznesowych</span><span class="sxs-lookup"><span data-stu-id="6b737-120">Edit a business document template</span></span>

1. <span data-ttu-id="6b737-121">W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.</span><span class="sxs-lookup"><span data-stu-id="6b737-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="6b737-122">Na stronie **Utwórz nowy szablon** wybierz szablon **Faktura niezależna (przykład ER)(Excel)**.</span><span class="sxs-lookup"><span data-stu-id="6b737-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="6b737-123">Wybierz opcję **Utwórz dokument**.</span><span class="sxs-lookup"><span data-stu-id="6b737-123">Select **Create document**.</span></span>
4. <span data-ttu-id="6b737-124">W polu **Tytuł** wpisz **FTI sample Litware**.</span><span class="sxs-lookup"><span data-stu-id="6b737-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="6b737-125">Wybierz **OK**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="6b737-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b737-126">Jeśli jeszcze nie zalogowano się do systemu Office Online, nastąpi [przekierowanie do strony logowania Office 365](er-business-document-management.md#i-selected-edit-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-microsoft-365-web-page).</span><span class="sxs-lookup"><span data-stu-id="6b737-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#i-selected-edit-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-microsoft-365-web-page).</span></span> <span data-ttu-id="6b737-127">Aby powrócić do środowiska Finance, wybierz przycisk **Wstecz** w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="6b737-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="6b737-128">Nowy szablon zostanie otwarty do edycji w osadzonym formancie Excel Online na stronie Edytor szablonów.</span><span class="sxs-lookup"><span data-stu-id="6b737-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="6b737-129">[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu rozpoczęcia edycji szablonu dokumentu biznesowego](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="6b737-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="6b737-130">Przejrzyj bieżącą strukturę edytowalnego szablonu</span><span class="sxs-lookup"><span data-stu-id="6b737-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="6b737-131">W formancie Excel Online, na wstążce na karcie **Widok** w grupie **Pokaż** wybierz **Linie siatki**.</span><span class="sxs-lookup"><span data-stu-id="6b737-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="6b737-132">W szablonie edytowalnym zaznacz prostokąt nad tytułem szablonu.</span><span class="sxs-lookup"><span data-stu-id="6b737-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="6b737-133">Ten prostokąt jest obrazem o nazwie **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="6b737-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="6b737-134">Jeśli okienko **Struktura szablonu** jest ukryte, wybierz **Pokaż strukturę**.</span><span class="sxs-lookup"><span data-stu-id="6b737-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="6b737-135">W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="6b737-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="6b737-136">Należy zauważyć, że w strukturze szablonów w module Finance element **rptHeaderCompLogo** jest przedstawiany jako element podrzędny elementu **Raport \> Faktura \> rptHeader faktury \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="6b737-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="6b737-137">[![Przeglądanie bieżącej struktury edytowalnego szablonu za pomocą obszaru roboczego zarządzania dokumentami biznesowymi](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="6b737-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="6b737-138">Aktualizowanie struktury szablonu dokumentu biznesowego przez usunięcie obrazu</span><span class="sxs-lookup"><span data-stu-id="6b737-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="6b737-139">W formancie Excel Online w szablonie edytowalnym wybierz obraz **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="6b737-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="6b737-140">Aby usunąć zaznaczony obraz z szablonu edytowalnego, należy wykonać jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="6b737-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="6b737-141">Naciśnij klawisz **Delete**.</span><span class="sxs-lookup"><span data-stu-id="6b737-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="6b737-142">Zaznacz obraz i przytrzymaj go (lub kliknij prawym przyciskiem myszy), a następnie wybierz opcję **Wytnij**.</span><span class="sxs-lookup"><span data-stu-id="6b737-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b737-143">**Element rptHeaderCompLogo** nadal znajduje się w strukturze szablonów w module Finance, nawet jeśli tego obrazu nie ma już w szablonie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="6b737-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="6b737-144">Wybierz opcję **Aktualizuj strukturę**, aby zsynchronizować strukturę szablonu edytowalnego w programie Excel i module Finance.</span><span class="sxs-lookup"><span data-stu-id="6b737-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="6b737-145">W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="6b737-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="6b737-146">Elementu **rptHeaderCompLogo** nie będzie już w strukturze szablonów w module Finance.</span><span class="sxs-lookup"><span data-stu-id="6b737-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="6b737-147">[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu usuwania obrazu z szablonu dokumentu biznesowego](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="6b737-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="6b737-148">Aktualizowanie struktury szablonu dokumentu biznesowego przez dodawanie obrazu</span><span class="sxs-lookup"><span data-stu-id="6b737-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="6b737-149">W formancie Excel Online, na wstążce na karcie **Wstawianie** w grupie **Ilustracje** wybierz **Obraz**.</span><span class="sxs-lookup"><span data-stu-id="6b737-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="6b737-150">Wybierz opcję **Wybierz plik**, przejdź do obrazu, który chcesz dodać, zaznacz go, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b737-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="6b737-151">Wybierz **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="6b737-151">Select **Insert**.</span></span>
4. <span data-ttu-id="6b737-152">Przenieś nowy obraz w odpowiednie miejsce.</span><span class="sxs-lookup"><span data-stu-id="6b737-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="6b737-153">Domyślnie program Excel nazywa obraz.</span><span class="sxs-lookup"><span data-stu-id="6b737-153">By default, Excel names the picture.</span></span> <span data-ttu-id="6b737-154">Na przykład może to być obraz o nazwie **Obraz 2**.</span><span class="sxs-lookup"><span data-stu-id="6b737-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="6b737-155">Wybierz opcję **Aktualizuj strukturę**, aby zsynchronizować strukturę szablonu edytowalnego w programie Excel i module Finance.</span><span class="sxs-lookup"><span data-stu-id="6b737-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="6b737-156">W okienku **Struktura szablonu** rozwiń węzeł **Raport \> Faktura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="6b737-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="6b737-157">Nowy obraz jest teraz elementem struktury szablonów w module Finance.</span><span class="sxs-lookup"><span data-stu-id="6b737-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="6b737-158">[![Używanie obszaru roboczego zarządzanie dokumentami biznesowymi w celu dodawania obrazu do dokumentu biznesowego](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="6b737-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="6b737-159">Powiązane łącza</span><span class="sxs-lookup"><span data-stu-id="6b737-159">Related links</span></span>

[<span data-ttu-id="6b737-160">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="6b737-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="6b737-161">Omówienie zarządzania dokumentami biznesowymi</span><span class="sxs-lookup"><span data-stu-id="6b737-161">Business document management overview</span></span>](er-business-document-management.md)
