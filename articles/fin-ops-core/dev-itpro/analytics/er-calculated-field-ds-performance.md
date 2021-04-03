---
title: Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH
description: W tym temacie wyjaśniono, w jaki sposób można usprawnić działanie rozwiązań raportowania elektronicznego (ER), dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c63d64774b5b97a562da20655400078ed47c5675
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569232"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="c4b53-103">Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH</span><span class="sxs-lookup"><span data-stu-id="c4b53-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4b53-104">W tym temacie wyjaśniono, w jaki sposób można pobierać [dane śledzenia wydajności](trace-execution-er-troubleshoot-perf.md) dla uruchomionych formatów [raportowania elektronicznego (ER)](general-electronic-reporting.md), a następnie używać informacji z tych procesów w celu zwiększenia wydajności, konfigurując źródło danych dla sparametryzowanych **pól obliczeniowych**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="c4b53-105">W ramach procesu projektowania konfiguracji raportowania elektronicznego (ER) w celu generowania dokumentów biznesowych należy zdefiniować metodę, która jest używana do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="c4b53-106">Po zaprojektowaniu wstępnie zdefiniowanego źródła danych dla **Pola obliczeniowego** można zmniejszyć liczbę wywołań bazy danych i znacząco zredukować czas i koszt, który ma być związany z zbieraniem szczegółów dotyczących wykonania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c4b53-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="c4b53-107">Prerequisites</span></span>

- <span data-ttu-id="c4b53-108">Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do jednej z następujących [ról](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="c4b53-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="c4b53-109">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="c4b53-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="c4b53-110">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="c4b53-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="c4b53-111">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="c4b53-111">System administrator</span></span>

- <span data-ttu-id="c4b53-112">Firmę należy ustawić na wartość **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="c4b53-113">Wykonaj kroki opisane w [dodatku 1](#appendix1) do tego tematu, aby pobrać składniki przykładowego rozwiązania Microsoft ER wymagane do przetwarzania płatności dostawców.</span><span class="sxs-lookup"><span data-stu-id="c4b53-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="c4b53-114">Postępuj zgodnie z krokami opisanymi w [dodatku 2](#appendix2) do tego tematu, aby skonfigurować minimalny zestaw parametrów funkcji ER, który jest wymagany w celu zwiększenia wydajności przykładowego rozwiązania Microsoft ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="c4b53-115">Importuj przykładowe rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-115">Import the sample ER solution</span></span>

<span data-ttu-id="c4b53-116">Załóżmy, że rozpoczęto projektowanie nowego rozwiązania ER w celu wygenerowania nowego raportu, który przedstawia transakcje dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c4b53-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="c4b53-117">Dotychczas transakcje wybranego dostawcy można było znaleźć na stronie **Transakcje dostawcy** (przejdź do **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**, wybierz dostawcę, a następnie, w okienku akcji, na karcie **Dostawca**, w grupie **Transakcje** wybierz opcję **Transakcje**).</span><span class="sxs-lookup"><span data-stu-id="c4b53-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="c4b53-118">Chcesz jednak mieć wszystkie transakcje dostawcy w jednym dokumencie elektronicznym w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="c4b53-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="c4b53-119">To rozwiązanie będzie składać się z kilku konfiguracji ER, które zawierają wymagany model danych, metadane, mapowanie modeli i składniki formatu.</span><span class="sxs-lookup"><span data-stu-id="c4b53-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="c4b53-120">Pierwszym krokiem jest zaimportowanie przykładowego rozwiązania ER w celu wygenerowania raportu transakcji dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c4b53-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="c4b53-121">Zaloguj się do wystąpienia Microsoft Dynamics 365 Finance, które zostało zainicjowane dla danej firmy.</span><span class="sxs-lookup"><span data-stu-id="c4b53-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="c4b53-122">W tym temacie utworzysz i zmodyfikujesz konfiguracje dla przykładowej firmy **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="c4b53-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="c4b53-123">Upewnij się zatem, że ten dostawca konfiguracji jest dodany do wystąpienia Finance i wybrany jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="c4b53-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="c4b53-124">Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c4b53-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="c4b53-125">W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="c4b53-126">Na stronie **Konfiguracje** zaimportuj konfiguracje ER, które zostały pobrane jako wstępnie wymagane do Finance, w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="c4b53-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="c4b53-127">Dla każdej konfiguracji wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="c4b53-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="c4b53-128">W okienku akcji wybierz opcję **Wymiana** \> **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="c4b53-129">Kliknij przycisk **Przeglądaj** i wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="c4b53-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="c4b53-130">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-130">Select **OK**.</span></span>

![Zaimportowane konfiguracje na stronie Konfiguracje](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="c4b53-132">Przejrzyj przykładowe rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="c4b53-133">Przeglądanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="c4b53-133">Review the model mapping</span></span>

1. <span data-ttu-id="c4b53-134">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model poprawy wydajności**, a potem wybierz **Mapowanie poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="c4b53-135">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="c4b53-136">Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Modelowanie do mapowania źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="c4b53-137">W tym mapowaniu modelu ER jest przeznaczony do wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c4b53-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="c4b53-138">Umożliwia pobieranie listy transakcji dostawcy, które są przechowywane w tabeli VendTrans (Źródło danych **transakcji**).</span><span class="sxs-lookup"><span data-stu-id="c4b53-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="c4b53-139">Dla każdej transakcji należy pobrać z tabeli VendTable rekord dostawcy, dla którego zaksięgowano transakcję (Źródło danych **\#Dostawca**).</span><span class="sxs-lookup"><span data-stu-id="c4b53-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4b53-140">Źródło danych **\#Dostawca** jest skonfigurowane do pobierania odpowiedniego rekordu dostawcy przy użyciu istniejącej relacji wiele-do-jednego **\@.'\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="c4b53-141">Mapowanie modelu w tej konfiguracji implementuje podstawowy model danych dla dowolnego formatu ER utworzonego dla tego modelu i wykonywanego w Finance.</span><span class="sxs-lookup"><span data-stu-id="c4b53-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="c4b53-142">W wyniku tego zawartość źródeł danych **Transakcji** jest udostępniana dla formatów ER, takich jak **modelowe** źródła danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Dodano źródło danych transakcji w konstruktorze mapowania modelu](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="c4b53-144">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="c4b53-145">Zamknij stronę **Mapowanie modelu do źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="c4b53-146">Format przeglądu</span><span class="sxs-lookup"><span data-stu-id="c4b53-146">Review format</span></span>

1. <span data-ttu-id="c4b53-147">Na stronie **Konfiguracje** w drzewie konfiguracji w panelu po lewej wybierz pozycję **Model poprawy wydajności**, a potem wybierz **Format poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="c4b53-148">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="c4b53-149">Na stronie **Projektant formatów**, na karcie **Mapowanie** wybierz **Zwiń/Rozwiń**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="c4b53-150">Rozwiń **Model**, **Dane,** i **Transakcja**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="c4b53-151">Ten format ER jest przeznaczony do generowania raportu transakcji dostawcy w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="c4b53-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Formatowanie źródeł danych i skonfigurowanych powiązań elementów formatu na stronie Projektant formatów](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="c4b53-153">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="c4b53-154">Uruchom przykładowe rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="c4b53-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="c4b53-155">Załóżmy, że zakończono projektowanie pierwszej wersji rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="c4b53-156">Chcesz teraz przetestować je w swoim wystąpieniu Finance oraz przeanalizować wydajność wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c4b53-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="c4b53-157">Włączanie śledzenia wydajności ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="c4b53-158">Wybierz pole firmę **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="c4b53-159">Przejdź przez kroki w [Włączanie śledzenia wydajności ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace), aby wygenerować śledzenie wydajności podczas uruchamiania formatu encji, gdy wykonywany jest format ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![Okno dialogowe parametry użytkownika](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="c4b53-161">Uruchamianie formatu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-161">Run the ER format</span></span>

1. <span data-ttu-id="c4b53-162">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="c4b53-163">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Format poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="c4b53-164">W okienku akcji wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="c4b53-165">Śledzenie wydajności umożliwia analizowanie wydajności mapowania modeli</span><span class="sxs-lookup"><span data-stu-id="c4b53-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="c4b53-166">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="c4b53-167">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="c4b53-168">Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="c4b53-169">Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="c4b53-170">Wybierz najnowszy wygenerowany wynik śledzenia, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="c4b53-171">Zostaną teraz udostępnione nowe informacje dotyczące niektórych pozycji źródła danych bieżącego mapowania modelu:</span><span class="sxs-lookup"><span data-stu-id="c4b53-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="c4b53-172">Rzeczywisty czas poświęcony na uzyskiwanie danych przy użyciu źródła danych</span><span class="sxs-lookup"><span data-stu-id="c4b53-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="c4b53-173">Ten sam czas wyrażony jako procent łącznego czasu, jaki zajęło wykonywanie całego mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="c4b53-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Szczegóły czasu wykonania na stronie projektanta mapowania modelu](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="c4b53-175">Siatka **Statystyka wydajności** pokazuje, że źródło danych **Transakcji** wywołuje tabelę VendTrans jeden raz.</span><span class="sxs-lookup"><span data-stu-id="c4b53-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="c4b53-176">Wartość **\[265\]\[Q:265\]** źródła danych **Transakcji** wskazuje, że 265 transakcje dostawcy zostały pobrane z tabeli aplikacji i zwrócone do modelu danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="c4b53-177">Siatka **statystyk wydajności** pokazuje również, że bieżące mapowanie modeli powoduje duplikowanie żądań baz danych podczas uruchamiania źródła danych **\#Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="c4b53-178">Duplikacja odbywa się z następujących powodów:</span><span class="sxs-lookup"><span data-stu-id="c4b53-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="c4b53-179">Tabela dostawcy jest wywoływana dwa razy dla każdej z 265 powtarzających się transakcji dostawcy, co daje łączną liczbę wezwań 530:</span><span class="sxs-lookup"><span data-stu-id="c4b53-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="c4b53-180">Jedno wywołanie jest wykonywane w celu wprowadzenia numeru konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c4b53-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="c4b53-181">Jedno wywołanie jest wykonywane w celu wprowadzenia nazwy dostawcy.</span><span class="sxs-lookup"><span data-stu-id="c4b53-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="c4b53-182">Tabela dostawców jest wywoływana dla każdej powtarzanej transakcji dostawcy, nawet jeśli pobrane transakcje zostały zaksięgowane tylko dla pięciu dostawców.</span><span class="sxs-lookup"><span data-stu-id="c4b53-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="c4b53-183">Spośród 530 wywołań, 525 to duplikaty.</span><span class="sxs-lookup"><span data-stu-id="c4b53-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="c4b53-184">Na poniższej ilustracji przedstawiono komunikat dotyczący zduplikowanych wywołań (żądań bazy danych).</span><span class="sxs-lookup"><span data-stu-id="c4b53-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Komunikat dotyczący zduplikowanych żądań bazy danych na stronie projektanta mapowania modelu](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="c4b53-186">Spośród całkowitego czasu wykonywania mapowania modelu (około osiem sekund) pobieranie wartości z tabeli aplikacji VendTable zajęło więcej niż 80% (około sześciu sekund).</span><span class="sxs-lookup"><span data-stu-id="c4b53-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="c4b53-187">Wartość procentowa jest zbyt duża dla dwóch atrybutów pięciu dostawców w porównaniu z ilością informacji z tabeli aplikacji VendTrans.</span><span class="sxs-lookup"><span data-stu-id="c4b53-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="c4b53-188">Aby zmniejszyć liczbę wywołań, które są wykonywane w celu uzyskania szczegółów dotyczących dostawcy dla każdej transakcji, oraz zwiększyć wydajność mapowania modeli, można korzystać z buforowania dla źródła danych **\#Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b53-189">Źródło danych **Transakcja\\\#Dostawca** będzie buforowane w zakresie bieżącej transakcji źródła danych **transakcji** w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c4b53-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="c4b53-190">Dzięki buforowaniu źródła danych **\#Dostawca** zmniejsza się liczbę zduplikowanych wywołań z 525 do 260, ale nie eliminuje to całkowicie duplikatów.</span><span class="sxs-lookup"><span data-stu-id="c4b53-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="c4b53-191">Aby całkowicie wyeliminować duplikacje, można skonfigurować nowe, sparametryzowane źródło danych typu **pola obliczeniowego**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="c4b53-192">Poprawianie mapowania modelu na podstawie informacji ze śladu wykonywania</span><span class="sxs-lookup"><span data-stu-id="c4b53-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="c4b53-193">Zmiana mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="c4b53-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="c4b53-194">Wykonaj poniższe kroki, aby użyć buforowania i źródła danych typu **pola obliczeniowego** w celu uniknięcia zduplikowanych wywołań bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="c4b53-195">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="c4b53-196">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="c4b53-197">Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="c4b53-198">Na stronie **Projektant mapowania modeli** wykonaj poniższe kroki, aby dodać źródło danych typu **rekord tabeli** w celu uzyskania dostępu do rekordów w tabeli aplikacji VendTable:</span><span class="sxs-lookup"><span data-stu-id="c4b53-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="c4b53-199">W okienku **Typy źródła danych** rozwiń opcję **Dynamics 365 for Operations** i wybierz **Rekordy tabeli**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="c4b53-200">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="c4b53-201">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="c4b53-202">W polu **Tabela** wprowadź **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="c4b53-203">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-203">Select **OK**.</span></span>

5. <span data-ttu-id="c4b53-204">Można parametryzować wywołania źródeł danych **pola obliczeniowego** tylko wtedy, gdy te źródła danych znajdują się w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="c4b53-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="c4b53-205">Dlatego należy wykonać poniższe kroki w celu dodania źródła danych do typu **pustego kontenera** w celu przechowywania nowego sparametryzowanego źródła danych typu **obliczanego pola**:</span><span class="sxs-lookup"><span data-stu-id="c4b53-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="c4b53-206">W okienku **Typy źródła danych** rozwiń opcję **Ogólne** i wybierz **Pusty kontener**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="c4b53-207">Wybierz **Dodaj element główny**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="c4b53-208">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Pole**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="c4b53-209">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-209">Select **OK**.</span></span>

    ![Dodano źródło danych pole w konstruktorze mapowania modelu](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="c4b53-211">Aby dodać sparametryzowane źródło danych typu **pola obliczeniowego**, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c4b53-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="c4b53-212">Wybierz opcję **Pole** w okienku **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="c4b53-213">W okienku **Typy źródła danych** rozwiń pozycję **Funkcje** i wybierz **Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="c4b53-214">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-214">Select **Add**.</span></span>
    4. <span data-ttu-id="c4b53-215">W oknie dialogowym rozwijanym w polu **Nazwa** wprowadź **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="c4b53-216">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="c4b53-217">Na stronie **Projektant formuł** wybierz **Parametry**, aby określić parametry, które muszą zostać dostarczone, gdy to źródło danych zostanie wywołane.</span><span class="sxs-lookup"><span data-stu-id="c4b53-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="c4b53-218">W oknie dialogowym **Parametry** wybierz przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="c4b53-219">W polu **Nazwa** wpisz **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="c4b53-220">W polu **Typ** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="c4b53-221">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-221">Select **OK**.</span></span>
    11. <span data-ttu-id="c4b53-222">W polu **Formuła** wprowadź **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="c4b53-223">Wybierz **Zapisz** oraz zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="c4b53-224">Wybierz przycisk **OK**, aby dodać nowe źródło danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="c4b53-225">Aby oznaczyć dodane źródło danych jako buforowane podczas wykonywania, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c4b53-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="c4b53-226">W okienku **Źródła danych** wybierz **Pole\\Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="c4b53-227">Wybierz opcję **Pamięć podręczna**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4b53-228">Źródło danych **Pole\\Dostawca** będzie buforowane w zakresie wszystkich transakcji źródła danych **transakcji** w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c4b53-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="c4b53-229">Wykonaj poniższe kroki, aby zaktualizować zagnieżdżone źródło danych **Transakcja\\\#Dostawca**, aby korzystało ze źródła **Pole\\Dostawca**:</span><span class="sxs-lookup"><span data-stu-id="c4b53-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="c4b53-230">W okienku **Źródła danych** rozwiń **Transakcja**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="c4b53-231">Wybierz źródło danych **Transakcje\\\#Dostawca**, a następnie wybierz opcję **Edytuj** \> **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="c4b53-232">Na stronie **Projektant formuł** wprowadź w polu **Formuła** następującą wartość **Box.Vend(\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="c4b53-233">Zamknij stronę **Projektowanie formuły** i wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="c4b53-234">Wybierz przycisk **OK**, aby ukończyć wprowadzanie zmian w wybranym źródle danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="c4b53-235">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-235">Select **Save**.</span></span>

    ![Źródło danych dostawca w konstruktorze mapowania modelu](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="c4b53-237">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="c4b53-238">Zamknij stronę **Mapowanie modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="c4b53-239">Kończenie zmodyfikowanej wersji mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="c4b53-240">Na stronie **Konfiguracje** na karcie skróconej **Wersje** wybierz wersję **1.2** konfiguracji **Mapowanie poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="c4b53-241">Wybierz pozycję **Zmień stan** \> **Zakończone**, a następnie wybierz opcję **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="c4b53-242">Uruchom zmodyfikowane rozwiązanie ER, aby śledzić wykonywanie</span><span class="sxs-lookup"><span data-stu-id="c4b53-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="c4b53-243">Powtórz kroki opisane w sekcji [Uruchamianie formatu ER](#run-format) tego tematu, aby wygenerować nowy ślad wydajności.</span><span class="sxs-lookup"><span data-stu-id="c4b53-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="c4b53-244">Śledzenie wydajności umożliwia zmiany w mapowaniu modeli</span><span class="sxs-lookup"><span data-stu-id="c4b53-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="c4b53-245">Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Mapowanie poprawy wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="c4b53-246">W okienku akcji wybierz opcję **Projektant**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="c4b53-247">Wybierz opcję **Projektant** w okienku akcji, aby otworzyć stronę **Mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="c4b53-248">Na stronie **Projektant mapowania modelu** w okienku akcji wybierz opcję **Ślad wydajności**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="c4b53-249">Wybierz najnowszy wygenerowany wynik śledzenia, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="c4b53-250">Korekty wprowadzone w mapowaniu modelu wyeliminowały duplikowanie zapytań do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c4b53-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="c4b53-251">Liczba wywołań tabel bazy danych i źródeł danych tego mapowania modelu również została zmniejszona.</span><span class="sxs-lookup"><span data-stu-id="c4b53-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Śledzenie danych w konstruktorze mapowania modelu 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="c4b53-253">Całkowity czas wykonania został zredukowany o 20 razy (z 8 sekund do około 400 milisekund).</span><span class="sxs-lookup"><span data-stu-id="c4b53-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="c4b53-254">Wydajność całego rozwiązania ER uległa zatem poprawie.</span><span class="sxs-lookup"><span data-stu-id="c4b53-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Śledzenie danych w konstruktorze mapowania modelu 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="c4b53-256">Dodatek 1: Pobierz składniki przykładowego rozwiązania Microsoft ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="c4b53-257">Musisz również pobrać i lokalnie zapisać następujące pliki.</span><span class="sxs-lookup"><span data-stu-id="c4b53-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="c4b53-258">Plik</span><span class="sxs-lookup"><span data-stu-id="c4b53-258">File</span></span>                                        | <span data-ttu-id="c4b53-259">Zawartość</span><span class="sxs-lookup"><span data-stu-id="c4b53-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="c4b53-260">Performance improvement model.version.1</span><span class="sxs-lookup"><span data-stu-id="c4b53-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="c4b53-261">Przykładowa konfiguracja modelu danych ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-261">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="c4b53-262">Performance improvement mapping.version.1.1</span><span class="sxs-lookup"><span data-stu-id="c4b53-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="c4b53-263">Przykładowa konfiguracja mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-263">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="c4b53-264">Performance improvement format.version.1.1</span><span class="sxs-lookup"><span data-stu-id="c4b53-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="c4b53-265">Przykładowa konfiguracja formatu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-265">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="c4b53-266">Dodatek 2: Konfigurowanie struktury ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="c4b53-267">Zanim będzie można rozpocząć korzystanie z struktury ER w celu zwiększenia wydajności przykładowego rozwiązania Microsoft ER, należy skonfigurować minimalny zestaw parametrów ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="c4b53-268">Konfigurowanie parametrów modułu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-268">Configure ER parameters</span></span>

1. <span data-ttu-id="c4b53-269">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="c4b53-270">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Parametry raportowania elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="c4b53-271">Na stronie **Parametry raportowania elektronicznego** na karcie **Ogólne** ustaw opcję **Włącz tryb projektowania** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="c4b53-272">Na karcie **Załączniki** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="c4b53-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="c4b53-273">W polu **Konfiguracje** wybierz typ **Plik** dla firmy **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="c4b53-274">W polach **Archiwum zadań**, **Tymczasowe**, **Podstawowe** i **Inne** należy wybrać typ **Plik**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="c4b53-275">Aby uzyskać więcej informacji o parametrach modułu ER, zapoznaj się z tematem [Konfiguracja struktury ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c4b53-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="c4b53-276">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="c4b53-277">Każda dodana konfiguracja ER jest oznaczona jako posiadana przez dostawcę konfiguracji ER.</span><span class="sxs-lookup"><span data-stu-id="c4b53-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="c4b53-278">W tym celu jest używany dostawca konfiguracji ER, który został aktywowany w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="c4b53-279">Dlatego przed rozpoczęciem dodawania lub edytowania konfiguracji ER należy aktywować dostawcę konfiguracji ER w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b53-280">Tylko właściciel konfiguracji ER może edytować konfigurację.</span><span class="sxs-lookup"><span data-stu-id="c4b53-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="c4b53-281">Dlatego przed rozpoczęciem edytowania konfiguracji ER należy aktywować samą konfigurację w obszarze roboczym **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="c4b53-282">Przejrzenie listy dostawców konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="c4b53-283">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="c4b53-284">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="c4b53-285">Na stronie **Tabela dostawcy konfiguracji** każdy rekord dostawcy ma unikatową nazwę i adres URL.</span><span class="sxs-lookup"><span data-stu-id="c4b53-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="c4b53-286">Przejrzyj zawartość tej strony.</span><span class="sxs-lookup"><span data-stu-id="c4b53-286">Review the contents of this page.</span></span> <span data-ttu-id="c4b53-287">Jeśli rekord dla **Litware, Inc.** już istnieje, pomiń następną procedurę, [Dodawanie nowego dostawcy konfiguracji ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="c4b53-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="c4b53-288">Dodawanie nowego dostawcy formatu ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="c4b53-289">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="c4b53-290">Na stronie **Konfiguracje lokalizacji** w sekcji **Powiązane łącza** wybierz kafelek **Dostawcy konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="c4b53-291">Na stronie **Dostawcy konfiguracji** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="c4b53-292">W polu **Nazwa** wpisz **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="c4b53-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="c4b53-293">W polu **Adres internetowy** wprowadź `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="c4b53-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="c4b53-294">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="c4b53-295">Aktywowanie dostawcy konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="c4b53-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="c4b53-296">Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="c4b53-297">Na stronie **Konfiguracje lokalizacji** w sekcji **Dostawcy konfiguracji** wybierz pozycję **Litware, Inc.**, a następnie wybierz pozycję **Ustaw, jako aktywne**.</span><span class="sxs-lookup"><span data-stu-id="c4b53-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="c4b53-298">Dalsze informacje o dostawcach konfiguracji ER znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c4b53-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4b53-299">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c4b53-299">Additional resources</span></span>

- [<span data-ttu-id="c4b53-300">Raportowanie elektroniczne — omówienie</span><span class="sxs-lookup"><span data-stu-id="c4b53-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="c4b53-301">Śledzenie wykonywania formatów raportowania elektronicznego w celu rozwiązywania problemów z wydajnością</span><span class="sxs-lookup"><span data-stu-id="c4b53-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="c4b53-302">Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="c4b53-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]