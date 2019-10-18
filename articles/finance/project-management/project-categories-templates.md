---
title: Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation
description: Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między Microsoft Dynamics 365 Finance a programem Dynamics 365 Project Service Automation.
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
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 482febc91a04766216f9887ab59d30cc9aed5096
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250514"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="93c49-103">Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c49-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="93c49-104">Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Dynamics 365 Finance a programem Dynamics 365 Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="93c49-105">Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w wersji 8.0.</span><span class="sxs-lookup"><span data-stu-id="93c49-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="93c49-106">Funkcja integrowania wartości rzeczywistych jest dostępna wersji 8.01 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="93c49-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="93c49-107">Jeśli używasz Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji.</span><span class="sxs-lookup"><span data-stu-id="93c49-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="93c49-108">Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="93c49-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="93c49-109">Przepływ danych z programu Project Service Automation i Finance</span><span class="sxs-lookup"><span data-stu-id="93c49-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="93c49-110">Rozwiązanie integracji rozwiązania Project Service Automation i Finance korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c49-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="93c49-111">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących kategorii transakcji wydatkowych w projektach pomiędzy rozwiązaniem Project Service Automation i rozwiązaniem Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="93c49-112">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Finance, przepływ integracji następuje najpierw z programu Finance and Operations do programu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="93c49-113">Identyfikatory integracji kategorii wydatków w projekcie są następnie aktualizowane poprzez synchronizację z programu Project Service Automation do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="93c49-114">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Project Service Automation, przepływ integracji następuje najpierw z programu Project Service Automation do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="93c49-115">Kategorie projektu muszą być skonfigurowane w rozwiązaniu Finance przed synchronizacją z rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="93c49-116">Następnie przeprowadź synchronizację z rozwiązania Finance and Operations ponownie do rozwiązania Project Service Automation, a następnie jeszcze raz z rozwiązania Project Service Automation do rozwiązania Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="93c49-117">W ten sposób zapewniasz, że kategorie są połączone i nie powstają żadne duplikaty.</span><span class="sxs-lookup"><span data-stu-id="93c49-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="93c49-118">Na ogół kategorie wydatków projektu są zarządzane w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="93c49-119">Jednak jeśli nie są one zarządzane lub jeśli kategorie wydatków zostały już utworzone w programie Project Service Automation, należy je najpierw zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="93c49-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="93c49-120">Następnie należy wykonać synchronizację przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).</span><span class="sxs-lookup"><span data-stu-id="93c49-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="93c49-121">Następnie należy wykonać jeszcze jedną synchronizację z programu Project Service Automation do programu Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="93c49-122">Jeśli synchronizujesz najpierw z programu Project Service Automation, następujące wymagania muszą być spełnione w programie Finance przed uruchomieniem synchronizacji:</span><span class="sxs-lookup"><span data-stu-id="93c49-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="93c49-123">Udostępniona kategoria, która pasuje do kategorii projektu skonfigurowanej w programie Project Service Automation, musi istnieć oraz mieć włączone opcje **Projekt** i **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="93c49-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="93c49-124">Dla każdej firmy, z którą ma być integrowany program Finance, muszą istnieć następujące kategorie projektu:</span><span class="sxs-lookup"><span data-stu-id="93c49-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="93c49-125">Element **Kategoria projektu** istnieje.</span><span class="sxs-lookup"><span data-stu-id="93c49-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="93c49-126">Opcja **Użyj w module wydatków** jest włączona.</span><span class="sxs-lookup"><span data-stu-id="93c49-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="93c49-127">Opcja **Aktywne w arkuszu** jest włączona.</span><span class="sxs-lookup"><span data-stu-id="93c49-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="93c49-128">W ustawieniu **Typ transakcji** zaznaczono opcję **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="93c49-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="93c49-129">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance.</span><span class="sxs-lookup"><span data-stu-id="93c49-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="93c49-130">[![Przepływ danych w integracji programu Project Service Automation z programem Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="93c49-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="93c49-131">Synchronizowanie kategorii wydatków w projekcie z programu Finance do programu Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c49-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="93c49-132">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="93c49-132">Template and task</span></span>

<span data-ttu-id="93c49-133">Aby uzyskać dostęp do szablonu, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.</span><span class="sxs-lookup"><span data-stu-id="93c49-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="93c49-134">Następujący szablon i zadania podrzędne służą do synchronizowania szacunków wydatków z rozwiązania Finance do Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="93c49-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="93c49-135">**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA)</span><span class="sxs-lookup"><span data-stu-id="93c49-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="93c49-136">**Nazwa zadania w projekcie:** Synchronizowanie kategorii do PSA</span><span class="sxs-lookup"><span data-stu-id="93c49-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="93c49-137">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="93c49-137">Entity set</span></span>

| <span data-ttu-id="93c49-138">Finanse</span><span class="sxs-lookup"><span data-stu-id="93c49-138">Finance</span></span>                           | <span data-ttu-id="93c49-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c49-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="93c49-140">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="93c49-140">Integration entity for categories</span></span> | <span data-ttu-id="93c49-141">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="93c49-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="93c49-142">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="93c49-142">Entity flow</span></span>

<span data-ttu-id="93c49-143">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="93c49-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="93c49-144">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="93c49-144">Power Query</span></span>

<span data-ttu-id="93c49-145">Jeżeli synchronizujesz z rozwiązania Project Service Automation, należy za pomocą dodatku Microsoft Power Query dla programu Excel ustawić typ fakturowania w kategorii transakcji.</span><span class="sxs-lookup"><span data-stu-id="93c49-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="93c49-146">Szablon Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA) zawiera domyślną kolumnę i mapowanie.</span><span class="sxs-lookup"><span data-stu-id="93c49-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="93c49-147">Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową w narzędziu Power Query.</span><span class="sxs-lookup"><span data-stu-id="93c49-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="93c49-148">Wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="93c49-148">Follow these steps.</span></span>

1. <span data-ttu-id="93c49-149">Kliknij strzałkę, aby otworzyć mapowanie zadania kategorie wydatków w projekcie w szablonie Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).</span><span class="sxs-lookup"><span data-stu-id="93c49-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="93c49-150">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby otworzyć aplikację Power Query.</span><span class="sxs-lookup"><span data-stu-id="93c49-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="93c49-151">Wybierz opcję **Dodaj kolumnę warunkową**.</span><span class="sxs-lookup"><span data-stu-id="93c49-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="93c49-152">Nadaj nazwę nowej kolumnie, taką jak **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="93c49-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="93c49-153">Wprowadź następujący warunek: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="93c49-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="93c49-154">W kolumnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="93c49-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="93c49-155">Pamiętaj, aby zamapować tę nową kolumnę na stronie mapowania.</span><span class="sxs-lookup"><span data-stu-id="93c49-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="93c49-156">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="93c49-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="93c49-157">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="93c49-158">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="93c49-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="93c49-159">Synchronizowanie kategorii wydatków w projekcie z programu Project Service Automation do Finance</span><span class="sxs-lookup"><span data-stu-id="93c49-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="93c49-160">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="93c49-160">Template and task</span></span>

<span data-ttu-id="93c49-161">Następujący szablon i zadania podrzędne służą do synchronizowania szacunków wydatków z rozwiązania Project Service Automation do Finance:</span><span class="sxs-lookup"><span data-stu-id="93c49-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="93c49-162">**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="93c49-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="93c49-163">**Nazwa zadania w projekcie:** Synchronizowanie kategorii do Fin Ops</span><span class="sxs-lookup"><span data-stu-id="93c49-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="93c49-164">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="93c49-164">Entity set</span></span>

| <span data-ttu-id="93c49-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c49-165">Project Service Automation</span></span> | <span data-ttu-id="93c49-166">Finanse</span><span class="sxs-lookup"><span data-stu-id="93c49-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="93c49-167">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="93c49-167">Transaction categories</span></span>     | <span data-ttu-id="93c49-168">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="93c49-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="93c49-169">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="93c49-169">Entity flow</span></span>

<span data-ttu-id="93c49-170">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="93c49-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="93c49-171">Ponowna synchronizacja do rozwiązania Finance aktualizuje kategorię projektu w rozwiązaniu Finance o identyfikator integracji z rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="93c49-172">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="93c49-172">Template mapping in Data integration</span></span>

<span data-ttu-id="93c49-173">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="93c49-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="93c49-174">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c49-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="93c49-175">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="93c49-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
