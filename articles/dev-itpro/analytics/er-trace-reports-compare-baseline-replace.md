---
title: Poprawa śledzenia wyników wygenerowanych raportów ER i porównanie ich z wartościami wyjściowymi
description: Ten temat zawiera informacje o tym, jak ulepszono funkcję linii bazowej ER w Microsoft Dynamics 365 for Finance and Operations wersja 10.0.3 (czerwiec 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 222a415f686c8028fc2a414f97eed0291d850ae7
ms.sourcegitcommit: 9917df8c0c9320955c61186cd922c8df894a4f25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700689"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="fe18a-103">Poprawa śledzenia wyników wygenerowanych raportów ER i porównanie ich z wartościami wyjściowymi</span><span class="sxs-lookup"><span data-stu-id="fe18a-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fe18a-104">W tym temacie wyjaśniono, w jaki sposób można poprawić korzystanie z podstawowej funkcji platformy Elektroniczne raportowanie (ER).</span><span class="sxs-lookup"><span data-stu-id="fe18a-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="fe18a-105">Te poprawki są dostępne w Microsoft Dynamics 365 for Finance and Operations wersja 10.0.3 (czerwiec 2019) i późniejsze.</span><span class="sxs-lookup"><span data-stu-id="fe18a-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="fe18a-106">Zautomatyzuj ustawianie zasad podstawowych</span><span class="sxs-lookup"><span data-stu-id="fe18a-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="fe18a-107">Temat [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) wyjaśnia, jak skonfigurować strukturę ER do zbierania informacji o wykonaniach w formacie ER i oceny wyników tych egzekucji.</span><span class="sxs-lookup"><span data-stu-id="fe18a-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="fe18a-108">Przykład w tym temacie pokazuje kroki, które należy wykonać.</span><span class="sxs-lookup"><span data-stu-id="fe18a-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="fe18a-109">Oto kilka najważniejszych kroków:</span><span class="sxs-lookup"><span data-stu-id="fe18a-109">Here are some of the steps:</span></span>

- <span data-ttu-id="fe18a-110">Uruchom format ER, aby wygenerować plik wychodzący, i zapisz plik lokalnie.</span><span class="sxs-lookup"><span data-stu-id="fe18a-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="fe18a-111">Dodaj plik przechowywany lokalnie jako załącznik linii bazowej dodanej do formatu ER.</span><span class="sxs-lookup"><span data-stu-id="fe18a-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="fe18a-112">Skonfiguruj regułę bazową dla dodanej linii bazowej.</span><span class="sxs-lookup"><span data-stu-id="fe18a-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="fe18a-113">Ta konfiguracja obejmuje następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="fe18a-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="fe18a-114">Ustal format ER, aby wygenerować plik wychodzący, i zapisz plik lokalnie.</span><span class="sxs-lookup"><span data-stu-id="fe18a-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="fe18a-115">Wybierz załącznik, który odnosi się do pliku wychodzącego.</span><span class="sxs-lookup"><span data-stu-id="fe18a-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="fe18a-116">Te kroki muszą być wykonane ręcznie, nawet jeśli nowe możliwości ER umożliwiają ich automatyzację.</span><span class="sxs-lookup"><span data-stu-id="fe18a-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="fe18a-117">Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="fe18a-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="fe18a-118">Przykład: Zautomatyzuj ustawianie zasad linii bazowej</span><span class="sxs-lookup"><span data-stu-id="fe18a-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="fe18a-119">Żeby wykonać te kroki, musisz najpierw wypełnić procedury w temacie [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) aż do "Dodaj nową linię bazową dla wyznaczonego formatu ER".</span><span class="sxs-lookup"><span data-stu-id="fe18a-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="fe18a-120">Przeglądnij dodaną linię bazową</span><span class="sxs-lookup"><span data-stu-id="fe18a-120">Review added baseline</span></span>

1. <span data-ttu-id="fe18a-121">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-122">Wybierz **Linie bazowe**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe18a-123">Przycisk **Linie bazowe** w panelu akcji jest dostępny tylko wtedy, kiedy parametr ER **Uruchom w trybie debugowania** jest włączony dla danej firmy.</span><span class="sxs-lookup"><span data-stu-id="fe18a-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="fe18a-124">Linia bazowa została dodana do **Format do nauki podstawowych linii ER** format, ale zasady linii bazowej nie zostały jeszcze dodane dla tej linii bazowej.</span><span class="sxs-lookup"><span data-stu-id="fe18a-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="fe18a-125">![Strona parametrów elektronicznego raportowania formatu linii bazowych](media/GER-BaselineSample-AddBaseline2.PNG "Zrzut ekranu strony parametrów elektronicznego raportowania formatu linii bazowych")</span><span class="sxs-lookup"><span data-stu-id="fe18a-125">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="fe18a-126">Utwórz nową zasadę bazową</span><span class="sxs-lookup"><span data-stu-id="fe18a-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="fe18a-127">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-128">W widoku drzewa otwórz **Model do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fe18a-129">W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fe18a-130">Na skróconej karcie **Wersje** wybierz **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="fe18a-131">W polu **Wpisz Id** wpisz **1**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="fe18a-132">Ustaw opcję **Zrób pliki linii bazowych** jako **tak**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="fe18a-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-133">Select **OK**.</span></span>

    <span data-ttu-id="fe18a-134">![Okienko parametrów elektronicznego raportowania](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Zrzut ekranu okienka parametrów elektronicznego raportowania")</span><span class="sxs-lookup"><span data-stu-id="fe18a-134">![Electronic report parameters dialog box](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Screenshot of the Electronic report parameters dialog box")</span></span>

8. <span data-ttu-id="fe18a-135">Wybierz **Linie bazowe**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-135">Select **Baselines**.</span></span>

    <span data-ttu-id="fe18a-136">![Strona parametrów elektronicznego raportowania formatu linii bazowych](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Zrzut ekranu strony parametrów elektronicznego raportowania formatu linii bazowych")</span><span class="sxs-lookup"><span data-stu-id="fe18a-136">![Electronic reporting format baselines page](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="fe18a-137">Wygenerowany plik wychodzący został automatycznie dołączony do linii bazowej wykonanego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="fe18a-137">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="fe18a-138">Reguła linii bazowej została automatycznie dodana do tej linii bazowej i zawiera również odniesienie do załączonego pliku.</span><span class="sxs-lookup"><span data-stu-id="fe18a-138">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="fe18a-139">W polu **Nazwa** wpisz **Linia Bazowa 1**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-139">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="fe18a-140">W polu **Maska nazwy pliku** wpisz **.xml**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-140">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="fe18a-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-141">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="fe18a-142">Uruchom format</span><span class="sxs-lookup"><span data-stu-id="fe18a-142">Run the format</span></span>

<span data-ttu-id="fe18a-143">Jesteś gotowy zakończyć pozostałe kroki w [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md) począwszy od „Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki”.</span><span class="sxs-lookup"><span data-stu-id="fe18a-143">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="fe18a-144">Po usunięciu automatycznie dodanej reguły linii bazowej w **linie bazowe** na karcie skróconej przywoływany załącznik nie jest automatycznie usuwany.</span><span class="sxs-lookup"><span data-stu-id="fe18a-144">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="fe18a-145">Skonfiguruj linię bazową, tak aby ignorowała stale zmieniające się części wyjścia ER</span><span class="sxs-lookup"><span data-stu-id="fe18a-145">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="fe18a-146">Skonfiguruj linię bazową, aby ignorować stare zmieniające się części wyjścia ER</span><span class="sxs-lookup"><span data-stu-id="fe18a-146">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="fe18a-147">Na przykład informacje mogą być datą i godziną przetwarzania lub unikalnym identyfikatorem wygenerowanego dokumentu w różnych formatach (unikatowy identyfikator globalny \[GUID\], itd.).</span><span class="sxs-lookup"><span data-stu-id="fe18a-147">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="fe18a-148">Nowe funkcje ER umożliwiają skonfigurowanie reguły linii bazowej, tak aby ignorowała zmienne elementy formatu ER, gdy format jest uruchamiany w celu porównania wartości linii bazowej z wynikami wykonania formatu.</span><span class="sxs-lookup"><span data-stu-id="fe18a-148">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="fe18a-149">Zapoznaj się z poniższym przykładem, aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="fe18a-149">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="fe18a-150">Przykład: Skonfiguruj linię bazową, tak aby ignorowała stale zmieniające się części wyjścia ER</span><span class="sxs-lookup"><span data-stu-id="fe18a-150">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="fe18a-151">Żeby wykonać te kroki, musisz najpierw wypełnić procedury w przykładzie w [Śledź wygenerowane wyniki raportu i porównaj je z wartościami bazowymi](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="fe18a-151">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="fe18a-152">Zmodyfikuj skonfigurowany format ER</span><span class="sxs-lookup"><span data-stu-id="fe18a-152">Modify a configured ER format</span></span>

1. <span data-ttu-id="fe18a-153">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-153">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-154">W widoku drzewa otwórz **Model do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-154">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fe18a-155">W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-155">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fe18a-156">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-156">Select **Designer**.</span></span>
5. <span data-ttu-id="fe18a-157">W widoku drzewa wybierz **Wyjście\\Dokument**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-157">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="fe18a-158">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-158">Select **Add**.</span></span>
7. <span data-ttu-id="fe18a-159">W rozwijanym menu w widoku drzewa wybier **XML\\Attribute**.z</span><span class="sxs-lookup"><span data-stu-id="fe18a-159">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="fe18a-160">W polu **Nazwa** wpisz **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-160">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="fe18a-161">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-161">Select **OK**.</span></span>
10. <span data-ttu-id="fe18a-162">Na karcie **Mapowanie** wybierz **Wyjście\\Dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-162">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="fe18a-163">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-163">Select **Edit formula**.</span></span>
12. <span data-ttu-id="fe18a-164">W polu **Formuła** wpisz: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="fe18a-164">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="fe18a-165">Wybierz **Zapisz** i następnie wybierz **Test**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-165">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="fe18a-166">Wybierz **Test** ponownie, żeby jeszcze raz sprawdzić skonfigurowaną formułę.</span><span class="sxs-lookup"><span data-stu-id="fe18a-166">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="fe18a-167">![Strona projektowania formuły](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Zrzut ekranu strony projektowania formuły")</span><span class="sxs-lookup"><span data-stu-id="fe18a-167">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe18a-168">Karta **Wyniki testu** pokazuje, że skonfigurowane wyrażenie zwraca inną wartość daty i godziny, gdy jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="fe18a-168">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="fe18a-169">Zamknij stronę **Projektowanie formuły** i następnie wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-169">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="fe18a-170">![Strona projektowania formuły](media/GER-BaselineSample-FormatMappingDesign2.PNG "Zrzut ekranu strony Projektowania formuły")</span><span class="sxs-lookup"><span data-stu-id="fe18a-170">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="fe18a-171">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-171">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="fe18a-172">Usuń istniejącą zasadę bazową</span><span class="sxs-lookup"><span data-stu-id="fe18a-172">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="fe18a-173">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-173">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-174">Wybierz **Linie bazowe**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-174">Select **Baselines**.</span></span>
3. <span data-ttu-id="fe18a-175">Na liście linii bazowych wybierz linię, która została skonfigurowana do **Format do nauki podstawowych linii ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-175">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="fe18a-176">Na skróconej karcie **Linie bazowe** wybierz **Usuń**, żeby usunąć zasadę linii bazowej. którą ustaliłes wcześniej.</span><span class="sxs-lookup"><span data-stu-id="fe18a-176">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="fe18a-177">![Strona parametrów elektronicznego raportowania formatu linii bazowych](media/GER-BaselineSample-AddBaseline3.PNG "Zrzut ekranu strony parametrów elektronicznego raportowania formatu linii bazowych")</span><span class="sxs-lookup"><span data-stu-id="fe18a-177">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="fe18a-178">Zdefiniuj zamienniki dla powiązań zaprojektowanego formatu ER</span><span class="sxs-lookup"><span data-stu-id="fe18a-178">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="fe18a-179">Na stonie **Konfiguracje** na skróconej karcie **Zastąpienia** wybierz **Wybierz komponenty**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-179">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="fe18a-180">Na drzewie komponentów formatu rozwiń **Wyjście**, rozwiń **Wyjście\\Dokument**, a następnie zaznacz okienko dla **Wyjście\\Dokument\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-180">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>

    <span data-ttu-id="fe18a-181">![Okienko wyboru komponentów](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Zrzut ekranu okienka wyboru komponentów")</span><span class="sxs-lookup"><span data-stu-id="fe18a-181">![Select Components dialog box](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Screenshot of the Select Components dialog box")</span></span>

3. <span data-ttu-id="fe18a-182">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-182">Select **OK**.</span></span>

<span data-ttu-id="fe18a-183">![Strona parametrów elektronicznego raportowania formatu linii bazowych](media/GER-BaselineSample-AddBaseline4.PNG "Zrzut ekranu strony parametrów elektronicznego raportowania formatu linii bazowych")</span><span class="sxs-lookup"><span data-stu-id="fe18a-183">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="fe18a-184">Wybrany komponent formatu ER został dodany do listy komponentów na skróconej karcie w **Zastąpienia**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-184">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="fe18a-185">Gdy podstawowy format ER jest uruchamiany w trybie debugowania, powiązanie formatu dla każdego komponentu zostanie zastąpione przez powiązanie pokazane w kolumnie **Powiązania**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-185">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="fe18a-186">Aby zmienić domyślne wiązanie dla komponentu wymienionego na skróconej karcie w **Zastąpienia** wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-186">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="fe18a-187">Utwórz nową zasadę bazową</span><span class="sxs-lookup"><span data-stu-id="fe18a-187">Make a new baseline rule</span></span>

<span data-ttu-id="fe18a-188">Wykonaj kroki opisane w sekcji „Przykład: zautomatyzuj ustawienie zasad podstawowych” wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="fe18a-188">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="fe18a-189">Powiadomienie ostrzega, że plik wychodzący został wygenerowany przy użyciu ustawień linii bazowej i wystąpiła wymuszona wymiana powiązań formatu.</span><span class="sxs-lookup"><span data-stu-id="fe18a-189">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="fe18a-190">![Notyfikacja na stonie konfiguracjii](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Zrzut ekranu notyfikacji na stronie Konfiguracji")</span><span class="sxs-lookup"><span data-stu-id="fe18a-190">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="fe18a-191">Pomiń ostrzeżenia dotyczące wymiany powiązań formatu</span><span class="sxs-lookup"><span data-stu-id="fe18a-191">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="fe18a-192">Ustawiając określone parametry ER, można pominąć powiadomienia ostrzegające o zamianie powiązań formatu.</span><span class="sxs-lookup"><span data-stu-id="fe18a-192">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="fe18a-193">To wyłączenie może być przydatne, gdy powiązania formatu są zastępowane w trybie nienadzorowanym za pomocą narzędzia Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="fe18a-193">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="fe18a-194">W takim przypadku ostrzeżenie można uznać za awarię uruchomionego przypadku testowego.</span><span class="sxs-lookup"><span data-stu-id="fe18a-194">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="fe18a-195">na stronie **konfiguracje** na panelu akcji na karcie **Konfiguracje** wybierz **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="fe18a-196">Ustaw **Pomiń ostrzeżenia bazowe** na **Tak**, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-196">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

<span data-ttu-id="fe18a-197">![Okienko parametrów użytkownika](media/GER-BaselineSample-ERUserParameters1.png "Zrzut ekranu okienka parametrów użytkownika")</span><span class="sxs-lookup"><span data-stu-id="fe18a-197">![User parameters dialog box](media/GER-BaselineSample-ERUserParameters1.png "Screenshot of the User parameters dialog box")</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="fe18a-198">Przeglądnij wygenerowany plik bazowy</span><span class="sxs-lookup"><span data-stu-id="fe18a-198">Review the generated baseline file</span></span>

1. <span data-ttu-id="fe18a-199">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-199">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-200">Wybierz **Linie bazowe**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-200">Select **Baselines**.</span></span>
3. <span data-ttu-id="fe18a-201">Wybierz **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-201">Select **Attachments**.</span></span>

    <span data-ttu-id="fe18a-202">![Strona załączników](media/GER-BaselineSample-AttachedBaselineFile.PNG "Zrzut ekranu strony załączników")</span><span class="sxs-lookup"><span data-stu-id="fe18a-202">![Attachments page](media/GER-BaselineSample-AttachedBaselineFile.PNG "Screenshot of the Attachments page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe18a-203">Wygenerowany plik zawiera tekst i datę przetwarzania (**"#"**) z powiązania skonfigurowanego w dodanej regule linii bazowej, a nie z powiązania formatu.</span><span class="sxs-lookup"><span data-stu-id="fe18a-203">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>

4. <span data-ttu-id="fe18a-204">Zamknij stronę **Załączniki**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-204">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="fe18a-205">Uruchom zaprojektowany format ER i przejrzyj dziennik, aby przeanalizować wyniki</span><span class="sxs-lookup"><span data-stu-id="fe18a-205">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="fe18a-206">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-206">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fe18a-207">W widoku drzewa otwórz **Model do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-207">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fe18a-208">W widoku drzewa wybierz **Model do nauki linii bazowych ER\\Format do nauki linii bazowych ER**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-208">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fe18a-209">Na skróconej karcie **Wersje** wybierz **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-209">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="fe18a-210">W polu **Wpisz Id** wpisz **1**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-210">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="fe18a-211">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-211">Select **OK**.</span></span>
7. <span data-ttu-id="fe18a-212">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Dzienniki debugowania konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-212">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="fe18a-213">Dziennik wykonania zawiera informacje o wynikach porównania wygenerowanego pliku ze skonfigurowaną linią bazową.</span><span class="sxs-lookup"><span data-stu-id="fe18a-213">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="fe18a-214">Dziennik wskazuje, że wygenerowany plik i linia bazowa są równe, nawet jeśli wykonany format zawiera powiązanie, aby wprowadzić stale zmieniającą się datę i godzinę w pliku wychodzącym.</span><span class="sxs-lookup"><span data-stu-id="fe18a-214">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="fe18a-215">Mimo że plik wychodzący został wygenerowany przy użyciu ustawień linii bazowej, które wymuszają zastąpienie powiązań formatu, nie otrzymasz żadnych ostrzeżeń o zmianie.</span><span class="sxs-lookup"><span data-stu-id="fe18a-215">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="fe18a-216">Wymień ustawienia linii bazowej między środowiskami</span><span class="sxs-lookup"><span data-stu-id="fe18a-216">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="fe18a-217">Eksportuj ustawień linii bazowej</span><span class="sxs-lookup"><span data-stu-id="fe18a-217">Export baseline settings</span></span>

<span data-ttu-id="fe18a-218">Nowe funkcje ER umożliwiają eksportowanie ustawień podstawowych dla wybranego formatu ER z bieżącego środowiska Finance and Operations i zapisywanie ich jako plików XML.</span><span class="sxs-lookup"><span data-stu-id="fe18a-218">The new ER capabilities let you export baseline settings for the selected ER format from the current Finance and Operations environment and store them as XML files.</span></span> 

<span data-ttu-id="fe18a-219">Aby wyeksportować ustawienia linii bazowej, w przypadku linii bazowych **Elektronicznego formatu raportowania** wybierz opcję **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-219">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="fe18a-220">Importuj ustawienia podstawowe</span><span class="sxs-lookup"><span data-stu-id="fe18a-220">Import baseline settings</span></span>

<span data-ttu-id="fe18a-221">Wyeksportowane ustawienia linii bazowej można zaimportować do innego środowiska Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe18a-221">Exported baseline settings can be imported into a different Finance and Operations environment.</span></span> <span data-ttu-id="fe18a-222">Środowisko należy najpierw zaimportować jako format ER.</span><span class="sxs-lookup"><span data-stu-id="fe18a-222">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="fe18a-223">Możesz importowaćustawienia linii bazowej</span><span class="sxs-lookup"><span data-stu-id="fe18a-223">You can then import the baseline settings.</span></span>

<span data-ttu-id="fe18a-224">Aby zaimportować ustawienia linii bazowej z lokalnie przechowywanego pliku XML, w przypadku linii bazowych na stronie **Elektronicznego formatu raportowania** wybierz **Import**, a następnie wybierz **Przeglądaj**, aby wybrać plik XML.</span><span class="sxs-lookup"><span data-stu-id="fe18a-224">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="fe18a-225">![Okienko importu ustawień linii bazowych](media/GER-BaselineSample-ImportBaseline1.PNG "Zrzut ekranu okienka importu ustawień linii bazowych")</span><span class="sxs-lookup"><span data-stu-id="fe18a-225">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="fe18a-226">Aby zaimportować ustawienia linii bazowej z pliku XML przechowywanego na serwerze Microsoft SharePoint w oparciu o bieżące ustawienia zarządzania dokumentami i wybrany typ dokumentu, w przypadku linii bazowych **Elektronicznego formatu raportowania** wybierz opcję **Import ze źródła**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-226">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="fe18a-227">Następnie wybierz typ dokumentu i plik XML.</span><span class="sxs-lookup"><span data-stu-id="fe18a-227">Then select the document type and the XML file.</span></span> <span data-ttu-id="fe18a-228">Wymagany typ dokumentu, aby uzyskać dostęp do folderu SharePoint należy go wcześniej skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="fe18a-228">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="fe18a-229">![Okienko importu ze źródła](media/GER-BaselineSample-ImportBaseline2.PNG "Zrzut ekranu okienka importu ze źródła")</span><span class="sxs-lookup"><span data-stu-id="fe18a-229">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="fe18a-230">Możesz użyć Rejestratora zadań do zapisania kroków wyboru wymaganego typu dokumentu i nazwy pliku w oknie dialogowym **Import ze źródła**.</span><span class="sxs-lookup"><span data-stu-id="fe18a-230">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="fe18a-231">W ten sposób można zachować wymagane ustawienia linii bazowej na serwerze SharePoint, a następnie automatycznie zaimportować je, odtwarzając nagranie zadania po uruchomieniu automatycznych testów za pomocą narzędzia Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="fe18a-231">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe18a-232">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fe18a-232">Additional resources</span></span>

- [<span data-ttu-id="fe18a-233">Śledzenie wyników wygenerowanych raportów i porównywanie ich z wartościami bazowymi</span><span class="sxs-lookup"><span data-stu-id="fe18a-233">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="fe18a-234">Rejestrator zadań</span><span class="sxs-lookup"><span data-stu-id="fe18a-234">Task recorder</span></span>](../user-interface/task-recorder.md)
