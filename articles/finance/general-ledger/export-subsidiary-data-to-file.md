---
title: Eksportowanie danych oddziałów do plików
description: W tym temacie wyjaśniono, jak przygotować się do wyeksportowania danych z Microsoft Dynamics 365 Finance, a następnie zaimportowania ich do skonsolidowanej firmy.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: bae0a28c59f327e47378eef6392d5e304bbde9a8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826185"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="a73a6-103">Eksportowanie danych oddziałów do plików</span><span class="sxs-lookup"><span data-stu-id="a73a6-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a73a6-104">Strona **Eksportu** umożliwia (**Administrowanie systemem \> Obszary robocze \> Import/Eksport**) przygotowanie do eksportowania danych oddziałów do plików, które następnie można zaimportować do firmy skonsolidowanej.</span><span class="sxs-lookup"><span data-stu-id="a73a6-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="a73a6-105">Więcej informacji o procesach importu i eksportu, zapoznaj się z [Omówieniem importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="a73a6-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="a73a6-106">Utwórz firmę dla procesu konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="a73a6-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="a73a6-107">Aby uzyskać informacje na temat tworzenia firm, zapoznaj się z tematem [Tworzenie firmy](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="a73a6-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="a73a6-108">Aby uzyskać więcej informacji, zobacz temat [Przygotowanie firmy do użycia w procesie konsolidacji](prepare-company-for-consolidation.md) i [Konfigurowanie firmy zależnej do konsolidacji](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="a73a6-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="a73a6-109">Przejdź do **Konsolidacje \> Eksportuj salda firmy**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="a73a6-110">Na stronie **Eksportuj salda firmy** na karcie **Kryteria** określ szczegóły konsolidacji, ustawiając następujące pola.</span><span class="sxs-lookup"><span data-stu-id="a73a6-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="a73a6-111">Pole</span><span class="sxs-lookup"><span data-stu-id="a73a6-111">Field</span></span>                             | <span data-ttu-id="a73a6-112">opis</span><span class="sxs-lookup"><span data-stu-id="a73a6-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="a73a6-113">Konto główne</span><span class="sxs-lookup"><span data-stu-id="a73a6-113">Main account</span></span>                      | <span data-ttu-id="a73a6-114">Określ konta do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="a73a6-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="a73a6-115">Aby uwzględnić wszystkie konta, należy pozostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="a73a6-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="a73a6-116">Użyj konta konsolidacji</span><span class="sxs-lookup"><span data-stu-id="a73a6-116">Use consolidation account</span></span>         | <span data-ttu-id="a73a6-117">Jeśli określono konta konsolidacji, ustaw tę opcję na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="a73a6-118">Wybierz konto konsolidacji z</span><span class="sxs-lookup"><span data-stu-id="a73a6-118">Select consolidation account from</span></span> | <span data-ttu-id="a73a6-119">Wybierz **Konto główne** lub **Grupę kont konsolidacji**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="a73a6-120">Grupa kont konsolidacji</span><span class="sxs-lookup"><span data-stu-id="a73a6-120">Consolidation account group</span></span>       | <span data-ttu-id="a73a6-121">Wybierz grupę kont konsolidacyjnych dla wybranego konta konsolidacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a73a6-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="a73a6-122">Okres konsolidacji</span><span class="sxs-lookup"><span data-stu-id="a73a6-122">Consolidation period</span></span>              | <span data-ttu-id="a73a6-123">Określ daty „od” i „do” konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="a73a6-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="a73a6-124">Uwzględnij kwoty rzeczywiste</span><span class="sxs-lookup"><span data-stu-id="a73a6-124">Include actual amounts</span></span>            | <span data-ttu-id="a73a6-125">Ustaw dla tej opcji wartość **Tak**, aby uwzględnić dokładne wartości rzeczywiste.</span><span class="sxs-lookup"><span data-stu-id="a73a6-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="a73a6-126">Uwzględnij kwoty budżetu</span><span class="sxs-lookup"><span data-stu-id="a73a6-126">Include budget amounts</span></span>            | <span data-ttu-id="a73a6-127">Ustaw dla tej opcji wartość **Tak**, aby uwzględnić kwoty budżetu w konsolidacjach.</span><span class="sxs-lookup"><span data-stu-id="a73a6-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="a73a6-128">Modele budżetu</span><span class="sxs-lookup"><span data-stu-id="a73a6-128">Budget models</span></span>                     | <span data-ttu-id="a73a6-129">Określ model budżetu, który ma być uwzględniany.</span><span class="sxs-lookup"><span data-stu-id="a73a6-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="a73a6-130">Na karcie **Wymiary finansowe** podaj szczegóły konsolidacji:</span><span class="sxs-lookup"><span data-stu-id="a73a6-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="a73a6-131">Podaj informacje o wymiarze finansowym, które są przenoszone z transakcji kont oddziałów do transakcji firmy konsolidowanej.</span><span class="sxs-lookup"><span data-stu-id="a73a6-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="a73a6-132">Wybierz wymiary finansowe z listy.</span><span class="sxs-lookup"><span data-stu-id="a73a6-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="a73a6-133">Określ poprawną specyfikację dla każdego konsolidowanego wymiaru finansowego.</span><span class="sxs-lookup"><span data-stu-id="a73a6-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="a73a6-134">Dostępne opcje to **Wymiar**, **Wymiar grupy**, **Firma** i **Konto**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a73a6-135">Opcja **Grupuj wymiary** umożliwia definiowanie wartości wymiaru używanej przez grupę firm, które są konsolidowane.</span><span class="sxs-lookup"><span data-stu-id="a73a6-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="a73a6-136">Określ kolejność segmentów do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="a73a6-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="a73a6-137">Na karcie **Firmy** wykonaj następujące kroki, aby określić eksportowanie firmy:</span><span class="sxs-lookup"><span data-stu-id="a73a6-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="a73a6-138">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-138">Select **New**.</span></span>
    2. <span data-ttu-id="a73a6-139">W polu **Firma źródłowa** wprowadź nazwę firmy.</span><span class="sxs-lookup"><span data-stu-id="a73a6-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="a73a6-140">Jeśli identyczne kryteria dotyczą kilku oddziałów z tej samej bazy danych, za pomocą jednej operacji można przenieść dane oddziałów znajdujące się w tej samej bazie danych do osobnych plików eksportu:</span><span class="sxs-lookup"><span data-stu-id="a73a6-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="a73a6-141">Utwórz wiersz dla każdej zależnej firmy, dla której konta mają zostać wyeksportowane do plików.</span><span class="sxs-lookup"><span data-stu-id="a73a6-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="a73a6-142">Pliki te zostaną później zaimportowane do skonsolidowanej osoby prawnej.</span><span class="sxs-lookup"><span data-stu-id="a73a6-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="a73a6-143">Dla każdego oddziału wprowadź nazwę oddziału i nazwę pliku eksportu, który zostanie utworzony podczas zadania eksportu.</span><span class="sxs-lookup"><span data-stu-id="a73a6-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="a73a6-144">W polu **Typ konta różnic konwersji** wybierz pozycję **Wynikowe** lub **Bilans**.</span><span class="sxs-lookup"><span data-stu-id="a73a6-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="a73a6-145">Wprowadź nazwę pliku eksportu, który zostanie utworzony.</span><span class="sxs-lookup"><span data-stu-id="a73a6-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="a73a6-146">Wybierz przycisk **OK**, aby uruchomić eksport.</span><span class="sxs-lookup"><span data-stu-id="a73a6-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="a73a6-147">Po zakończeniu eksportu zostanie wyświetlony komunikat zawierający liczbę rekordów zapisanych w każdym pliku.</span><span class="sxs-lookup"><span data-stu-id="a73a6-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="a73a6-148">Następnie można importować pliki w skonsolidowanej firmie.</span><span class="sxs-lookup"><span data-stu-id="a73a6-148">You can then import the files into the consolidated legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]