---
title: Dostosowanie formatu ER w celu wygenerowania niestandardowego dokumentu elektronicznego
description: W tym temacie opisano sposób korygowania formatu modułu raportowanie elektronicznego (ER) dostarczonego przez Microsoft, aby wygenerować niestandardowy dokument elektroniczny.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67763b29744c4262249ef1ec04e7df490b31fe5b
ms.sourcegitcommit: 1e6a7b50596eaf9d965e0155f3f2c50f7f50747e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2020
ms.locfileid: "3498111"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="9b7ea-103">Dostosowanie formatu ER w celu wygenerowania niestandardowego dokumentu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="9b7ea-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9b7ea-104">W procedurach opisanych w tym temacie opisano, jak użytkownik o roli Administratora systemu lub konsultanta funkcjonalnego dla funkcji raportowania elektronicznego może wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="9b7ea-105">Konfigurowanie parametrów modułu [Raportowanie elektroniczne (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="9b7ea-106">Importowanie konfiguracji systemu, które są dostarczane przez Microsoft i używane do generowania pliku płatności podczas przetwarzania [płatności dostawcy](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="9b7ea-107">Utwórz niestandardową wersję standardowej konfiguracji formatu modułu ER, która jest oferowana przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="9b7ea-108">Zmodyfikuj konfigurację formatu niestandardowego, tak aby generowała pliki płatności spełniające wymagania określonego banku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="9b7ea-109">Zastosuj zmiany wprowadzone w standardowej konfiguracji formatu modułu ER w konfiguracji niestandardowego formatu.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="9b7ea-110">Wszystkie poniższe procedury można wykonać dla firmy **GBSI**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="9b7ea-111">Nie są wymagane umiejętności kodowania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-111">No coding is required.</span></span>

- [<span data-ttu-id="9b7ea-112">Konfigurowanie struktury ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="9b7ea-113">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="9b7ea-114">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="9b7ea-115">Przejrzenie listy dostawców konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="9b7ea-116">Dodawanie nowego dostawcy formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="9b7ea-117">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="9b7ea-118">Importowanie standardowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="9b7ea-119">Importowanie standardowych konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="9b7ea-120">Przeglądanie zaimportowanych konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="9b7ea-121">Przygotowywanie płatności dostawcy na potrzeby przetwarzania</span><span class="sxs-lookup"><span data-stu-id="9b7ea-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="9b7ea-122">Dodawanie informacji bankowych dla konta dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="9b7ea-123">Podawanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="9b7ea-124">Przetwarzanie płatności dostawcy przy użyciu standardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="9b7ea-125">Konfigurowanie elektronicznej metody płatności</span><span class="sxs-lookup"><span data-stu-id="9b7ea-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="9b7ea-126">Przetwarzanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="9b7ea-127">Dostosowywanie standardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="9b7ea-128">Tworzenie niestandardowego formatu</span><span class="sxs-lookup"><span data-stu-id="9b7ea-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="9b7ea-129">Edytowanie niestandardowego formatu</span><span class="sxs-lookup"><span data-stu-id="9b7ea-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="9b7ea-130">Oznaczanie formatu niestandardowego jako wykonywalnego</span><span class="sxs-lookup"><span data-stu-id="9b7ea-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="9b7ea-131">Przetwarzanie płatności dostawcy przy użyciu niestandardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="9b7ea-132">Konfigurowanie elektronicznej metody płatności</span><span class="sxs-lookup"><span data-stu-id="9b7ea-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="9b7ea-133">Przetwarzanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="9b7ea-134">Importowanie nowych wersji standardowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="9b7ea-135">Importowanie nowych wersji standardowej konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="9b7ea-136">Przeglądanie zaimportowanych konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="9b7ea-137">Zaadaptowanie zmian z nowej wersji importowanego formatu w formacie niestandardowym</span><span class="sxs-lookup"><span data-stu-id="9b7ea-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="9b7ea-138">Zakończenie obecnej wersji roboczej formatu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="9b7ea-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="9b7ea-139">Zmiana formatu niestandardowego do nowej wersji bazowej</span><span class="sxs-lookup"><span data-stu-id="9b7ea-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="9b7ea-140">Przetwarzanie płatności dostawcy przy użyciu zmienionego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="9b7ea-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9b7ea-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="9b7ea-142">Konfigurowanie struktury ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-142">Configure the ER framework</span></span>

<span data-ttu-id="9b7ea-143">Użytkownik należący w roli konsultanta funkcjonalnego do raportowania elektronicznego musi skonfigurować minimalny zestaw parametrów ER, aby można było rozpocząć korzystanie z struktury ER w celu zaprojektowania niestandardowej wersji standardowego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="9b7ea-144">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-144">Configure ER parameters</span></span>

1. <span data-ttu-id="9b7ea-145">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-146">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="9b7ea-147">Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="9b7ea-148">Na karcie **Załączniki** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="9b7ea-149">W polu **Konfiguracje** wybierz typ **Plik** dla firmy **USMF**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="9b7ea-150">W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy wybrać typ **Plik**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="9b7ea-151">Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="9b7ea-152">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="9b7ea-153">Każda dodana konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="9b7ea-154">W tym celu jest używany dostawca konfiguracji ER, który został aktywowany w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="9b7ea-155">Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="9b7ea-156">Tylko właściciel konfiguracji ER może ją edytować.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="9b7ea-157">Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="9b7ea-158">Przejrzenie listy dostawców konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="9b7ea-159">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-160">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="9b7ea-161">Na stronie **Tabela dostawcy konfiguracji** każdy rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="9b7ea-162">Przejrzyj zawartość tej strony.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-162">Review the contents of this page.</span></span> <span data-ttu-id="9b7ea-163">Jeśli rekord dla **Litware, Inc.** (`https://www.litware.com`) już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="9b7ea-164">Dodawanie nowego dostawcy formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="9b7ea-165">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-166">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="9b7ea-167">Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="9b7ea-168">W polu **Nazwa** wpisz **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="9b7ea-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="9b7ea-169">W polu **Adres internetowy** wprowadź `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="9b7ea-170">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="9b7ea-171">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="9b7ea-172">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-173">Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="9b7ea-174">Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="9b7ea-175">Importowanie standardowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="9b7ea-176">Importowanie standardowych konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-176">Import the standard ER configurations</span></span>

<span data-ttu-id="9b7ea-177">Aby dodać standardowe konfiguracje obiektu ER do bieżącego wystąpienia rozwiązania Microsoft Dynamics 365 Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="9b7ea-178">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-179">Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="9b7ea-180">Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="9b7ea-181">Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="9b7ea-182">Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **BACS (brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="9b7ea-183">Na skróconej karcie **Wersje** wybierz wersję **1.1** wybranej konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="9b7ea-184">Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Strona Repozytorium konfiguracji](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="9b7ea-186">Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje](download-electronic-reporting-configuration-lcs.md) z Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="9b7ea-187">Przeglądanie zaimportowanych konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="9b7ea-188">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-189">WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="9b7ea-190">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="9b7ea-191">Należy zauważyć, że oprócz wybranego formatu ER **BACS (brytyjski)** zostały zaimportowane inne wymagane konfiguracje obiektów konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="9b7ea-192">Upewnij się, że w drzewie konfiguracji są dostępne następujące konfiguracje modułu ER:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="9b7ea-193">**Model płatności** – Ta konfiguracja zawiera składnik ER [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components), który reprezentuje strukturę danych domeny biznesowej płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="9b7ea-194">**Mapowanie modelu płatności 1611** – Ta konfiguracja zawiera [składnik mapowanie modelu](general-electronic-reporting.md#data-model-and-model-mapping-components), który opisuje sposób wypełniania modelu danych przy użyciu danych aplikacji w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="9b7ea-195">**BACS (brytyjski)** – Ta konfiguracja zawiera [format](general-electronic-reporting.md#FormatComponentOutbound) i mapowanie formatów składników ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="9b7ea-196">Składnik formatu określa układ raportu.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-196">The format component specifies the report layout.</span></span> <span data-ttu-id="9b7ea-197">Składnik mapowanie formatu zawiera źródło danych modelu i określa sposób wypełniania układu raportu przy użyciu tego źródła danych w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Strona Konfiguracje](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="9b7ea-199">Przygotowywanie płatności dostawcy na potrzeby przetwarzania</span><span class="sxs-lookup"><span data-stu-id="9b7ea-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="9b7ea-200">Dodawanie informacji bankowych dla konta dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="9b7ea-201">Należy dodać informacje dotyczące banku dla konta dostawcy, które będzie odwoływać się później w zarejestrowanej płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="9b7ea-202">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="9b7ea-203">Na stronie **Wszyscy dostawcy** wybierz konto dostawcy **GB_SI_000001**, a następnie w okienku akcji na karcie **Dostawca** w formularzu **Konfiguracja** wybierz pozycję **Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="9b7ea-204">Na stronie **Konta bankowe dostawcy** wybierz opcję **Nowe**, a następnie wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="9b7ea-205">W polu **Konto bankowe** wpisz **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="9b7ea-206">W polu **Grupy bankowe** wybierz opcję **BankGBP**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="9b7ea-207">W polu **Numer konta bankowego** wpisz **202015**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="9b7ea-208">W polu **Kod SWIFT** wprowadź <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="9b7ea-209">W polu **IBAN** wprowadź **GB33BUKB20201555555555**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="9b7ea-210">W polu **Numer RBN** zachowaj wartość domyślną <a id="DefineRoutingNumber"></a>**123456**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Strona konta bankowe dostawcy](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="9b7ea-212">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-212">Select **Save**.</span></span>
5. <span data-ttu-id="9b7ea-213">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-213">Close the page.</span></span>
6. <span data-ttu-id="9b7ea-214">Na stronie **Wszyscy dostawcy** otwórz konto dostawcy **GB_SI_000001**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="9b7ea-215">Na stronie Szczegóły dostawcy wybierz opcję **Edytuj**, aby umożliwić edytowanie strony w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="9b7ea-216">Na skróconej karcie **Opłaty** w polu **Konto bankowe** wybierz opcję **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Strona szczegółów dot. dostawcy](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="9b7ea-218">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-218">Select **Save**.</span></span>
10. <span data-ttu-id="9b7ea-219">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="9b7ea-220">Podawanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-220">Enter a vendor payment</span></span>

<span data-ttu-id="9b7ea-221">Należy utworzyć nową płatność dostawcy za pomocą [propozycji płatności](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-221">You must enter a new vendor payment by using a [payment proposal](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span></span>

1. <span data-ttu-id="9b7ea-222">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="9b7ea-223">Na stronie **Arkusz płatności dostawców** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="9b7ea-224">W polu **Nazwa** wybierz **VendPay**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="9b7ea-225">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-225">Select **Lines**.</span></span>
5. <span data-ttu-id="9b7ea-226">Wybierz **Propozycja płatności** \> **Utwórz propozycję płatności**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="9b7ea-227">W oknie dialogowym **Propozycja płatności dostawcy** skonfiguruj warunki filtrowania rekordów tylko dla konta dostawcy **GB_SI_000001**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="9b7ea-228">Wybierz wiersz faktury **00000007_Inv**, a następnie wybierz opcję **Utwórz płatność**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Okno dialogowe – propozycje płatności dostawcy](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="9b7ea-230">Sprawdź, czy wprowadzona płatność jest skonfigurowana do używania **Elektronicznej** metody płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Strona Płatności dla dostawców](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="9b7ea-232">Przetwarzanie płatności dostawcy przy użyciu standardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="9b7ea-233">Konfigurowanie elektronicznej metody płatności</span><span class="sxs-lookup"><span data-stu-id="9b7ea-233">Set up the electronic payment method</span></span>

<span data-ttu-id="9b7ea-234">Należy skonfigurować elektroniczną metodę płatności, aby korzystała z importowanej konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="9b7ea-235">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="9b7ea-236">Na stronie **Metody płatności – dostawcy** wybierz **Elektroniczną** metodę płatności w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="9b7ea-237">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-237">Select **Edit**.</span></span>
4. <span data-ttu-id="9b7ea-238">W karcie **Formaty plików** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="9b7ea-239">W polu **Konfiguracja formatu eksportu** wybierz format konfiguracji **BACS (brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Metody płatności – strona dostawcy](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="9b7ea-241">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="9b7ea-242">Przetwarzanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-242">Process a vendor payment</span></span>

1. <span data-ttu-id="9b7ea-243">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="9b7ea-244">Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześniej, a następnie wybierz pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="9b7ea-245">Na stronie **Płatności dostawcy** wybierz pozycję **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="9b7ea-246">W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="9b7ea-247">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="9b7ea-248">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="9b7ea-249">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-249">Select **OK**.</span></span>
6. <span data-ttu-id="9b7ea-250">W oknie dialogowym **Parametry raportu elektronicznego**, w polu **Drukuj raport kontroli** wybierz **Tak**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Strona dialogowa Parametry raportu elektronicznego](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="9b7ea-252">Oprócz pliku płatności można teraz wygenerować raport kontroli.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="9b7ea-253">Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="9b7ea-254">Raport kontrolny w formacie programu Excel</span><span class="sxs-lookup"><span data-stu-id="9b7ea-254">The control report in Excel format</span></span>
    - <span data-ttu-id="9b7ea-255">Plik płatności w formacie TXT</span><span class="sxs-lookup"><span data-stu-id="9b7ea-255">The payment file in TXT format</span></span>

        <span data-ttu-id="9b7ea-256">Należy zauważyć, że zgodnie ze [strukturą](#PositionRoutingNumber) dostarczonego formatu modułu ER, wiersz płatności w wygenerowanym pliku rozpoczyna się od numeru kodu banku [zdefiniowanego](#DefineRoutingNumber) dla konfigurowanego konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="9b7ea-258">Dostosowywanie standardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-258">Customize the standard ER format</span></span>

<span data-ttu-id="9b7ea-259">W przykładzie pokazanym w tej sekcji zachodzi potrzeba użycia konfiguracji ER dostarczonej przez Microsoft w celu wygenerowania plików płatności dostawców w formacie BACS, ale konieczne jest także dodanie dostosowania w celu obsługi wymagań określonego banku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="9b7ea-260">Można również uaktualnić format niestandardowy, gdy będą dostępne nowe wersje konfiguracji systemu ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="9b7ea-261">Jednak użytkownik chce mieć możliwość dokonania uaktualnienia przy najniższym koszcie.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="9b7ea-262">W tym przypadku, jako przedstawiciel Litware, Inc., należy utworzyć (uzyskać) nową konfigurację formatu ER, używając **BACS (brytyjski)** konfiguracji dostarczonej przez Microsoft jako podstawy.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="9b7ea-263">Tworzenie niestandardowego formatu</span><span class="sxs-lookup"><span data-stu-id="9b7ea-263">Create a custom format</span></span>

1. <span data-ttu-id="9b7ea-264">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="9b7ea-265">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="9b7ea-266">Litware, Inc. będzie używał wersji 1.1 tej konfiguracji formatu ER jako podstawy dla wersji niestandardowej.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="9b7ea-267">Wybierz przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="9b7ea-268">Nowe okno dialogowe pozwoli utworzyć nową konfigurację dla niestandardowego formatu płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="9b7ea-269">W **Nowej** grupie pól, wybierz opcję **Pochodna od nazwy: BACS (brytyjski), Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="9b7ea-270">W polu **Nazwa** wpisz **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Utwórz okno dialogowe tworzenia konfiguracji](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="9b7ea-272">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-272">Select **Create configuration**.</span></span>

<span data-ttu-id="9b7ea-273">Utworzono konfigurację tematu ER **BACS (niestandardowy brytyjski)** w wersji 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="9b7ea-274">Ta wersja ma [stan](general-electronic-reporting.md#component-versioning) **Wersji roboczej** i można ją edytować.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="9b7ea-275">Bieżąca zawartość niestandardowego formatu ER jest zgodna z zawartością formatu dostarczonego przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Strona Konfiguracje](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="9b7ea-277">Edytowanie niestandardowego formatu</span><span class="sxs-lookup"><span data-stu-id="9b7ea-277">Edit a custom format</span></span>

<span data-ttu-id="9b7ea-278">Musisz skonfigurować format niestandardowy, aby spełniał wymagania specyficzne dla banku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="9b7ea-279">Na przykład bank może wymagać, aby generowane pliki płatności obejmowały kod SWIFT banku, do którego przypisano rolę agenta w przetwarzanej płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="9b7ea-280">Kody SWIFT są międzynarodowymi kodami, które identyfikują poszczególne banki na całym świecie.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="9b7ea-281">Są one znane także jako kody identyfikacyjne banku (BICs).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="9b7ea-282">Kod SWIFT musi składać się z 11 znaków i musi być wprowadzony na początku każdego wiersza płatności w wygenerowanym pliku płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="9b7ea-283">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="9b7ea-284">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="9b7ea-285">Na skróconej karcie **Wersje** wybierz wersję **1.1.1** wybranej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="9b7ea-286">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-286">Select **Designer**.</span></span>
5. <span data-ttu-id="9b7ea-287">Na stronie **Projektant formatów** wybierz opcję **Pokaż szczegóły**, aby wyświetlić więcej informacji o elementach formatu.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="9b7ea-288">Rozwiń i przejrzyj następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="9b7ea-289">Element **Element BACSReportsFolder** typu **Folder**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="9b7ea-290">Ten element jest używany do generowania danych wyjściowych w formacie ZIP.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="9b7ea-291">Element **plik** typu **Plik**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="9b7ea-292">Ten element jest używany do generowania pliku płatności w formacie TXT.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="9b7ea-293">Element **transakcje** typu **Sekwencja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="9b7ea-294">Ten element jest używany do generowania pojedynczego wiersza płatności w pliku płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="9b7ea-295">Element **transakcja** typu **Sekwencja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="9b7ea-296">Ten element jest używany do generowania pojedynczych pól w jednym wierszu płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="9b7ea-297">Umożliwia wybranie elementu **transakcja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-297">Select the **transaction** element.</span></span>

    ![Element transakcji w projektancie operacji ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="9b7ea-299">Podany raport jest skonfigurowany w taki sposób, aby <a id="PositionRoutingNumber"></a>każdy wiersz płatności zaczynał się od numeru rozliczeniowego banku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="9b7ea-300">Element formatu **vendBankRouteNum** jest do tego używany.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="9b7ea-301">Wybierz opcję **Dodaj**, a następnie wybierz typ **Tekst\\Ciąg** dodawanego elementu formatu:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="9b7ea-302">W polu **Nazwa** wpisz **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="9b7ea-303">W polu **Długość minimalna** wpisz **11**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="9b7ea-304">W polu **Długość maksymalna** wpisz **11**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="9b7ea-305">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b7ea-306">Element **vendBankSWIFT** zostanie użyty do wprowadzenia kodu SWIFT banku dostawcy w wygenerowanych plikach.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="9b7ea-307">W drzewie struktury formatu wybierz **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="9b7ea-308">Wybierz przycisk **Przenieś w górę**, aby przenieść wybrany element formatu o jeden poziom w górę.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="9b7ea-309">Powtarzaj ten krok do momentu, aż element **vendBankSWIFT** będzie <a id="PositionSWIFTCode"></a>pierwszym elementem w nadrzędnym elemencie **transakcji**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT jako pierwszy element w obszarze transakcja w projektancie operacji ER](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="9b7ea-311">Gdy **vendBankSWIFT** jest wciąż zaznaczone w drzewie struktury formatu, wybierz kartę **Mapowanie**, a następnie rozwiń źródło danych **Model**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="9b7ea-312">Rozwiń **model.Payment** \> **model.Payment.CreditorAgent**oraz wybierz pole źródła danych **model.Payment.CreditorAgent.BICFI**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="9b7ea-313">To pole źródła danych opisuje kod SWIFT banku dostawcy, któremu przypisano rolę agenta w przetwarzanej płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="9b7ea-314">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-314">Select **Bind**.</span></span> <span data-ttu-id="9b7ea-315">Element formatu **vendBankSWIFT** jest powiązany ze źródłem danych **model.Payment.CreditorAgent.BICFI** data source field, dzięki czemu kody SWIFT zostaną wprowadzone w plikach wygenerowanych płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![Element formatu vendBankSWIFT powiązany z polem źródła danych model.Payment.CreditorAgent.BICFI. w projektancie operacji ER](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="9b7ea-317">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-317">Select **Save**.</span></span>
15. <span data-ttu-id="9b7ea-318">Zamknij stronę projektowania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="9b7ea-319">Oznaczanie formatu niestandardowego jako wykonywalnego</span><span class="sxs-lookup"><span data-stu-id="9b7ea-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="9b7ea-320">Teraz, gdy została utworzona pierwsza wersja formatu niestandardowego i ma ona stan **Wersja robocza**, można ją uruchomić w celach testowych.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="9b7ea-321">Aby uruchomić raport, należy przetworzyć płatność dostawcy, używając metody płatności, która odwołuje się do niestandardowego formatu encji (ER).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="9b7ea-322">Domyślnie, podczas wywoływania formatu ER w aplikacji, jedynie wersje, które mają stan **Zakończono** lub **Udostępniono**, są [używane](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="9b7ea-323">To zachowanie pomaga zapobiegać używaniu formatów ER, w których znajdują się nieukończone projekty.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="9b7ea-324">Jednak w przypadku uruchamiania testów można wymusić na aplikacji używanie wersji formatu ER, która ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="9b7ea-325">W ten sposób można dostosować bieżącą wersję formatu, jeśli są wymagane jakiekolwiek modyfikacje.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="9b7ea-326">Aby uzyskać więcej informacji, zobacz [Zastosowanie](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="9b7ea-327">Aby można było skorzystać z wersji roboczej formatu ER, należy odpowiednio go oznaczyć.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="9b7ea-328">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="9b7ea-329">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="9b7ea-330">W oknie dialogowym **Parametry użytkownika** określ opcję **Ustawienia uruchamiania** na **Tak**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="9b7ea-331">W razie potrzeby wybierz opcję **Edytuj**, aby bieżąca strona była możliwa do edycji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="9b7ea-332">W drzewie konfiguracji w lewym okienku wybierz **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="9b7ea-333">Ustaw wartość **Uruchom wersję roboczą** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Uruchom Wersję roboczą na stronie konfiguracje](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="9b7ea-335">Przetwarzanie płatności dostawcy przy użyciu niestandardowego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="9b7ea-336">Konfigurowanie elektronicznej metody płatności</span><span class="sxs-lookup"><span data-stu-id="9b7ea-336">Set up the electronic payment method</span></span>

<span data-ttu-id="9b7ea-337">Należy skonfigurować elektroniczną metodę płatności, aby do przetwarzania płatności dostawców był używany niestandardowy format ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="9b7ea-338">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="9b7ea-339">Na stronie **Metody płatności – dostawcy** wybierz **Elektroniczną** metodę płatności w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="9b7ea-340">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-340">Select **Edit**.</span></span>
4. <span data-ttu-id="9b7ea-341">W karcie **Format plików** ustaw **Ogólny elektroniczny format eksportu** jako **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="9b7ea-342">W polu **Konfiguracja formatu eksportu** wybierz format konfiguracji **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Metody płatności – strona dostawcy](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="9b7ea-344">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="9b7ea-345">Przetwarzanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="9b7ea-345">Process a vendor payment</span></span>

1. <span data-ttu-id="9b7ea-346">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="9b7ea-347">Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześnie.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="9b7ea-348">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-348">Select **Lines**.</span></span>
4. <span data-ttu-id="9b7ea-349">Na **Płatności dostawców**, powyżej siatki, wybierz **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="9b7ea-350">Wybierz **Generuj płatność**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="9b7ea-351">W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="9b7ea-352">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="9b7ea-353">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="9b7ea-354">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-354">Select **OK**.</span></span>
8. <span data-ttu-id="9b7ea-355">W oknie dialogowym **Parametry raportu elektronicznego**, w polu **Drukuj raport kontroli** wybierz **Tak**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b7ea-356">Oprócz pliku płatności można teraz wygenerować tylko raport kontroli.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="9b7ea-357">Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="9b7ea-358">Raport kontrolny w formacie programu Excel</span><span class="sxs-lookup"><span data-stu-id="9b7ea-358">The control report in Excel format</span></span>
    - <span data-ttu-id="9b7ea-359">Plik płatności w formacie TXT</span><span class="sxs-lookup"><span data-stu-id="9b7ea-359">The payment file in TXT format</span></span>

        <span data-ttu-id="9b7ea-360">Należy zauważyć, że zgodnie ze strukturą niestandardowego formatu ER, wiersz płatności w wygenerowanym pliku [rozpoczyna się](#PositionSWIFTCode) od kodu SWIFT, który został [wprowadzony](#DefineSWIFTCode) dla konta bankowego dostawcy, którego płatność została przetworzona.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="9b7ea-362">Importowanie nowych wersji standardowej konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="9b7ea-363">W przykładzie pokazanym w tej sekcji zostanie wyświetlone powiadomienie dotyczące artykułu bazy wiedzy [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="9b7ea-364">To powiadomienie informuje o nowej wersji formatu ER **BACS (brytyjski)** opublikowanego przez Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="9b7ea-365">Oprócz raportu kontrolnego, nowa wersja umożliwia użytkownikom generowanie raportu zawiadomienia o płatności oraz raportu notatki towarzyszącej podczas przetwarzania płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="9b7ea-366">Chcesz rozpocząć korzystanie z tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="9b7ea-367">Importowanie nowych wersji standardowej konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="9b7ea-368">Aby dodać nowe wersje konfiguracji ER do bieżącego wystąpienia Finance, należy zaimportować je z [repozytorium](general-electronic-reporting.md#Repository) ER, które zostało skonfigurowane dla tego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="9b7ea-369">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-370">Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz kafelek **Microsoft**, a następnie wybierz pozycję **Repozytoria**, aby wyświetlić listę repozytoriów dla dostawcy rozwiązania: Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="9b7ea-371">Na stronie **Repozytoria konfiguracji** zaznacz repozytorium typu **Globalne**, a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="9b7ea-372">Jeśli zostanie wyświetlony monit o autoryzację połączenia z usługą Regulatory Configuration Service, postępuj zgodnie z instrukcjami autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="9b7ea-373">Na stronie **Repozytorium konfiguracji** w drzewie konfiguracje w panelu po lewej wybierz format konfiguracji **BACS (brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="9b7ea-374">Na skróconej karcie **Wersje** wybierz wersję **3.3** wybranej konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="9b7ea-375">Wybierz **Importuj**, aby pobrać wybraną wersję z Globalnego repozytorium do bieżącego wystąpienia Finance.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Strona Repozytorium konfiguracji](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="9b7ea-377">Jeśli masz problemy z dostępem do [repozytorium globalnego](er-download-configurations-global-repo.md), zamiast tego możesz [pobrać konfiguracje z](download-electronic-reporting-configuration-lcs.md) LCS.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="9b7ea-378">Przeglądanie zaimportowanych konfiguracji formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="9b7ea-379">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-380">WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="9b7ea-381">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="9b7ea-382">Na skróconej karcie **wersje** wybierz opcję wersja **3.3**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="9b7ea-383">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-383">Select **Designer**.</span></span>
6. <span data-ttu-id="9b7ea-384">Na stronie **Projektant formatów** rozwiń element formatu **BACSReportsFolder**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="9b7ea-385">Zwróć uwagę, że wersja 3.3 element formatu **PaymentAdviceReport** używany do generowania raportu zawiadomienia o płatności podczas przetwarzania płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![Element formatu PaymentAdviceReport w projektancie operacji ER](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="9b7ea-387">Zamknij stronę projektowania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="9b7ea-388">Zaadaptowanie zmian z nowej wersji importowanego formatu w formacie niestandardowym</span><span class="sxs-lookup"><span data-stu-id="9b7ea-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="9b7ea-389">Zakończenie obecnej wersji roboczej formatu niestandardowego</span><span class="sxs-lookup"><span data-stu-id="9b7ea-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="9b7ea-390">Aby zachować bieżący stan formatu niestandardowego, należy uzupełnić wersję roboczą 1.1.1, zmieniając jej stan z **Wersja robocza** na **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="9b7ea-391">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="9b7ea-392">WNa stronie **Konfiguracje lokalizacji** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="9b7ea-393">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, rozwiń **BACS (brytyjski)**, a potem wybierz **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="9b7ea-394">Na skróconej karcie **Wersje** wybierz **Zmień stan** \> **Zakończ**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="9b7ea-395">Stan wersji 1.1.1 został zmieniony z **Wersji roboczej** na **Zakończone**, a wersja jest tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="9b7ea-396">Dodano nową wersję do edycji, 1.1.2, która ma stan **Wersja robocza**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="9b7ea-397">Możesz skorzystać z tej wersji, aby wprowadzić dalsze zmiany w niestandardowym formacie ER.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="9b7ea-398">Zmiana formatu niestandardowego do nowej wersji bazowej</span><span class="sxs-lookup"><span data-stu-id="9b7ea-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="9b7ea-399">Aby rozpocząć korzystanie z nowej funkcji w wersji 3.3 formatu **BACS (brytyjski)** w dostosowaniu, należy zmienić podstawową wersję konfiguracji dla konfiguracji niestandardowej **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="9b7ea-400">Ten proces jest nazywany [zmianą bazy](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="9b7ea-401">Zamiast wersji 1.1 konfiguracji **BACS (brytyjski)** należy używać nowej wersji 3.3.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="9b7ea-402">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="9b7ea-403">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model płatności**, a potem wybierz **BACS (niestandardowy brytyjski)**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="9b7ea-404">Na skróconej karcie **Wersje** wybierz wersję **1.1.2**, a następnie wybierz opcję **Zmień podstawę**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="9b7ea-405">W oknie **Zmień podstawę** w polu **Wersja docelowa** wybierz wersję **3.3** konfiguracji podstawowej, aby ją zastosować jako nową podstawę i użyć jej do zaktualizowania konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Okno dialogowe zmiana podstawy](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="9b7ea-407">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-407">Select **OK**.</span></span>
6. <span data-ttu-id="9b7ea-408">Zauważ, że numer wersji roboczej został zmieniony z **1.1.2** na **3.3.2**, aby odzwierciedlić zmianę w wersji bazowej.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="9b7ea-409">Po scaleniu wersji niestandardowej z nową wersją bazową mogą zostać wykryte konflikty. Konflikty te reprezentują niektóre zmiany formatu, których nie można scalić automatycznie.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Zmiana podstawy konfiguracji z konfliktami na stronie konfiguracje](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="9b7ea-411">Jeśli zostaną wykryte konflikty, należy je rozwiązać ręcznie w projektancie formatów.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="9b7ea-412">Na skróconej karcie **wersje** wybierz opcję wersja **3.3.2**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="9b7ea-413">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-413">Select **Designer**.</span></span>
9. <span data-ttu-id="9b7ea-414">Na stronie **Projektant formatów** na skróconej karcie **Szczegóły**, wybierz rekord powodujący konflikt, a następnie wybierz opcję **Zastosuj wartość podstawową**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Konflikt rekordów zmiany podstawy w projektancie operacji ER](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="9b7ea-416">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-416">Select **Save**.</span></span>

    <span data-ttu-id="9b7ea-417">Konfliktu nie powinien już pojawiać się w skróconej karcie **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Konflikt rozwiązany w projektancie operacji ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="9b7ea-419">Konflikt został rozwiązany przez potwierdzenie, że w tym formacie ER musi być używana wersja 3 modelu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="9b7ea-420">Rozwiń **BACSReportsFolder** \> **plik** \> **transakcje** \> **transakcja**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="9b7ea-421">Na karcie **Mapowanie** należy zauważyć, że wersja 3.3.2 niestandardowego formatu ER zawiera zarówno dostosowanie (element **vendBankSWIFT** i jego powiązanie), jak i nową funkcjonalność wersji 3.3 podstawowego formatu ER dostarczonego przez Microsoft (element **PaymentAdviceReport** wraz z zagnieżdżonymi elementami i skonfigurowanymi powiązaniami).</span><span class="sxs-lookup"><span data-stu-id="9b7ea-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="9b7ea-422">Po kilku kliknięciach myszą zawarto modyfikacje nowej wersji bazowej, scalając je z dostosowaniem.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Format scalony w projektancie operacji ER](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="9b7ea-424">Zamknij stronę projektowania.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="9b7ea-425">Akcja zmiany podstawy jest odwracalna.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-425">The rebase action is reversible.</span></span> <span data-ttu-id="9b7ea-426">Aby anulować tę operację , należy wybrać wersję **1.1.1** w formacie **BACS (niestandardowy brytyjski)** na skróconej karcie **Wersje**, a następnie wybrać opcję **Pobierz tę wersję**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="9b7ea-427">Następnie w wersji 3.3.2 zostanie ponownie numerowana na 1.1.2, a zawartość wersji roboczej 1.1.2 będzie zgodna z treścią wersji 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="9b7ea-428">Przetwarzanie płatności dostawcy przy użyciu zmienionego formatu ER</span><span class="sxs-lookup"><span data-stu-id="9b7ea-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="9b7ea-429">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="9b7ea-430">Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności dodany wcześnie.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="9b7ea-431">Wybierz **Linie**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-431">Select **Lines**.</span></span>
4. <span data-ttu-id="9b7ea-432">Na **Płatności dostawców**, powyżej siatki, wybierz **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="9b7ea-433">Wybierz **Generuj płatność**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="9b7ea-434">W oknie dialogowym **Generuj płatności** wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="9b7ea-435">W polu **Metoda płatności** wybierz pozycję **Elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="9b7ea-436">W polu **Konto bankowe** wybierz pozycję **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="9b7ea-437">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-437">Select **OK**.</span></span>
8. <span data-ttu-id="9b7ea-438">W oknie dialogowym **Parametry raportowania elektronicznego** wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="9b7ea-439">Ustaw opcję **Wydrukuj raport kontrolny** jako **tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="9b7ea-440">Ustaw opcję **Wydrukuj poradę odnośnie do płatności** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Okno dialogowe Parametry raportu elektronicznego](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="9b7ea-442">Oprócz pliku płatności można teraz wygenerować zarówno raport kontrolny, jak i raport zawiadomienia o płatności.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="9b7ea-443">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-443">Select **OK**.</span></span>
10. <span data-ttu-id="9b7ea-444">Pobierz plik zip, a następnie wyodrębnij z niego następujące pliki:</span><span class="sxs-lookup"><span data-stu-id="9b7ea-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="9b7ea-445">Raport kontrolny w formacie programu Excel</span><span class="sxs-lookup"><span data-stu-id="9b7ea-445">The control report in Excel format</span></span>
    - <span data-ttu-id="9b7ea-446">Porada dot. płatności w formacie programu Excel</span><span class="sxs-lookup"><span data-stu-id="9b7ea-446">The payment advice report in Excel format</span></span>

        ![Porada dot. płatności w formacie programu Excel](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="9b7ea-448">Plik płatności w formacie TXT</span><span class="sxs-lookup"><span data-stu-id="9b7ea-448">The payment file in TXT format</span></span>

        <span data-ttu-id="9b7ea-449">Należy zauważyć, że wiersz płatności w wygenerowanym pliku rozpoczyna się od kodu SWIFT, który został wprowadzony dla konta bankowego dostawcy, którego płatność została przetworzona.</span><span class="sxs-lookup"><span data-stu-id="9b7ea-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![Plik płatności w formacie TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="9b7ea-451">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9b7ea-451">Additional resources</span></span>

- [<span data-ttu-id="9b7ea-452">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="9b7ea-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="9b7ea-453">Pobieranie konfiguracji ER z usługi Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="9b7ea-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="9b7ea-454">Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service</span><span class="sxs-lookup"><span data-stu-id="9b7ea-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
