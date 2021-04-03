---
title: Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego
description: Ten temat zawiera informacje dotyczące używania typu pola obliczeniowego dla źródeł danych ER.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
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
ms.openlocfilehash: 1c2c13cd3f165826e0d5b5ac901ffa61895301e7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569208"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="29545-103">Obsługuj sparametryzowane wywołania źródeł danych ER typu pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29545-104">W tym temacie wyjaśniono, jak można zaprojektować źródło danych elektronicznego raportowania (ER) przy użyciu typu **pola obliczeniowego**.</span><span class="sxs-lookup"><span data-stu-id="29545-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="29545-105">To źródło danych może zawierać wyrażenie właściciela, które po wykonaniu można kontrolować za pomocą wartości argumentów parametrów skonfigurowanych w powiązaniu, które wywołuje to źródło danych.</span><span class="sxs-lookup"><span data-stu-id="29545-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="29545-106">Dzięki skonfigurowaniu sparametryzowanych wywołań takiego źródła danych można ponownie użyć jednego źródła danych w wielu powiązaniach, zmniejszając jednocześnie liczbę źródeł danych, które muszą być skonfigurowane w mapowaniach modelu ER lub w formatach ER.</span><span class="sxs-lookup"><span data-stu-id="29545-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="29545-107">Upraszcza także skonfigurowany składnik ER, który zmniejsza koszty obsługi i koszty użytkowania innych odbiorców.</span><span class="sxs-lookup"><span data-stu-id="29545-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29545-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="29545-108">Prerequisites</span></span>
<span data-ttu-id="29545-109">Aby wykonać przykłady opisane w tym temacie, musisz mieć następujące uprawnienia dostępu:</span><span class="sxs-lookup"><span data-stu-id="29545-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="29545-110">Dostęp do jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="29545-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="29545-111">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="29545-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="29545-112">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="29545-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="29545-113">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="29545-113">System administrator</span></span>

- <span data-ttu-id="29545-114">Dostęp do wystąpienia Regulatory Configuration Services (RCS), które zostało zainicjowane dla tej samej dzierżawy co Finance and Operations dla jednej z następujących ról:</span><span class="sxs-lookup"><span data-stu-id="29545-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="29545-115">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="29545-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="29545-116">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="29545-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="29545-117">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="29545-117">System administrator</span></span>

<span data-ttu-id="29545-118">Musisz również pobrać i lokalnie zapisać następujące pliki.</span><span class="sxs-lookup"><span data-stu-id="29545-118">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="29545-119">**Zawartość**</span><span class="sxs-lookup"><span data-stu-id="29545-119">**Content**</span></span>                           | <span data-ttu-id="29545-120">**Nazwa pliku**</span><span class="sxs-lookup"><span data-stu-id="29545-120">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="29545-121">Przykładowa konfiguracja modelu danych ER</span><span class="sxs-lookup"><span data-stu-id="29545-121">Sample ER data model configuration</span></span>    | [<span data-ttu-id="29545-122">Model do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="29545-122">Model to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| <span data-ttu-id="29545-123">Przykładowa konfiguracja metadanych ER</span><span class="sxs-lookup"><span data-stu-id="29545-123">Sample ER metadata configuration</span></span>      | [<span data-ttu-id="29545-124">Dane do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="29545-124">Metadata to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| <span data-ttu-id="29545-125">Przykładowa konfiguracja mapowania modelu ER</span><span class="sxs-lookup"><span data-stu-id="29545-125">Sample ER model mapping configuration</span></span> | [<span data-ttu-id="29545-126">Mapowanie do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="29545-126">Mapping to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="29545-127">Przykładowa konfiguracja formatu ER</span><span class="sxs-lookup"><span data-stu-id="29545-127">Sample ER format configuration</span></span>        | [<span data-ttu-id="29545-128">Format do nauczenia sparametryzowanych calls.version.1.xml.</span><span class="sxs-lookup"><span data-stu-id="29545-128">Format to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="29545-129">Zaloguj się do swojego wystąpienia RCS.</span><span class="sxs-lookup"><span data-stu-id="29545-129">Sign in to your RCS instance</span></span>
<span data-ttu-id="29545-130">W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, najpierw trzeba wykonać kroki wymienione w procedurze [ER Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="29545-130">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="29545-131">Na domyślnym pulpicie nawigacyjnym wybierz opcję **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="29545-131">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="29545-132">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="29545-132">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="29545-133">Zaimportuj pobrane konfiguracje do RCS w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="29545-133">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="29545-134">W każdej konfiguracji modułu ER należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="29545-134">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="29545-135">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="29545-135">Select **Exchange.**</span></span>
    2. <span data-ttu-id="29545-136">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="29545-136">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="29545-137">Kliknij przycisk **Przeglądaj**, nastepnie wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="29545-137">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="29545-138">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-138">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="29545-139">Przejrzyj dostarczone rozwiązanie ER</span><span class="sxs-lookup"><span data-stu-id="29545-139">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="29545-140">Przejrzyj mapowanie modelu</span><span class="sxs-lookup"><span data-stu-id="29545-140">Review model mapping</span></span>

1. <span data-ttu-id="29545-141">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-141">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="29545-142">Wybierz opcję **mapowanie, aby poznać wywołania sparametryzowane**.</span><span class="sxs-lookup"><span data-stu-id="29545-142">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="29545-143">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="29545-143">Select **Designer**.</span></span>
4. <span data-ttu-id="29545-144">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="29545-144">Select **Designer**.</span></span>  
   
    <span data-ttu-id="29545-145">W tym mapowaniu modelu ER jest przeznaczona do wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="29545-145">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="29545-146">Pobierz listę kodów podatków (Źródło danych **podatku**) znajdujących się w tabeli **Tabela Podatkowa**.</span><span class="sxs-lookup"><span data-stu-id="29545-146">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="29545-147">Pobierz listę kodów transakcji podatkowych (Źródło danych **tansakcji**) znajdujących się w tabeli **Tabela Podatkowa**:</span><span class="sxs-lookup"><span data-stu-id="29545-147">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="29545-148">Umożliwia grupowanie listy pobranych transakcji (**Gr** Źródło danych) według kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="29545-148">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="29545-149">Oblicz dla zgrupowanych transakcji po wartości zagregowanych według kodu podatku:</span><span class="sxs-lookup"><span data-stu-id="29545-149">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="29545-150">Suma wartości podstawowych podatku.</span><span class="sxs-lookup"><span data-stu-id="29545-150">Sum of tax base values.</span></span>
            - <span data-ttu-id="29545-151">Suma wartości podatku.</span><span class="sxs-lookup"><span data-stu-id="29545-151">Sum of tax values.</span></span>
            - <span data-ttu-id="29545-152">Minimalna wartość zastosowanej stawki podatkowej.</span><span class="sxs-lookup"><span data-stu-id="29545-152">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="29545-153">Mapowanie modelu w tej konfiguracji implementuje podstawowy model danych dla dowolnego formatu ER utworzonego dla tego modelu i wykonywany w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="29545-153">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="29545-154">W wyniku tego zawartość źródeł danych **podatków** i **Gr** jest udostępniana dla formatów ER, takich jak abstrakcyjne źródła danych.</span><span class="sxs-lookup"><span data-stu-id="29545-154">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Strona projektanta mapowania modelu pokazująca źródła danych podatkowych i Gr.](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="29545-156">Zamknij stronę **Projektant mapowania modelu**.</span><span class="sxs-lookup"><span data-stu-id="29545-156">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="29545-157">Zamknij stronę **Mapowanie modelu**.</span><span class="sxs-lookup"><span data-stu-id="29545-157">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="29545-158">Format przeglądu</span><span class="sxs-lookup"><span data-stu-id="29545-158">Review format</span></span>

1. <span data-ttu-id="29545-159">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-159">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="29545-160">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-160">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="29545-161">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="29545-161">Select **Designer**.</span></span> <span data-ttu-id="29545-162">Format ER jest przeznaczona do wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="29545-162">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="29545-163">Generowanie oświadczenia podatkowego w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="29545-163">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="29545-164">Zaprezentuj następujące poziomy opodatkowania w sprawozdaniu podatkowym: regularnym, obniżonym i brak.</span><span class="sxs-lookup"><span data-stu-id="29545-164">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="29545-165">Umożliwia prezentowanie wielu szczegółów na poziomie opodatkowania, mających różną liczbę szczegółów na każdym poziomie.</span><span class="sxs-lookup"><span data-stu-id="29545-165">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Strona projektanta formatu](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="29545-167">Wybierz **Mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="29545-167">Select **Mapping**.</span></span>
5. <span data-ttu-id="29545-168">Rozwiń **Model**, **Dane,** i **podsumowanie**.</span><span class="sxs-lookup"><span data-stu-id="29545-168">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="29545-169">Obliczone pole **Model.Data.Summary.Level** zawiera wyrażenie zwracające kod poziomu opodatkowania (**zwykły**, **ograniczony**, **brak** lub **inny**) jako wartość tekstowa dla dowolnego kodu podatku, który może zostać pobrany z **Model.Data.Summary** źródła danych w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="29545-169">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![Strona projektant formatów pokazująca szczegóły modelu modelu danych, aby poznać wywołania parametryczne](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="29545-171">Rozwiń **Model**.**Dane2**.</span><span class="sxs-lookup"><span data-stu-id="29545-171">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="29545-172">Rozwiń **Model**.**Dane2.Summary2**.</span><span class="sxs-lookup"><span data-stu-id="29545-172">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="29545-173">**Model**.**Data2.Summary2** źródło danych jest skonfigurowane do grupowania **Model.Data.Summary** transakcji źródła danych sumarycznych według poziomu opodatkowania (zwrócone przez pole obliczeniowe **Model.Data.Summary.Level**) i oblicza agregacje.</span><span class="sxs-lookup"><span data-stu-id="29545-173">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![Strona Projektant formatów pokazująca szczegóły źródła danych Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="29545-175">Umożliwia przejrzenie obliczonych pól **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span><span class="sxs-lookup"><span data-stu-id="29545-175">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="29545-176">Te pola obliczeniowe służą do filtrowania **Model**.**Dane2.Summary2** rekordów listy i zwracają tylko rekordy reprezentujące określony poziom opodatkowania.</span><span class="sxs-lookup"><span data-stu-id="29545-176">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="29545-177">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="29545-177">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="29545-178">Tworzenie pochodnego formatu</span><span class="sxs-lookup"><span data-stu-id="29545-178">Create a derived format</span></span>
<span data-ttu-id="29545-179">Można poprawić podany format, dodając jedno pole obliczeniowe w celu odfiltrowania wymaganego poziomu opodatkowania, zamiast korzystać z trzech pól **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** i **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="29545-179">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="29545-180">Wymagany poziom opodatkowania można określić w lokalizacji, w której zostanie wywołane nowe pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="29545-180">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="29545-181">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-181">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="29545-182">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-182">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="29545-183">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="29545-183">Select **Create configuration**.</span></span>
4. <span data-ttu-id="29545-184">Wybierz **pochodną z Nazwy: Format, aby poznać wywołania sparametryzowane Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="29545-184">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="29545-185">W polu **nazwa** wprowadź **Format, aby poznać wywołania sparametryzowane (dostosowane)**.</span><span class="sxs-lookup"><span data-stu-id="29545-185">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="29545-186">Wybierz **Utwórz konfigurację**.</span><span class="sxs-lookup"><span data-stu-id="29545-186">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="29545-187">Skonfiguruj sparametryzowane pole obliczeniowe, które zwraca listę rekordów</span><span class="sxs-lookup"><span data-stu-id="29545-187">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="29545-188">Rozpocznij dodawanie nowego pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-188">Start adding a new calculated field</span></span>

1. <span data-ttu-id="29545-189">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="29545-189">Select **Designer**.</span></span>
2. <span data-ttu-id="29545-190">Wybierz **Rozwiń/Zwiń**, aby rozwinąć wszystkie elementy formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-190">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="29545-191">Wybierz **Mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="29545-191">Select **Mapping**.</span></span>
4. <span data-ttu-id="29545-192">Rozwiń **Model**.</span><span class="sxs-lookup"><span data-stu-id="29545-192">Expand the **Model** item.</span></span>
5. <span data-ttu-id="29545-193">Wybierz  **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="29545-193">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="29545-194">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="29545-194">Select **Add**.</span></span>
7. <span data-ttu-id="29545-195">Wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="29545-195">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="29545-196">W polu **Nazwa** wprowadź nazwę **Poziomy**.</span><span class="sxs-lookup"><span data-stu-id="29545-196">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="29545-197">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="29545-197">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="29545-198">Definiowanie parametru służącego do dodawania pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-198">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="29545-199">Wybierz **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="29545-199">Select **Parameters**.</span></span>
2. <span data-ttu-id="29545-200">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="29545-200">Select **New**.</span></span>
3. <span data-ttu-id="29545-201">W polu **Nazwa** wpisz **Poziom opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="29545-201">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="29545-202">W polu **Typ** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="29545-202">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="29545-203">Do określania typu argumentu parametru mogą być używane tylko pierwotne typy danych</span><span class="sxs-lookup"><span data-stu-id="29545-203">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="29545-204">Dlatego w tym celu nie można używać **Listy rekordów**, **Rekordu** i **Wyliczeń**.</span><span class="sxs-lookup"><span data-stu-id="29545-204">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="29545-205">Maksymalna liczba parametrów, które można określić dla pojedynczego pola obliczeniowego wynosi 8.</span><span class="sxs-lookup"><span data-stu-id="29545-205">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista źródeł danych parametrów](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="29545-207">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-207">Select **OK**.</span></span>

<span data-ttu-id="29545-208">Dodając ten parametr, należy określić warunek, który musi mieć miejsce w celu wywołania tego pola obliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="29545-208">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="29545-209">Po wywołaniu tego pola obliczeniowego należy określić argument parametru **poziomu opodatkowania** jako wartość w formacie **ciągu**.</span><span class="sxs-lookup"><span data-stu-id="29545-209">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="29545-210">Należy się upewnić, że parametry są definiowane tylko dla tych pól obliczeniowych, które znajdują się w kontenerze (**Lista rekordów**, **Rekord** lub **Kontener**).</span><span class="sxs-lookup"><span data-stu-id="29545-210">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="29545-211">Skonfigurowany parametr jest dostępny na liście źródeł danych dla tego pola obliczeniowego.</span><span class="sxs-lookup"><span data-stu-id="29545-211">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="29545-212">Ten parametr można dodać do skonfigurowanego wyrażenia, wybierając opcję **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="29545-212">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Pola źródła danych](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="29545-214">Definiowanie wyrażenia służącego do dodawania pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-214">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="29545-215">W polu **Formuła** wpisz:</span><span class="sxs-lookup"><span data-stu-id="29545-215">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="29545-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="29545-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="29545-217">Wybierz parametr **poziomu opodatkowania** z listy źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="29545-217">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="29545-218">Wybierz **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="29545-218">Select **Add data source**.</span></span>
4. <span data-ttu-id="29545-219">W polu **Formuła** skończ następujące wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="29545-219">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="29545-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="29545-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="29545-221">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="29545-221">Select **Save**.</span></span>

    ![Informacje dotyczące pola źródła danych](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="29545-223">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="29545-223">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="29545-224">Skończ dodawanie nowego pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-224">Finish adding a new calculated field</span></span>

- <span data-ttu-id="29545-225">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-225">Select **OK**.</span></span>

<span data-ttu-id="29545-226">Na stronie **Projektant formatu** dla skonfigurowanych **poziomów** pól obliczeniowych z parametrami jest wymagany argument typu **ciąg**.</span><span class="sxs-lookup"><span data-stu-id="29545-226">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Rozszerzona lista poziomów pól obliczeniowych](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="29545-228">Dla elementów formatu powiązania należy zastosować skonfigurowane pole obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="29545-228">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="29545-229">Wybierz **Model.Data2.Levels** poziomy, aby wybrać skonfigurowane pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="29545-229">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="29545-230">Umożliwia wybranie **elemeStatement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="29545-230">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="29545-231">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="29545-231">Select **Bind**.</span></span>
4. <span data-ttu-id="29545-232">Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **, Level1**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu wybranego elementu formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-232">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="29545-233">Zastosowane powiązanie zostało skompilowane jako wywołanie pola obliczeniowego sparametryzowanego.</span><span class="sxs-lookup"><span data-stu-id="29545-233">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="29545-234">Domyślnie nazwa elementu formatu powiązanego jest używana jako argument dla sparametryzowanego pola obliczeniowego w następujących warunkach:</span><span class="sxs-lookup"><span data-stu-id="29545-234">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="29545-235">W polu obliczeniowym jest skonfigurowane użycie jednego parametru.</span><span class="sxs-lookup"><span data-stu-id="29545-235">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="29545-236">Typ danych tego parametru jest zdefiniowany jako **ciąg**.</span><span class="sxs-lookup"><span data-stu-id="29545-236">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="29545-237">Jeśli nazwa elementu formatu powiązanego jest pusta, nazwa źródła danych tego elementu jest używana w zastosowaniu powiązania.</span><span class="sxs-lookup"><span data-stu-id="29545-237">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="29545-238">Wybierz element formatu **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="29545-238">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="29545-239">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="29545-239">Select **Bind**.</span></span>
7. <span data-ttu-id="29545-240">Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **, Level2**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu poniżej wybranego elementu formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-240">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="29545-241">Wybierz element formatu **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="29545-241">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="29545-242">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="29545-242">Select **Bind**.</span></span>
10. <span data-ttu-id="29545-243">Wybierz **tak**, aby potwierdzić zastąpienie aktualnie używanego źródła danych **Level3**, według nowego źródła danych, **poziomów** we wszystkich zagnieżdżonych elementach formatu poniżej wybranego elementu formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-243">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="29545-244">Po określeniu argumentu sparametryzowanego pola obliczeniowego dla elementu XML reprezentującego poziom opodatkowania (na przykład **Model.Data2.Levels(„zmniejszone”)** jako wartość tekstową), nie trzeba tego robić w przypadku zagnieżdżonych atrybutów XML — ich powiązania automatycznie odziedziczą wartość argumentu zdefiniowanego na poziomie nadrzędnym (**Model.Data2.Levels.aggregated.Base**, a nie **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="29545-244">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="29545-245">Cykliczne wywołania wszelkich sparametryzowanych pól obliczeniowych nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="29545-245">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="29545-246">Można wybrać opcję **Edytuj formułę** i zmienić argument zastosowany przez domyślny dla sparametryzowanego pola obliczeniowego w wybranym powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="29545-246">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="29545-247">Brak tego argumentu może spowodować błędy w czasie wykonywania — użytkownicy są informowani o takiej sytuacji w przypadku sprawdzania poprawności bieżącego formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-247">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Powiadomienie o sprawdzeniu poprawności](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="29545-249">Skonfiguruj sparametryzowane pole obliczeniowe, które zwraca rekord</span><span class="sxs-lookup"><span data-stu-id="29545-249">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="29545-250">Jeśli sparametryzowane pole obliczeniowe zwraca rekord, należy obsługiwać powiązanie poszczególnych pól tego rekordu, aby formatować elementy.</span><span class="sxs-lookup"><span data-stu-id="29545-250">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="29545-251">W takich przypadkach nie zostanie utworzone powiązanie nadrzędne zawierające wartość argumentu wywołującego sparametryzowane pole obliczeniowe — ta wartość musi być zdefiniowana w powiązaniu pola z pojedynczym rekordem.</span><span class="sxs-lookup"><span data-stu-id="29545-251">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="29545-252">Rozpocznij dodawanie nowego pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-252">Start adding a new calculated field</span></span>

1. <span data-ttu-id="29545-253">Wybierz  **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="29545-253">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="29545-254">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="29545-254">Select **Add**.</span></span>
3. <span data-ttu-id="29545-255">Wybierz **Funkcje\\Pole obliczeniowe**.</span><span class="sxs-lookup"><span data-stu-id="29545-255">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="29545-256">W polu **Nazwa** wpisz **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="29545-256">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="29545-257">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="29545-257">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="29545-258">Definiowanie parametru służącego do dodawania pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-258">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="29545-259">Wybierz **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="29545-259">Select **Parameters**.</span></span>
2. <span data-ttu-id="29545-260">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="29545-260">Select **New**.</span></span>
3. <span data-ttu-id="29545-261">W polu **Nazwa** wpisz **Poziom opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="29545-261">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="29545-262">W polu **Typ** wybierz **Ciąg**.</span><span class="sxs-lookup"><span data-stu-id="29545-262">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="29545-263">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-263">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="29545-264">Definiowanie wyrażenia służącego do dodawania pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-264">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="29545-265">W polu **Formuła** wprowadź następujące:</span><span class="sxs-lookup"><span data-stu-id="29545-265">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="29545-266">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="29545-266">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="29545-267">Wybierz parametru **poziomu opodatkowania**.</span><span class="sxs-lookup"><span data-stu-id="29545-267">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="29545-268">Wybierz **Dodaj źródło danych**.</span><span class="sxs-lookup"><span data-stu-id="29545-268">Select **Add data source**.</span></span>
4. <span data-ttu-id="29545-269">W polu **formuła** dołącz **„poziom opodatkowania”))** do tego, co zostało wprowadzone w kroku 1, aby zakończyć wyrażenie:</span><span class="sxs-lookup"><span data-stu-id="29545-269">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="29545-270">**FIRSTORNULL(\@.Levels(„poziom opodatkowania”))**</span><span class="sxs-lookup"><span data-stu-id="29545-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="29545-271">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="29545-271">Select **Save**.</span></span>
6. <span data-ttu-id="29545-272">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="29545-272">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="29545-273">Skończ dodawanie nowego pola obliczeniowego</span><span class="sxs-lookup"><span data-stu-id="29545-273">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="29545-274">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-274">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="29545-275">Dla elementów formatu powiązania należy zastosować skonfigurowane pole obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="29545-275">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="29545-276">Rozwiń **Model.Data2.LevelRecord** poziomy, aby wybrać skonfigurowane pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="29545-276">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="29545-277">Rozwiń **Model.Data2.LevelRecord.aggregated** kontener, aby wybrać skonfigurowane pole obliczeniowe.</span><span class="sxs-lookup"><span data-stu-id="29545-277">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="29545-278">Wybierz **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="29545-278">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="29545-279">Wybierz element formatu **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="29545-279">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="29545-280">Wybierz **Odwiąż**.</span><span class="sxs-lookup"><span data-stu-id="29545-280">Select **Unbind**.</span></span>
6. <span data-ttu-id="29545-281">Wybierz element formatu **Statement.Taxation.Base**.</span><span class="sxs-lookup"><span data-stu-id="29545-281">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="29545-282">Wybierz **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="29545-282">Select **Bind**.</span></span>
8. <span data-ttu-id="29545-283">Wybierz opcję **Edytuj formułę**.</span><span class="sxs-lookup"><span data-stu-id="29545-283">Select **Edit formula**.</span></span>
9. <span data-ttu-id="29545-284">Zmień wyrażenie na **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="29545-284">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Aktualizowane wyrażenie](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="29545-286">Usuń pola obliczeniowe, które nie są używane</span><span class="sxs-lookup"><span data-stu-id="29545-286">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="29545-287">Wybierz **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="29545-287">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="29545-288">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="29545-288">Select **Delete**.</span></span>
3. <span data-ttu-id="29545-289">Wybierz **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="29545-289">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="29545-290">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="29545-290">Select **Delete**.</span></span>
5. <span data-ttu-id="29545-291">Wybierz **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="29545-291">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="29545-292">Wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="29545-292">Select **Delete**.</span></span>
7. <span data-ttu-id="29545-293">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="29545-293">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="29545-294">Ponownie użyto tego samego modelu pola **Model.Data2.Levels** w powiązaniach formatu.</span><span class="sxs-lookup"><span data-stu-id="29545-294">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="29545-295">Znacznie łatwiej jest używać jednego pola obliczeniowego i utrzymywać je w odniesieniu do wielu podobnych pól.</span><span class="sxs-lookup"><span data-stu-id="29545-295">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="29545-296">Zamknij stronę **Projektowanie formuły**.</span><span class="sxs-lookup"><span data-stu-id="29545-296">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="29545-297">Pełna skorygowana wersja formatu pochodnego</span><span class="sxs-lookup"><span data-stu-id="29545-297">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="29545-298">W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="29545-298">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="29545-299">Wybierz opcję **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="29545-299">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="29545-300">Eksport skończonej wersji formatu pochodnego</span><span class="sxs-lookup"><span data-stu-id="29545-300">Export completed version of a derived format</span></span>

1. <span data-ttu-id="29545-301">Wybierz **Format, aby uzyskać informacje o formacie wywołań sparametryzowanych (niestandardowy)** w drzewie konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="29545-301">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="29545-302">W obszarze **wersje** na skróconej karcie wybierz wersję zakończoną 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="29545-302">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="29545-303">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="29545-303">Select **Exchange**.</span></span>
4. <span data-ttu-id="29545-304">Wybierz **Eksportuj jako plik XML**.</span><span class="sxs-lookup"><span data-stu-id="29545-304">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="29545-305">Przechowaj pobraną konfigurację lokalnie w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="29545-305">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="29545-306">Testowanie formatów ER</span><span class="sxs-lookup"><span data-stu-id="29545-306">Test ER formats</span></span> 
<span data-ttu-id="29545-307">Można uruchomić wstępne i ulepszone formaty ER, aby upewnić się, że skonfigurowane pola obliczeniowe o sparametryzowanym działaniu będą działać prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="29545-307">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="29545-308">Importowanie konfiguracji ER</span><span class="sxs-lookup"><span data-stu-id="29545-308">Import ER configurations</span></span>
<span data-ttu-id="29545-309">Przejrzane konfiguracje można importować ze RCS za pomocą repozytorium ER typu **RCS.**</span><span class="sxs-lookup"><span data-stu-id="29545-309">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="29545-310">Jeśli wykonano już kroki opisane w temacie, należy [zaimportować konfiguracje raportowania elektronicznego z usług Regulatory Configuration Services (RCS)](rcs-download-configurations.md), a następnie skorzystać z skonfigurowanego repozytorium ER, aby zaimportować konfiguracje opisane wcześniej w tym temacie do środowiska.</span><span class="sxs-lookup"><span data-stu-id="29545-310">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="29545-311">W innym razie należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="29545-311">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="29545-312">Wybierz firmę **DEMF** i na domyślnym pulpicie nawigacyjnym, wybierz opcję **Raportowanie elektroniczne**.</span><span class="sxs-lookup"><span data-stu-id="29545-312">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="29545-313">Wybierz **Raportowanie konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="29545-313">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="29545-314">Zaimportuj pobrane konfiguracje z Microsoft Download Center w następującej kolejności: model danych, metadane, mapowanie modelu, format.</span><span class="sxs-lookup"><span data-stu-id="29545-314">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="29545-315">W każdej konfiguracji modułu ER należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="29545-315">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="29545-316">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="29545-316">Select **Exchange.**</span></span>
    2. <span data-ttu-id="29545-317">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="29545-317">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="29545-318">Kliknij przycisk **Przeglądaj**, nastepnie wybierz odpowiedni plik wymaganej konfiguracji ER w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="29545-318">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="29545-319">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-319">Select **OK**.</span></span>

4. <span data-ttu-id="29545-320">Zaimportuj eksport ze RCS ukończył wersję 1.1.1 formatu , aby uzyskać informacje o **formacie sparametryzowanych wywołań (niestandardowych)**:</span><span class="sxs-lookup"><span data-stu-id="29545-320">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="29545-321">Wybierz **Zamień**.</span><span class="sxs-lookup"><span data-stu-id="29545-321">Select **Exchange.**</span></span>
    2. <span data-ttu-id="29545-322">Wybierz **Załaduj z pliku XML**.</span><span class="sxs-lookup"><span data-stu-id="29545-322">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="29545-323">Wybierz **Przegladaj**, aby wybrać **format przechowywany lokalnie, aby poznać plik wywołań sparametryzowanych (niestandardowych)** w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="29545-323">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="29545-324">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="29545-324">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="29545-325">Uruchamianie formatów ER</span><span class="sxs-lookup"><span data-stu-id="29545-325">Run ER formats</span></span>

1. <span data-ttu-id="29545-326">W drzewie konfiguracji rozwiń zawartość **Model, aby uzyskać informacje o elementach sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-326">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="29545-327">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań**.</span><span class="sxs-lookup"><span data-stu-id="29545-327">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="29545-328">Wybierz **Uruchom** na wstążce u góry.</span><span class="sxs-lookup"><span data-stu-id="29545-328">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="29545-329">Zapisz wygenerowane lokalnie dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="29545-329">Save the locally generated output.</span></span>
5. <span data-ttu-id="29545-330">Wybierz opcję **Format do nauczenia sparametryzowanych wywołań (niestandardowe)**.</span><span class="sxs-lookup"><span data-stu-id="29545-330">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="29545-331">Wybierz **Uruchom** na wstążce u góry.</span><span class="sxs-lookup"><span data-stu-id="29545-331">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="29545-332">Zapisz wygenerowane lokalnie dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="29545-332">Save the generated output locally.</span></span> 
8. <span data-ttu-id="29545-333">Umożliwia porównanie zawartości wygenerowanych wyjść.</span><span class="sxs-lookup"><span data-stu-id="29545-333">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29545-334">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="29545-334">Additional resources</span></span>

- [<span data-ttu-id="29545-335">Projektant formuł w module Raportowanie elektroniczne (ER)</span><span class="sxs-lookup"><span data-stu-id="29545-335">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="29545-336">Zwiększ wydajność rozwiązań Raportowania elektronicznego, dodając sparametryzowane źródła danych PÓL OBLICZENIOWYCH</span><span class="sxs-lookup"><span data-stu-id="29545-336">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]