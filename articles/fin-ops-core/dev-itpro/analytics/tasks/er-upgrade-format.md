---
title: ER Uaktualnianie formatu poprzez przyjęcie jego nowej wersji bazowej
description: W tym temacie opisano sposób obsługi konfiguracji formatu raportowania elektronicznego (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 336551f4e9858269010ec7debd1750a8d8453163
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564249"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="939c1-103">ER Uaktualnianie formatu poprzez przyjęcie jego nowej wersji bazowej</span><span class="sxs-lookup"><span data-stu-id="939c1-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="939c1-104">W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zarządzać konfiguracją formatu raportowania elektronicznego (ER).</span><span class="sxs-lookup"><span data-stu-id="939c1-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="939c1-105">W tej procedurze pokazano sposób tworzenia niestandardowej wersji formatu w oparciu o format otrzymany od dostawcy konfiguracji (CP).</span><span class="sxs-lookup"><span data-stu-id="939c1-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="939c1-106">Ponadto wyjaśniono, jak zastosować nową bazową wersję tego formatu.</span><span class="sxs-lookup"><span data-stu-id="939c1-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="939c1-107">Przed wykonaniem tych kroków należy najpierw wykonać procedury „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego” i „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”.</span><span class="sxs-lookup"><span data-stu-id="939c1-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="939c1-108">Kroki można wykonać na danych firmy GBSI.</span><span class="sxs-lookup"><span data-stu-id="939c1-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="939c1-109">Wybór konfiguracji formatu do dostosowania</span><span class="sxs-lookup"><span data-stu-id="939c1-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="939c1-110">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="939c1-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="939c1-111">W tym przykładzie przykładowa firma Litware, Inc. (https://www.litware.com) będzie pełniła rolę dostawcy konfiguracji, który obsługuje konfiguracje formatów płatności elektronicznych dla określonego kraju.</span><span class="sxs-lookup"><span data-stu-id="939c1-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="939c1-112">Przykładowa firma Proseware, Inc. (http://www.proseware.com) będzie pełniła rolę użytkownika konfiguracji formatu dostarczonej przez firmę Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="939c1-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="939c1-113">Firma Proseware, Inc. będzie używać tych formatów w niektórych regionach tego kraju.</span><span class="sxs-lookup"><span data-stu-id="939c1-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="939c1-114">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="939c1-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="939c1-115">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="939c1-115">Click Show filters.</span></span>
4. <span data-ttu-id="939c1-116">Zastosuj następujące filtry: w polu „Nazwa” wprowadź wartość filtru „BACS (fikcyjny brytyjski)”, używając operatora filtru „zaczyna się od”.</span><span class="sxs-lookup"><span data-stu-id="939c1-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="939c1-117">Wybrana konfiguracja formatu BACS (fikcyjny brytyjski) jest własnością dostawcy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="939c1-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="939c1-118">Kliknij przycisk Pokaż filtry.</span><span class="sxs-lookup"><span data-stu-id="939c1-118">Click Show filters.</span></span>
6. <span data-ttu-id="939c1-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="939c1-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="939c1-120">Wersja formatu o stanie Zakończono będzie używana przez firmę Proseware, Inc. w celu dostosowania.</span><span class="sxs-lookup"><span data-stu-id="939c1-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="939c1-121">Tworzenie nowej konfiguracji niestandardowego formatu dokumentów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="939c1-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="939c1-122">Firma Proseware, Inc. otrzymała wersję 1.1 konfiguracji BACS (fikcyjnej brytyjskiej), która zawiera początkowy format do generowania dokumentów płatności elektronicznych, od firmy Litware, Inc. zgodnie z wykupioną subskrypcją usług.</span><span class="sxs-lookup"><span data-stu-id="939c1-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="939c1-123">Firma Proseware, Inc. chce rozpocząć używanie tego formatu jako standardowego w swoim kraju, ale jest potrzebne pewne dostosowanie w celu obsługi specjalnych wymagań regionalnych.</span><span class="sxs-lookup"><span data-stu-id="939c1-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="939c1-124">Firma Proseware, Inc. chce także zachować możliwość uaktualniania niestandardowego formatu natychmiast, gdy jego nowa wersja (ze zmianami uwzględniającymi nowe wymagania specyficzne dla kraju) zostanie pobrana z firmy Litware, Inc., oraz wykonywać to uaktualnienie jak najtaniej.</span><span class="sxs-lookup"><span data-stu-id="939c1-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="939c1-125">W tym celu firma Proseware, Inc. musi utworzyć konfigurację, używając jako bazy konfiguracji BACS (fikcyjnej brytyjskiej) otrzymanej od firmy Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="939c1-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="939c1-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="939c1-126">Close the page.</span></span>
2. <span data-ttu-id="939c1-127">Wybierz firmę Proseware, Inc., aby ustawić ją jako aktywnego dostawcę.</span><span class="sxs-lookup"><span data-stu-id="939c1-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="939c1-128">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="939c1-128">Click Set active.</span></span>
4. <span data-ttu-id="939c1-129">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="939c1-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="939c1-130">W drzewie rozwiń węzeł „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="939c1-131">W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="939c1-132">Zaznacz konfigurację BACS (fikcyjną brytyjską) firmy Litware, Inc. Firma Proseware, Inc. użyje wersji 1.1 jako bazy dla niestandardowej wersji.</span><span class="sxs-lookup"><span data-stu-id="939c1-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="939c1-133">Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="939c1-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="939c1-134">Pozwoli to utworzyć nową konfigurację dla niestandardowego formatu płatności.</span><span class="sxs-lookup"><span data-stu-id="939c1-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="939c1-135">W polu Nowy wpisz „Pochodzi od nazwy: BACS (fikcyjny brytyjski), Litware, Inc.”.</span><span class="sxs-lookup"><span data-stu-id="939c1-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="939c1-136">Wybierz opcję Utwórz pochodne, aby potwierdzić użycie konfiguracji BACS (fikcyjnej brytyjskiej) jako bazy do utworzenia niestandardowej wersji.</span><span class="sxs-lookup"><span data-stu-id="939c1-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="939c1-137">W polu Nazwa wpisz „BACS (niestandardowy fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="939c1-138">W polu Opis wpisz „Płatność dla dostawcy BACS (niestandardowy fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="939c1-139">Aktywny dostawca konfiguracji (firma Proseware, Inc.) jest automatycznie umieszczany w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="939c1-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="939c1-140">Ten dostawca będzie mógł obsługiwać tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="939c1-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="939c1-141">Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.</span><span class="sxs-lookup"><span data-stu-id="939c1-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="939c1-142">Kliknij przycisk Utwórz konfigurację.</span><span class="sxs-lookup"><span data-stu-id="939c1-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="939c1-143">Dostosowywanie formatu dokumentów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="939c1-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="939c1-144">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="939c1-144">Click Designer.</span></span>
2. <span data-ttu-id="939c1-145">Kliknij przycisk Rozwiń/zwiń.</span><span class="sxs-lookup"><span data-stu-id="939c1-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="939c1-146">Kliknij przycisk Rozwiń/zwiń.</span><span class="sxs-lookup"><span data-stu-id="939c1-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="939c1-147">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.</span><span class="sxs-lookup"><span data-stu-id="939c1-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="939c1-148">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="939c1-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="939c1-149">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="939c1-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="939c1-150">W polu Nazwa wpisz „IBAN”.</span><span class="sxs-lookup"><span data-stu-id="939c1-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="939c1-151">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-151">Click OK.</span></span>
9. <span data-ttu-id="939c1-152">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\IBAN”.</span><span class="sxs-lookup"><span data-stu-id="939c1-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="939c1-153">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="939c1-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="939c1-154">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="939c1-155">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-155">Click OK.</span></span>
13. <span data-ttu-id="939c1-156">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="939c1-157">W polu Długość maksymalna wpisz „60”.</span><span class="sxs-lookup"><span data-stu-id="939c1-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="939c1-158">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="939c1-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="939c1-159">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="939c1-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="939c1-160">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="939c1-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="939c1-161">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="939c1-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="939c1-162">W drzewie rozwiń „model\Płatności\Konto wierzyciela".</span><span class="sxs-lookup"><span data-stu-id="939c1-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="939c1-163">W drzewie zaznacz element „model\Płatności\Wierzyciel\Konto\IBAN”.</span><span class="sxs-lookup"><span data-stu-id="939c1-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="939c1-164">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar = model.Płatności\Dostawca\Bank\IBAN\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="939c1-165">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="939c1-165">Click Bind.</span></span>
23. <span data-ttu-id="939c1-166">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="939c1-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="939c1-167">Sprawdzanie poprawności formatu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="939c1-167">Validate the customized format</span></span>
1. <span data-ttu-id="939c1-168">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="939c1-168">Click Validate.</span></span>

    <span data-ttu-id="939c1-169">Sprawdź poprawność modyfikacji układu i mapowań danych dostosowanego formatu niestandardowego, aby się upewnić, że wszystkie powiązania działają poprawnie.</span><span class="sxs-lookup"><span data-stu-id="939c1-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="939c1-170">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="939c1-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="939c1-171">Zmiana stanu bieżącej wersji niestandardowej konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="939c1-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="939c1-172">Zmień stan żądanej konfiguracji formatu z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby generowania dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="939c1-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="939c1-173">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="939c1-173">Click Change status.</span></span>

    <span data-ttu-id="939c1-174">Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="939c1-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="939c1-175">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="939c1-175">Click Complete.</span></span>
3. <span data-ttu-id="939c1-176">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="939c1-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="939c1-177">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-177">Click OK.</span></span>
5. <span data-ttu-id="939c1-178">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="939c1-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="939c1-179">Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="939c1-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="939c1-180">Oznacza to, że jest to wersja 1 niestandardowego formatu BACS (niestandardowego fikcyjnego brytyjskiego), która bazuje na wersji 1 formatu BACS (fikcyjnego brytyjskiego), który z kolei jest oparty na wersji 1 modelu danych Płatności (modelu uproszczonego).</span><span class="sxs-lookup"><span data-stu-id="939c1-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="939c1-181">Testowanie niestandardowego formatu generowania plików płatności</span><span class="sxs-lookup"><span data-stu-id="939c1-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="939c1-182">W równoległej sesji Finance and Operations wykonaj procedurę „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”.</span><span class="sxs-lookup"><span data-stu-id="939c1-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="939c1-183">W parametrach metody płatności elektronicznych wybierz format BACS (niestandardowy fikcyjny brytyjski).</span><span class="sxs-lookup"><span data-stu-id="939c1-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="939c1-184">Upewnij się, że utworzony plik płatności zawiera ostatnio wprowadzony węzeł XML przedstawiający kod IBAN zgodnie wymogami regionalnymi.</span><span class="sxs-lookup"><span data-stu-id="939c1-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="939c1-185">Aktualizowanie istniejącej konfiguracji specyficznej dla kraju</span><span class="sxs-lookup"><span data-stu-id="939c1-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="939c1-186">Firma Litware, Inc. musi zaktualizować konfigurację BACS (niestandardową fikcyjną brytyjską) i dostosować ją do nowych wymagań krajowych dotyczących zarządzania formatem dokumentów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="939c1-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="939c1-187">Później zmiany te zostaną zawarte w nowej wersji tej konfiguracji, który będzie oferowana subskrybentom usług, w tym firmie Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="939c1-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="939c1-188">W faktycznych procesach związanych ze świadczeniem usług każda nowa wersja konfiguracji BACS (fikcyjnej, brytyjskiej) może być importowana przez firmę Proseware, Inc. z repozytorium konfiguracji firmy Litware, Inc. w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="939c1-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="939c1-189">W tej procedurze zasymulujemy to poprzez aktualizację konfiguracji BACS (fikcyjnej brytyjskiej) w imieniu usługodawcy.</span><span class="sxs-lookup"><span data-stu-id="939c1-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="939c1-190">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="939c1-190">Close the page.</span></span>
2. <span data-ttu-id="939c1-191">Zaznacz dostawcę Litware, Inc.  </span><span class="sxs-lookup"><span data-stu-id="939c1-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="939c1-192">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="939c1-192">Click Set active.</span></span>
4. <span data-ttu-id="939c1-193">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="939c1-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="939c1-194">W drzewie rozwiń węzeł „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="939c1-195">W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="939c1-196">Wersja robocza konfiguracji BACS (fikcyjnej brytyjskiej) należąca do dostawcy Litware, Inc. została wybrana, aby wprowadzić zmiany uwzględniające nowe wymagania specyficzne dla kraju.</span><span class="sxs-lookup"><span data-stu-id="939c1-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="939c1-197">Lokalizowanie bazowego formatu dokumentów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="939c1-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="939c1-198">Załóżmy, że istnieją nowe wymagania specyficzne dla kraju, których obsługę musi zapewnić firma Litware, Inc.:</span><span class="sxs-lookup"><span data-stu-id="939c1-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="939c1-199">Wypełnienie kodu SWIFT banku wierzyciela w każdej transakcji płatności.</span><span class="sxs-lookup"><span data-stu-id="939c1-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="939c1-200">Limit 100 znaków długości tekstu nazwy dostawcy w generowanym pliku.</span><span class="sxs-lookup"><span data-stu-id="939c1-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="939c1-201">Nowe wymagania specyficzne dla kraju</span><span class="sxs-lookup"><span data-stu-id="939c1-201">New country-specific requirements</span></span>  
- <span data-ttu-id="939c1-202">Zaznacz wersję roboczą żądanej konfiguracji, aby wprowadzić w niej wymagane zmiany.</span><span class="sxs-lookup"><span data-stu-id="939c1-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="939c1-203">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="939c1-203">Click Designer.</span></span>
2. <span data-ttu-id="939c1-204">Kliknij przycisk Rozwiń/zwiń.</span><span class="sxs-lookup"><span data-stu-id="939c1-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="939c1-205">Kliknij przycisk Rozwiń/zwiń.</span><span class="sxs-lookup"><span data-stu-id="939c1-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="939c1-206">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.</span><span class="sxs-lookup"><span data-stu-id="939c1-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="939c1-207">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="939c1-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="939c1-208">W drzewie zaznacz element „XML\Element”.</span><span class="sxs-lookup"><span data-stu-id="939c1-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="939c1-209">W polu Nazwa wpisz „SWIFT”.</span><span class="sxs-lookup"><span data-stu-id="939c1-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="939c1-210">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-210">Click OK.</span></span>
9. <span data-ttu-id="939c1-211">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\SWIFT”.</span><span class="sxs-lookup"><span data-stu-id="939c1-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="939c1-212">Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="939c1-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="939c1-213">W drzewie zaznacz element „Tekst\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="939c1-214">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-214">Click OK.</span></span>
13. <span data-ttu-id="939c1-215">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="939c1-216">W polu Długość maksymalna wpisz „100”.</span><span class="sxs-lookup"><span data-stu-id="939c1-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="939c1-217">Kliknij kartę Mapowanie.</span><span class="sxs-lookup"><span data-stu-id="939c1-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="939c1-218">W drzewie rozwiń model„”</span><span class="sxs-lookup"><span data-stu-id="939c1-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="939c1-219">W drzewie rozwiń węzeł „model\Płatności”.</span><span class="sxs-lookup"><span data-stu-id="939c1-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="939c1-220">W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.</span><span class="sxs-lookup"><span data-stu-id="939c1-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="939c1-221">W drzewie rozwiń „model\Płatności\Wierzyciel\Agent".</span><span class="sxs-lookup"><span data-stu-id="939c1-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="939c1-222">W drzewie zaznacz element „model\Płatności\Wierzyciel\Agent\SWIFT”.</span><span class="sxs-lookup"><span data-stu-id="939c1-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="939c1-223">W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar = model.Płatności\Dostawca\Bank\SWIFT\Ciąg”.</span><span class="sxs-lookup"><span data-stu-id="939c1-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="939c1-224">Kliknij opcję Powiąż.</span><span class="sxs-lookup"><span data-stu-id="939c1-224">Click Bind.</span></span>
23. <span data-ttu-id="939c1-225">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="939c1-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="939c1-226">Sprawdzanie poprawności zlokalizowanego formatu</span><span class="sxs-lookup"><span data-stu-id="939c1-226">Validate the localized format</span></span>
1. <span data-ttu-id="939c1-227">Kliknij przycisk Sprawdź poprawność.</span><span class="sxs-lookup"><span data-stu-id="939c1-227">Click Validate.</span></span>
2. <span data-ttu-id="939c1-228">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="939c1-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="939c1-229">Zmiana stanu bieżącej wersji konfiguracji formatu bazowego</span><span class="sxs-lookup"><span data-stu-id="939c1-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="939c1-230">Zmień stan zaktualizowanej konfiguracji formatu bazowego z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby generowania dokumentów płatności oraz aktualizowania opartych na niej konfiguracji formatów.</span><span class="sxs-lookup"><span data-stu-id="939c1-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="939c1-231">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="939c1-231">Click Change status.</span></span>

    <span data-ttu-id="939c1-232">Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="939c1-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="939c1-233">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="939c1-233">Click Complete.</span></span>
3. <span data-ttu-id="939c1-234">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="939c1-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="939c1-235">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-235">Click OK.</span></span>
5. <span data-ttu-id="939c1-236">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="939c1-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="939c1-237">Zmiana bazowej wersji niestandardowej konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="939c1-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="939c1-238">Firma Proseware, Inc. została poinformowana, że nowa wersja 1.2 konfiguracji BACS (fikcyjnej brytyjskiej) jest dostępna na potrzeby generowania elektronicznych dokumentów płatności zgodnie z niedawno ogłoszonymi wymaganiami specyficznymi dla kraju.</span><span class="sxs-lookup"><span data-stu-id="939c1-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="939c1-239">Firma Proseware, Inc. chce zacząć używać tego formatu jako standardowego dla kraju.</span><span class="sxs-lookup"><span data-stu-id="939c1-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="939c1-240">W tym celu firma Proseware, Inc. musi zmienić wersję konfiguracji stanowiącą bazę dla niestandardowej konfiguracji BACS (niestandardowej fikcyjnej brytyjskiej).</span><span class="sxs-lookup"><span data-stu-id="939c1-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="939c1-241">Zamiast wersji 1.1 konfiguracji BACS (fikcyjnej brytyjskiej) należy używać nowej wersji 1.2.</span><span class="sxs-lookup"><span data-stu-id="939c1-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="939c1-242">Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.</span><span class="sxs-lookup"><span data-stu-id="939c1-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="939c1-243">Wybierz dostawcę Proseware, Inc., aby oznaczyć go jako aktywnego.</span><span class="sxs-lookup"><span data-stu-id="939c1-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="939c1-244">Kliknij opcję Ustaw jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="939c1-244">Click Set active.</span></span>
4. <span data-ttu-id="939c1-245">Kliknij opcję Konfiguracje raportowania.</span><span class="sxs-lookup"><span data-stu-id="939c1-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="939c1-246">W drzewie rozwiń węzeł „Płatności (model uproszczony)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="939c1-247">W drzewie rozwiń węzeł „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="939c1-248">W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)\BACS (niestandardowy fikcyjny brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="939c1-249">Zaznacz konfigurację BACS (niestandardową fikcyjną brytyjską), która jest własnością firmy Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="939c1-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="939c1-250">Użyj wersji roboczej wybranej konfiguracji, aby wprowadzić wymagane zmiany.</span><span class="sxs-lookup"><span data-stu-id="939c1-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="939c1-251">Kliknij opcję Zmień bazę.</span><span class="sxs-lookup"><span data-stu-id="939c1-251">Click Rebase.</span></span>

    <span data-ttu-id="939c1-252">Zaznacz nową wersję 1.2 konfiguracji bazowej, aby zastosować ją jako nową podstawę do aktualizowania konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="939c1-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="939c1-253">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-253">Click OK.</span></span>

    <span data-ttu-id="939c1-254">Należy zauważyć, że wykryto pewne konflikty między scaleniem niestandardowej wersji a nową wersją bazową. Konflikty te reprezentują niektóre zmiany formatu, których nie można scalić automatycznie.</span><span class="sxs-lookup"><span data-stu-id="939c1-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="939c1-255">Rozwiązywanie konfliktów związanych ze zmianą bazy</span><span class="sxs-lookup"><span data-stu-id="939c1-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="939c1-256">Kliknij przycisk Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="939c1-256">Click Designer.</span></span>
    
    <span data-ttu-id="939c1-257">Należy zauważyć, że zmiana limitu długości tekstu nazwy dostawcy nie została rozwiązana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="939c1-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="939c1-258">W związku z tym znajduje się na liście konfliktów.</span><span class="sxs-lookup"><span data-stu-id="939c1-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="939c1-259">Dla każdego konfliktu o typie Aktualizacja są dostępne następujące opcje: - Zastosowanie poprzedniej wartości bazowej (przycisk na siatce), aby umieścić wartość z poprzedniej wersji bazowej (0 w naszym przypadku).</span><span class="sxs-lookup"><span data-stu-id="939c1-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="939c1-260">- Zastosowanie wartości bazowej (przycisk u góry siatki) w celu umieszczenia wartości nowej wersji bazowej (100 w naszym przypadku).</span><span class="sxs-lookup"><span data-stu-id="939c1-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="939c1-261">- Zachowanie własnej (niestandardowej) wartości (60 w naszym przypadku).</span><span class="sxs-lookup"><span data-stu-id="939c1-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="939c1-262">Kliknij przycisk Zastosuj wartość podstawową, aby stosować limit 100 znaków w długości nazwy dostawcy.</span><span class="sxs-lookup"><span data-stu-id="939c1-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="939c1-263">Należy zwrócić uwagę, że firmy Proseware, Inc. i Litware, Inc. mają niestandardowe i lokalne wersje tego formatu wykorzystujące kody IBAN i SWIFT z powiązanymi składnikami, które są automatycznie scalane w formacie zarządzania.</span><span class="sxs-lookup"><span data-stu-id="939c1-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="939c1-264">Kliknij opcję Zastosuj wartość podstawową.</span><span class="sxs-lookup"><span data-stu-id="939c1-264">Click Apply base value.</span></span>

    <span data-ttu-id="939c1-265">Kliknij przycisk Zastosuj wartość podstawową, aby stosować limit 100 znaków specyficzny dla kraju do nazw dostawców.</span><span class="sxs-lookup"><span data-stu-id="939c1-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="939c1-266">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="939c1-266">Click Save.</span></span>

    <span data-ttu-id="939c1-267">Zapisanie formatu spowoduje usunięcie rozwiązanych konfliktów z listy konfliktów.</span><span class="sxs-lookup"><span data-stu-id="939c1-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="939c1-268">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="939c1-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="939c1-269">Zmiana stanu nowej wersji niestandardowej konfiguracji formatu</span><span class="sxs-lookup"><span data-stu-id="939c1-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="939c1-270">Kliknij przycisk Zmień stan.</span><span class="sxs-lookup"><span data-stu-id="939c1-270">Click Change status.</span></span>

    <span data-ttu-id="939c1-271">Zmień stan zaktualizowanej niestandardowej konfiguracji formatu z Wersja robocza na Zakończono.</span><span class="sxs-lookup"><span data-stu-id="939c1-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="939c1-272">Spowoduje to udostępnienie konfiguracji formatu do generowania dokumentów płatności.</span><span class="sxs-lookup"><span data-stu-id="939c1-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="939c1-273">Należy zauważyć, że bieżąca wersja wybranej konfiguracji ma stan Wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="939c1-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="939c1-274">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="939c1-274">Click Complete.</span></span>
3. <span data-ttu-id="939c1-275">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="939c1-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="939c1-276">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="939c1-276">Click OK.</span></span>

    <span data-ttu-id="939c1-277">Należy zauważyć, że utworzona konfiguracji została zapisana jako ukończona wersja 1.2.2: wersja 2 bazowego formatu BACS (niestandardowego fikcyjnego brytyjskiego), która bazuje na wersji 2 formatu BACS (fikcyjnego brytyjskiego), który z kolei jest oparty na wersji 1 modelu danych Płatności (modelu uproszczonego).</span><span class="sxs-lookup"><span data-stu-id="939c1-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="939c1-278">Testowanie niestandardowego formatu generowania plików płatności</span><span class="sxs-lookup"><span data-stu-id="939c1-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="939c1-279">W równoległej sesji Finance and Operations wykonaj procedurę „Używanie utworzonego formatu do generowania elektronicznych dokumentów płatności”.</span><span class="sxs-lookup"><span data-stu-id="939c1-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="939c1-280">W parametrach metody płatności elektronicznych wybierz utworzony format „BACS (niestandardowy, fikcyjny, brytyjski)”.</span><span class="sxs-lookup"><span data-stu-id="939c1-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="939c1-281">Upewnij się, że utworzony plik płatności zawiera ostatnio wprowadzony przez firmę Proseware, Inc. węzeł XML przedstawiający kod konta IBAN zgodnie wymogami regionalnymi.</span><span class="sxs-lookup"><span data-stu-id="939c1-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="939c1-282">Plik powinien również zawierać ostatnio wprowadzony przez firmę Litware, Inc. węzeł XML przedstawiający kod banku SWIFT zgodnie wymogami krajowymi.</span><span class="sxs-lookup"><span data-stu-id="939c1-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]