---
title: Raport magazynu wartości zapasów
description: W tym temacie wyjaśniono, jak uruchomić raport magazynowy wartości zapasówi udostępnić go cyfrowo jako stronę interaktywną w Microsoft Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 03426e86186c6aa283531eb37ae26527e6891042
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276950"
---
# <a name="inventory-value-storage-report"></a><span data-ttu-id="c25f0-103">Raport magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-103">Inventory value storage report</span></span>

<span data-ttu-id="c25f0-104">W tym temacie wyjaśniono, jak uruchomić raport **Magazynu wartości zapasów** i udostępnić go cyfrowo jako stronę interaktywną w Microsoft Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.</span><span class="sxs-lookup"><span data-stu-id="c25f0-104">This topic explains how to run an **Inventory value storage** report and make the output available digitally, either as an interactive page in Microsoft Dynamics 365 Supply Chain Management or as an exported document in any of several formats.</span></span>

<span data-ttu-id="c25f0-105">Podczas wyświetlania raportu w przeglądarce kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on the layout that you've configured.</span></span> <span data-ttu-id="c25f0-106">Można posortować wyniki, przefiltrować je, przejść do kolejnych danych i wykonać inne zadania.</span><span class="sxs-lookup"><span data-stu-id="c25f0-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="c25f0-107">Wyniki raportu są przechowywane w jednostce danych **Wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-107">Report results are stored in the **Inventory value** data entity.</span></span> <span data-ttu-id="c25f0-108">Można więc filtrować i eksportować wyniki do formatu, takiego jak wartości rozdzielane przecinkami (CSV) lub Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c25f0-108">Therefore, you can filter and export the results to a format such as comma-separated values (CSV) or Microsoft Excel format.</span></span>

<span data-ttu-id="c25f0-109">Raport **Magazyn wartości zapasów** jest przydatny, gdy dane wyjściowe zawierają wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="c25f0-109">The **Inventory value storage** report is helpful when the output contains many lines.</span></span> <span data-ttu-id="c25f0-110">Na przykład pozycje 50 000 i 300 sklepów zostały utworzone jako magazyny.</span><span class="sxs-lookup"><span data-stu-id="c25f0-110">For example, you have 50,000 items, and 300 stores have been created as warehouses.</span></span> <span data-ttu-id="c25f0-111">W takim przypadku, jeśli salda końcowe zapasów są żądane według towarów, oddziału i magazynu, produkcja będzie zawierała wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="c25f0-111">In this case, if you request inventory ending balances by item, site, and warehouse, the output will contain many lines.</span></span>

> [!NOTE]
> <span data-ttu-id="c25f0-112">Raport nie będzie zawierać sum częściowych, które są zdefiniowane w układzie raportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-112">The report won't include subtotals that are defined in the report layout.</span></span> <span data-ttu-id="c25f0-113">Nie uwzględnia również sald księgi głównej, nawet jeśli są zdefiniowane w układzie raportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-113">It also won't include general ledger balances, even when they are defined in the report layout.</span></span> <span data-ttu-id="c25f0-114">Uzgodnienia księgi głównej należy wykonać przy użyciu bilansów próbnych.</span><span class="sxs-lookup"><span data-stu-id="c25f0-114">Reconciliation to the general ledger must be done by using trial balances.</span></span>

## <a name="turn-on-the-inventory-value-storage-feature"></a><span data-ttu-id="c25f0-115">Włącz raport magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-115">Turn on the Inventory value storage feature</span></span>

<span data-ttu-id="c25f0-116">Aby można było wygenerować raport **magazynu wartości zapasów**, należy włączyć tę funkcję w systemie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-116">Before you can generate an **Inventory value storage** report, you must turn on the feature in your system.</span></span> <span data-ttu-id="c25f0-117">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="c25f0-117">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c25f0-118">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="c25f0-118">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c25f0-119">**Moduł** - zarządzanie kosztami</span><span class="sxs-lookup"><span data-stu-id="c25f0-119">**Module** – Cost management</span></span>
- <span data-ttu-id="c25f0-120">**Nazwa funkcji** – Włącz raport magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-120">**Feature name** – Inventory value storage</span></span>

## <a name="generate-an-inventory-value-storage-report"></a><span data-ttu-id="c25f0-121">Tworzenie raportu magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-121">Generate an Inventory value storage report</span></span>

<span data-ttu-id="c25f0-122">Wykonaj poniższe kroki, aby wygenerować i zapisać raport **magazynu wartości zapasów**:</span><span class="sxs-lookup"><span data-stu-id="c25f0-122">Follow these steps to generate and store an **Inventory value storage** report.</span></span>

1. <span data-ttu-id="c25f0-123">Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-123">Go to **Cost management \> Inquiries and reports \> Inventory value report storage**.</span></span>
1. <span data-ttu-id="c25f0-124">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-124">Select **New**.</span></span>
1. <span data-ttu-id="c25f0-125">W wyświetlonym oknie dialogowym **Wartość zapasów** należy określić następujące wartości, aby określić, które rekordy będą uwzględniane w raporcie:</span><span class="sxs-lookup"><span data-stu-id="c25f0-125">In the **Inventory value** dialog box that appears, set the following values to define which records are included in your report:</span></span>

    - <span data-ttu-id="c25f0-126">Na skróconej karcie **Parametry** należy wprowadzić unikatową nazwę raportu, a następnie za pomocą pól w sekcji **Zakres dat** określić, które rekordy mają być uwzględniane w raporcie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-126">On the **Parameters** FastTab, enter a unique name for the report, and use the fields in the **Date interval** section to define which records are included in the report.</span></span> <span data-ttu-id="c25f0-127">Aby zdefiniować interwał dat, można wybrać wstępnie zdefiniowany zakres (w odniesieniu do daty generowania raportu) w polu **Kod zakresu dat** lub wybrać określone daty w polach **Od dnia** i **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-127">To define the date interval, you can either select a preset range (relative to the report generation date) in the **Date interval code** field, or select specific dates in the **From date** and **To date** fields.</span></span> <!-- KFM: What is the ID setting for here? What do its values mean? -->
    - <span data-ttu-id="c25f0-128">Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych uwzględnionych w raporcie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-128">On the **Records to include** FastTab, set up filters and constraints to define which data is included in the report.</span></span>
    - <span data-ttu-id="c25f0-129">Na skróconej karcie **Uruchom w tle** określ sposób, kiedy i jak często generowany jest raport.</span><span class="sxs-lookup"><span data-stu-id="c25f0-129">On the **Run in the background** FastTab, specify how, when, and how often the report is generated.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c25f0-130">Ten raport jest zawsze wykonywany w ramach zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="c25f0-130">This report is always run as part of a batch job.</span></span>

1. <span data-ttu-id="c25f0-131">Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c25f0-131">Select **OK** to apply your settings and close the dialog box.</span></span>

<span data-ttu-id="c25f0-132">Po zakończeniu zadania wsadowego raport będzie wyświetlany na stronie **Magazyn raportów wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-132">After the batch job is completed, the report will be listed on the **Inventory value report storage** page.</span></span> <span data-ttu-id="c25f0-133">W celu wyświetlenia zaktualizowanego raportu może być konieczne odświeżenie strony.</span><span class="sxs-lookup"><span data-stu-id="c25f0-133">You might have to refresh the page to see the report.</span></span>

## <a name="explore-an-inventory-value-storage-report"></a><span data-ttu-id="c25f0-134">Poznawanie raportu magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-134">Explore an Inventory value storage report</span></span>

<span data-ttu-id="c25f0-135">Po wygenerowaniu raportu można go przeglądać i eksplorować w dowolnym momencie wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c25f0-135">After you've generated a report, you can view and explore it at any time by following these steps.</span></span>

1. <span data-ttu-id="c25f0-136">Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-136">Go to **Cost management \> Inquiries and reports \> Inventory value report storage**.</span></span>
1. <span data-ttu-id="c25f0-137">Na liście wybierz raport.</span><span class="sxs-lookup"><span data-stu-id="c25f0-137">Select a report in the list.</span></span>
1. <span data-ttu-id="c25f0-138">Wybierz opcję **Wyświetl szczegóły**, aby wyświetlić zawartość raportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-138">Select **View details** to show the report content.</span></span>
1. <span data-ttu-id="c25f0-139">Przeglądaj raport, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c25f0-139">Explore the report by following any of these steps:</span></span>

    - <span data-ttu-id="c25f0-140">Podobnie jak w przypadku większości standardowych formularzy w Supply Chain Management możesz wybrać niemal dowolny nagłówek kolumny, aby posortować lub przefiltrować siatkę według wartości w tej kolumnie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-140">As for most standard pages in Supply Chain Management, you can select almost any column heading to sort or filter the grid by the values in that column.</span></span>
    - <span data-ttu-id="c25f0-141">Pole **Filtr** umożliwia filtrowanie raportu według dowolnej wartości w dowolnej z kilku dostępnych kolumn.</span><span class="sxs-lookup"><span data-stu-id="c25f0-141">Use the **Filter** field to filter the report by any value in any of several available columns.</span></span>
    - <span data-ttu-id="c25f0-142">Aby zapisać i załadować Ulubione kombinacje opcji sortowania i filtrowania, należy skorzystać z menu Widok (powyżej pola **Filtr**).</span><span class="sxs-lookup"><span data-stu-id="c25f0-142">Use the view menu (above the **Filter** field) to save and load your favorite combinations of sort and filter options.</span></span>

## <a name="export-an-inventory-value-storage-report"></a><span data-ttu-id="c25f0-143">Eksportowanie raportu magazynu wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="c25f0-143">Export an Inventory value storage report</span></span>

<span data-ttu-id="c25f0-144">Każdy generowany raport jest przechowywany w jednostce danych **Wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-144">Every report that you generate is stored in the **Inventory value** data entity.</span></span> <span data-ttu-id="c25f0-145">Za pomocą standardowych funkcji Supply Chain Management można eksportować dane z tej jednostki do dowolnego obsługiwanego formatu danych, w tym także do pliku CSV lub programu Excel.</span><span class="sxs-lookup"><span data-stu-id="c25f0-145">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, such as CSV or Excel format.</span></span>

<span data-ttu-id="c25f0-146">W poniższym przykładzie przedstawiono sposób eksportowania raportu dotyczącego **raportu wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-146">The following example shows how to export an **Inventory value report** report.</span></span>

1. <span data-ttu-id="c25f0-147">Wybierz kolejno opcje **Administrowanie systemem \> Obszary robocze \> Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-147">Go to **System administration \> Workspaces \> Data management**.</span></span>
1. <span data-ttu-id="c25f0-148">W sekcji **Import/eksport** wybierz kafelek **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-148">In the **Import / Export** section, select the **Export** tile.</span></span> 
1. <span data-ttu-id="c25f0-149">Na wyświetlonej stronie **Eksportuj**, zostanie skonfigurowane zadanie eksportowania.</span><span class="sxs-lookup"><span data-stu-id="c25f0-149">On the **Export** page that appears, you will set up the export job.</span></span> <span data-ttu-id="c25f0-150">Najpierw wprowadź nazwę grupy dla zadania.</span><span class="sxs-lookup"><span data-stu-id="c25f0-150">First enter a group name for the job.</span></span>
1. <span data-ttu-id="c25f0-151">W sekcji **Wybrane jednostki** wybierz pozycję **Dodaj jednostkę**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-151">In the **Selected entities** section, select **Add entity**.</span></span>
1. <span data-ttu-id="c25f0-152">W wyświetlonym oknie dialogowym można ustawić następujące pola:</span><span class="sxs-lookup"><span data-stu-id="c25f0-152">In the dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="c25f0-153">**Nazwa jednostki** — umożliwia wybór **Wartości zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-153">**Entity name** – Select **Inventory value**.</span></span>
    - <span data-ttu-id="c25f0-154">**Docelowy format danych** — umożliwia wybór formatu, do którego mają zostać wyeksportowane dane.</span><span class="sxs-lookup"><span data-stu-id="c25f0-154">**Target data format** – Select the format to export data to.</span></span>

1. <span data-ttu-id="c25f0-155">Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c25f0-155">Select **Add** to add the new row, and then select **Close** to close the dialog box.</span></span>
1. <span data-ttu-id="c25f0-156">Zazwyczaj w danym momencie można eksportować jeden raport.</span><span class="sxs-lookup"><span data-stu-id="c25f0-156">Usually, you will export one report at a time.</span></span> <span data-ttu-id="c25f0-157">Aby wyeksportować jeden raport, należy skonfigurować filtr dla wiersza dodanego właśnie do okna dialogowego **Zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-157">To export a single report, set up a filter for the row that you just added to the **Inquiry** dialog box.</span></span> <span data-ttu-id="c25f0-158">W ten sposób można określić, który Raport z jednostki **Wartość zapasów** będzie uwzględniony w eksporcie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-158">In this way, you can define which report from the **Inventory value** entity is included in your export.</span></span> <span data-ttu-id="c25f0-159">Wykonaj następujące kroki, aby skonfigurować następujące opcje filtrowania i wyeksportować pojedynczy raport:</span><span class="sxs-lookup"><span data-stu-id="c25f0-159">Follow these steps to set the following filter options to export a single report:</span></span>

    1. <span data-ttu-id="c25f0-160">Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz.</span><span class="sxs-lookup"><span data-stu-id="c25f0-160">On the **Range** tab, select **Add** to add a row.</span></span>
    2. <span data-ttu-id="c25f0-161">W polu **Tabela** ustaw wartość **Wartość zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-161">Set the **Table** field to **Inventory value**.</span></span>
    3. <span data-ttu-id="c25f0-162">W polu **Tabela pochodna** ustaw wartość **Wartość zapasów**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-162">Set the **Derived table** field to **Inventory value**.</span></span>
    4. <span data-ttu-id="c25f0-163">Ustaw pole **Pole**, według którego ma być wykonywane filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="c25f0-163">Set the **Field** field to the field that you want to filter by.</span></span> <span data-ttu-id="c25f0-164">Zazwyczaj używane jest pole **Nazwa wykonania** i/lub pole **Czas wykonania**.</span><span class="sxs-lookup"><span data-stu-id="c25f0-164">Usually, you will use the **Execution name** field and/or the **Execution time** field.</span></span>
    5. <span data-ttu-id="c25f0-165">W polu **Kryterium** należy określić wartość, która ma być wyszukiwana w wybranym polu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-165">Set the **Criteria** field to the value that you want to look for in the selected field.</span></span> <span data-ttu-id="c25f0-166">(Jeśli w poprzednim kroku zaznaczono pole **Nazwa wykonania**, ta wartość będzie nazwą raportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-166">(If you selected the **Execution name** field in the previous step, this value will be the name of the report.</span></span> <span data-ttu-id="c25f0-167">Jeśli zaznaczono pole **Czas wykonania**, będzie to godzina wygenerowania raportu.)</span><span class="sxs-lookup"><span data-stu-id="c25f0-167">If you selected the **Execution time** field, it will be the time when the report was generated.)</span></span>
    6. <span data-ttu-id="c25f0-168">Dodaj wiersze na karcie **Zakres** w razie potrzeby, dopóki szukany raport nie zostanie jednoznacznie zidentyfikowany.</span><span class="sxs-lookup"><span data-stu-id="c25f0-168">Add more rows to the **Range** tab as you require, until you've uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="c25f0-169">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.</span><span class="sxs-lookup"><span data-stu-id="c25f0-169">Select **OK** to save your settings and close the dialog box.</span></span>
1. <span data-ttu-id="c25f0-170">Wybierz **Zapisz**, by zapisać ustawienia eksportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-170">Select **Save** to save your export setup.</span></span>
1. <span data-ttu-id="c25f0-171">Otwórz kartę **Opcje eksportu** i wybierz pozycję **Eksportuj teraz**, aby wygenerować plik eksportu.</span><span class="sxs-lookup"><span data-stu-id="c25f0-171">On the **Export options** tab, select **Export now** to generate the export file.</span></span>
1. <span data-ttu-id="c25f0-172">Zostanie otwarta strona **podsumowanie wykonania**, na której możesz zobaczyć stan zadania eksportowania oraz listę wyeksportowanych jednostek.</span><span class="sxs-lookup"><span data-stu-id="c25f0-172">On the **Execution summary** page that appears, you can view the status of your export job and a list of the entities that were exported.</span></span> <span data-ttu-id="c25f0-173">W obszarze **Stan przetwarzania jednostki** wybierz jednostkę **Wartość zapasów** z listy, a następnie wybierz opcję **Pobierz plik**, aby pobrać dane wyeksportowane z tej jednostki.</span><span class="sxs-lookup"><span data-stu-id="c25f0-173">In the **Entity processing status** section, select the **Inventory value** entity in the list, and then select **Download file** to download the data that was exported from that entity.</span></span>

<span data-ttu-id="c25f0-174">Aby uzyskać więcej informacji o używaniu funkcji zarządzania danymi do eksportowania danych, patrze [omówienie importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="c25f0-174">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>