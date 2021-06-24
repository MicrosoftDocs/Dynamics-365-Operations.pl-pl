---
title: Rozwiązywanie problemów z wydajnością w konfiguracjach ER
description: W tym temacie opisano sposób wykrywania i usuwania problemów z wydajnością w konfiguracjach raportowania elektronicznego (ER).
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216872"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="aee47-103">Rozwiązywanie problemów z wydajnością w konfiguracjach ER</span><span class="sxs-lookup"><span data-stu-id="aee47-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="aee47-104">W tym temacie opisano sposób wykrywania i usuwania problemów z wydajnością w [konfiguracjach](general-electronic-reporting.md#Configuration) [raportowania elektronicznego (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="aee47-105">Zazwyczaj badanie wydajności składa się z kilku kroków.</span><span class="sxs-lookup"><span data-stu-id="aee47-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="aee47-106">[Zebranie](#collecting-data) danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="aee47-107">Analizowanie zebranych danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="aee47-108">Na podstawie wyników analizy użycie konfiguracji ER, aby [wprowadzić zmiany](#making-changes) lub zdecydować się na zebranie większej ilości danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="aee47-109">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="aee47-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="aee47-110">Analizowanie czasu wykonania</span><span class="sxs-lookup"><span data-stu-id="aee47-110">Analyze execution time</span></span>

<span data-ttu-id="aee47-111">Czas wykonania może zależeć od nieprzewidywalnych czynników, takich jak inne zadania, które działają w tym samym środowisku oraz buforowanie, które wykorzystuje dane, gdy jest wywoływane po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="aee47-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="aee47-112">Dlatego należy kilkakrotnie powtórzyć wykonanie i pomiar.</span><span class="sxs-lookup"><span data-stu-id="aee47-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="aee47-113">Czasami problemy z wydajnością nie są spowodowane konfiguracją formatu ER, który jest używany do raportowania.</span><span class="sxs-lookup"><span data-stu-id="aee47-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="aee47-114">Zamiast tego, są one powodowane przez kod X++, który jest używany do otwarcia konfiguracji formatu ER.</span><span class="sxs-lookup"><span data-stu-id="aee47-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="aee47-115">W [Centrum akcji](#infolog-time) lub [w dzienniku zdarzeń](#event-log-time) przyjrzyj się czasowi wykonania raportu.</span><span class="sxs-lookup"><span data-stu-id="aee47-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="aee47-116">Porównaj czas wykonania raportu z całkowitym czasem wykonania w scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="aee47-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="aee47-117">Jeśli czas wykonania raportu jest znacznie mniejszy niż całkowity czas wykonania, należy rozważyć ilość danych przetwarzanych przez raport:</span><span class="sxs-lookup"><span data-stu-id="aee47-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="aee47-118">Jeśli raport przetwarza niewielką ilość danych, problem może dotyczyć czasu ładowania konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aee47-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="aee47-119">Jeśli raport przetwarza dużą ilość danych, problem może dotyczyć wstępnego przetwarzania X++.</span><span class="sxs-lookup"><span data-stu-id="aee47-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="aee47-120">Użyj [Trace parsera](#analyze-trace-parser-trace) do analizy sprawy.</span><span class="sxs-lookup"><span data-stu-id="aee47-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="aee47-121">W innych przypadkach zobacz następne sekcje.</span><span class="sxs-lookup"><span data-stu-id="aee47-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="aee47-122">Uruchom wiele testów, które zawierają różne ilości danych, aby określić, jak czas wykonania zależy od ilości danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="aee47-123">Śledzenie danych za pomocą programu Trace Parser</span><span class="sxs-lookup"><span data-stu-id="aee47-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="aee47-124">Przygotuj mały przykład, lub zbierz kilka śladów podczas losowo wybranych części generowania raportu.</span><span class="sxs-lookup"><span data-stu-id="aee47-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="aee47-125">Następnie w [Trace parserze](#trace-parser) wykonaj standardową analizę od dołu do góry i odpowiedz na następujące pytania:</span><span class="sxs-lookup"><span data-stu-id="aee47-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="aee47-126">Jakie są najlepsze metody pod względem zużycia czasu?</span><span class="sxs-lookup"><span data-stu-id="aee47-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="aee47-127">Jaką część całkowitego czasu wykorzystują te metody?</span><span class="sxs-lookup"><span data-stu-id="aee47-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="aee47-128">Odpowiedz na te same pytania dla zapytań.</span><span class="sxs-lookup"><span data-stu-id="aee47-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="aee47-129">Jeśli widzisz, że metody są poprzedzone „ER”, przejdź do następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="aee47-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="aee47-130">Jeśli widzisz, że metody lub kwerendy pochodzą z pakietu aplikacji, należy wziąć pod uwagę ogólne optymalizacje (na przykład utworzyć indeksy).</span><span class="sxs-lookup"><span data-stu-id="aee47-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="aee47-131">Analiza liczby połączeń.</span><span class="sxs-lookup"><span data-stu-id="aee47-131">Analyze the number of calls.</span></span> <span data-ttu-id="aee47-132">Jeśli liczba jest znacznie wyższa niż oczekiwano, należy rozważyć buforowanie odpowiednich węzłów konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aee47-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="aee47-133">Analizowanie wywołań bazy danych</span><span class="sxs-lookup"><span data-stu-id="aee47-133">Analyze database calls</span></span>

<span data-ttu-id="aee47-134">Przygotuj przykład, który ma niewielką ilość danych, dzięki czemu można zebrać [ślad ER](#electronic-reporting-traces).</span><span class="sxs-lookup"><span data-stu-id="aee47-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="aee47-135">Następnie otwórz śledzenie w projektancie mapowania modelu ER i spójrz na dół- strony.</span><span class="sxs-lookup"><span data-stu-id="aee47-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="aee47-136">Odpowiedz na następujące pytania:</span><span class="sxs-lookup"><span data-stu-id="aee47-136">Answer the following questions:</span></span>

- <span data-ttu-id="aee47-137">Czy istnieje jakaś duplikacja kwerend?</span><span class="sxs-lookup"><span data-stu-id="aee47-137">Is there any query duplication?</span></span> <span data-ttu-id="aee47-138">Jeśli tak, rozważ jedną z następujących poprawek:</span><span class="sxs-lookup"><span data-stu-id="aee47-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="aee47-139">[Użyj buforowania](#use-caching), jeśli uważasz, że istnieje kilka wywołań wewnątrz jednego rekordu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="aee47-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="aee47-140">[Użyj buforowanego, sparametryzowanego pola obliczeniowego](#cached-parameterized), jeśli uważasz, że istnieją wywołania tego samego rekordu wewnątrz różnych rekordów.</span><span class="sxs-lookup"><span data-stu-id="aee47-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="aee47-141">[Użyj źródła danych **JOIN**](#use-join-datasource), jeśli trzeba odczytać do znacznej liczby różnych rekordów z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="aee47-142">Czy liczba zapytań i pobranych rekordów odpowiada ogólnej ilości danych?</span><span class="sxs-lookup"><span data-stu-id="aee47-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="aee47-143">Na przykład jeśli dokument ma 10 wierszy, czy statystyki pokazują, że raport wyodrębnia 10 wierszy lub 1000 wierszy?</span><span class="sxs-lookup"><span data-stu-id="aee47-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="aee47-144">Jeśli masz znaczną liczbę pobranych rekordów, należy wziąć pod uwagę jedną z następujących poprawek:</span><span class="sxs-lookup"><span data-stu-id="aee47-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="aee47-145">[Użyj funkcji **FILTER** zamiast funkcji **WHERE**](#filter) do przetwarzania danych po stronie programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aee47-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="aee47-146">Użyj buforowania, aby uniknąć pobierania tych samych danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="aee47-147">[Użyj funkcji zebranych danych](#collected-data), aby uniknąć pobierania tych samych danych do podsumowania.</span><span class="sxs-lookup"><span data-stu-id="aee47-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="aee47-148">Analizowanie śladów PerfView</span><span class="sxs-lookup"><span data-stu-id="aee47-148">Analyze PerfView traces</span></span>

<span data-ttu-id="aee47-149">[PerfView](#perfview) to narzędzie dla doświadczonych programistów.</span><span class="sxs-lookup"><span data-stu-id="aee47-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="aee47-150">Aby uzyskać bardziej szczegółowe informacje na temat następujących kroków, zobacz [Zegar ścienny – podstawy badania czasu](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span><span class="sxs-lookup"><span data-stu-id="aee47-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="aee47-151">Zbieranie śledzenia przy użyciu czasu wątku.</span><span class="sxs-lookup"><span data-stu-id="aee47-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="aee47-152">Uwzględnij tylko stosy, które używają **runUnattended**, aby filtrować tylko wątek, który ma wykonanie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="aee47-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="aee47-153">(Dodaj **runUnattended** do pola wejściowego **IncPats**.)</span><span class="sxs-lookup"><span data-stu-id="aee47-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="aee47-154">Złóż cały czas procesora, sieci i zablokowany czas.</span><span class="sxs-lookup"><span data-stu-id="aee47-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="aee47-155">Załaduj [ustawienia ER dla PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="aee47-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="aee47-156">Wybierz **ER** \> **Inne ustawienia predefiniowane**.</span><span class="sxs-lookup"><span data-stu-id="aee47-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="aee47-157">Spójrz na nazwy:</span><span class="sxs-lookup"><span data-stu-id="aee47-157">Look at the names:</span></span>

    - <span data-ttu-id="aee47-158">Prawdopodobnie zobaczysz kod platformy, która zużywa najwięcej czasu.</span><span class="sxs-lookup"><span data-stu-id="aee47-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="aee47-159">Możesz dwukrotnie stuknąć (lub dwukrotnie kliknąć) i przejść w górę przez **wywoływane**.</span><span class="sxs-lookup"><span data-stu-id="aee47-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="aee47-160">Jeśli znajdziesz klasy, które mają prefiks „ERExpression” i jeśli są to funkcje, które są związane z formułami, można odgadnąć nazwę funkcji na podstawie nazwy klasy i można spojrzeć na repozytorium ER, aby wyświetlić atrybuty.</span><span class="sxs-lookup"><span data-stu-id="aee47-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="aee47-161">Poprawki</span><span class="sxs-lookup"><span data-stu-id="aee47-161">Fixes</span></span>

- <span data-ttu-id="aee47-162">Jeśli widzisz, że większość czasu procesora jest zużywana przez kwerendy, spróbuj zmniejszyć liczbę zapytań:</span><span class="sxs-lookup"><span data-stu-id="aee47-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="aee47-163">[Przejrzyj śledzenie ER](#analyze-database-calls) dla zduplikowanych zapytań.</span><span class="sxs-lookup"><span data-stu-id="aee47-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="aee47-164">Zobacz, ile rekordów jest pobieranych i oceń, ile danych teoretycznie powinno być pobieranych.</span><span class="sxs-lookup"><span data-stu-id="aee47-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="aee47-165">Jeśli widzisz, że większość czasu procesora jest zużywana przez funkcje, które są używane, spróbuj znaleźć miejsce w konfiguracji, które zużywa najwięcej zasobów.</span><span class="sxs-lookup"><span data-stu-id="aee47-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="aee47-166">Jeśli widzisz, że większość czasu procesora jest zużywana przez funkcje zbierania danych, rozważ zastąpienie ich przez *Grupuj w/g SQL* po stronie mapowania modelu.</span><span class="sxs-lookup"><span data-stu-id="aee47-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="aee47-167">Gromadzenie danych</span><span class="sxs-lookup"><span data-stu-id="aee47-167">Collecting data</span></span>

<span data-ttu-id="aee47-168">W zależności od środowiska istnieje kilka sposobów zbierania dostępnych danych:</span><span class="sxs-lookup"><span data-stu-id="aee47-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="aee47-169">Uzyskanie całkowitego czasu pracy:</span><span class="sxs-lookup"><span data-stu-id="aee47-169">Get the total running time:</span></span>

    - <span data-ttu-id="aee47-170">Z Centrum akcji</span><span class="sxs-lookup"><span data-stu-id="aee47-170">From the Action center</span></span>
    - <span data-ttu-id="aee47-171">Z dziennika zdarzeń</span><span class="sxs-lookup"><span data-stu-id="aee47-171">From the event log</span></span>

- <span data-ttu-id="aee47-172">Wykonanie profilu:</span><span class="sxs-lookup"><span data-stu-id="aee47-172">Profile the execution:</span></span>

    - <span data-ttu-id="aee47-173">Za pomocą narzędzi ER</span><span class="sxs-lookup"><span data-stu-id="aee47-173">By using ER tools</span></span>
    - <span data-ttu-id="aee47-174">Za pomocą analizatora śledzenia</span><span class="sxs-lookup"><span data-stu-id="aee47-174">By using Trace parser</span></span>
    - <span data-ttu-id="aee47-175">Za pomocą PerfView</span><span class="sxs-lookup"><span data-stu-id="aee47-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="aee47-176">Gromadzenie danych w środowisku produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="aee47-176">Collecting data in a production environment</span></span>

<span data-ttu-id="aee47-177">Czasami problemy mogą być powielane tylko w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="aee47-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="aee47-178">Istnieją następujące sposoby gromadzenia danych:</span><span class="sxs-lookup"><span data-stu-id="aee47-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="aee47-179">Śledzenie danych za pomocą programu [Trace Parser](../perf-test/trace-trace-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="aee47-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="aee47-180">Za pomocą śladów [wykonania ER](trace-execution-er-troubleshoot-perf.md)</span><span class="sxs-lookup"><span data-stu-id="aee47-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="aee47-181">Korzystając z całkowitego czasu wykonania</span><span class="sxs-lookup"><span data-stu-id="aee47-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="aee47-182">Gromadzenie danych w środowisku projektowym</span><span class="sxs-lookup"><span data-stu-id="aee47-182">Collecting data in a development environment</span></span>

<span data-ttu-id="aee47-183">Oprócz narzędzi, które mogą być używane w środowisku produkcyjnym, istnieje kilka narzędzi, których można używać w środowisku programistycznym:</span><span class="sxs-lookup"><span data-stu-id="aee47-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="aee47-184">Dziennik zdarzeń (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="aee47-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="aee47-185">Ten dziennik może dać ci całkowity czas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="aee47-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="aee47-186">Typowe narzędzia .NET, takie jak PerfView.</span><span class="sxs-lookup"><span data-stu-id="aee47-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="aee47-187">Ponadto środowisko programistyczne zapewnia większą elastyczność eksperymentowania.</span><span class="sxs-lookup"><span data-stu-id="aee47-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="aee47-188">Na przykład można wyłączyć części raportów, aby zobaczyć, jak wpływa to na czas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="aee47-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="aee47-189">Narzędzia</span><span class="sxs-lookup"><span data-stu-id="aee47-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="aee47-190">Czas wykonania w Centrum akcji</span><span class="sxs-lookup"><span data-stu-id="aee47-190">Execution time in the Action center</span></span>

<span data-ttu-id="aee47-191">ER może pokazać czas wykonania konfiguracji w Centrum akcji.</span><span class="sxs-lookup"><span data-stu-id="aee47-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="aee47-192">Ta opcja działa tylko dla określonego użytkownika i określonej firmy i tylko dla sesji interaktywnych.</span><span class="sxs-lookup"><span data-stu-id="aee47-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="aee47-193">Aby udostępnić tę funkcję, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="aee47-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="aee47-194">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="aee47-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="aee47-195">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="aee47-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="aee47-196">W oknie dialogowym **Parametry użytkownika** ustaw opcję **Pokaż czas wygenerowania pliku** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="aee47-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="aee47-197">Czas wykonania w dzienniku zdarzeń</span><span class="sxs-lookup"><span data-stu-id="aee47-197">Execution time in the event log</span></span>

1. <span data-ttu-id="aee47-198">Otwórz przeglądarkę zdarzeń systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="aee47-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="aee47-199">W obszarze **Dzienniki aplikacji i usług** otwórz okno **Microsoft-Dynamics-ElectronicReporting/Operational**.</span><span class="sxs-lookup"><span data-stu-id="aee47-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="aee47-200">Poszukaj zdarzeń **FormatMapingRun**, gdzie **EventID=2**, ponieważ te zdarzenia zawierają informacje o upływie czasu.</span><span class="sxs-lookup"><span data-stu-id="aee47-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="aee47-201">Śledzenie danych za pomocą programu Trace Parser</span><span class="sxs-lookup"><span data-stu-id="aee47-201">Trace parser traces</span></span> 

<span data-ttu-id="aee47-202">Ponieważ ER jest zaimplementowany w X++, możesz użyć typowych narzędzi X++ do analizy wydajności.</span><span class="sxs-lookup"><span data-stu-id="aee47-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="aee47-203">Aby uzyskać więcej informacji, zobacz temat [Śledzenie przy użyciu programu Trace Parser](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="aee47-204">To podejście ma kilka ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="aee47-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="aee47-205">Ponieważ część ER jest zaimplementowana w języku C#, nie wszystkie szczegóły będą dostępne.</span><span class="sxs-lookup"><span data-stu-id="aee47-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="aee47-206">Można jednak wyświetlić szczegóły dotyczące użycia danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-206">However, you can view the data usage details.</span></span> <span data-ttu-id="aee47-207">Ponadto długie raporty mogą przekraczać limity śledzenia przechowywania.</span><span class="sxs-lookup"><span data-stu-id="aee47-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="aee47-208">Śledzenie ER</span><span class="sxs-lookup"><span data-stu-id="aee47-208">ER traces</span></span>

<span data-ttu-id="aee47-209">Narzędzie ER może zbierać własne dane śledzenia oraz ma narzędzia wizualizacji i analizy tych danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="aee47-210">Aby uzyskać więcej informacji, zobacz [Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="aee47-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="aee47-211">PerfView</span></span>

<span data-ttu-id="aee47-212">Ponieważ zarówno X++ jak i ER są zaimplementowane na platformie .NET, można używać typowych narzędzi .NET.</span><span class="sxs-lookup"><span data-stu-id="aee47-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="aee47-213">Można na przykład użyć bezpłatnego narzędzia [PerfView](https://github.com/Microsoft/perfview).</span><span class="sxs-lookup"><span data-stu-id="aee47-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="aee47-214">Można także zbierać dane z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="aee47-214">You can also collect data from the command line.</span></span> <span data-ttu-id="aee47-215">Na przykład, poniższy skrypt Windows PowerShell zbiera czas wykonania do momentu zatrzymania wykonywania dowolnego formatu na maszynie.</span><span class="sxs-lookup"><span data-stu-id="aee47-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="aee47-216">To podejście ma kilka ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="aee47-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="aee47-217">Musisz mieć dostęp administracyjny do maszyny.</span><span class="sxs-lookup"><span data-stu-id="aee47-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="aee47-218">Dodatkowo, musisz być doświadczonym programistą, ponieważ krzywa uczenia się jest bardzo stroma.</span><span class="sxs-lookup"><span data-stu-id="aee47-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="aee47-219">Dokonywanie zmian</span><span class="sxs-lookup"><span data-stu-id="aee47-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="aee47-220">Użyj buforowania</span><span class="sxs-lookup"><span data-stu-id="aee47-220">Use caching</span></span>

<span data-ttu-id="aee47-221">Chociaż buforowanie zmniejsza ilość czasu, który jest wymagany do ponownego pobrania danych, kosztuje pamięć.</span><span class="sxs-lookup"><span data-stu-id="aee47-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="aee47-222">Używaj buforowania w przypadkach, gdy ilość pobieranych danych nie jest zbyt duża.</span><span class="sxs-lookup"><span data-stu-id="aee47-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="aee47-223">Więcej informacji oraz przykład pokazujący jak używać buforowania można znaleźć w [Ulepszanie odwzorowania modelu na podstawie informacji ze śladu wykonania](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span><span class="sxs-lookup"><span data-stu-id="aee47-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="aee47-224">Użyj buforowanych, parametryzowanych pól obliczeniowych</span><span class="sxs-lookup"><span data-stu-id="aee47-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="aee47-225">Czasami wartości muszą być szukane wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="aee47-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="aee47-226">Przykłady: nazwy kont i numery kont.</span><span class="sxs-lookup"><span data-stu-id="aee47-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="aee47-227">Aby zaoszczędzić czas, można utworzyć pole obliczeniowe z parametrami najwyższego poziomu, a następnie dodać je do pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="aee47-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="aee47-228">Zaleca się, aby tej metody użyć tylko wtedy, gdy rozmiar danych w pamięci podręcznej jest mały.</span><span class="sxs-lookup"><span data-stu-id="aee47-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="aee47-229">Aby uzyskać więcej informacji, zobacz temat [Usprawnij działanie rozwiązań ER, dodając OBLICZANE POLA jako źródła danych](er-calculated-field-ds-performance.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="aee47-230">Używanie JOIN jako źródła danych</span><span class="sxs-lookup"><span data-stu-id="aee47-230">Use a JOIN data source</span></span>

<span data-ttu-id="aee47-231">Źródło danych **JOIN** umożliwia pobranie kilku połączonych rekordów przez jedną kwerendę.</span><span class="sxs-lookup"><span data-stu-id="aee47-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="aee47-232">Do pobrania każdego połączonego rekordu nie musi być używana osobna kwerenda.</span><span class="sxs-lookup"><span data-stu-id="aee47-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="aee47-233">Na przykład, jeśli masz 1 000 wierszy i pobierasz dane pozycji dla każdego wiersza przez relację, będziesz miał 1 001 zapytań (= 1 000 + 1).</span><span class="sxs-lookup"><span data-stu-id="aee47-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="aee47-234">W przypadku użycia źródła danych **JOIN** można pobierać te same dane tylko jedną kwerendą.</span><span class="sxs-lookup"><span data-stu-id="aee47-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="aee47-235">Aby uzyskać więcej informacji, zob. [Użyj źródeł danych JOIN w odwzorowaniach modelu ER, aby uzyskać dane z wielu tabel aplikacji](er-join-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="aee47-236">Użyj funkcji FILTER zamiast funkcji WHERE</span><span class="sxs-lookup"><span data-stu-id="aee47-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="aee47-237">Funkcja **[FILTER](er-functions-list-filter.md)** uruchamia warunki na serwerze SQL, podczas gdy funkcja **WHERE** pobiera wszystkie dane z listy, jeden rekord na raz i stosuje warunek do każdego rekordu.</span><span class="sxs-lookup"><span data-stu-id="aee47-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="aee47-238">Na przykład chcesz wybrać jeden rekord z 1000 rekordów.</span><span class="sxs-lookup"><span data-stu-id="aee47-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="aee47-239">W przypadku użycia **WHERE** zostanie pobranych wszystkie 1000 rekordów.</span><span class="sxs-lookup"><span data-stu-id="aee47-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="aee47-240">Jednak w przypadku użycia **FILTER** zostanie pobrany dokładnie jeden rekord.</span><span class="sxs-lookup"><span data-stu-id="aee47-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="aee47-241">**FILTER** może również używać indeksów po stronie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="aee47-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="aee47-242">Korzystanie ze zebranych funkcji danych lub skumulowanego źródła danych</span><span class="sxs-lookup"><span data-stu-id="aee47-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="aee47-243">Jeśli konfiguracja zawiera składnik *grupuj według*, który podsumowuje poprzednio pobrane dane według raportu, składnik ponownie pobierze wszystkie dane.</span><span class="sxs-lookup"><span data-stu-id="aee47-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="aee47-244">Funkcja zbieranych danych umożliwia ER gromadzenie danych podczas pierwszego pobrania.</span><span class="sxs-lookup"><span data-stu-id="aee47-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="aee47-245">Aby uzyskać więcej informacji, zobacz [Konfigurowanie formatu ER w celu zliczania i sumowania](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="aee47-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="aee47-246">Przepisanie części konfiguracji w X++</span><span class="sxs-lookup"><span data-stu-id="aee47-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="aee47-247">ER obsługuje wywoływanie metod tabel i klas, w tym rozszerzeń.</span><span class="sxs-lookup"><span data-stu-id="aee47-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="aee47-248">Rozważ przepisanie części odwzorowania modelu w X++, aby poprawić wydajność.</span><span class="sxs-lookup"><span data-stu-id="aee47-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="aee47-249">ER może pobierać dane z następujących źródeł:</span><span class="sxs-lookup"><span data-stu-id="aee47-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="aee47-250">Klasy (źródła danych **obiekt** i **klasa**)</span><span class="sxs-lookup"><span data-stu-id="aee47-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="aee47-251">Tabele (źródła danych **tabela** i **rekordy tabeli**)</span><span class="sxs-lookup"><span data-stu-id="aee47-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="aee47-252">Interfejs [API ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) także oferuje sposób wysyłania wstępnie obliczonych danych z wywołującego kodu.</span><span class="sxs-lookup"><span data-stu-id="aee47-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="aee47-253">Pakiet aplikacji zawiera wiele przykładów tego podejścia.</span><span class="sxs-lookup"><span data-stu-id="aee47-253">The application suite contains numerous examples of this approach.</span></span>
