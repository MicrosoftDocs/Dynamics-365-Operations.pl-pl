---
title: Synchronizowanie szacunków projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations
description: Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b885610ac9ca8645358ba8ab6d46ab82143a534
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250491"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="5eef2-103">Synchronizowanie szacunków projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5eef2-103">Synchronize project estimates directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5eef2-104">Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między programem Dynamics 365 Project Service Automation a programem Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="5eef2-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="5eef2-105">Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w wersji 8.0.</span><span class="sxs-lookup"><span data-stu-id="5eef2-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in version 8.0.</span></span>
> - <span data-ttu-id="5eef2-106">Funkcja integrowania wartości rzeczywistych jest dostępna wersji 8.01 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-106">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="5eef2-107">Przepływ danych z programu Project Service Automation do Finance</span><span class="sxs-lookup"><span data-stu-id="5eef2-107">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="5eef2-108">Rozwiązanie integracji rozwiązania Project Service Automation dp Finance korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5eef2-108">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="5eef2-109">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących szacunków godzinowych i szacowań wydatków dotyczących projektu z rozwiązania Project Service Automation do rozwiązania Finance.</span><span class="sxs-lookup"><span data-stu-id="5eef2-109">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.</span></span>

<span data-ttu-id="5eef2-110">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance.</span><span class="sxs-lookup"><span data-stu-id="5eef2-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="5eef2-111">[![Przepływ danych w integracji programu Project Service Automation z programem Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="5eef2-111">[![Data flow for Project Service Automation integration with Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>

## <a name="project-hour-estimates"></a><span data-ttu-id="5eef2-112">Szacunki godzinowe projektu</span><span class="sxs-lookup"><span data-stu-id="5eef2-112">Project hour estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="5eef2-113">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="5eef2-113">Template and tasks</span></span>

<span data-ttu-id="5eef2-114">Aby przejść do dostępnych szablonów, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-114">To access the available templates, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="5eef2-115">Następujący szablon i zadania podrzędne służą do synchronizowania szacunków godzin projektu z rozwiązania Project Service Automation do rozwiązania Finance:</span><span class="sxs-lookup"><span data-stu-id="5eef2-115">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="5eef2-116">**Nazwa szablonu w narzędziu Integracja danych:** Szacunki godzin w projekcie (PSA do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="5eef2-116">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="5eef2-117">**Nazwa zadania w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="5eef2-117">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="5eef2-118">Relacje transakcji</span><span class="sxs-lookup"><span data-stu-id="5eef2-118">Transaction relationships</span></span>
    - <span data-ttu-id="5eef2-119">Oszacowania wydatków</span><span class="sxs-lookup"><span data-stu-id="5eef2-119">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="5eef2-120">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="5eef2-120">Entity set</span></span>

| <span data-ttu-id="5eef2-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="5eef2-121">Project Service Automation</span></span> | <span data-ttu-id="5eef2-122">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eef2-122">Finance</span></span>                                       |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="5eef2-123">Zadania w projekcie</span><span class="sxs-lookup"><span data-stu-id="5eef2-123">Project tasks</span></span>              | <span data-ttu-id="5eef2-124">Jednostka integracji szacunków godzinowych projektu</span><span class="sxs-lookup"><span data-stu-id="5eef2-124">Integration entity for project hour estimates</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="5eef2-125">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="5eef2-125">Entity flow</span></span>

<span data-ttu-id="5eef2-126">Zarządzanie szacunkami godzin w projekcie odbywa się w programie Project Service Automation i są one synchronizowane z programem Finance jako prognozy godzin w projekcie.</span><span class="sxs-lookup"><span data-stu-id="5eef2-126">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance as project hour forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5eef2-127">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5eef2-127">Prerequisites</span></span>

<span data-ttu-id="5eef2-128">Zanim będzie możliwa synchronizacja szacunków godzin w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.</span><span class="sxs-lookup"><span data-stu-id="5eef2-128">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="5eef2-129">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="5eef2-129">Power Query</span></span>

<span data-ttu-id="5eef2-130">W szablonie szacunków godzinowych projektu należy za pomocą dodatku Microsoft Power Query dla programu Excel wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="5eef2-130">In the project hour estimates template, you must use Microsoft Power Query for Excel to complete these tasks:</span></span>

- <span data-ttu-id="5eef2-131">Ustawienie domyślnego identyfikatora modelu prognozy, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.</span><span class="sxs-lookup"><span data-stu-id="5eef2-131">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="5eef2-132">Odfiltrowanie wszystkich rekordów specyficznych dla zasobów w zadaniu, które spowodowałyby niepowodzenie integracji z prognozami godzin.</span><span class="sxs-lookup"><span data-stu-id="5eef2-132">Filter out any resource-specific records in the task that will fail the integration into hour forecasts.</span></span>
- <span data-ttu-id="5eef2-133">Odfiltrować wszystkie puste wiersze kategorii transakcji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-133">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="5eef2-134">Niewykonanie tych zadań może spowodować błędy w prognozach godzin.</span><span class="sxs-lookup"><span data-stu-id="5eef2-134">Failure to complete this task might result in incorrect hour forecasts.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="5eef2-135">Ustawianie domyślnego identyfikatora modelu prognozy</span><span class="sxs-lookup"><span data-stu-id="5eef2-135">Set the default forecast model ID</span></span>

<span data-ttu-id="5eef2-136">Aby zaktualizować domyślny identyfikator modelu prognozy do szablonu, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie.</span><span class="sxs-lookup"><span data-stu-id="5eef2-136">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="5eef2-137">Następnie kliknij łącze **Zaawansowane zapytania i filtrowanie**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-137">Then select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="5eef2-138">Jeśli używasz domyślnego szablonu Szacunki godzin w projekcie (PSA do Fin and Ops), na liście **Zastosowane kroki** zaznacz element **Wstawiony warunek**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-138">If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**.</span></span> <span data-ttu-id="5eef2-139">We wpisie **Funkcja** zastąp tekst **O\_forecast** nazwą identyfikatora modelu prognozy, który powinien być używany w integracji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-139">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="5eef2-140">Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-140">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="5eef2-141">Jeśli tworzysz nowy szablon, należy dodać tę kolumnę.</span><span class="sxs-lookup"><span data-stu-id="5eef2-141">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="5eef2-142">W narzędziu Power Query wybierz opcję **Dodaj kolumnę warunkową**, a następnie nadaj nowej kolumnie nazwę, taką jak **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-142">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="5eef2-143">Wprowadź warunek dla kolumny, gdzie jeśli parametr Zadanie projektu nie ma wartości null, to \<wprowadź identyfikatora modelu prognozy\>; w przeciwnym razie null.</span><span class="sxs-lookup"><span data-stu-id="5eef2-143">Enter the condition for the column, where, if Project task is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="5eef2-144">Odfiltrowywanie rekordów specyficznych dla zasobów</span><span class="sxs-lookup"><span data-stu-id="5eef2-144">Filter out resource-specific records</span></span>

<span data-ttu-id="5eef2-145">Szablon Szacunki godzin w projekcie (PSA do Fin and Ops) zawiera filtr domyślny, który usuwa wszystkie rekordy określonych zasobów.</span><span class="sxs-lookup"><span data-stu-id="5eef2-145">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records.</span></span> <span data-ttu-id="5eef2-146">Jeśli tworzysz własny szablon, musisz dodać ten filtr.</span><span class="sxs-lookup"><span data-stu-id="5eef2-146">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="5eef2-147">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby wyfiltrować według kolumny **msdyn\_islinetask** i wyświetlić tylko rekordy spełniające warunek **Fałsz**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-147">Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.</span></span>

#### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="5eef2-148">Odfiltrowywanie wszystkich pustych wierszy kategorii transakcji</span><span class="sxs-lookup"><span data-stu-id="5eef2-148">Filter out empty transaction category rows</span></span>

<span data-ttu-id="5eef2-149">Należy dodać filtr, aby usunąć wszystkie wiersze mające puste kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-149">You must add a filter to remove any rows that have empty transaction categories.</span></span> <span data-ttu-id="5eef2-150">To zadanie jest wymagane bez względu na to, czy używasz szablonu domyślnego, czy tworzysz własny.</span><span class="sxs-lookup"><span data-stu-id="5eef2-150">This task is required, regardless of whether you're using the default template or creating your own template.</span></span> <span data-ttu-id="5eef2-151">Ten filtr spowoduje usunięcie wszystkich wierszy podsumowania pochodzących z rozwiązania Project Service Automation, które mogą powodować nieprawidłowe prognozy godzinowe w programie Finance.</span><span class="sxs-lookup"><span data-stu-id="5eef2-151">This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect.</span></span> <span data-ttu-id="5eef2-152">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby odfiltrować rekordy o wartości null w kolumnie **msdyn\_transactioncategory\_value**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-152">Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="5eef2-153">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="5eef2-153">Template mapping in Data integration</span></span>

<span data-ttu-id="5eef2-154">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-154">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="5eef2-155">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="5eef2-155">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="5eef2-156">[![Mapowanie szablonu](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="5eef2-156">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

## <a name="project-expense-estimates"></a><span data-ttu-id="5eef2-157">Szacunki wydatków w projekcie</span><span class="sxs-lookup"><span data-stu-id="5eef2-157">Project expense estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="5eef2-158">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="5eef2-158">Template and tasks</span></span>

<span data-ttu-id="5eef2-159">Następujący szablon i zadania podrzędne służą do synchronizowania szacunków wydatków z rozwiązania Project Service Automation do rozwiązania Finance:</span><span class="sxs-lookup"><span data-stu-id="5eef2-159">The following template and underlying tasks are used to synchronize project expense estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="5eef2-160">**Nazwa szablonu w narzędziu Integracja danych:** Szacunki wydatków w projekcie (PSA do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="5eef2-160">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="5eef2-161">**Nazwa zadania w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="5eef2-161">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="5eef2-162">Relacje transakcji</span><span class="sxs-lookup"><span data-stu-id="5eef2-162">Transaction relationships</span></span> 
    - <span data-ttu-id="5eef2-163">Oszacowania wydatków</span><span class="sxs-lookup"><span data-stu-id="5eef2-163">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="5eef2-164">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="5eef2-164">Entity set</span></span>

| <span data-ttu-id="5eef2-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="5eef2-165">Project Service Automation</span></span> | <span data-ttu-id="5eef2-166">Finanse</span><span class="sxs-lookup"><span data-stu-id="5eef2-166">Finance</span></span>                                                  |
|----------------------------|----------------------------------------------------------|
| <span data-ttu-id="5eef2-167">Połączenia transakcji</span><span class="sxs-lookup"><span data-stu-id="5eef2-167">Transaction Connections</span></span>    | <span data-ttu-id="5eef2-168">Jednostka integracji relacji transakcji projektu</span><span class="sxs-lookup"><span data-stu-id="5eef2-168">Integration entity for project transaction relationships</span></span> |
| <span data-ttu-id="5eef2-169">Wiersze oszacowania</span><span class="sxs-lookup"><span data-stu-id="5eef2-169">Estimate Lines</span></span>             | <span data-ttu-id="5eef2-170">Jednostka integracji szacowań wydatków projektu</span><span class="sxs-lookup"><span data-stu-id="5eef2-170">Integration entity for project expense estimates</span></span>         |

### <a name="entity-flow"></a><span data-ttu-id="5eef2-171">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="5eef2-171">Entity flow</span></span>

<span data-ttu-id="5eef2-172">Zarządzanie szacunkami wydatków w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z aplikacją Finance jako prognozy wydatków w projekcie.</span><span class="sxs-lookup"><span data-stu-id="5eef2-172">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance as project expense forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5eef2-173">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5eef2-173">Prerequisites</span></span>

<span data-ttu-id="5eef2-174">Zanim będzie możliwa synchronizacja szacunków wydatków w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.</span><span class="sxs-lookup"><span data-stu-id="5eef2-174">Before synchronization of project expense estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="5eef2-175">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="5eef2-175">Power Query</span></span>

<span data-ttu-id="5eef2-176">W szablonie szacunków wydatków projektu należy użyć programu Power Query w celu wykonania następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="5eef2-176">In the project expense estimates template, you must use Power Query to complete the following tasks:</span></span>

- <span data-ttu-id="5eef2-177">Wyfiltrowanie, aby uwzględnić tylko rekordy wierszy szacowania wydatków.</span><span class="sxs-lookup"><span data-stu-id="5eef2-177">Filter to include only expense estimate line records.</span></span>
- <span data-ttu-id="5eef2-178">Ustawienie domyślnego identyfikatora modelu prognozy, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.</span><span class="sxs-lookup"><span data-stu-id="5eef2-178">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="5eef2-179">Przekształć typy fakturowania.</span><span class="sxs-lookup"><span data-stu-id="5eef2-179">Transform the billing types.</span></span>
- <span data-ttu-id="5eef2-180">Przekształć typy transakcji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-180">Transform the transaction types.</span></span>

#### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="5eef2-181">Filtrowanie w celu uwzględnienia tylko wierszy szacowania wydatków</span><span class="sxs-lookup"><span data-stu-id="5eef2-181">Filter to include only expense estimate lines</span></span>

<span data-ttu-id="5eef2-182">Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) ma domyślny filtr uwzględniający w integracji tylko wiersze wydatków.</span><span class="sxs-lookup"><span data-stu-id="5eef2-182">The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration.</span></span> <span data-ttu-id="5eef2-183">Jeśli tworzysz własny szablon, musisz dodać ten filtr.</span><span class="sxs-lookup"><span data-stu-id="5eef2-183">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="5eef2-184">Wybierz zadanie **Relacje transakcji**, a następnie kliknij strzałkę **Mapuj**, aby otworzyć mapowanie.</span><span class="sxs-lookup"><span data-stu-id="5eef2-184">Select the **Transaction relationships** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="5eef2-185">Kliknij łącze **Zaawansowane zapytania i filtrowanie**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-185">Select the **Advanced Query and Filtering** link.</span></span> <span data-ttu-id="5eef2-186">Wyfiltruj kolumnę **msdyn\_transactiontype1**, tak aby zawierała tylko element **msdyn\_estimateline**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-186">Filter the **msdyn\_transactiontype1** column so that it includes only **msdyn\_estimateline**.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="5eef2-187">Ustawianie domyślnego identyfikatora modelu prognozy</span><span class="sxs-lookup"><span data-stu-id="5eef2-187">Set the default forecast model ID</span></span>

<span data-ttu-id="5eef2-188">Aby zaktualizować domyślny identyfikator modelu prognozy w szablonie, wybierz zadanie **Oszacowania wydatków**, a następnie kliknij strzałkę **Mapuj**, aby otworzyć mapowanie.</span><span class="sxs-lookup"><span data-stu-id="5eef2-188">To update the default forecast model ID in the template, select the **Expense estimates** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="5eef2-189">Kliknij łącze **Zaawansowane zapytania i filtrowanie**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-189">Select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="5eef2-190">Jeśli używasz domyślnego szablonu Szacunki wydatków w projekcie (PSA do Fin and Ops), w programie Power Query w sekcji **Zastosowane kroki** zaznacz pierwszy element na liście **Wstawiony warunek**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-190">If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section.</span></span> <span data-ttu-id="5eef2-191">We wpisie **Funkcja** zastąp tekst **O\_forecast** nazwą identyfikatora modelu prognozy, który powinien być używany w integracji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-191">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="5eef2-192">Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-192">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="5eef2-193">Jeśli tworzysz nowy szablon, należy dodać tę kolumnę.</span><span class="sxs-lookup"><span data-stu-id="5eef2-193">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="5eef2-194">W narzędziu Power Query wybierz opcję **Dodaj kolumnę warunkową**, a następnie nadaj nowej kolumnie nazwę, taką jak **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-194">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="5eef2-195">Wprowadź warunek dla kolumny, gdzie jeśli parametr Identyfikator wiersza szacowania nie ma wartości null, to \<wprowadź identyfikatora modelu prognozy\>; w przeciwnym razie null.</span><span class="sxs-lookup"><span data-stu-id="5eef2-195">Enter the condition for the column, where, if Estimate line ID is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="transform-the-billing-types"></a><span data-ttu-id="5eef2-196">Przekształć typy fakturowania</span><span class="sxs-lookup"><span data-stu-id="5eef2-196">Transform the billing types</span></span>

<span data-ttu-id="5eef2-197">Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) zawiera warunkową kolumnę używaną do przekształcania typów faktur otrzymanych z rozwiązania Project Service Automation podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-197">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the billing types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="5eef2-198">Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową.</span><span class="sxs-lookup"><span data-stu-id="5eef2-198">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="5eef2-199">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, a następnie wybierz opcję **Dodaj kolumnę warunkową**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-199">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="5eef2-200">Nadaj nazwę nowej kolumnie, taką jak **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-200">Enter a name for the new column, such as **BillingType**.</span></span> <span data-ttu-id="5eef2-201">Następnie wprowadź poniższy warunek:</span><span class="sxs-lookup"><span data-stu-id="5eef2-201">Then enter the following condition:</span></span>

<span data-ttu-id="5eef2-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span><span class="sxs-lookup"><span data-stu-id="5eef2-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span></span>  
<span data-ttu-id="5eef2-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span><span class="sxs-lookup"><span data-stu-id="5eef2-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span></span>  
<span data-ttu-id="5eef2-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span><span class="sxs-lookup"><span data-stu-id="5eef2-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span></span>  
<span data-ttu-id="5eef2-205">else **NotAvailable**</span><span class="sxs-lookup"><span data-stu-id="5eef2-205">else **NotAvailable**</span></span>

#### <a name="transform-the-transaction-types"></a><span data-ttu-id="5eef2-206">Przekształć typy transakcji</span><span class="sxs-lookup"><span data-stu-id="5eef2-206">Transform the transaction types</span></span>

<span data-ttu-id="5eef2-207">Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) zawiera warunkową kolumnę używaną do przekształcania typów transakcji otrzymanych z rozwiązania Project Service Automation podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="5eef2-207">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the transaction types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="5eef2-208">Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową.</span><span class="sxs-lookup"><span data-stu-id="5eef2-208">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="5eef2-209">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, a następnie wybierz opcję **Dodaj kolumnę warunkową**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-209">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="5eef2-210">Nadaj nazwę nowej kolumnie, taką jak **TransactionType**.</span><span class="sxs-lookup"><span data-stu-id="5eef2-210">Enter a name for the new column, such as **TransactionType**.</span></span> <span data-ttu-id="5eef2-211">Następnie wprowadź poniższy warunek:</span><span class="sxs-lookup"><span data-stu-id="5eef2-211">Then enter the following condition:</span></span>

<span data-ttu-id="5eef2-212">If **msdyn\_transactiontypecode** = 192350000, then **Koszt**</span><span class="sxs-lookup"><span data-stu-id="5eef2-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span></span>  
<span data-ttu-id="5eef2-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sprzedaż**</span><span class="sxs-lookup"><span data-stu-id="5eef2-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span></span>  
<span data-ttu-id="5eef2-214">else **null**</span><span class="sxs-lookup"><span data-stu-id="5eef2-214">else **null**</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="5eef2-215">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="5eef2-215">Template mapping in Data integration</span></span>

<span data-ttu-id="5eef2-216">Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="5eef2-216">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="5eef2-217">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="5eef2-217">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="5eef2-218">[![Mapowanie szablonu](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="5eef2-218">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="5eef2-219">[![Mapowanie szablonu](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="5eef2-219">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>
