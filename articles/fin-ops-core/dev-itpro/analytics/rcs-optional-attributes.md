---
title: Importowanie plików w formacie XML z opcjonalnymi atrybutami
description: Ten temat zawiera informacje dotyczące projektowania formatów ER, które określają atrybuty XML służące do analizy przychodzących dokumentów elektronicznych w formacie XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 10795c90cb90961c17a4326b71ed43dc72039f2b
ms.sourcegitcommit: 66eae22cd99e53fe8e4c6c94945ad8061b69a442
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/11/2020
ms.locfileid: "3117432"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="9fd39-103">Importowanie plików w formacie XML z opcjonalnymi atrybutami</span><span class="sxs-lookup"><span data-stu-id="9fd39-103">Import files in XML format with optional attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9fd39-104">Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby analizowały przychodzące dokumenty elektroniczne w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="9fd39-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="9fd39-105">Niektóre atrybuty elementów XML można określać w zaprojektowanym formacie ER jako opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="9fd39-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="9fd39-106">Pozwoli to na prawidłową obsługę przychodzących plików z takimi atrybutami XML lub bez nich.</span><span class="sxs-lookup"><span data-stu-id="9fd39-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="9fd39-107">Następnie można użyć zawartości tych plików do aktualizacji danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9fd39-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="9fd39-108">Aby dowiedzieć się więcej o tej funkcji, należy wykonać kroki opisane w temacie, [(RCS) Importuj pliki w formacie XML z opcjonalnymi atrybutami](tasks/import-files-xml-format-optional-attributes.md), które są częścią procesu biznesowego 7.5.4.3 Nabycie/Opracowanie procesu biznesowego dotyczącego usług IT/komponentów rozwiązania (10677).</span><span class="sxs-lookup"><span data-stu-id="9fd39-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="9fd39-109">Możesz pobrać ten przewodnik zadań i powiązane przykładowe pliki z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="9fd39-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="9fd39-110">Opis zawartości</span><span class="sxs-lookup"><span data-stu-id="9fd39-110">Content description</span></span>       | <span data-ttu-id="9fd39-111">Plik</span><span class="sxs-lookup"><span data-stu-id="9fd39-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="9fd39-112">Przykładowy plik w formacie XML</span><span class="sxs-lookup"><span data-stu-id="9fd39-112">Sample file in XML format</span></span> | <span data-ttu-id="9fd39-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml.</span><span class="sxs-lookup"><span data-stu-id="9fd39-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="9fd39-114">Przewodniki po zadaniach</span><span class="sxs-lookup"><span data-stu-id="9fd39-114">Task guide</span></span>                | <span data-ttu-id="9fd39-115">RCS Importowanie plików w formacie XML z opcjonalnymi atrybutami.axtr</span><span class="sxs-lookup"><span data-stu-id="9fd39-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="9fd39-116">W poniższych krokach wyjaśniono, jak użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może zaprojektować konfigurację formatu ER do importowania plików w formacie XML zawierającym atrybuty opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="9fd39-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="9fd39-117">Aby wykonać te kroki, należy najpierw wykonać kroki w tej procedurze [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9fd39-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="9fd39-118">Przed rozpoczęciem należy pobrać i zapisać lokalnie plik IncomingDocumentToLearnHowToHandleOptionalAttributes.XML z centrum pobierania Microsoft (https://go.microsoft.com/fwlink/?linkid=874684 ).</span><span class="sxs-lookup"><span data-stu-id="9fd39-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="9fd39-119">Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="9fd39-120">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="9fd39-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="9fd39-121">Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki opisane w temacie [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9fd39-121">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="9fd39-122">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="9fd39-123">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="9fd39-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="9fd39-124">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="9fd39-125">W polu **Nazwa** wpisz „Model do importu pliku XML”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="9fd39-126">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="9fd39-127">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-127">Click **Designer**.</span></span>
5. <span data-ttu-id="9fd39-128">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="9fd39-129">W polu **Nazwa** wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="9fd39-130">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-130">Click **Add**.</span></span>
8. <span data-ttu-id="9fd39-131">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="9fd39-132">W polu **Nazwa** wpisz „Lista”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-132">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="9fd39-133">W polu **Kod przedmiotu** wybierz **Lista tabel**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-133">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="9fd39-134">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-134">Click **Add**.</span></span>
12.    <span data-ttu-id="9fd39-135">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-135">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="9fd39-136">W polu **Nazwa** wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-136">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="9fd39-137">W polu **Typ przedmiotu** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-137">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="9fd39-138">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-138">Click **Add**.</span></span>
16.    <span data-ttu-id="9fd39-139">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-139">Click **Save**.</span></span>
17.    <span data-ttu-id="9fd39-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9fd39-140">Close the page.</span></span>
18.    <span data-ttu-id="9fd39-141">Kliknij przycisk **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-141">Click **Change status**.</span></span>
19.    <span data-ttu-id="9fd39-142">Kliknij przycisk **Wykonaj.**</span><span class="sxs-lookup"><span data-stu-id="9fd39-142">Click **Complete**.</span></span>
20.    <span data-ttu-id="9fd39-143">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="9fd39-144">Tworzenie formatu importu danych</span><span class="sxs-lookup"><span data-stu-id="9fd39-144">Create a format for data import</span></span>
1. <span data-ttu-id="9fd39-145">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="9fd39-146">W polu **Nowy** wpisz „Format oparty na modelu danych Model do importowania pliku xml”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="9fd39-147">W polu **Nazwa** wpisz „Format do importu pliku XML”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-147">In the **Nam**e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="9fd39-148">Wybierz opcję **Tak** w polu **Obsługuje import danych**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="9fd39-149">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="9fd39-150">Umożliwia zaprojektowanie formatu w celu przeanalizowania pliku przychodzącego w formacie XML</span><span class="sxs-lookup"><span data-stu-id="9fd39-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="9fd39-151">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-151">Click **Designer**.</span></span>
2. <span data-ttu-id="9fd39-152">Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="9fd39-153">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="9fd39-154">W polu **Nazwa** wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="9fd39-155">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-155">Click **OK**.</span></span>
6. <span data-ttu-id="9fd39-156">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="9fd39-157">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="9fd39-158">W polu **Nazwa** wpisz „dokument”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="9fd39-159">W polu **Wielość** wybierz opcję **Jeden wiele**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-159">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="9fd39-160">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-160">Click **OK**.</span></span>
11.    <span data-ttu-id="9fd39-161">W drzewie wybierz **element główny\dokument**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-161">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="9fd39-162">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9fd39-162">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="9fd39-163">W drzewie zaznacz element **XML\Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-163">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="9fd39-164">W polu **Nazwa** wpisz „id”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-164">In the **Name** field, type 'id'.</span></span>
15.    <span data-ttu-id="9fd39-165">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-165">Click **OK**.</span></span>
16.    <span data-ttu-id="9fd39-166">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="9fd39-167">Umożliwia zaprojektowanie mapowania formatu w celu zapisania przeanalizowanej informacji w modelu danych</span><span class="sxs-lookup"><span data-stu-id="9fd39-167">Design a format mapping to save parsed information to data model</span></span>
1.    <span data-ttu-id="9fd39-168">Kliknij opcję **Mapuj format na model**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-168">Click **Map format to model**.</span></span>
2.    <span data-ttu-id="9fd39-169">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-169">Click **New**.</span></span>
3.    <span data-ttu-id="9fd39-170">W polu **Definicja** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9fd39-170">In the **Definition** field, enter or select a value.</span></span>
4.    <span data-ttu-id="9fd39-171">W polu **Nazwa** wpisz „mapowanie”.</span><span class="sxs-lookup"><span data-stu-id="9fd39-171">In the **Name** field, type 'Mapping'.</span></span>
5.    <span data-ttu-id="9fd39-172">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-172">Click **Save**.</span></span>
6.    <span data-ttu-id="9fd39-173">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-173">Click **Designer**.</span></span>
7.    <span data-ttu-id="9fd39-174">W drzewie rozwiń węzeł **format**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-174">In the tree, expand **format**.</span></span>
8.    <span data-ttu-id="9fd39-175">W drzewie rozwiń **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.    <span data-ttu-id="9fd39-176">W drzewie wybierz \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="9fd39-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9fd39-177">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="9fd39-177">(document)\*\*.</span></span>
10.    <span data-ttu-id="9fd39-178">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-178">Click **Bind**.</span></span>
11.    <span data-ttu-id="9fd39-179">W drzewie rozwiń \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="9fd39-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9fd39-180">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="9fd39-180">(document)\*\*.</span></span>
12.    <span data-ttu-id="9fd39-181">W drzewie wybierz \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="9fd39-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="9fd39-182">(dokument)\identyfikator\*\*.</span><span class="sxs-lookup"><span data-stu-id="9fd39-182">(document)\id\*\*.</span></span>
13.    <span data-ttu-id="9fd39-183">W drzewie rozwiń węzeł **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-183">In the tree, expand **List = format.root.document**.</span></span>
14.    <span data-ttu-id="9fd39-184">W drzewie wybierz **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-184">In the tree, select **List = format.root.document\Code**.</span></span>
15.    <span data-ttu-id="9fd39-185">Kliknij opcję **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-185">Click **Bind**.</span></span>
16.    <span data-ttu-id="9fd39-186">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-186">Click **Save**.</span></span>
17.    <span data-ttu-id="9fd39-187">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9fd39-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="9fd39-188">Uruchom mapowanie formatu</span><span class="sxs-lookup"><span data-stu-id="9fd39-188">Run format mapping</span></span>
1. <span data-ttu-id="9fd39-189">Kliknij przycisk **Uruchom.**</span><span class="sxs-lookup"><span data-stu-id="9fd39-189">Click **Run**.</span></span>
2. <span data-ttu-id="9fd39-190">Kliknij przycisk **Przeglądaj** i wybierz plik **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="9fd39-191">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="9fd39-192">Wybrany plik nie został zaimportowany, ponieważ projekt formatu przyjmuje istnienie atrybutu „ID” dla elementu „Document”, ale importowany plik nie zawiera takiego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9fd39-192">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="9fd39-193">Modyfikowanie struktury formatu w celu obsługi atrybutu XML jako opcjonalnego</span><span class="sxs-lookup"><span data-stu-id="9fd39-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="9fd39-194">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9fd39-194">Close the page.</span></span>
2. <span data-ttu-id="9fd39-195">W drzewie rozwiń **element główny\dokument**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="9fd39-196">W drzewie wybierz **element główny\dokument\id**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="9fd39-197">Wybierz wartość **Tak** w polu **Ciąg pusty dla brakującego atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="9fd39-198">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="9fd39-199">Uruchom mapowanie formatu w celu przetestowania zmian</span><span class="sxs-lookup"><span data-stu-id="9fd39-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="9fd39-200">Kliknij opcję **Mapuj format na model**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="9fd39-201">Kliknij przycisk **Uruchom.**</span><span class="sxs-lookup"><span data-stu-id="9fd39-201">Click **Run**.</span></span>
3. <span data-ttu-id="9fd39-202">Kliknij przycisk **Przeglądaj** i wybierz plik **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="9fd39-203">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd39-203">Click **OK**.</span></span>
5. <span data-ttu-id="9fd39-204">Przejrzyj wygenerowany plik.</span><span class="sxs-lookup"><span data-stu-id="9fd39-204">Review the generated file.</span></span> <span data-ttu-id="9fd39-205">Zauważmy, że ten sam plik został zaimportowany, ponieważ projekt formatu uwzględnia teraz atrybut „id” dla elementu „dokument” jako opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="9fd39-205">Note that same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>
