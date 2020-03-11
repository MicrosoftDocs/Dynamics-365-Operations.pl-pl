---
title: Raport magazynowy porównania cen pozycji
description: Sposób generowania raportu magazynowego porównania cen pozycji, a następnie przeglądania i/lub eksportowania wyniku.
author: AndersGirke
manager: AnnBe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 80e376db3616af27d94ee55480cd2f56441db93b
ms.sourcegitcommit: 0dace221e8874021dd212271567666f717d39793
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2020
ms.locfileid: "3072122"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="a3416-103">Raport magazynowy porównania cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3416-104">W tym temacie wyjaśniono, jak uruchomić raport **magazynowy porównania cen pozycji** i udostępnić go cyfrowo jako stronę interaktywną w systemie Dynamics 365 Supply Chain Management lub w postaci wyeksportowanego dokumentu w dowolnym z kilku formatów.</span><span class="sxs-lookup"><span data-stu-id="a3416-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="a3416-105">Podczas wyświetlania raportu w przeglądarce kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu.</span><span class="sxs-lookup"><span data-stu-id="a3416-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="a3416-106">Można posortować wyniki, przefiltrować je, przejść do kolejnych danych i wykonać inne zadania.</span><span class="sxs-lookup"><span data-stu-id="a3416-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="a3416-107">Wyniki raportu są przechowywane w jednostce danych **Porównaj ceny towaru**, która umożliwia filtrowanie i eksportowanie wyników do formatu, takiego jak CSV lub Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a3416-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="a3416-108">Raport **porównania cen magazynowych dla towaru** jest przydatny w przypadkach, gdy dane wyjściowe zawierają wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="a3416-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="a3416-109">Na przykład produkcja będzie zawierać wiele wierszy, jeśli w wersji ceny znajduje się więcej niż 40 000 towarów oczekujących cenę pozycji.</span><span class="sxs-lookup"><span data-stu-id="a3416-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="a3416-110">Włącz magazynowe porównanie cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-110">Enable compare item prices storage</span></span>

<span data-ttu-id="a3416-111">Aby móc używać tej funkcji, musisz ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="a3416-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="a3416-112">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="a3416-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="a3416-113">W tym miejscu funkcja jest wyświetlana jako:</span><span class="sxs-lookup"><span data-stu-id="a3416-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="a3416-114">**Moduł** — zarządzanie kosztami</span><span class="sxs-lookup"><span data-stu-id="a3416-114">**Module** - Cost management</span></span>
- <span data-ttu-id="a3416-115">**Nazwa funkcji** — magazynowe porównanie cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="a3416-116">Generowanie raportu magazynowego porównania cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="a3416-117">Wykonaj poniższe kroki, aby wygenerować i zapisać **raport dotyczący porównania cen magazynowych pozycji**:</span><span class="sxs-lookup"><span data-stu-id="a3416-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="a3416-118">Umożliwia przejście do **Zarządzani kosztem > Zapytania i raporty > Raporty wstępnie określonych kosztów > Magazynowe porównanie cen pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="a3416-119">Wybierz opcję **nowy**, aby otworzyć okno **porównanie cen pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="a3416-120">Aby określić, które ceny mają być porównywane w raporcie, należy skonfigurować następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="a3416-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="a3416-121">Ma skróconej karcie **Parametry** podaj unikalną **Nazwę** dla raportu i użyj pól sekcji **Oczekujące ceny do porównania** i **Ceny użyte do porównania** do określenia, które ceny i daty porównać.</span><span class="sxs-lookup"><span data-stu-id="a3416-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="a3416-122">Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych, które mają zostać uwzględnione w raporcie.</span><span class="sxs-lookup"><span data-stu-id="a3416-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="a3416-123">W skróconej karcie **Uruchom w tle** określ, kiedy, jak i z jaką częstotliwością ma być generowany raport.</span><span class="sxs-lookup"><span data-stu-id="a3416-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a3416-124">Ten raport jest zawsze wykonywany w ramach zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="a3416-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="a3416-125">Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko.</span><span class="sxs-lookup"><span data-stu-id="a3416-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="a3416-126">Po zakończeniu zadania wsadowego zostanie ono wyświetlone na stronie **porównywanie cen zapasów**.</span><span class="sxs-lookup"><span data-stu-id="a3416-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="a3416-127">Może być konieczne odświeżenie strony, aby wyświetlić raport.</span><span class="sxs-lookup"><span data-stu-id="a3416-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="a3416-128">Eksploracja raportu magazynowego porównania cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="a3416-129">Po wygenerowaniu raportu można go przeglądać i eksplorować w dowolnym momencie w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a3416-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="a3416-130">Umożliwia przejście do **Zarządzani kosztem > Zapytania i raporty > Raporty wstępnie określonych kosztów > Magazynowe porównanie cen pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="a3416-131">Wybierz raport z listy.</span><span class="sxs-lookup"><span data-stu-id="a3416-131">Select a report from the list.</span></span>

1. <span data-ttu-id="a3416-132">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="a3416-132">Do one of the following:</span></span>

    - <span data-ttu-id="a3416-133">Wybierz **Omówienie**, by wyświetlić przegląd wyników raportu.</span><span class="sxs-lookup"><span data-stu-id="a3416-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="a3416-134">Wybierz **Wyświetl szczegóły**, aby uzyskać bardziej szczegółowy widok raportu</span><span class="sxs-lookup"><span data-stu-id="a3416-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="a3416-135">Po otwarciu wybranego widoku można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a3416-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="a3416-136">Wybierz niemal dowolny nagłówek kolumny, aby posortować lub przefiltrować tabelę według wartości w tej kolumnie, podobnie jak w przypadku większości standardowych formularzy w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a3416-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="a3416-137">Uwaga, nie można sortować ani filtrować kolumn **% zmiany ceny netto**, ponieważ jest to pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="a3416-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="a3416-138">Wybranie opcji **Wyświetlanie wymiarów** umożliwia otwarcie okienka, w którym można wybrać kolumnę wymiaru, która ma zostać uwzględniona w formularzu.</span><span class="sxs-lookup"><span data-stu-id="a3416-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="a3416-139">Ustaw opcję **Zapisz ustawienia** na **tak**, jeśli chcesz zapisać te ustawienia, aby zostały zachowane podczas następnego otwierania raportu.</span><span class="sxs-lookup"><span data-stu-id="a3416-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="a3416-140">Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć.</span><span class="sxs-lookup"><span data-stu-id="a3416-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="a3416-141">Wybierz dowolny wiersz w formularzu, a następnie wybierz opcje **Wyświetl szczegóły**, aby wyświetlić więcej informacji o wybranym towarze.</span><span class="sxs-lookup"><span data-stu-id="a3416-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="a3416-142">W tym miejscu będziesz mieć możliwość przechodzenia do szczegółów danych.</span><span class="sxs-lookup"><span data-stu-id="a3416-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="a3416-143">Zaznacz dowolny wiersz w formularzu, a następnie wybierz opcję **Widok wykresu porównawczego**, aby zobaczyć interaktywną graficzną reprezentację wyników w miarę ich odnoszący się do wybranego elementu.</span><span class="sxs-lookup"><span data-stu-id="a3416-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="a3416-144">Wyniki te można poznać, wybierając różne elementy graficzne w legendzie wykresu i wykresie.</span><span class="sxs-lookup"><span data-stu-id="a3416-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="a3416-145">Wybierz dowolny wiersz w formularzu, a następnie wybierz opcje **Wyświetl szczegóły obliczenia**, aby wyświetlić więcej informacji dotyczących obliczeń dla wybranego towaru.</span><span class="sxs-lookup"><span data-stu-id="a3416-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="a3416-146">W tym miejscu będziesz mieć możliwość przechodzenia do szczegółów danych.</span><span class="sxs-lookup"><span data-stu-id="a3416-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="a3416-147">Eksport raportu magazynowego porównania cen pozycji</span><span class="sxs-lookup"><span data-stu-id="a3416-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="a3416-148">Każdy generowany raport jest przechowywany w jednostce danych **Porównaj ceny towaru**.</span><span class="sxs-lookup"><span data-stu-id="a3416-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="a3416-149">Za pomocą standardowych funkcji Supply Chain Management można eksportować dane z tej jednostki do dowolnego obsługiwanego formatu danych, w tym także do pliku CSV lub programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a3416-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="a3416-150">Poniżej przedstawiono przykład sposobu eksportowania raportu dotyczącego **magazynowego porównania cen pozycji**:</span><span class="sxs-lookup"><span data-stu-id="a3416-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="a3416-151">Wybierz kolejno opcje **Administrowanie systemem > Obszary robocze > Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="a3416-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="a3416-152">Wybierz przycisk **Eksportuj** w sekcji **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="a3416-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="a3416-153">Zostanie otwarta strona **Eksport**, która zostanie użyta do skonfigurowania zadania eksportu.</span><span class="sxs-lookup"><span data-stu-id="a3416-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="a3416-154">Zacznij od nadania **nazwy grupy** zadaniu.</span><span class="sxs-lookup"><span data-stu-id="a3416-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="a3416-155">W sekcji **wybrane jednostki** wybierz opcję **Dodaj jednostkę**, aby otworzyć okno dialogowe, w którym można określić następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="a3416-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="a3416-156">**Nazwa jednostki** — wybierz opcję **Porównaj ceny pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="a3416-157">**Format danych docelowych** — wybierz format, do którego chcesz eksportować dane.</span><span class="sxs-lookup"><span data-stu-id="a3416-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="a3416-158">Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a3416-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="a3416-159">Zazwyczaj w danym momencie można eksportować jeden raport.</span><span class="sxs-lookup"><span data-stu-id="a3416-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="a3416-160">W tym celu należy skonfigurować **filtr** dla wiersza dodanego właśnie do okienka **Zapytanie**.</span><span class="sxs-lookup"><span data-stu-id="a3416-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="a3416-161">Pozwoli to określić, które raporty z jednostki **porównywana cena towaru** mają zostać uwzględnione w eksporcie.</span><span class="sxs-lookup"><span data-stu-id="a3416-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="a3416-162">Aby wyeksportować pojedynczy raport, należy skonfigurować następujące opcje filtrowania:</span><span class="sxs-lookup"><span data-stu-id="a3416-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="a3416-163">Na karcie **zakres** wybierz opcję **Dodaj**, aby dodać nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="a3416-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="a3416-164">Ustaw **Tabela** na **Porównaj ceny pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="a3416-165">Ustaw **Tabela pochodna** na **Porównaj ceny pozycji**.</span><span class="sxs-lookup"><span data-stu-id="a3416-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="a3416-166">Ustaw **Pole** na pole, według którego ma być wykonywane filtrowanie.</span><span class="sxs-lookup"><span data-stu-id="a3416-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="a3416-167">Zazwyczaj używana jest **nazwa wykonania** lub **czas wykonania**.</span><span class="sxs-lookup"><span data-stu-id="a3416-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="a3416-168">Określ **kryteria** dla wartości z wybranego pola, które chcesz wyszukać (nazwę raportu lub godzinę wygenerowania raportu).</span><span class="sxs-lookup"><span data-stu-id="a3416-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="a3416-169">W razie potrzeby Dodaj wiersze do tabeli **zakresu**, dopóki szukany raport nie zostanie jednoznacznie zidentyfikowany.</span><span class="sxs-lookup"><span data-stu-id="a3416-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="a3416-170">Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć.</span><span class="sxs-lookup"><span data-stu-id="a3416-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="a3416-171">Wybierz **Zapisz**, by zapisać ustawienia eksportu.</span><span class="sxs-lookup"><span data-stu-id="a3416-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="a3416-172">Otwórz kartę **opcje eksportu** i wybierz pozycję **Eksportuj teraz**, aby wygenerować plik eksportu.</span><span class="sxs-lookup"><span data-stu-id="a3416-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="a3416-173">Zostanie otwarta strona **podsumowanie wykonania**, na której możesz zobaczyć stan zadania eksportowania oraz listę wyeksportowanych jednostek.</span><span class="sxs-lookup"><span data-stu-id="a3416-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="a3416-174">Wybierz jednostkę **Porównaj ceny towaru** na liście w obszarze **stan przetwarzania jednostki**, a następnie wybierz opcję **Pobierz plik**, aby pobrać dane wyeksportowane z tej jednostki.</span><span class="sxs-lookup"><span data-stu-id="a3416-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="a3416-175">Aby uzyskać więcej informacji o używaniu funkcji zarządzania danymi do eksportowania danych, patrze [omówienie importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="a3416-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
