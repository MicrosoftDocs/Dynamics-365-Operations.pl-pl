---
title: (RCS) Importowanie plików w formacie XML z opcjonalnymi atrybutami
description: Ten temat zawiera informacje o sposobach projektowania konfiguracji formatu ER w celu importowania plików w formacie XML zawierających atrybuty opcjonalne.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1290598d8dbd5b72d679ccf3e642e75b6dc3215
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182193"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="68aee-103">(RCS) Importowanie plików w formacie XML z opcjonalnymi atrybutami</span><span class="sxs-lookup"><span data-stu-id="68aee-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68aee-104">W poniższych krokach wyjaśniono, jak użytkownik w roli administratora systemu lub programisty raportowania elektronicznego może zaprojektować konfigurację formatu ER do importowania plików w formacie XML zawierającym atrybuty opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="68aee-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="68aee-105">Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.</span><span class="sxs-lookup"><span data-stu-id="68aee-105">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="68aee-106">Przed rozpoczęciem należy pobrać i zapisać lokalnie plik IncomingDocumentToLearnHowToHandleOptionalAttributes. XML z [centrum pobierania Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="68aee-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.  <span data-ttu-id="68aee-107">Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**.</span><span class="sxs-lookup"><span data-stu-id="68aee-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.  <span data-ttu-id="68aee-108">Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny**</span><span class="sxs-lookup"><span data-stu-id="68aee-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="68aee-109">Jeśli nie widzisz dostawcy konfiguracji, musisz wykonać kroki w procedurze, [Utwórz dostawcę konfiguracji i oznacz go jako aktywnego](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="68aee-109">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.  <span data-ttu-id="68aee-110">Kliknij opcję **Konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="68aee-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="68aee-111">Tworzenie nowej konfiguracji modelu danych</span><span class="sxs-lookup"><span data-stu-id="68aee-111">Create a new data model configuration</span></span>
1.  <span data-ttu-id="68aee-112">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-112">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="68aee-113">W polu **Nazwa** wpisz „Model do importu pliku XML”.</span><span class="sxs-lookup"><span data-stu-id="68aee-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.  <span data-ttu-id="68aee-114">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="68aee-114">Click **Create configuration**.</span></span>
4.  <span data-ttu-id="68aee-115">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="68aee-115">Click **Designer**.</span></span>
5.  <span data-ttu-id="68aee-116">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-116">Click **New** to open the drop dialog.</span></span>
6.  <span data-ttu-id="68aee-117">W polu **Nazwa** wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="68aee-117">In the **Name** field, type 'Root'.</span></span>
7.  <span data-ttu-id="68aee-118">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="68aee-118">Click **Add**.</span></span>
8.  <span data-ttu-id="68aee-119">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-119">Click **New** to open the drop dialog.</span></span>
9.  <span data-ttu-id="68aee-120">W polu **Nazwa** wpisz „Lista”.</span><span class="sxs-lookup"><span data-stu-id="68aee-120">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="68aee-121">W polu **Kod przedmiotu** wybierz **Lista tabel**.</span><span class="sxs-lookup"><span data-stu-id="68aee-121">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="68aee-122">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="68aee-122">Click **Add**.</span></span>
12. <span data-ttu-id="68aee-123">Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-123">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="68aee-124">W polu **Nazwa** wpisz „Kod”.</span><span class="sxs-lookup"><span data-stu-id="68aee-124">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="68aee-125">W polu **Typ przedmiotu** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="68aee-125">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="68aee-126">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="68aee-126">Click **Add**.</span></span>
16. <span data-ttu-id="68aee-127">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68aee-127">Click **Save**.</span></span>
17. <span data-ttu-id="68aee-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="68aee-128">Close the page.</span></span>
18. <span data-ttu-id="68aee-129">Kliknij przycisk **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="68aee-129">Click **Change status**.</span></span>
19. <span data-ttu-id="68aee-130">Kliknij przycisk **Wykonaj.**</span><span class="sxs-lookup"><span data-stu-id="68aee-130">Click **Complete**.</span></span>
20. <span data-ttu-id="68aee-131">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="68aee-132">Tworzenie formatu importu danych</span><span class="sxs-lookup"><span data-stu-id="68aee-132">Create a format for data import</span></span>
1.  <span data-ttu-id="68aee-133">Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-133">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="68aee-134">W polu **Nowy** wpisz „Format oparty na modelu danych Model do importowania pliku xml”.</span><span class="sxs-lookup"><span data-stu-id="68aee-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.  <span data-ttu-id="68aee-135">W polu **nazwa** wpisz „format do importu pliku XML”.</span><span class="sxs-lookup"><span data-stu-id="68aee-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.  <span data-ttu-id="68aee-136">Wybierz opcję **Tak** w polu **Obsługuje import danych**.</span><span class="sxs-lookup"><span data-stu-id="68aee-136">Select **Yes** in the **Supports data import** field.</span></span>
5.  <span data-ttu-id="68aee-137">Kliknij przycisk **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="68aee-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="68aee-138">Umożliwia zaprojektowanie formatu w celu przeanalizowania pliku przychodzącego w formacie XML</span><span class="sxs-lookup"><span data-stu-id="68aee-138">Design a format to parse incoming file in xml format</span></span>
1.  <span data-ttu-id="68aee-139">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="68aee-139">Click **Designer**.</span></span>
2.  <span data-ttu-id="68aee-140">Kliknij przycisk **Dodaj element główny**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-140">Click **Add root** to open the drop dialog.</span></span>
3.  <span data-ttu-id="68aee-141">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="68aee-141">In the tree, select **XML\Element**.</span></span>
4.  <span data-ttu-id="68aee-142">W polu **Nazwa** wpisz „Element główny”.</span><span class="sxs-lookup"><span data-stu-id="68aee-142">In the **Name** field, type 'root'.</span></span>
5.  <span data-ttu-id="68aee-143">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-143">Click **OK**.</span></span>
6.  <span data-ttu-id="68aee-144">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-144">Click **Add** to open the drop dialog.</span></span>
7.  <span data-ttu-id="68aee-145">W drzewie zaznacz element **XML\Element**.</span><span class="sxs-lookup"><span data-stu-id="68aee-145">In the tree, select **XML\Element**.</span></span>
8.  <span data-ttu-id="68aee-146">W polu **Nazwa** wpisz „dokument”.</span><span class="sxs-lookup"><span data-stu-id="68aee-146">In the **Name** field, type 'document'.</span></span>
9.  <span data-ttu-id="68aee-147">W polu **Wielość** wybierz opcję **Jeden wiele**.</span><span class="sxs-lookup"><span data-stu-id="68aee-147">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="68aee-148">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-148">Click **OK**.</span></span>
11. <span data-ttu-id="68aee-149">W drzewie wybierz **element główny\dokument**.</span><span class="sxs-lookup"><span data-stu-id="68aee-149">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="68aee-150">Kliknij przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="68aee-150">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="68aee-151">W drzewie zaznacz element **XML\Atrybut**.</span><span class="sxs-lookup"><span data-stu-id="68aee-151">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="68aee-152">W polu **Nazwa** wpisz „Identyfikator”.</span><span class="sxs-lookup"><span data-stu-id="68aee-152">In the **Name** field, type 'ID'.</span></span>
15. <span data-ttu-id="68aee-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-153">Click **OK**.</span></span>
16. <span data-ttu-id="68aee-154">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68aee-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="68aee-155">Umożliwia zaprojektowanie mapowania formatu w celu zapisania przeanalizowanej informacji w modelu danych</span><span class="sxs-lookup"><span data-stu-id="68aee-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="68aee-156">Kliknij opcję **Mapuj format na model**.</span><span class="sxs-lookup"><span data-stu-id="68aee-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="68aee-157">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="68aee-157">Click **New**.</span></span>
3. <span data-ttu-id="68aee-158">W polu **Definicja** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="68aee-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="68aee-159">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="68aee-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="68aee-160">W polu **Nazwa** wpisz „mapowanie”.</span><span class="sxs-lookup"><span data-stu-id="68aee-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="68aee-161">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68aee-161">Click **Save**.</span></span>
7. <span data-ttu-id="68aee-162">Kliknij przycisk **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="68aee-162">Click **Designer**.</span></span>
8. <span data-ttu-id="68aee-163">W drzewie rozwiń węzeł **format**.</span><span class="sxs-lookup"><span data-stu-id="68aee-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="68aee-164">W drzewie rozwiń **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="68aee-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10. <span data-ttu-id="68aee-165">W drzewie wybierz \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="68aee-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="68aee-166">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="68aee-166">(document)\*\*.</span></span>
11. <span data-ttu-id="68aee-167">Kliknij **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="68aee-167">Click **Bind**.</span></span>
12. <span data-ttu-id="68aee-168">W drzewie rozwiń \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="68aee-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="68aee-169">(dokument)\*\*.</span><span class="sxs-lookup"><span data-stu-id="68aee-169">(document)\*\*.</span></span>
13. <span data-ttu-id="68aee-170">W drzewie wybierz \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="68aee-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="68aee-171">(dokument)\identyfikator\*\*.</span><span class="sxs-lookup"><span data-stu-id="68aee-171">(document)\id\*\*.</span></span>
14. <span data-ttu-id="68aee-172">W drzewie rozwiń węzeł **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="68aee-172">In the tree, expand **List = format.root.document**.</span></span>
15. <span data-ttu-id="68aee-173">W drzewie wybierz **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="68aee-173">In the tree, select **List = format.root.document\Code**.</span></span>
16. <span data-ttu-id="68aee-174">Kliknij opcję **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="68aee-174">Click **Bind**.</span></span>
17. <span data-ttu-id="68aee-175">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68aee-175">Click **Save**.</span></span>
18. <span data-ttu-id="68aee-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="68aee-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="68aee-177">Uruchom Mapowanie formatu</span><span class="sxs-lookup"><span data-stu-id="68aee-177">Run format mapping</span></span>
1. <span data-ttu-id="68aee-178">Kliknij przycisk **Uruchom.**</span><span class="sxs-lookup"><span data-stu-id="68aee-178">Click **Run**.</span></span>
2. <span data-ttu-id="68aee-179">Kliknij przycisk **Przeglądaj** i wybierz **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="68aee-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="68aee-180">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="68aee-181">Wybrany plik nie został zaimportowany, ponieważ projekt formatu przyjmuje istnienie atrybutu „ID” dla elementu „Document”, ale importowany plik nie zawiera takiego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="68aee-181">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="68aee-182">Modyfikowanie struktury formatu w celu obsługi atrybutu XML jako opcjonalnego</span><span class="sxs-lookup"><span data-stu-id="68aee-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="68aee-183">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="68aee-183">Close the page.</span></span>
2. <span data-ttu-id="68aee-184">W drzewie rozwiń **element główny\dokument**.</span><span class="sxs-lookup"><span data-stu-id="68aee-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="68aee-185">W drzewie wybierz **element główny\dokument\id**.</span><span class="sxs-lookup"><span data-stu-id="68aee-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="68aee-186">Wybierz wartość **Tak** w polu **Ciąg pusty dla brakującego atrybutu**.</span><span class="sxs-lookup"><span data-stu-id="68aee-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="68aee-187">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68aee-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="68aee-188">Uruchom mapowanie formatu w celu przetestowania zmian</span><span class="sxs-lookup"><span data-stu-id="68aee-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="68aee-189">Kliknij opcję **Mapuj format na model**.</span><span class="sxs-lookup"><span data-stu-id="68aee-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="68aee-190">Kliknij przycisk **Uruchom.**</span><span class="sxs-lookup"><span data-stu-id="68aee-190">Click **Run**.</span></span>
3. <span data-ttu-id="68aee-191">Kliknij przycisk **Przeglądaj** i wybierz plik **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="68aee-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="68aee-192">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="68aee-192">Click **OK**.</span></span>
5. <span data-ttu-id="68aee-193">Przejrzyj wygenerowany plik.</span><span class="sxs-lookup"><span data-stu-id="68aee-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="68aee-194">Ten sam plik został zaimportowany jako projekt formatu; traktuj atrybut „Identyfikator” dla elementu „Dokument” jako opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="68aee-194">The same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
